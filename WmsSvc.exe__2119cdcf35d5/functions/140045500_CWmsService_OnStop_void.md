# CWmsService::OnStop(void)

- ea: `0x140045500`
- end: `0x140045690`
- name: `?OnStop@CWmsService@@UEAAXXZ`
- size: `400`
- prototype: `void __fastcall(CWmsService *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x140044dbc`
- `0x140045500`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c290`
- `0x14005c408`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1400455bc`
- `KERNEL32!SetEvent` at `0x1400455bc`
- `KERNEL32!WaitForSingleObject` at `0x14004567e`
- `KERNEL32!WaitForSingleObject` at `0x14004567e`
- `KERNEL32!GetLastError` at `0x1400455ca`
- `KERNEL32!GetLastError` at `0x1400455ca`
- `KERNEL32!IsDebuggerPresent` at `0x140045557`
- `KERNEL32!IsDebuggerPresent` at `0x140045613`
- `KERNEL32!IsDebuggerPresent` at `0x140045557`
- `KERNEL32!IsDebuggerPresent` at `0x140045613`

## string_xrefs

- `0x140045532`: `termsrv\wms\src\devices\wmssvc\wmsservice.cpp`
- `0x14004550f`: `CWmsService::OnStop\n`
- `0x14004553b`: `m_hThreadProcKillEvent != NULL`
- `0x14004552b`: `CWmsService::OnStop`

## pseudocode

```c

```
