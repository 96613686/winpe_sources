# FindBITSJob(_GUID const &,IBackgroundCopyJob * *)

- ea: `0x14004eb3c`
- end: `0x14004ec72`
- name: `?FindBITSJob@@YAJAEBU_GUID@@PEAPEAUIBackgroundCopyJob@@@Z`
- size: `310`
- prototype: `__int64 __fastcall(UUID *Uuid, struct IBackgroundCopyJob **)`
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14004a704`
- `0x14004a854`
- `0x14004a9a4`
- `0x14004ba08`
- `0x14004c074`

## callees

- `0x1400095b4`
- `0x14004eb3c`
- `0x14004eff4`
- `0x14004f5e4`
- `0x14005d010`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x14004ebab`
- `RPCRT4!UuidToStringW` at `0x14004ebab`
- `RPCRT4!RpcStringFreeW` at `0x14004ec46`
- `RPCRT4!RpcStringFreeW` at `0x14004ec46`

## string_xrefs

- `0x14004ec0e`: `FindBITSJob:BITS job '%1' is not found. The BITS job may have completed already.`

## pseudocode

```c

```
