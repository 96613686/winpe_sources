# AfdTdiGetBaseDeviceObject

- ea: `0x140067804`
- end: `0x1400679e1`
- name: `AfdTdiGetBaseDeviceObject`
- size: `477`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14002e43c`
- `0x1400679e8`

## callees

- `0x140067804`
- `0x1400943a0`

## import_xrefs

- `ntoskrnl!IoCreateFile` at `0x1400678e7`
- `ntoskrnl!IoCreateFile` at `0x1400678e7`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x1400679a5`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x1400679a5`
- `ntoskrnl!ZwClose` at `0x14006795e`
- `ntoskrnl!ZwClose` at `0x14006795e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14006784f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14006784f`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140067996`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140067996`
- `ntoskrnl!ObfDereferenceObject` at `0x1400679b7`
- `ntoskrnl!ObfDereferenceObject` at `0x1400679b7`
- `ntoskrnl!IoFileObjectType` at `0x14006791f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14006794c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14006794c`

## pseudocode

```c

```
