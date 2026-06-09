# SHComputeDPI(HWND__ *,int *,int *)

- ea: `0x18006beb8`
- end: `0x18006bf26`
- name: `?SHComputeDPI@@YAXPEAUHWND__@@PEAH1@Z`
- size: `110`
- prototype: `void __fastcall(HWND, int *, int *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18006c078`
- `0x18006d26c`
- `0x18006e648`
- `0x18006e6f0`

## callees

- `0x18006beb8`

## import_xrefs

- `GDI32!GetDeviceCaps` at `0x18006bee1`
- `GDI32!GetDeviceCaps` at `0x18006bef1`
- `GDI32!GetDeviceCaps` at `0x18006bee1`
- `GDI32!GetDeviceCaps` at `0x18006bef1`
- `USER32!GetDC` at `0x18006becb`
- `USER32!GetDC` at `0x18006becb`
- `USER32!ReleaseDC` at `0x18006befe`
- `USER32!ReleaseDC` at `0x18006befe`

## pseudocode

```c

```
