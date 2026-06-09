# CInplaceRename::_DrawCompositionLine(HWND__ *,HDC__ *,HFONT__ *,ushort const *,uchar const *,uint,uint,uint)

- ea: `0x1800236e8`
- end: `0x180023925`
- name: `?_DrawCompositionLine@CInplaceRename@@AEAAXPEAUHWND__@@PEAUHDC__@@PEAUHFONT__@@PEBGPEBEIII@Z`
- size: `573`
- prototype: `void(CInplaceRename *__hidden this, HWND, HDC, HFONT, const unsigned __int16 *, const unsigned __int8 *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18008444c`

## callees

- `0x1800236e8`
- `0x1800243b0`
- `0x1800563fc`
- `0x18013f7d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800238f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800238f4`
- `USER32!DrawTextW` at `0x1800238c0`
- `USER32!DrawTextW` at `0x1800238c0`
- `USER32!SendMessageW` at `0x180023860`
- `USER32!SendMessageW` at `0x180023887`
- `USER32!SendMessageW` at `0x180023860`
- `USER32!SendMessageW` at `0x180023887`
- `USER32!GetSysColor` at `0x1800237f4`
- `USER32!GetSysColor` at `0x180023801`
- `USER32!GetSysColor` at `0x180023816`
- `USER32!GetSysColor` at `0x180023823`
- `USER32!GetSysColor` at `0x1800237f4`
- `USER32!GetSysColor` at `0x180023801`
- `USER32!GetSysColor` at `0x180023816`
- `USER32!GetSysColor` at `0x180023823`
- `GDI32!SetTextColor` at `0x180023831`
- `GDI32!SetTextColor` at `0x1800238dd`
- `GDI32!SetTextColor` at `0x180023831`
- `GDI32!SetTextColor` at `0x1800238dd`
- `GDI32!SelectObject` at `0x18002386e`
- `GDI32!SelectObject` at `0x1800238d1`
- `GDI32!SelectObject` at `0x18002386e`
- `GDI32!SelectObject` at `0x1800238d1`
- `GDI32!SetBkColor` at `0x180023840`
- `GDI32!SetBkColor` at `0x1800238e9`
- `GDI32!SetBkColor` at `0x180023840`
- `GDI32!SetBkColor` at `0x1800238e9`

## pseudocode

```c

```
