# UnionFs::Utils::GetMappingTableForFileObject(_FLT_INSTANCE const &,_FILE_OBJECT const &,UnionFs::UfsScratchMappingTable * *,UnionFs::StackEventTracer &,wistd::unique_ptr<UnionFs::UfsSiloCtx,wil::function_deleter<void (*)(void *),&PsDereferenceSiloContext(void *)>> *)

- ea: `0x14006f198`
- end: `0x14006f2f2`
- name: `?GetMappingTableForFileObject@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@PEAPEAVUfsScratchMappingTable@2@AEAVStackEventTracer@2@PEAV?$unique_ptr@VUfsSiloCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?PsDereferenceSiloContext@@YAX0@Z@wil@@@wistd@@@Z`
- size: `346`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x140011e20`
- `0x14002e468`
- `0x140031cfc`
- `0x1400365c8`
- `0x140037b54`
- `0x14003a668`

## callees

- `0x140056c7c`
- `0x14005a5b8`
- `0x14006f198`

## import_xrefs

- `ntoskrnl!PsIsHostSilo` at `0x14006f1f3`
- `ntoskrnl!PsIsHostSilo` at `0x14006f1f3`
- `ntoskrnl!IoGetSilo` at `0x14006f1e1`
- `ntoskrnl!IoGetSilo` at `0x14006f1e1`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14006f1d2`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14006f266`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14006f2d8`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14006f1d2`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14006f266`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14006f2d8`

## pseudocode

```c

```
