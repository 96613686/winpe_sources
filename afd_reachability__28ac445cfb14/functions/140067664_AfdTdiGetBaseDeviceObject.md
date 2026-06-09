# AfdTdiGetBaseDeviceObject

- ea: `0x140067664`
- end: `0x140067841`
- name: `AfdTdiGetBaseDeviceObject`
- size: `477`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14002e43c`
- `0x140067848`

## callees

- `0x140067664`
- `0x1400943a0`

## import_xrefs

- `ntoskrnl!IoCreateFile` at `0x140067747`
- `ntoskrnl!IoCreateFile` at `0x140067747`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x140067805`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x140067805`
- `ntoskrnl!ZwClose` at `0x1400677be`
- `ntoskrnl!ZwClose` at `0x1400677be`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400676af`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400676af`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400677f6`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400677f6`
- `ntoskrnl!ObfDereferenceObject` at `0x140067817`
- `ntoskrnl!ObfDereferenceObject` at `0x140067817`
- `ntoskrnl!IoFileObjectType` at `0x14006777f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400677ac`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400677ac`

## pseudocode

```c

```
