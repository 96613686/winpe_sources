# UrlEscapeATraits::Convert(char const *,char *,ulong *,ulong)

- ea: `0x180059d84`
- end: `0x18005a051`
- name: `?Convert@UrlEscapeATraits@@SA_NPEBDPEADPEAKK@Z`
- size: `717`
- prototype: `bool __fastcall(LPCCH lpMultiByteStr, char *, DWORD *pcchEscaped, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000e128`

## callees

- `0x1800060fc`
- `0x180006ed4`
- `0x180007e28`
- `0x18000ec98`
- `0x18001ccf0`
- `0x180059d84`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180059de0`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180059e2e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180059de0`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180059e2e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180059f36`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180059f66`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180059f36`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180059f66`
- `api-ms-win-core-url-l1-1-0!UrlEscapeW` at `0x180059ee3`
- `api-ms-win-core-url-l1-1-0!UrlEscapeW` at `0x180059ee3`

## string_xrefs

- `0x18005a00f`: `shellcommon\shell\wpccore\corelib\url.cpp`
- `0x18005a027`: `shellcommon\shell\wpccore\corelib\url.cpp`
- `0x18005a03f`: `shellcommon\shell\wpccore\corelib\url.cpp`

## pseudocode

```c

```
