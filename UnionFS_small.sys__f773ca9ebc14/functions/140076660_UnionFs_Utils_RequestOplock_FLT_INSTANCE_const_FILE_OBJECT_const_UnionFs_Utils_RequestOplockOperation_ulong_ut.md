# UnionFs::Utils::RequestOplock(_FLT_INSTANCE const &,_FILE_OBJECT const &,UnionFs::Utils::RequestOplockOperation,ulong,utl::unique_ptr<UnionFs::Utils::RequestOplockContext,utl::default_delete<UnionFs::Utils::RequestOplockContext>> &&,UnionFs::StackEventTracer &,ulong)

- ea: `0x140076660`
- end: `0x1400768aa`
- name: `?RequestOplock@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@W4RequestOplockOperation@12@K$$QEAV?$unique_ptr@VRequestOplockContext@Utils@UnionFs@@U?$default_delete@VRequestOplockContext@Utils@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@K@Z`
- size: `586`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, __int64, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140058a30`
- `0x1400769b0`

## callees

- `0x140056a50`
- `0x140056ac4`
- `0x140076660`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140076786`
- `ntoskrnl!ExFreePoolWithTag` at `0x140076786`
- `ntoskrnl!ExAllocatePool2` at `0x14007668e`
- `ntoskrnl!ExAllocatePool2` at `0x14007668e`
- `FLTMGR!FltPerformAsynchronousIo` at `0x140076812`
- `FLTMGR!FltPerformAsynchronousIo` at `0x140076812`
- `FLTMGR!FltFreeCallbackData` at `0x14007672c`
- `FLTMGR!FltFreeCallbackData` at `0x140076775`
- `FLTMGR!FltFreeCallbackData` at `0x14007685d`
- `FLTMGR!FltFreeCallbackData` at `0x14007672c`
- `FLTMGR!FltFreeCallbackData` at `0x140076775`
- `FLTMGR!FltFreeCallbackData` at `0x14007685d`
- `FLTMGR!FltAllocateCallbackData` at `0x140076705`
- `FLTMGR!FltAllocateCallbackData` at `0x140076705`

## pseudocode

```c

```
