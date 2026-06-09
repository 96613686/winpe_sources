# PAL_System_Win32_CredProtect(ushort const *,uint,ushort * *,uint *)

- ea: `0x180112be4`
- end: `0x180112ff4`
- name: `?PAL_System_Win32_CredProtect@@YAJPEBGIPEAPEAGPEAI@Z`
- size: `1040`
- prototype: `__int64 __fastcall(LPWSTR pszCredentials, DWORD cchCredentials, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180115470`

## callees

- `0x1800018a4`
- `0x180046a84`
- `0x1800711c8`
- `0x180112be4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180112c70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180112e79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180112c70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180112e79`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180112d64`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180112d64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180112efc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180112efc`
- `api-ms-win-security-credentials-l1-1-0!CredProtectW` at `0x180112c62`
- `api-ms-win-security-credentials-l1-1-0!CredProtectW` at `0x180112e6b`
- `api-ms-win-security-credentials-l1-1-0!CredProtectW` at `0x180112c62`
- `api-ms-win-security-credentials-l1-1-0!CredProtectW` at `0x180112e6b`

## string_xrefs

- `0x180112cb6`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x180112da6`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x180112f8b`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`

## pseudocode

```c

```
