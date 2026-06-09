# CMDMPushConfiguration::ComputeNextRenewal(_ULARGE_INTEGER,_SYSTEMTIME *,int *)

- ea: `0x14001f6c0`
- end: `0x14001f8a2`
- name: `?ComputeNextRenewal@CMDMPushConfiguration@@AEAAJT_ULARGE_INTEGER@@PEAU_SYSTEMTIME@@PEAH@Z`
- size: `482`
- prototype: `__int64 __fastcall(CMDMPushConfiguration *this, union _ULARGE_INTEGER, struct _SYSTEMTIME *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001f8a8`

## callees

- `0x1400042f0`
- `0x140009594`
- `0x1400095b4`
- `0x14001f6c0`
- `0x140026064`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x14001f6f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x14001f6f1`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x14001f707`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x14001f707`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x14001f848`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x14001f848`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x14001f82d`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x14001f82d`

## pseudocode

```c

```
