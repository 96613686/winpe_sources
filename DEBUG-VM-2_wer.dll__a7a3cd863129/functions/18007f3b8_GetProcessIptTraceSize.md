# GetProcessIptTraceSize

- ea: `0x18007f3b8`
- end: `0x18007f4da`
- name: `GetProcessIptTraceSize`
- size: `290`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002054c`
- `0x180027bc8`

## callees

- `0x18002babc`
- `0x180050db0`
- `0x18007f384`
- `0x18007f3b8`

## import_xrefs

- `ntdll!RtlReleasePrivilege` at `0x18007f494`
- `ntdll!RtlReleasePrivilege` at `0x18007f494`
- `ntdll!NtDeviceIoControlFile` at `0x18007f47a`
- `ntdll!NtDeviceIoControlFile` at `0x18007f47a`
- `ntdll!NtClose` at `0x18007f486`
- `ntdll!NtClose` at `0x18007f486`

## pseudocode

```c

```
