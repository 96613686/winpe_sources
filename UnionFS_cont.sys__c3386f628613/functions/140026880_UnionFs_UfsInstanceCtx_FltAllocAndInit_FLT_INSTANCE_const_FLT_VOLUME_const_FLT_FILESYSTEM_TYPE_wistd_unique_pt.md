# UnionFs::UfsInstanceCtx::FltAllocAndInit(_FLT_INSTANCE const &,_FLT_VOLUME const &,_FLT_FILESYSTEM_TYPE,wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)

- ea: `0x140026880`
- end: `0x140026d74`
- name: `?FltAllocAndInit@UfsInstanceCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FLT_VOLUME@@W4_FLT_FILESYSTEM_TYPE@@AEAV?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z`
- size: `1268`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFLT_VOLUME Volume@<rdx>, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14000b218`

## callees

- `0x140026880`
- `0x140056a50`
- `0x140056ac4`
- `0x140079c48`
- `0x140079d0c`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!RtlGUIDFromString` at `0x140026a32`
- `ntoskrnl!RtlGUIDFromString` at `0x140026a32`
- `ntoskrnl!ObfDereferenceObject` at `0x140026ac9`
- `ntoskrnl!ObfDereferenceObject` at `0x140026cc3`
- `ntoskrnl!ObfDereferenceObject` at `0x140026d25`
- `ntoskrnl!ObfDereferenceObject` at `0x140026ac9`
- `ntoskrnl!ObfDereferenceObject` at `0x140026cc3`
- `ntoskrnl!ObfDereferenceObject` at `0x140026d25`
- `FLTMGR!FltQueryVolumeInformation` at `0x140026b44`
- `FLTMGR!FltQueryVolumeInformation` at `0x140026b44`
- `FLTMGR!FltGetVolumeGuidName` at `0x1400269e7`
- `FLTMGR!FltGetVolumeGuidName` at `0x1400269e7`
- `FLTMGR!FltGetVolumeName` at `0x140026c0c`
- `FLTMGR!FltGetVolumeName` at `0x140026cee`
- `FLTMGR!FltGetVolumeName` at `0x140026c0c`
- `FLTMGR!FltGetVolumeName` at `0x140026cee`
- `FLTMGR!FltAllocateContext` at `0x140026912`
- `FLTMGR!FltAllocateContext` at `0x140026912`
- `FLTMGR!FltGetVolumeFromInstance` at `0x140026b90`
- `FLTMGR!FltGetVolumeFromInstance` at `0x140026b90`
- `FLTMGR!FltGetDiskDeviceObject` at `0x140026a99`
- `FLTMGR!FltGetDiskDeviceObject` at `0x140026a99`
- `FLTMGR!FltReleaseContext` at `0x1400268d6`
- `FLTMGR!FltReleaseContext` at `0x140026cd2`
- `FLTMGR!FltReleaseContext` at `0x140026d39`
- `FLTMGR!FltReleaseContext` at `0x1400268d6`
- `FLTMGR!FltReleaseContext` at `0x140026cd2`
- `FLTMGR!FltReleaseContext` at `0x140026d39`
- `FLTMGR!FltObjectDereference` at `0x140026bb8`
- `FLTMGR!FltObjectDereference` at `0x140026ca8`
- `FLTMGR!FltObjectDereference` at `0x140026d0a`
- `FLTMGR!FltObjectDereference` at `0x140026bb8`
- `FLTMGR!FltObjectDereference` at `0x140026ca8`
- `FLTMGR!FltObjectDereference` at `0x140026d0a`

## pseudocode

```c

```
