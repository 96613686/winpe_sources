# Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::ProcessEtwDataForAssembly(_EVENT_RECORD const *)

- ea: `0x180038904`
- end: `0x180038a21`
- name: `?ProcessEtwDataForAssembly@ManagedInformationAgent@StandardCollector@DiagnosticsHub@Microsoft@@AEAAXPEBU_EVENT_RECORD@@@Z`
- size: `285`
- prototype: `void __fastcall(Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent *__hidden this, const struct _EVENT_RECORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180038310`

## callees

- `0x180009fa4`
- `0x18000a078`
- `0x180038904`
- `0x180039824`
- `0x180039c8c`
- `0x18003ad70`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180038a04`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180038a04`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18003895f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18003895f`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800389b2`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800389b2`

## pseudocode

```c

```
