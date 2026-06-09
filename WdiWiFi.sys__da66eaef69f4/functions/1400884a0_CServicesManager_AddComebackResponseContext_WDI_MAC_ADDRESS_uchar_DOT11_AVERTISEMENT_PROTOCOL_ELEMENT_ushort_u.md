# CServicesManager::AddComebackResponseContext(_WDI_MAC_ADDRESS *,uchar,_DOT11_AVERTISEMENT_PROTOCOL_ELEMENT *,ushort,uchar *)

- ea: `0x1400884a0`
- end: `0x1400885aa`
- name: `?AddComebackResponseContext@CServicesManager@@QEAAPEAVCServiceComebackResponseContext@@PEAU_WDI_MAC_ADDRESS@@EPEAU_DOT11_AVERTISEMENT_PROTOCOL_ELEMENT@@GPEAE@Z`
- size: `266`
- prototype: `struct CServiceComebackResponseContext *__usercall@<rax>(CServicesManager *__hidden this@<rcx>, struct _WDI_MAC_ADDRESS *@<rdx>, unsigned __int8@<r8b>, struct _DOT11_AVERTISEMENT_PROTOCOL_ELEMENT *@<r9>, unsigned __int16, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400b5828`

## callees

- `0x140023ae0`
- `0x14004363c`
- `0x1400884a0`
- `0x1400885b0`
- `0x1400b92e0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400884fc`
- `ntoskrnl!ExAllocatePool2` at `0x1400884fc`

## pseudocode

```c

```
