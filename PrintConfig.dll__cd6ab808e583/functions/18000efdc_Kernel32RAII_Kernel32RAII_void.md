# Kernel32RAII::Kernel32RAII(void)

- ea: `0x18000efdc`
- end: `0x18000f157`
- name: `??0Kernel32RAII@@QEAA@XZ`
- size: `379`
- prototype: `Kernel32RAII *__fastcall(Kernel32RAII *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180011954`
- `0x180011ba4`
- `0x180012164`

## callees

- `0x180004424`
- `0x18000efdc`
- `0x18000f380`
- `0x180018bbc`
- `0x180150ce8`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000f025`
- `KERNEL32!GetProcAddress` at `0x18000f039`
- `KERNEL32!GetProcAddress` at `0x18000f04e`
- `KERNEL32!GetProcAddress` at `0x18000f063`
- `KERNEL32!GetProcAddress` at `0x18000f078`
- `KERNEL32!GetProcAddress` at `0x18000f08d`
- `KERNEL32!GetProcAddress` at `0x18000f025`
- `KERNEL32!GetProcAddress` at `0x18000f039`
- `KERNEL32!GetProcAddress` at `0x18000f04e`
- `KERNEL32!GetProcAddress` at `0x18000f063`
- `KERNEL32!GetProcAddress` at `0x18000f078`
- `KERNEL32!GetProcAddress` at `0x18000f08d`
- `KERNEL32!GetLastError` at `0x18000f0f2`
- `KERNEL32!GetLastError` at `0x18000f0f2`

## string_xrefs

- `0x18000f006`: `kernel32.dll`
- `0x18000f01a`: `CreatePrivateNamespaceW`
- `0x18000f02e`: `OpenPrivateNamespaceW`
- `0x18000f058`: `CreateBoundaryDescriptorW`
- `0x18000f06d`: `DeleteBoundaryDescriptor`
- `0x18000f082`: `AddSIDToBoundaryDescriptor`

## pseudocode

```c

```
