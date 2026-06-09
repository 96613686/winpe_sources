# UnionFs::UfsInstanceCtx::FltGet(_FILE_OBJECT const &,bool,wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)

- ea: `0x140027624`
- end: `0x14002775e`
- name: `?FltGet@UfsInstanceCtx@UnionFs@@SAJAEBU_FILE_OBJECT@@_NAEAV?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z`
- size: `314`
- prototype: `__int64 __fastcall(PFILE_OBJECT FileObject)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400365c8`
- `0x14003a1a4`

## callees

- `0x140027624`
- `0x140027764`
- `0x140056c7c`
- `0x14006ed2c`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x140027645`
- `FLTMGR!FltReleaseContext` at `0x140027717`
- `FLTMGR!FltReleaseContext` at `0x140027735`
- `FLTMGR!FltReleaseContext` at `0x140027645`
- `FLTMGR!FltReleaseContext` at `0x140027717`
- `FLTMGR!FltReleaseContext` at `0x140027735`
- `FLTMGR!FltObjectDereference` at `0x1400276a1`
- `FLTMGR!FltObjectDereference` at `0x140027746`
- `FLTMGR!FltObjectDereference` at `0x1400276a1`
- `FLTMGR!FltObjectDereference` at `0x140027746`

## pseudocode

```c

```
