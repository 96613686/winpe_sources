# UnionFs::Utils::ChangeBackingFileObject(_FILE_OBJECT &,_FILE_OBJECT &,UnionFs::StackEventTracer &)

- ea: `0x140069980`
- end: `0x140069a79`
- name: `?ChangeBackingFileObject@Utils@UnionFs@@YAXAEAU_FILE_OBJECT@@0AEAVStackEventTracer@2@@Z`
- size: `249`
- prototype: `void __fastcall(PFILE_OBJECT CurrentFileObject, PFILE_OBJECT NewFileObject, struct _FILE_OBJECT *, struct UnionFs::StackEventTracer *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140054a70`
- `0x140058968`

## callees

- `0x140056bd0`
- `0x140069980`

## import_xrefs

- `ntoskrnl!FsRtlChangeBackingFileObject` at `0x1400699aa`
- `ntoskrnl!FsRtlChangeBackingFileObject` at `0x1400699ed`
- `ntoskrnl!FsRtlChangeBackingFileObject` at `0x140069a31`
- `ntoskrnl!FsRtlChangeBackingFileObject` at `0x1400699aa`
- `ntoskrnl!FsRtlChangeBackingFileObject` at `0x1400699ed`
- `ntoskrnl!FsRtlChangeBackingFileObject` at `0x140069a31`

## string_xrefs

- `0x140069a41`: `API: Swapping file object for shared cache map`

## pseudocode

```c

```
