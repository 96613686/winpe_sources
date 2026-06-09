# PAL_System_Win32_CryptProtectMemory(uchar *,uint,uchar * *,uint *)

- ea: `0x18011346c`
- end: `0x1801136c6`
- name: `?PAL_System_Win32_CryptProtectMemory@@YAJPEAEIPEAPEAEPEAI@Z`
- size: `602`
- prototype: `__int64 __fastcall(unsigned __int8 *Src, size_t Size, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1801154b0`

## callees

- `0x1800018a4`
- `0x18011346c`
- `0x1801614c4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180113547`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180113547`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011369e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011369e`
- `CRYPT32!CryptProtectMemory` at `0x1801135eb`
- `CRYPT32!CryptProtectMemory` at `0x1801135eb`

## string_xrefs

- `0x1801134f0`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x180113585`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x18011362f`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`

## pseudocode

```c

```
