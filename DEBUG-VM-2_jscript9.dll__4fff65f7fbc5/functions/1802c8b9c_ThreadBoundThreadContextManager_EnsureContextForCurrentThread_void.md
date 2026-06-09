# ThreadBoundThreadContextManager::EnsureContextForCurrentThread(void)

- ea: `0x1802c8b9c`
- end: `0x1802c8cbb`
- name: `?EnsureContextForCurrentThread@ThreadBoundThreadContextManager@@SAPEAVThreadContext@@XZ`
- size: `287`
- prototype: `struct ThreadContext *(void)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x1801d914c`
- `0x1801fd320`
- `0x18021d1ac`

## callees

- `0x180107364`
- `0x1801a0e88`
- `0x1801b9f68`
- `0x1802032c4`
- `0x1802c8b9c`
- `0x1802cabb8`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x1802c8bcc`
- `KERNEL32!TlsGetValue` at `0x1802c8be5`
- `KERNEL32!TlsGetValue` at `0x1802c8bcc`
- `KERNEL32!TlsGetValue` at `0x1802c8be5`
- `KERNEL32!EnterCriticalSection` at `0x1802c8bbf`
- `KERNEL32!EnterCriticalSection` at `0x1802c8bbf`
- `KERNEL32!LeaveCriticalSection` at `0x1802c8c98`
- `KERNEL32!LeaveCriticalSection` at `0x1802c8ca6`
- `KERNEL32!LeaveCriticalSection` at `0x1802c8c98`
- `KERNEL32!LeaveCriticalSection` at `0x1802c8ca6`

## pseudocode

```c

```
