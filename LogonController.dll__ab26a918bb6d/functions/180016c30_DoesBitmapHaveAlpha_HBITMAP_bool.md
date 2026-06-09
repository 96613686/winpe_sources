# _DoesBitmapHaveAlpha(HBITMAP__ *,bool *)

- ea: `0x180016c30`
- end: `0x180016e5d`
- name: `?_DoesBitmapHaveAlpha@@YAJPEAUHBITMAP__@@PEA_N@Z`
- size: `557`
- prototype: `__int64 __fastcall(HBITMAP hbm, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001684c`

## callees

- `0x180016c30`
- `0x180016e64`
- `0x18006c000`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180016d4e`
- `KERNEL32!GetLastError` at `0x180016d4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016d01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016d01`
- `ext-ms-win-gdi-dc-l1-2-0!GetObjectW` at `0x180016c73`
- `ext-ms-win-gdi-dc-l1-2-0!GetObjectW` at `0x180016c73`
- `ext-ms-win-gdi-draw-l1-1-0!GetDIBits` at `0x180016e3b`
- `ext-ms-win-gdi-draw-l1-1-0!GetDIBits` at `0x180016e3b`
- `USER32!ReleaseDC` at `0x180016cf8`
- `USER32!ReleaseDC` at `0x180016cf8`
- `USER32!GetDC` at `0x180016dd4`
- `USER32!GetDC` at `0x180016dd4`

## pseudocode

```c

```
