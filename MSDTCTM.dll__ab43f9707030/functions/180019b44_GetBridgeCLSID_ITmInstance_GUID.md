# GetBridgeCLSID(ITmInstance *,_GUID *)

- ea: `0x180019b44`
- end: `0x180019c69`
- name: `?GetBridgeCLSID@@YAJPEAUITmInstance@@PEAU_GUID@@@Z`
- size: `293`
- prototype: `int(struct ITmInstance *, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008356c`

## callees

- `0x1800063b0`
- `0x180019b44`
- `0x18001a210`
- `0x1800b8420`
- `0x1800bd010`

## import_xrefs

- `RPCRT4!UuidFromStringA` at `0x180019bda`
- `RPCRT4!UuidFromStringA` at `0x180019bda`
- `msvcrt!strchr` at `0x180019bbf`
- `msvcrt!strchr` at `0x180019bbf`

## string_xrefs

- `0x180019bfe`: `GetBridgeCLSID`
- `0x180019bf7`: `com\complus\dtc\dtc\msdtc\src\initbridge.cpp`

## pseudocode

```c

```
