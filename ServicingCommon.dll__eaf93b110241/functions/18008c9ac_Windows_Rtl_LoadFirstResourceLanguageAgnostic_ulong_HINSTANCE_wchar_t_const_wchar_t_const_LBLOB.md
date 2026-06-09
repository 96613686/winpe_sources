# Windows::Rtl::LoadFirstResourceLanguageAgnostic(ulong,HINSTANCE__ *,wchar_t const *,wchar_t const *,_LBLOB *)

- ea: `0x18008c9ac`
- end: `0x18008cc2b`
- name: `?LoadFirstResourceLanguageAgnostic@Rtl@Windows@@YAJKPEAUHINSTANCE__@@PEB_W1PEAU_LBLOB@@@Z`
- size: `639`
- prototype: `int(Windows::Rtl *__hidden this, unsigned int, HINSTANCE, const wchar_t *, const wchar_t *, struct _LBLOB *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18006e9b0`

## callees

- `0x18001fd10`
- `0x1800293a0`
- `0x18007e720`
- `0x18008c9ac`
- `0x18008cc34`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18008ca2b`
- `KERNEL32!GetLastError` at `0x18008ca42`
- `KERNEL32!GetLastError` at `0x18008cabe`
- `KERNEL32!GetLastError` at `0x18008cad5`
- `KERNEL32!GetLastError` at `0x18008cb3e`
- `KERNEL32!GetLastError` at `0x18008cb55`
- `KERNEL32!GetLastError` at `0x18008cbae`
- `KERNEL32!GetLastError` at `0x18008cbed`
- `KERNEL32!GetLastError` at `0x18008ca2b`
- `KERNEL32!GetLastError` at `0x18008ca42`
- `KERNEL32!GetLastError` at `0x18008cabe`
- `KERNEL32!GetLastError` at `0x18008cad5`
- `KERNEL32!GetLastError` at `0x18008cb3e`
- `KERNEL32!GetLastError` at `0x18008cb55`
- `KERNEL32!GetLastError` at `0x18008cbae`
- `KERNEL32!GetLastError` at `0x18008cbed`
- `KERNEL32!LoadResource` at `0x18008caaa`
- `KERNEL32!LoadResource` at `0x18008caaa`
- `KERNEL32!FindResourceExW` at `0x18008ca17`
- `KERNEL32!FindResourceExW` at `0x18008ca17`
- `KERNEL32!LockResource` at `0x18008cb96`
- `KERNEL32!LockResource` at `0x18008cb96`
- `KERNEL32!SizeofResource` at `0x18008cb1d`
- `KERNEL32!SizeofResource` at `0x18008cb1d`

## string_xrefs

- `0x18008ca74`: `hResInfo = ::FindResourceExW(DllHandle, pwszResourceType, pwszResourceId, Language)`
- `0x18008cb07`: `hResData = ::LoadResource(DllHandle, hResInfo)`

## pseudocode

```c

```
