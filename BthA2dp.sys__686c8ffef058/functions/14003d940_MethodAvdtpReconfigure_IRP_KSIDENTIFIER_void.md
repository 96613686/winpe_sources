# MethodAvdtpReconfigure(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x14003d940`
- end: `0x14003d9ea`
- name: `?MethodAvdtpReconfigure@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `170`
- prototype: `__int64 __fastcall(PIRP Irp, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callees

- `0x140003530`
- `0x14001fd28`
- `0x14003d940`

## import_xrefs

- `ks!KsGetFilterFromIrp` at `0x14003d9bf`
- `ks!KsGetFilterFromIrp` at `0x14003d9bf`
- `ks!KsGetDevice` at `0x14003d9ce`
- `ks!KsGetDevice` at `0x14003d9ce`

## pseudocode

```c

```
