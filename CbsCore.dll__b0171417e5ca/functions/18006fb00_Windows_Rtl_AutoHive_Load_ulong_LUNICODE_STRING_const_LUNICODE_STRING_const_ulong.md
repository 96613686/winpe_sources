# Windows::Rtl::AutoHive::Load(ulong,_LUNICODE_STRING const &,_LUNICODE_STRING const &,ulong *)

- ea: `0x18006fb00`
- end: `0x18006ff81`
- name: `?Load@AutoHive@Rtl@Windows@@QEAAJKAEBU_LUNICODE_STRING@@0PEAK@Z`
- size: `1153`
- prototype: `__int64 __fastcall(Windows::Rtl::AutoHive *__hidden this, unsigned int, const struct _LUNICODE_STRING *, const struct _LUNICODE_STRING *, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x1801ee8c8`

## callees

- `0x18002e224`
- `0x180046198`
- `0x18006fad4`
- `0x18006fb00`
- `0x180070398`
- `0x1800aa1a4`
- `0x1800aa1d4`
- `0x1800be15c`
- `0x1800be788`
- `0x1800c177c`
- `0x1800eb920`
- `0x1800ef360`
- `0x18027d068`

## import_xrefs

- `ntdll!NtOpenKeyEx` at `0x18006fcc9`
- `ntdll!NtOpenKeyEx` at `0x18006fe58`
- `ntdll!NtOpenKeyEx` at `0x18006fcc9`
- `ntdll!NtOpenKeyEx` at `0x18006fe58`
- `ntdll!NtLoadKey2` at `0x18006fd0c`
- `ntdll!NtLoadKey2` at `0x18006fd3a`
- `ntdll!NtLoadKey2` at `0x18006fd0c`
- `ntdll!NtLoadKey2` at `0x18006fd3a`

## string_xrefs

- `0x18006fe91`: `NtOpenKeyEx(&m_RootKey, ((((0x00020000L)) | (0x0001) | (0x0008) | (0x0010)) & (~(0x00100000L))), &RootKeyAttributes, (0x00000004L))`

## pseudocode

```c

```
