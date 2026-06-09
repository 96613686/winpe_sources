# SE_HookComInterface

- ea: `0x18001f300`
- end: `0x18001f3be`
- name: `SE_HookComInterface`
- size: `190`
- prototype: `__int64 __usercall@<rax>(wchar_t *Str@<rcx>, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001f300`
- `0x18001f6d0`
- `0x180032e40`
- `0x180039a72`
- `0x180053d90`
- `0x18005a010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18001f36e`
- `ntdll!RtlLeaveCriticalSection` at `0x18001f36e`
- `ntdll!RtlEnterCriticalSection` at `0x18001f354`
- `ntdll!RtlEnterCriticalSection` at `0x18001f354`

## pseudocode

```c

```
