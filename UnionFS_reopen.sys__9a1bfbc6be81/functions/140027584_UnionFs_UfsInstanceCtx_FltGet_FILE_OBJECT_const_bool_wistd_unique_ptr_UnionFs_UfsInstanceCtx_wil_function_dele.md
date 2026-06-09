# UnionFs::UfsInstanceCtx::FltGet(_FILE_OBJECT const &,bool,wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)

- ea: `0x140027584`
- end: `0x1400276be`
- name: `?FltGet@UfsInstanceCtx@UnionFs@@SAJAEBU_FILE_OBJECT@@_NAEAV?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z`
- size: `314`
- prototype: `__int64 __fastcall(PFILE_OBJECT FileObject)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140036488`
- `0x14003a064`

## callees

- `0x140027584`
- `0x1400276c4`
- `0x140056afc`
- `0x14006eb3c`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x1400275a5`
- `FLTMGR!FltReleaseContext` at `0x140027677`
- `FLTMGR!FltReleaseContext` at `0x140027695`
- `FLTMGR!FltReleaseContext` at `0x1400275a5`
- `FLTMGR!FltReleaseContext` at `0x140027677`
- `FLTMGR!FltReleaseContext` at `0x140027695`
- `FLTMGR!FltObjectDereference` at `0x140027601`
- `FLTMGR!FltObjectDereference` at `0x1400276a6`
- `FLTMGR!FltObjectDereference` at `0x140027601`
- `FLTMGR!FltObjectDereference` at `0x1400276a6`

## pseudocode

```c

```
