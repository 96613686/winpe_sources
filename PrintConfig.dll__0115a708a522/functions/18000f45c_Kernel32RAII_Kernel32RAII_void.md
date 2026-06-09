# Kernel32RAII::Kernel32RAII(void)

- ea: `0x18000f45c`
- end: `0x18000f602`
- name: `??0Kernel32RAII@@QEAA@XZ`
- size: `422`
- prototype: `Kernel32RAII *__fastcall(Kernel32RAII *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180011fa8`
- `0x180012234`
- `0x180012870`

## callees

- `0x180004564`
- `0x18000f45c`
- `0x18000f830`
- `0x1800197b4`
- `0x180157d60`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000f4a5`
- `KERNEL32!GetProcAddress` at `0x18000f4bf`
- `KERNEL32!GetProcAddress` at `0x18000f4da`
- `KERNEL32!GetProcAddress` at `0x18000f4f5`
- `KERNEL32!GetProcAddress` at `0x18000f510`
- `KERNEL32!GetProcAddress` at `0x18000f52b`
- `KERNEL32!GetProcAddress` at `0x18000f4a5`
- `KERNEL32!GetProcAddress` at `0x18000f4bf`
- `KERNEL32!GetProcAddress` at `0x18000f4da`
- `KERNEL32!GetProcAddress` at `0x18000f4f5`
- `KERNEL32!GetProcAddress` at `0x18000f510`
- `KERNEL32!GetProcAddress` at `0x18000f52b`
- `KERNEL32!GetLastError` at `0x18000f597`
- `KERNEL32!GetLastError` at `0x18000f597`

## string_xrefs

- `0x18000f486`: `kernel32.dll`
- `0x18000f49a`: `CreatePrivateNamespaceW`
- `0x18000f4b4`: `OpenPrivateNamespaceW`
- `0x18000f4ea`: `CreateBoundaryDescriptorW`
- `0x18000f505`: `DeleteBoundaryDescriptor`
- `0x18000f520`: `AddSIDToBoundaryDescriptor`

## pseudocode

```c

```
