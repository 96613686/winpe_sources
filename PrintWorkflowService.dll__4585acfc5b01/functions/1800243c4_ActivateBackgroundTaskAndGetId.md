# ActivateBackgroundTaskAndGetId

- ea: `0x1800243c4`
- end: `0x18002448a`
- name: `ActivateBackgroundTaskAndGetId`
- size: `198`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const WCHAR *, const WCHAR *SourceString, __int64, _OWORD *)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, service_task`

## callers

- `0x18001b100`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180024402`
- `ntdll!RtlInitUnicodeString` at `0x180024415`
- `ntdll!RtlInitUnicodeString` at `0x180024427`
- `ntdll!RtlInitUnicodeString` at `0x180024402`
- `ntdll!RtlInitUnicodeString` at `0x180024415`
- `ntdll!RtlInitUnicodeString` at `0x180024427`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtActivateInBackground` at `0x180024461`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtActivateInBackground` at `0x180024461`

## string_xrefs

- `0x18002441b`: `Windows.PrintWorkflowBackgroundTask`

## pseudocode

```c

```
