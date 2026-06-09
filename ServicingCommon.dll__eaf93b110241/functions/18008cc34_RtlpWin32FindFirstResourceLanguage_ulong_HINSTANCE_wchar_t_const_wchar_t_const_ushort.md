# RtlpWin32FindFirstResourceLanguage(ulong,HINSTANCE__ *,wchar_t const *,wchar_t const *,ushort *)

- ea: `0x18008cc34`
- end: `0x18008cd49`
- name: `?RtlpWin32FindFirstResourceLanguage@@YAJKPEAUHINSTANCE__@@PEB_W1PEAG@Z`
- size: `277`
- prototype: `int(unsigned int, HINSTANCE, const wchar_t *, const wchar_t *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18008c9ac`

## callees

- `0x18001fd10`
- `0x1800293a0`
- `0x18007e720`
- `0x18008cc34`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18008ccac`
- `KERNEL32!GetLastError` at `0x18008ccc3`
- `KERNEL32!GetLastError` at `0x18008ccac`
- `KERNEL32!GetLastError` at `0x18008ccc3`
- `KERNEL32!EnumResourceLanguagesExW` at `0x18008cc98`
- `KERNEL32!EnumResourceLanguagesExW` at `0x18008cc98`

## string_xrefs

- `0x18008ccf1`: `::EnumResourceLanguagesExW( DllHandle, pwszResourceType, pwszResourceId, &RtlpWin32FindFirstResourceLanguage_EnumerateResourceLanguagesCallback, reinterpret_cast<LONG_PTR>(&EnumerationContext), (0x0001), 0)`

## pseudocode

```c

```
