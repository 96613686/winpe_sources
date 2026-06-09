# CiGetCatalogHintByFilePath

- ea: `0x1801f1098`
- end: `0x1801f1215`
- name: `CiGetCatalogHintByFilePath`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18021c2b4`

## callees

- `0x1801f1098`
- `0x1801f121c`

## import_xrefs

- `ntdll!NtClose` at `0x1801f11bb`
- `ntdll!NtClose` at `0x1801f11bb`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1801f10e8`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1801f10e8`
- `ntdll!RtlReleaseRelativeName` at `0x1801f11ee`
- `ntdll!RtlReleaseRelativeName` at `0x1801f11ee`
- `ntdll!RtlFreeHeap` at `0x1801f11de`
- `ntdll!RtlFreeHeap` at `0x1801f11de`
- `ntdll!NtCreateFile` at `0x1801f1192`
- `ntdll!NtCreateFile` at `0x1801f1192`

## pseudocode

```c

```
