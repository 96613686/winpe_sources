# UnionFs::Utils::EnumerateDirectory(_FLT_INSTANCE const &,_FILE_OBJECT const &,_FILE_INFORMATION_CLASS,ulong,uchar,utl::pair<gsl::span<gsl::byte,-1>,ulong> &,UnionFs::StackEventTracer &,_UNICODE_STRING const *)

- ea: `0x14006dee0`
- end: `0x14006e081`
- name: `?EnumerateDirectory@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@W4_FILE_INFORMATION_CLASS@@KEAEAU?$pair@V?$span@W4byte@gsl@@$0?0@gsl@@K@utl@@AEAVStackEventTracer@2@PEBU_UNICODE_STRING@@@Z`
- size: `417`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14001bf60`
- `0x140026798`

## callees

- `0x140056bd0`
- `0x14006dee0`
- `0x14007b2b0`

## import_xrefs

- `FLTMGR!FltPerformSynchronousIo` at `0x14006dfe3`
- `FLTMGR!FltPerformSynchronousIo` at `0x14006dfe3`
- `FLTMGR!FltFreeCallbackData` at `0x14006df3b`
- `FLTMGR!FltFreeCallbackData` at `0x14006e067`
- `FLTMGR!FltFreeCallbackData` at `0x14006df3b`
- `FLTMGR!FltFreeCallbackData` at `0x14006e067`
- `FLTMGR!FltAllocateCallbackData` at `0x14006df14`
- `FLTMGR!FltAllocateCallbackData` at `0x14006df14`

## string_xrefs

- `0x14006e043`: `UnionFs::Utils::EnumerateDirectory`
- `0x14006e02e`: `API: IRP_MJ_DIRECTORY_CONTROL/IRP_MN_QUERY_DIRECTORY`

## pseudocode

```c

```
