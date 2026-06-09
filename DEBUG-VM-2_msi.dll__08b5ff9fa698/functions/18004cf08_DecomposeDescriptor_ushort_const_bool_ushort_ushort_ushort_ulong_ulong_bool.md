# DecomposeDescriptor(ushort const *,bool,ushort *,ushort *,ushort *,ulong *,ulong *,bool *)

- ea: `0x18004cf08`
- end: `0x18004d384`
- name: `?DecomposeDescriptor@@YAHPEBG_NPEAG22PEAK3PEA_N@Z`
- size: `1148`
- prototype: `int(const unsigned __int16 *, bool, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int *, unsigned int *, bool *)`
- caller_count: `13`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001ab38`
- `0x18001db00`
- `0x18001f190`
- `0x18004c654`
- `0x18004e3b0`
- `0x180050710`
- `0x1800814d0`
- `0x180156d00`
- `0x180195090`
- `0x180195480`
- `0x180197c40`
- `0x18019a110`
- `0x18019a800`

## callees

- `0x180015690`
- `0x180025a18`
- `0x18004aff0`
- `0x18004cf08`
- `0x18025ab80`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18004cf75`
- `KERNEL32!lstrlenW` at `0x18004cf75`
- `KERNEL32!GlobalFree` at `0x18004d068`
- `KERNEL32!GlobalFree` at `0x18004d084`
- `KERNEL32!GlobalFree` at `0x18004d11b`
- `KERNEL32!GlobalFree` at `0x18004d137`
- `KERNEL32!GlobalFree` at `0x18004d270`
- `KERNEL32!GlobalFree` at `0x18004d291`
- `KERNEL32!GlobalFree` at `0x18004d068`
- `KERNEL32!GlobalFree` at `0x18004d084`
- `KERNEL32!GlobalFree` at `0x18004d11b`
- `KERNEL32!GlobalFree` at `0x18004d137`
- `KERNEL32!GlobalFree` at `0x18004d270`
- `KERNEL32!GlobalFree` at `0x18004d291`

## string_xrefs

- `0x18004d21d`: `MSI_DBG: Provided descriptor less than minimum size`
- `0x18004d29f`: `MSI_DBG: Invalid descriptor format - unable to decode ProductCode in descriptor`
- `0x18004d2b8`: `MSI_DBG: Invalid feature name provided in descriptor (exceeds max feature length)`
- `0x18004d16b`: `MSI_DBG: Invalid descriptor format`
- `0x18004d2f6`: `MSI_DBG: Descriptor feature validation failed`
- `0x18004d34b`: `MSI_DBG: Descriptor feature validation failed`
- `0x18004d1f5`: `MSI_DBG: Invalid descriptor format - missing component specification`
- `0x18004d1df`: `MSI_DBG: Invalid descriptor format - unable to decode component`

## pseudocode

```c

```
