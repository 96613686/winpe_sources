# Windows::Rtl::LoadFirstResourceLanguageAgnostic(ulong,HINSTANCE__ *,wchar_t const *,wchar_t const *,_LBLOB *)

- ea: `0x18008b874`
- end: `0x18008baf8`
- name: `?LoadFirstResourceLanguageAgnostic@Rtl@Windows@@YAJKPEAUHINSTANCE__@@PEB_W1PEAU_LBLOB@@@Z`
- size: `644`
- prototype: `int(Windows::Rtl *__hidden this, unsigned int, HINSTANCE, const wchar_t *, const wchar_t *, struct _LBLOB *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18006e780`

## callees

- `0x18002d2b0`
- `0x18007d794`
- `0x18008b874`
- `0x18008bb00`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18008b8f3`
- `KERNEL32!GetLastError` at `0x18008b90a`
- `KERNEL32!GetLastError` at `0x18008b986`
- `KERNEL32!GetLastError` at `0x18008b99d`
- `KERNEL32!GetLastError` at `0x18008ba06`
- `KERNEL32!GetLastError` at `0x18008ba1d`
- `KERNEL32!GetLastError` at `0x18008ba76`
- `KERNEL32!GetLastError` at `0x18008bab5`
- `KERNEL32!GetLastError` at `0x18008b8f3`
- `KERNEL32!GetLastError` at `0x18008b90a`
- `KERNEL32!GetLastError` at `0x18008b986`
- `KERNEL32!GetLastError` at `0x18008b99d`
- `KERNEL32!GetLastError` at `0x18008ba06`
- `KERNEL32!GetLastError` at `0x18008ba1d`
- `KERNEL32!GetLastError` at `0x18008ba76`
- `KERNEL32!GetLastError` at `0x18008bab5`
- `KERNEL32!LoadResource` at `0x18008b972`
- `KERNEL32!LoadResource` at `0x18008b972`
- `KERNEL32!FindResourceExW` at `0x18008b8df`
- `KERNEL32!FindResourceExW` at `0x18008b8df`
- `KERNEL32!LockResource` at `0x18008ba5e`
- `KERNEL32!LockResource` at `0x18008ba5e`
- `KERNEL32!SizeofResource` at `0x18008b9e5`
- `KERNEL32!SizeofResource` at `0x18008b9e5`
- `ntdll!RtlRaiseStatus` at `0x18008baca`
- `ntdll!RtlRaiseStatus` at `0x18008baca`

## string_xrefs

- `0x18008b93c`: `hResInfo = ::FindResourceExW(DllHandle, pwszResourceType, pwszResourceId, Language)`
- `0x18008b9cf`: `hResData = ::LoadResource(DllHandle, hResInfo)`

## pseudocode

```c

```
