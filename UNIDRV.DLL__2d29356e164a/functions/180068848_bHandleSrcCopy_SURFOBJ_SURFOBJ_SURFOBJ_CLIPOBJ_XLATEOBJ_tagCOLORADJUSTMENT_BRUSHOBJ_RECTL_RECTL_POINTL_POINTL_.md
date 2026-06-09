# bHandleSrcCopy(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_BRUSHOBJ *,_RECTL *,_RECTL *,_POINTL *,_POINTL *,ulong,ulong)

- ea: `0x180068848`
- end: `0x180068997`
- name: `?bHandleSrcCopy@@YAHPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAUtagCOLORADJUSTMENT@@PEAU_BRUSHOBJ@@PEAU_RECTL@@5PEAU_POINTL@@6KK@Z`
- size: `335`
- prototype: `int(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct tagCOLORADJUSTMENT *, struct _BRUSHOBJ *, struct _RECTL *, struct _RECTL *, struct _POINTL *, struct _POINTL *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800680fc`

## callees

- `0x180068648`
- `0x180068848`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180068874`
- `KERNEL32!SetLastError` at `0x180068874`
- `GDI32!EngStretchBlt` at `0x180068963`
- `GDI32!EngStretchBlt` at `0x180068963`

## pseudocode

```c

```
