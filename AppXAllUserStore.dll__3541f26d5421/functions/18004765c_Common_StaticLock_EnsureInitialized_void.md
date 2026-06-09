# Common::StaticLock::EnsureInitialized(void)

- ea: `0x18004765c`
- end: `0x1800476d1`
- name: `?EnsureInitialized@StaticLock@Common@@QEAAXXZ`
- size: `117`
- prototype: `void __fastcall(Common::StaticLock *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004bb6c`
- `0x18004be74`

## callees

- `0x18004765c`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800476c5`
- `ntdll!RtlLeaveCriticalSection` at `0x1800476c5`
- `ntdll!RtlEnterCriticalSection` at `0x180047673`
- `ntdll!RtlEnterCriticalSection` at `0x180047673`
- `ntdll!RtlInitializeCriticalSection` at `0x18004768d`
- `ntdll!RtlInitializeCriticalSection` at `0x18004768d`

## pseudocode

```c

```
