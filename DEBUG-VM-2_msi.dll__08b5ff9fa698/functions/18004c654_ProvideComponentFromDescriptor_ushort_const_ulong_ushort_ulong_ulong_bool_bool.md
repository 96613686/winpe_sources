# ProvideComponentFromDescriptor(ushort const *,ulong,ushort *,ulong *,ulong *,bool,bool)

- ea: `0x18004c654`
- end: `0x18004cb27`
- name: `?ProvideComponentFromDescriptor@@YAIPEBGKPEAGPEAK2_N3@Z`
- size: `1235`
- prototype: `unsigned int(const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int *, unsigned int *, bool, bool)`
- caller_count: `3`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001b230`
- `0x180050710`
- `0x180199ae0`

## callees

- `0x18001cab0`
- `0x18001d960`
- `0x180025560`
- `0x180025a18`
- `0x18004b75c`
- `0x18004c654`
- `0x18004cb30`
- `0x18004ceb0`
- `0x18004cee4`
- `0x18004cf08`
- `0x18006e53c`
- `0x18025ab12`
- `0x18025ab80`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18004c9e2`
- `KERNEL32!lstrlenW` at `0x18004ca86`
- `KERNEL32!lstrlenW` at `0x18004c9e2`
- `KERNEL32!lstrlenW` at `0x18004ca86`
- `KERNEL32!GlobalFree` at `0x18004c813`
- `KERNEL32!GlobalFree` at `0x18004c82d`
- `KERNEL32!GlobalFree` at `0x18004c847`
- `KERNEL32!GlobalFree` at `0x18004c8ba`
- `KERNEL32!GlobalFree` at `0x18004c8d6`
- `KERNEL32!GlobalFree` at `0x18004c8f2`
- `KERNEL32!GlobalFree` at `0x18004c92f`
- `KERNEL32!GlobalFree` at `0x18004c813`
- `KERNEL32!GlobalFree` at `0x18004c82d`
- `KERNEL32!GlobalFree` at `0x18004c847`
- `KERNEL32!GlobalFree` at `0x18004c8ba`
- `KERNEL32!GlobalFree` at `0x18004c8d6`
- `KERNEL32!GlobalFree` at `0x18004c8f2`
- `KERNEL32!GlobalFree` at `0x18004c92f`

## string_xrefs

- `0x18004c9a2`: `MsiProvideComponentFromDescriptor called for component %s: returning harcoded oleaut32.dll value`
- `0x18004c9db`: `oleaut32.dll`
- `0x18004ca19`: `oleaut32.dll`

## pseudocode

```c

```
