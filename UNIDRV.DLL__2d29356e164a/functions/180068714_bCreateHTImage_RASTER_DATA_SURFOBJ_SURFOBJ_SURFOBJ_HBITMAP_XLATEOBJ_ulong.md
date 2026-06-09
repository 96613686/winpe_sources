# bCreateHTImage(_RASTER_DATA *,_SURFOBJ *,_SURFOBJ *,_SURFOBJ * *,HBITMAP__ * *,_XLATEOBJ *,ulong)

- ea: `0x180068714`
- end: `0x180068842`
- name: `?bCreateHTImage@@YAHPEAU_RASTER_DATA@@PEAU_SURFOBJ@@1PEAPEAU2@PEAPEAUHBITMAP__@@PEAU_XLATEOBJ@@K@Z`
- size: `302`
- prototype: `__int64 __usercall@<rax>(struct _RASTER_DATA *@<rcx>, struct _SURFOBJ *@<rdx>, struct _SURFOBJ *@<r8>, struct _SURFOBJ **@<r9>, HBITMAP *, struct _XLATEOBJ *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180064378`

## callees

- `0x180067f0c`
- `0x180068714`
- `0x18006b334`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180068829`
- `KERNEL32!SetLastError` at `0x180068829`
- `GDI32!XLATEOBJ_piVector` at `0x1800687ab`
- `GDI32!XLATEOBJ_piVector` at `0x1800687ab`

## pseudocode

```c

```
