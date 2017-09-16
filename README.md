# siginfo_t
Tutorial about siginfo_t with sigaction for SIGCHLD

# example
```
gcc -Wall -o test_si test_si.c
./test_si &
>>>foo
PID=24540
<<<bar
signal 17 received with siginfo_t:
	signal number: si_signo=17
	error number: si_errno=0
	signal code: si_code=1
	signal value union: si_value, sival_int=7
	signal value union: si_value, sival_ptr=0x7
	sending process ID: si_pid=24540
	sending process user's ID: si_uid=1002
	faulting instruction at: si_addr=0x3ea00005fdc
	exit value or signal: si_status=7
	band event for SIGPOLL: si_band=4303557255132
	timer ID: si_timerid=24540
	overrun count: si_overrun=1002

test
>>>foo
PID=24541
<<<bar
signal 17 received with siginfo_t:
	signal number: si_signo=17
	error number: si_errno=0
	signal code: si_code=1
	signal value union: si_value, sival_int=7
	signal value union: si_value, sival_ptr=0x7
	sending process ID: si_pid=24541
	sending process user's ID: si_uid=1002
	faulting instruction at: si_addr=0x3ea00005fdd
	exit value or signal: si_status=7
	band event for SIGPOLL: si_band=4303557255133
	timer ID: si_timerid=24541
	overrun count: si_overrun=1002

test
fg
./test_si
^C
```

# thanks
man
