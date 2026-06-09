# CWmsWebService::AreReplacementCertTasksPending(int *)

- ea: `0x140046814`
- end: `0x140046b59`
- name: `?AreReplacementCertTasksPending@CWmsWebService@@QEAAJPEAH@Z`
- size: `837`
- prototype: `__int64 __fastcall(CWmsWebService *__hidden this, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x14003851c`

## callees

- `0x140012158`
- `0x140046814`
- `0x140049494`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x140046907`
- `ADVAPI32!RegGetValueW` at `0x140046907`
- `KERNEL32!GetLastError` at `0x140046a3c`
- `KERNEL32!GetLastError` at `0x140046a3c`
- `KERNEL32!IsDebuggerPresent` at `0x140046963`
- `KERNEL32!IsDebuggerPresent` at `0x140046aac`
- `KERNEL32!IsDebuggerPresent` at `0x140046963`
- `KERNEL32!IsDebuggerPresent` at `0x140046aac`
- `KERNEL32!FindClose` at `0x140046b26`
- `KERNEL32!FindClose` at `0x140046b26`
- `KERNEL32!FindFirstFileW` at `0x140046a29`
- `KERNEL32!FindFirstFileW` at `0x140046a29`

## string_xrefs

- `0x14004693f`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x140046a84`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004687f`: `CWmsWebService::AreReplacementCertTasksPending\n`
- `0x140046932`: `CWmsWebService::AreReplacementCertTasksPending`
- `0x140046a73`: `CWmsWebService::AreReplacementCertTasksPending`
- `0x1400468d1`: `SslCertificateReplacementWindowDays`

## pseudocode

```c

```
