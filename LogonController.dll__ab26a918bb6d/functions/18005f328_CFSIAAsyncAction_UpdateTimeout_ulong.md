# CFSIAAsyncAction::UpdateTimeout(ulong)

- ea: `0x18005f328`
- end: `0x18005f3b4`
- name: `?UpdateTimeout@CFSIAAsyncAction@@QEAAJK@Z`
- size: `140`
- prototype: `__int64 __fastcall(CFSIAAsyncAction *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180072310`
- `0x180072b70`

## callees

- `0x180026e70`
- `0x18005d4e8`
- `0x18005f328`
- `0x180070bf4`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18005f363`
- `KERNEL32!SetEvent` at `0x18005f363`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005f38d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005f3a1`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005f38d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005f3a1`

## pseudocode

```c

```
