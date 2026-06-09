# RtlpWin32FindFirstResourceLanguage(ulong,HINSTANCE__ *,wchar_t const *,wchar_t const *,ushort *)

- ea: `0x18008bb00`
- end: `0x18008bc1c`
- name: `?RtlpWin32FindFirstResourceLanguage@@YAJKPEAUHINSTANCE__@@PEB_W1PEAG@Z`
- size: `284`
- prototype: `int(unsigned int, HINSTANCE, const wchar_t *, const wchar_t *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18008b874`

## callees

- `0x18002d2b0`
- `0x18007d794`
- `0x18008bb00`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18008bb78`
- `KERNEL32!GetLastError` at `0x18008bb8f`
- `KERNEL32!GetLastError` at `0x18008bb78`
- `KERNEL32!GetLastError` at `0x18008bb8f`
- `KERNEL32!EnumResourceLanguagesExW` at `0x18008bb64`
- `KERNEL32!EnumResourceLanguagesExW` at `0x18008bb64`
- `ntdll!RtlRaiseStatus` at `0x18008bc0f`
- `ntdll!RtlRaiseStatus` at `0x18008bc0f`

## string_xrefs

- `0x18008bbbd`: `::EnumResourceLanguagesExW( DllHandle, pwszResourceType, pwszResourceId, &RtlpWin32FindFirstResourceLanguage_EnumerateResourceLanguagesCallback, reinterpret_cast<LONG_PTR>(&EnumerationContext), (0x0001), 0)`

## pseudocode

```c

```
