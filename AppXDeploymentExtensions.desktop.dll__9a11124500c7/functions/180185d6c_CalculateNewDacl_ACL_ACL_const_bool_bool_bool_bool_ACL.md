# CalculateNewDacl(_ACL *,_ACL * const,bool,bool,bool,bool *,_ACL * *)

- ea: `0x180185d6c`
- end: `0x1801860b3`
- name: `?CalculateNewDacl@@YAJPEAU_ACL@@QEAU1@_N22PEA_NPEAPEAU1@@Z`
- size: `839`
- prototype: `__int64 __usercall@<rax>(PACL pAcl@<rcx>, struct _ACL *const Src@<rdx>, bool@<r8b>, bool@<r9b>, bool, bool *, struct _ACL **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180185958`

## callees

- `0x18000669c`
- `0x18001adb4`
- `0x180068f18`
- `0x1800af1bc`
- `0x1800af220`
- `0x1800af85a`
- `0x1800af918`
- `0x1800ba45d`
- `0x180185d6c`
- `0x1801860bc`
- `0x1801861e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180185f46`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180185f46`
- `ntdll!RtlAddAce` at `0x180185f7b`
- `ntdll!RtlAddAce` at `0x180185f7b`
- `ADVAPI32!GetAce` at `0x180185dd5`
- `ADVAPI32!GetAce` at `0x180185e6b`
- `ADVAPI32!GetAce` at `0x180185dd5`
- `ADVAPI32!GetAce` at `0x180185e6b`

## string_xrefs

- `0x180185e09`: `onecore\admin\appmodel\common\directoryacls.cpp`
- `0x180185e25`: `onecore\admin\appmodel\common\directoryacls.cpp`
- `0x180185fc7`: `onecore\admin\appmodel\common\directoryacls.cpp`
- `0x180185fe6`: `onecore\admin\appmodel\common\directoryacls.cpp`
- `0x18018602b`: `onecore\admin\appmodel\common\directoryacls.cpp`
- `0x180186060`: `onecore\admin\appmodel\common\directoryacls.cpp`

## pseudocode

```c

```
