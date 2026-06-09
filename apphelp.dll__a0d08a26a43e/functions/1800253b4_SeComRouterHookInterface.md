# SeComRouterHookInterface

- ea: `0x1800253b4`
- end: `0x1800254c0`
- name: `SeComRouterHookInterface`
- size: `268`
- prototype: `__int64 __usercall@<rax>(PRTL_CRITICAL_SECTION CriticalSection@<rcx>, __int64, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180032e40`
- `0x180053d90`

## callees

- `0x1800253b4`
- `0x1800254c8`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800254aa`
- `ntdll!RtlLeaveCriticalSection` at `0x1800254aa`
- `ntdll!RtlEnterCriticalSection` at `0x1800253d0`
- `ntdll!RtlEnterCriticalSection` at `0x1800253d0`
- `ntdll!_wcsicmp` at `0x180025456`
- `ntdll!_wcsicmp` at `0x180025456`

## pseudocode

```c

```
