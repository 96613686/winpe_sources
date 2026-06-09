# CRTFWrite::GetRtfObjectMetafilePict(void *,_rtfobject &,tagSIZE &)

- ea: `0x18007d938`
- end: `0x18007da24`
- name: `?GetRtfObjectMetafilePict@CRTFWrite@@AEAAHPEAXAEAU_rtfobject@@AEAUtagSIZE@@@Z`
- size: `236`
- prototype: `int(CRTFWrite *__hidden this, void *, struct _rtfobject *, struct tagSIZE *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18007d7bc`

## callees

- `0x180038bd0`
- `0x18004a8fc`
- `0x18007d938`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x18007d9bf`
- `KERNEL32!GlobalAlloc` at `0x18007d9bf`
- `KERNEL32!GlobalLock` at `0x18007d953`
- `KERNEL32!GlobalLock` at `0x18007d9d0`
- `KERNEL32!GlobalLock` at `0x18007d953`
- `KERNEL32!GlobalLock` at `0x18007d9d0`
- `KERNEL32!GlobalUnlock` at `0x18007da0f`
- `KERNEL32!GlobalUnlock` at `0x18007da0f`
- `GDI32!GetMetaFileBitsEx` at `0x18007d9ac`
- `GDI32!GetMetaFileBitsEx` at `0x18007d9f3`
- `GDI32!GetMetaFileBitsEx` at `0x18007d9ac`
- `GDI32!GetMetaFileBitsEx` at `0x18007d9f3`

## pseudocode

```c

```
