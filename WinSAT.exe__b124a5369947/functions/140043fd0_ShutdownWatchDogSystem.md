# ShutdownWatchDogSystem

- ea: `0x140043fd0`
- end: `0x1400440f1`
- name: `ShutdownWatchDogSystem`
- size: `289`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14001a54c`

## callees

- `0x140011d58`
- `0x14003ec14`
- `0x14003f8e0`
- `0x14003fa8c`
- `0x140043fd0`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x14004408f`
- `KERNEL32!TerminateProcess` at `0x14004408f`
- `KERNEL32!CancelWaitableTimer` at `0x140043fe9`
- `KERNEL32!CancelWaitableTimer` at `0x140043ff6`
- `KERNEL32!CancelWaitableTimer` at `0x140044003`
- `KERNEL32!CancelWaitableTimer` at `0x140043fe9`
- `KERNEL32!CancelWaitableTimer` at `0x140043ff6`
- `KERNEL32!CancelWaitableTimer` at `0x140044003`
- `KERNEL32!CloseHandle` at `0x14004409c`
- `KERNEL32!CloseHandle` at `0x1400440a9`
- `KERNEL32!CloseHandle` at `0x1400440b6`
- `KERNEL32!CloseHandle` at `0x1400440c3`
- `KERNEL32!CloseHandle` at `0x14004409c`
- `KERNEL32!CloseHandle` at `0x1400440a9`
- `KERNEL32!CloseHandle` at `0x1400440b6`
- `KERNEL32!CloseHandle` at `0x1400440c3`
- `KERNEL32!GetLastError` at `0x140044060`
- `KERNEL32!GetLastError` at `0x140044060`
- `KERNEL32!WaitForSingleObject` at `0x140044021`
- `KERNEL32!WaitForSingleObject` at `0x140044021`
- `KERNEL32!GetCurrentProcess` at `0x140044081`
- `KERNEL32!GetCurrentProcess` at `0x140044081`

## string_xrefs

- `0x14004402e`: `The wait for the watch dog thread termination was abandoned`
- `0x14004404f`: `The wait for the watch dog thread termination timed out`
- `0x140044066`: `Cannot not wait for the watch dog thread to terminate`

## pseudocode

```c

```
