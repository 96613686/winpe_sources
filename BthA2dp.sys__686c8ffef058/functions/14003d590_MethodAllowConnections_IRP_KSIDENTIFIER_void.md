# MethodAllowConnections(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x14003d590`
- end: `0x14003d67c`
- name: `?MethodAllowConnections@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `236`
- prototype: `__int64 __fastcall(PIRP Irp, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x140003530`
- `0x140031d94`
- `0x14003d468`
- `0x14003d590`
- `0x140058390`

## import_xrefs

- `ks!KsGetFilterFromIrp` at `0x14003d613`
- `ks!KsGetFilterFromIrp` at `0x14003d613`
- `ks!KsGetDevice` at `0x14003d622`
- `ks!KsGetDevice` at `0x14003d622`

## pseudocode

```c

```
