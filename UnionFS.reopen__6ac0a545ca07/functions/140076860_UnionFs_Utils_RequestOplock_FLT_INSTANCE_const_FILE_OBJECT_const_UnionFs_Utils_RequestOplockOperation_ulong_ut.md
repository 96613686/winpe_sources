# UnionFs::Utils::RequestOplock(_FLT_INSTANCE const &,_FILE_OBJECT const &,UnionFs::Utils::RequestOplockOperation,ulong,utl::unique_ptr<UnionFs::Utils::RequestOplockContext,utl::default_delete<UnionFs::Utils::RequestOplockContext>> &&,UnionFs::StackEventTracer &,ulong)

- ea: `0x140076860`
- end: `0x140076aaa`
- name: `?RequestOplock@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@W4RequestOplockOperation@12@K$$QEAV?$unique_ptr@VRequestOplockContext@Utils@UnionFs@@U?$default_delete@VRequestOplockContext@Utils@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@K@Z`
- size: `586`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, __int64, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140058bb0`
- `0x140076bb0`

## callees

- `0x140056bd0`
- `0x140056c44`
- `0x140076860`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140076986`
- `ntoskrnl!ExFreePoolWithTag` at `0x140076986`
- `ntoskrnl!ExAllocatePool2` at `0x14007688e`
- `ntoskrnl!ExAllocatePool2` at `0x14007688e`
- `FLTMGR!FltPerformAsynchronousIo` at `0x140076a12`
- `FLTMGR!FltPerformAsynchronousIo` at `0x140076a12`
- `FLTMGR!FltFreeCallbackData` at `0x14007692c`
- `FLTMGR!FltFreeCallbackData` at `0x140076975`
- `FLTMGR!FltFreeCallbackData` at `0x140076a5d`
- `FLTMGR!FltFreeCallbackData` at `0x14007692c`
- `FLTMGR!FltFreeCallbackData` at `0x140076975`
- `FLTMGR!FltFreeCallbackData` at `0x140076a5d`
- `FLTMGR!FltAllocateCallbackData` at `0x140076905`
- `FLTMGR!FltAllocateCallbackData` at `0x140076905`

## pseudocode

```c

```
