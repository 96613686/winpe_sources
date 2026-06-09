# Windows::Rtl::SystemImplementation::CFilesystemObjectBase::Rename(ulong,Windows::Rtl::SystemImplementation::CDirectory *,_LUNICODE_STRING const &,ulong *)

- ea: `0x1801700f0`
- end: `0x180170619`
- name: `?Rename@CFilesystemObjectBase@SystemImplementation@Rtl@Windows@@QEAAJKPEAVCDirectory@234@AEBU_LUNICODE_STRING@@PEAK@Z`
- size: `1321`
- prototype: `__int64 __fastcall(Windows::Rtl::SystemImplementation::CFilesystemObjectBase *__hidden this, unsigned int, struct Windows::Rtl::SystemImplementation::CDirectory *, const struct _LUNICODE_STRING *, unsigned int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, loader_planting`

## callers

- `0x18013e434`
- `0x180162c00`

## callees

- `0x1800031d0`
- `0x18000aedc`
- `0x18000e098`
- `0x180030b68`
- `0x1800497c0`
- `0x180049c6c`
- `0x180118218`
- `0x18011a684`
- `0x1801440dc`
- `0x18014bc88`
- `0x1801700f0`
- `0x1801bd010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180170387`
- `ntdll!RtlFreeHeap` at `0x180170443`
- `ntdll!RtlFreeHeap` at `0x1801704ce`
- `ntdll!RtlFreeHeap` at `0x1801705c9`
- `ntdll!RtlFreeHeap` at `0x180170387`
- `ntdll!RtlFreeHeap` at `0x180170443`
- `ntdll!RtlFreeHeap` at `0x1801704ce`
- `ntdll!RtlFreeHeap` at `0x1801705c9`

## string_xrefs

- `0x18017028b`: `m_FileSystemProvider == NewParent->m_FileSystemProvider`
- `0x18017016c`: `Windows::Rtl::SystemImplementation::CFilesystemObjectBase::Rename`

## pseudocode

```c

```
