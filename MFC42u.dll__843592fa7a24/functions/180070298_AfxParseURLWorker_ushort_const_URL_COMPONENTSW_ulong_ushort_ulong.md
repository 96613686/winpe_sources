# _AfxParseURLWorker(ushort const *,URL_COMPONENTSW *,ulong &,ushort &,ulong)

- ea: `0x180070298`
- end: `0x18007042d`
- name: `?_AfxParseURLWorker@@YAHPEBGPEAUURL_COMPONENTSW@@AEAKAEAGK@Z`
- size: `405`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct URL_COMPONENTSW *, unsigned int *, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18006db90`
- `0x18006dc60`

## callees

- `0x18000ce50`
- `0x180070298`
- `0x1800d1fe0`
- `0x1800d2180`

## import_xrefs

- `msvcrt!free` at `0x180070354`
- `msvcrt!free` at `0x1800703af`
- `msvcrt!free` at `0x180070354`
- `msvcrt!free` at `0x1800703af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007030c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007030c`
- `WININET!InternetCanonicalizeUrlW` at `0x180070302`
- `WININET!InternetCanonicalizeUrlW` at `0x180070347`
- `WININET!InternetCanonicalizeUrlW` at `0x180070302`
- `WININET!InternetCanonicalizeUrlW` at `0x180070347`
- `WININET!InternetCrackUrlW` at `0x18007039f`
- `WININET!InternetCrackUrlW` at `0x18007039f`

## pseudocode

```c

```
