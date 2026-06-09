# CFont::CreatePointFontIndirect(tagLOGFONTW const *,CDC *)

- ea: `0x18005e8e0`
- end: `0x18005e9fd`
- name: `?CreatePointFontIndirect@CFont@@QEAAHPEBUtagLOGFONTW@@PEAVCDC@@@Z`
- size: `285`
- prototype: `__int64 __fastcall(CFont *__hidden this, const struct tagLOGFONTW *, struct CDC *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18005e850`

## callees

- `0x18005e820`
- `0x18005e8e0`
- `0x1800d1fe0`

## import_xrefs

- `USER32!ReleaseDC` at `0x18005e9d1`
- `USER32!ReleaseDC` at `0x18005e9d1`
- `USER32!GetDC` at `0x18005e917`
- `USER32!GetDC` at `0x18005e917`
- `GDI32!GetDeviceCaps` at `0x18005e965`
- `GDI32!GetDeviceCaps` at `0x18005e965`
- `GDI32!DPtoLP` at `0x18005e997`
- `GDI32!DPtoLP` at `0x18005e9af`
- `GDI32!DPtoLP` at `0x18005e997`
- `GDI32!DPtoLP` at `0x18005e9af`

## pseudocode

```c

```
