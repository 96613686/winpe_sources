# StatusUpdate::IncrementTick(uint)

- ea: `0x14004bbb8`
- end: `0x14004bc30`
- name: `?IncrementTick@StatusUpdate@@QEAAXI@Z`
- size: `120`
- prototype: `void __fastcall(StatusUpdate *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140010258`

## callees

- `0x14004bbb8`
- `0x14004bc38`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14004bbc3`
- `KERNEL32!EnterCriticalSection` at `0x14004bbc3`
- `KERNEL32!LeaveCriticalSection` at `0x14004bc29`
- `KERNEL32!SetEvent` at `0x14004bc06`
- `KERNEL32!SetEvent` at `0x14004bc06`
- `KERNEL32!WaitForSingleObject` at `0x14004bc18`
- `KERNEL32!WaitForSingleObject` at `0x14004bc18`

## pseudocode

```c

```
