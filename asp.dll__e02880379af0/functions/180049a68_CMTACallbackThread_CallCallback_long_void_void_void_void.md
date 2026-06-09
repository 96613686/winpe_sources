# CMTACallbackThread::CallCallback(long (*)(void *,void *),void *,void *)

- ea: `0x180049a68`
- end: `0x180049b25`
- name: `?CallCallback@CMTACallbackThread@@QEAAJP6AJPEAX0@Z00@Z`
- size: `189`
- prototype: `__int64 __fastcall(CMTACallbackThread *__hidden this, int (*)(void *, void *), void *, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180037fc0`

## callees

- `0x180049a68`

## import_xrefs

- `ole32!CoWaitForMultipleHandles` at `0x180049af4`
- `ole32!CoWaitForMultipleHandles` at `0x180049af4`
- `KERNEL32!LeaveCriticalSection` at `0x180049b12`
- `KERNEL32!LeaveCriticalSection` at `0x180049b12`
- `KERNEL32!SetEvent` at `0x180049ad2`
- `KERNEL32!SetEvent` at `0x180049ad2`
- `KERNEL32!EnterCriticalSection` at `0x180049a9f`
- `KERNEL32!EnterCriticalSection` at `0x180049a9f`

## pseudocode

```c

```
