# AfdPassQueryDeviceRelation

- ea: `0x1400439e0`
- end: `0x140043abb`
- name: `AfdPassQueryDeviceRelation`
- size: `219`
- prototype: `NTSTATUS __fastcall(PFILE_OBJECT FileObject, PIRP Irp, struct _IO_STACK_LOCATION *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140043904`

## callees

- `0x1400439e0`

## import_xrefs

- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140043a8c`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140043a8c`
- `ntoskrnl!ObfReferenceObject` at `0x140043a5f`
- `ntoskrnl!ObfReferenceObject` at `0x140043a5f`
- `ntoskrnl!IofCompleteRequest` at `0x140043a17`
- `ntoskrnl!IofCompleteRequest` at `0x140043a17`
- `ntoskrnl!IofCallDriver` at `0x140043a9e`
- `ntoskrnl!IofCallDriver` at `0x140043a9e`

## pseudocode

```c

```
