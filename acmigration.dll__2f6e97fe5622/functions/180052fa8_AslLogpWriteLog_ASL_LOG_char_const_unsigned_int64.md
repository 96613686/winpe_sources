# AslLogpWriteLog(_ASL_LOG *,char const *,unsigned __int64)

- ea: `0x180052fa8`
- end: `0x1800531a5`
- name: `?AslLogpWriteLog@@YAXPEAU_ASL_LOG@@PEBD_K@Z`
- size: `509`
- prototype: `void(struct _ASL_LOG *, const char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180053a68`

## callees

- `0x180002874`
- `0x180002b93`
- `0x180052cf0`
- `0x180052ee4`
- `0x180052fa8`
- `0x180065144`

## import_xrefs

- `KERNEL32!GetStdHandle` at `0x180053122`
- `KERNEL32!GetStdHandle` at `0x180053122`
- `KERNEL32!OutputDebugStringA` at `0x18005310b`
- `KERNEL32!OutputDebugStringA` at `0x18005310b`
- `KERNEL32!HeapReAlloc` at `0x180053082`
- `KERNEL32!HeapReAlloc` at `0x180053082`
- `KERNEL32!HeapAlloc` at `0x180053062`
- `KERNEL32!HeapAlloc` at `0x180053062`
- `ntdll!RtlEnterCriticalSection` at `0x180052fd7`
- `ntdll!RtlEnterCriticalSection` at `0x180053158`
- `ntdll!RtlEnterCriticalSection` at `0x180052fd7`
- `ntdll!RtlEnterCriticalSection` at `0x180053158`
- `ntdll!RtlLeaveCriticalSection` at `0x1800530dc`
- `ntdll!RtlLeaveCriticalSection` at `0x18005318e`
- `ntdll!RtlLeaveCriticalSection` at `0x1800530dc`
- `ntdll!RtlLeaveCriticalSection` at `0x18005318e`

## pseudocode

```c

```
