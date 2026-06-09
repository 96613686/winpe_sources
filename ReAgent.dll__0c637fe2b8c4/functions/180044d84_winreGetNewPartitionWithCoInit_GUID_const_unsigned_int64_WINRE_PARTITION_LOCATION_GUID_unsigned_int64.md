# winreGetNewPartitionWithCoInit(_GUID const *,unsigned __int64,_WINRE_PARTITION_LOCATION,_GUID *,unsigned __int64 *)

- ea: `0x180044d84`
- end: `0x180044ea0`
- name: `?winreGetNewPartitionWithCoInit@@YAHPEBU_GUID@@_KW4_WINRE_PARTITION_LOCATION@@PEAU1@PEA_K@Z`
- size: `284`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180036c38`

## callees

- `0x1800059fc`
- `0x18001a170`
- `0x18003da00`
- `0x18003da8c`
- `0x1800449cc`
- `0x180044d84`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180044e56`
- `KERNEL32!GetLastError` at `0x180044e56`
- `ole32!CoUninitialize` at `0x180044e69`
- `ole32!CoUninitialize` at `0x180044e69`
- `ole32!CoInitialize` at `0x180044dab`
- `ole32!CoInitialize` at `0x180044dab`

## string_xrefs

- `0x180044df4`: `winreGetNewPartitionWithCoInit Will create partition AFTER OS partition with size: %I64u `
- `0x180044dff`: `winreGetNewPartitionWithCoInit Will create partition at END of disk with size: %I64u (no shrinking)`
- `0x180044e20`: `winreGetNewPartitionWithCoInit Will create partition with size: %I64u `

## pseudocode

```c

```
