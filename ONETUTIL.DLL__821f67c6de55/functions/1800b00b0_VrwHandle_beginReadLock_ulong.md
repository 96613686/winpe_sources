# VrwHandle::beginReadLock(ulong)

- ea: `0x1800b00b0`
- end: `0x1800b0216`
- name: `?beginReadLock@VrwHandle@@IEAADK@Z`
- size: `358`
- prototype: `char __fastcall(VrwHandle *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800b0030`

## callees

- `0x1800b00b0`
- `0x1800b0394`
- `0x1800b0548`
- `0x1801519a0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1800b0109`
- `KERNEL32!WaitForSingleObject` at `0x1800b0164`
- `KERNEL32!WaitForSingleObject` at `0x1800b0191`
- `KERNEL32!WaitForSingleObject` at `0x1800b0109`
- `KERNEL32!WaitForSingleObject` at `0x1800b0164`
- `KERNEL32!WaitForSingleObject` at `0x1800b0191`
- `KERNEL32!SetEvent` at `0x1800b01e9`
- `KERNEL32!SetEvent` at `0x1800b01e9`
- `KERNEL32!ResetEvent` at `0x1800b0159`
- `KERNEL32!ResetEvent` at `0x1800b0159`
- `KERNEL32!ReleaseMutex` at `0x1800b01df`
- `KERNEL32!ReleaseMutex` at `0x1800b01f4`
- `KERNEL32!ReleaseMutex` at `0x1800b01df`
- `KERNEL32!ReleaseMutex` at `0x1800b01f4`

## string_xrefs

- `0x1800b0113`: `VrwObj::beginReadLock() could not get ReaderEvent`
- `0x1800b016e`: `VrwObj::beginReadLock() could not get ReaderMutex`
- `0x1800b01a2`: `VrwObj::beginReadLock() could not get DataBSem`

## pseudocode

```c

```
