# VrwHandle::beginWriteLock(ulong)

- ea: `0x1800b0240`
- end: `0x1800b0360`
- name: `?beginWriteLock@VrwHandle@@IEAADK@Z`
- size: `288`
- prototype: `char __fastcall(VrwHandle *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800b0030`

## callees

- `0x1800b0240`
- `0x1800b0394`
- `0x1800b0548`
- `0x1801519a0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1800b0299`
- `KERNEL32!WaitForSingleObject` at `0x1800b02f2`
- `KERNEL32!WaitForSingleObject` at `0x1800b0299`
- `KERNEL32!WaitForSingleObject` at `0x1800b02f2`
- `KERNEL32!SetEvent` at `0x1800b033d`
- `KERNEL32!SetEvent` at `0x1800b033d`
- `KERNEL32!ResetEvent` at `0x1800b02e6`
- `KERNEL32!ResetEvent` at `0x1800b02e6`

## string_xrefs

- `0x1800b02aa`: `VrwObj::beginWriteLock() could not get WriterEvent`
- `0x1800b0303`: `VrwObj::beginWriteLock() could not get DataBSem`

## pseudocode

```c

```
