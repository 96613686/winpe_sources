# ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)

- ea: `0x180008210`
- end: `0x18000861c`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z`
- size: `1036`
- prototype: `int(ATL::CRegParser *__hidden this, wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000861c`

## callees

- `0x18000755c`
- `0x180008210`
- `0x1804c6944`
- `0x18056bd00`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800084c2`
- `KERNEL32!EnterCriticalSection` at `0x1800084c2`
- `KERNEL32!LeaveCriticalSection` at `0x180008528`
- `KERNEL32!LeaveCriticalSection` at `0x180008528`
- `KERNEL32!lstrcmpiW` at `0x1800084e0`
- `KERNEL32!lstrcmpiW` at `0x1800084e0`
- `VCRUNTIME140!wcsstr` at `0x1800082fa`
- `VCRUNTIME140!wcsstr` at `0x1800082fa`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x18000848c`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x18000848c`
- `USER32!CharNextW` at `0x18000830d`
- `USER32!CharNextW` at `0x180008319`
- `USER32!CharNextW` at `0x180008325`
- `USER32!CharNextW` at `0x180008331`
- `USER32!CharNextW` at `0x18000837b`
- `USER32!CharNextW` at `0x180008392`
- `USER32!CharNextW` at `0x18000840a`
- `USER32!CharNextW` at `0x18000844e`
- `USER32!CharNextW` at `0x180008561`
- `USER32!CharNextW` at `0x180008580`
- `USER32!CharNextW` at `0x18000830d`
- `USER32!CharNextW` at `0x180008319`
- `USER32!CharNextW` at `0x180008325`
- `USER32!CharNextW` at `0x180008331`
- `USER32!CharNextW` at `0x18000837b`
- `USER32!CharNextW` at `0x180008392`
- `USER32!CharNextW` at `0x18000840a`
- `USER32!CharNextW` at `0x18000844e`
- `USER32!CharNextW` at `0x180008561`
- `USER32!CharNextW` at `0x180008580`
- `ole32!CoTaskMemFree` at `0x1800085ba`
- `ole32!CoTaskMemFree` at `0x1800085ba`
- `ole32!CoTaskMemAlloc` at `0x180008298`
- `ole32!CoTaskMemAlloc` at `0x180008298`

## pseudocode

```c

```
