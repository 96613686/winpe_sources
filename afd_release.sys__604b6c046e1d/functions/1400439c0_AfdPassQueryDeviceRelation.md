# AfdPassQueryDeviceRelation

- ea: `0x1400439c0`
- end: `0x140043a9b`
- name: `AfdPassQueryDeviceRelation`
- size: `219`
- prototype: `NTSTATUS __fastcall(PFILE_OBJECT FileObject, PIRP Irp, struct _IO_STACK_LOCATION *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400438e4`

## callees

- `0x1400439c0`

## import_xrefs

- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140043a6c`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140043a6c`
- `ntoskrnl!ObfReferenceObject` at `0x140043a3f`
- `ntoskrnl!ObfReferenceObject` at `0x140043a3f`
- `ntoskrnl!IofCompleteRequest` at `0x1400439f7`
- `ntoskrnl!IofCompleteRequest` at `0x1400439f7`
- `ntoskrnl!IofCallDriver` at `0x140043a7e`
- `ntoskrnl!IofCallDriver` at `0x140043a7e`

## pseudocode

```c

```
