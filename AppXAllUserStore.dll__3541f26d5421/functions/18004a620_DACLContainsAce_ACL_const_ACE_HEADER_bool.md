# DACLContainsAce(_ACL * const,_ACE_HEADER *,bool *)

- ea: `0x18004a620`
- end: `0x18004a6da`
- name: `?DACLContainsAce@@YAJQEAU_ACL@@PEAU_ACE_HEADER@@PEA_N@Z`
- size: `186`
- prototype: `__int64 __fastcall(PACL pAcl, struct _ACE_HEADER *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018f3c`

## callees

- `0x18001a324`
- `0x18004a620`
- `0x18004c966`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18004a65d`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18004a65d`

## string_xrefs

- `0x18004a6c7`: `onecore\admin\appmodel\common\directoryacls.cpp`

## pseudocode

```c

```
