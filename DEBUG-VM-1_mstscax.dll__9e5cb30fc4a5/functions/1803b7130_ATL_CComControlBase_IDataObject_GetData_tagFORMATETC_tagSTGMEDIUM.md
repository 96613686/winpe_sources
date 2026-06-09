# ATL::CComControlBase::IDataObject_GetData(tagFORMATETC *,tagSTGMEDIUM *)

- ea: `0x1803b7130`
- end: `0x1803b731c`
- name: `?IDataObject_GetData@CComControlBase@ATL@@QEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `492`
- prototype: `__int64 __fastcall(ATL::CComControlBase *__hidden this, struct tagFORMATETC *, struct tagSTGMEDIUM *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1803b6010`
- `0x1803b6030`

## callees

- `0x1803b309c`
- `0x1803b7130`
- `0x180688f3e`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x1803b72a1`
- `KERNEL32!GlobalAlloc` at `0x1803b72a1`
- `KERNEL32!GlobalLock` at `0x1803b72c2`
- `KERNEL32!GlobalLock` at `0x1803b72c2`
- `KERNEL32!GlobalUnlock` at `0x1803b72de`
- `KERNEL32!GlobalUnlock` at `0x1803b72de`
- `GDI32!RestoreDC` at `0x1803b7278`
- `GDI32!RestoreDC` at `0x1803b7278`
- `GDI32!SetWindowOrgEx` at `0x1803b7244`
- `GDI32!SetWindowOrgEx` at `0x1803b7244`
- `GDI32!SaveDC` at `0x1803b7232`
- `GDI32!SaveDC` at `0x1803b7232`
- `GDI32!DeleteMetaFile` at `0x1803b72b2`
- `GDI32!DeleteMetaFile` at `0x1803b72b2`
- `GDI32!CloseMetaFile` at `0x1803b7282`
- `GDI32!CloseMetaFile` at `0x1803b7282`
- `GDI32!SetWindowExtEx` at `0x1803b7258`
- `GDI32!SetWindowExtEx` at `0x1803b7258`
- `GDI32!CreateMetaFileW` at `0x1803b7225`
- `GDI32!CreateMetaFileW` at `0x1803b7225`

## pseudocode

```c

```
