# UnionFs::Utils::GetMappingTableForFileObject(_FLT_INSTANCE const &,_FILE_OBJECT const &,UnionFs::UfsScratchMappingTable * *,UnionFs::StackEventTracer &,wistd::unique_ptr<UnionFs::UfsSiloCtx,wil::function_deleter<void (*)(void *),&PsDereferenceSiloContext(void *)>> *)

- ea: `0x14006efa8`
- end: `0x14006f102`
- name: `?GetMappingTableForFileObject@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@PEAPEAVUfsScratchMappingTable@2@AEAVStackEventTracer@2@PEAV?$unique_ptr@VUfsSiloCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?PsDereferenceSiloContext@@YAX0@Z@wil@@@wistd@@@Z`
- size: `346`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x140011e00`
- `0x14002e3c8`
- `0x140031c5c`
- `0x140036488`
- `0x140037a14`
- `0x14003a528`

## callees

- `0x140056afc`
- `0x14005a438`
- `0x14006efa8`

## import_xrefs

- `ntoskrnl!PsIsHostSilo` at `0x14006f003`
- `ntoskrnl!PsIsHostSilo` at `0x14006f003`
- `ntoskrnl!IoGetSilo` at `0x14006eff1`
- `ntoskrnl!IoGetSilo` at `0x14006eff1`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14006efe2`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14006f076`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14006f0e8`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14006efe2`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14006f076`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14006f0e8`

## pseudocode

```c

```
