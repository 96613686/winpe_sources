# UnionFs::Utils::ChangeBackingFileObject(_FILE_OBJECT &,_FILE_OBJECT &,UnionFs::StackEventTracer &)

- ea: `0x140069790`
- end: `0x140069889`
- name: `?ChangeBackingFileObject@Utils@UnionFs@@YAXAEAU_FILE_OBJECT@@0AEAVStackEventTracer@2@@Z`
- size: `249`
- prototype: `void __fastcall(PFILE_OBJECT CurrentFileObject, PFILE_OBJECT NewFileObject, struct _FILE_OBJECT *, struct UnionFs::StackEventTracer *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400548f0`
- `0x1400587e8`

## callees

- `0x140056a50`
- `0x140069790`

## import_xrefs

- `ntoskrnl!FsRtlChangeBackingFileObject` at `0x1400697ba`
- `ntoskrnl!FsRtlChangeBackingFileObject` at `0x1400697fd`
- `ntoskrnl!FsRtlChangeBackingFileObject` at `0x140069841`
- `ntoskrnl!FsRtlChangeBackingFileObject` at `0x1400697ba`
- `ntoskrnl!FsRtlChangeBackingFileObject` at `0x1400697fd`
- `ntoskrnl!FsRtlChangeBackingFileObject` at `0x140069841`

## string_xrefs

- `0x140069851`: `API: Swapping file object for shared cache map`

## pseudocode

```c

```
