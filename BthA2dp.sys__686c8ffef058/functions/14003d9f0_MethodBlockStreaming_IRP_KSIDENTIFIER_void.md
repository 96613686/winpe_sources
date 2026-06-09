# MethodBlockStreaming(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x14003d9f0`
- end: `0x14003daf3`
- name: `?MethodBlockStreaming@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `259`
- prototype: `__int64 __fastcall(PIRP Irp, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x140003530`
- `0x14001bf14`
- `0x14001ebfc`
- `0x14003d9f0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14003dabf`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003dabf`
- `ks!KsGetFilterFromIrp` at `0x14003da78`
- `ks!KsGetFilterFromIrp` at `0x14003da78`

## pseudocode

```c

```
