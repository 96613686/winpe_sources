# Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::OnEtwEvent(_EVENT_RECORD const *,ulong,bool *)

- ea: `0x180013160`
- end: `0x1800132a2`
- name: `?OnEtwEvent@DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@UEAAJPEBU_EVENT_RECORD@@KPEA_N@Z`
- size: `322`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent *__hidden this, const struct _EVENT_RECORD *, unsigned int, bool *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180013160`
- `0x1800157a8`

## import_xrefs

- `VCRUNTIME140!memcmp` at `0x18001318a`
- `VCRUNTIME140!memcmp` at `0x1800131a3`
- `VCRUNTIME140!memcmp` at `0x18001318a`
- `VCRUNTIME140!memcmp` at `0x1800131a3`
- `KERNEL32!LeaveCriticalSection` at `0x18001327b`
- `KERNEL32!LeaveCriticalSection` at `0x18001328b`
- `KERNEL32!LeaveCriticalSection` at `0x18001327b`
- `KERNEL32!LeaveCriticalSection` at `0x18001328b`
- `KERNEL32!EnterCriticalSection` at `0x180013239`
- `KERNEL32!EnterCriticalSection` at `0x180013239`
- `OLEAUT32!__imp_SysAllocString` at `0x180013215`
- `OLEAUT32!__imp_SysAllocString` at `0x180013215`

## pseudocode

```c

```
