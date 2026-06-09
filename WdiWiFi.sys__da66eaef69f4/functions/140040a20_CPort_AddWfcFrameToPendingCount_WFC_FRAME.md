# CPort::AddWfcFrameToPendingCount(_WFC_FRAME *)

- ea: `0x140040a20`
- end: `0x140040ab3`
- name: `?AddWfcFrameToPendingCount@CPort@@AEAAHPEAU_WFC_FRAME@@@Z`
- size: `147`
- prototype: `__int64 __fastcall(CPort *__hidden this, struct _WFC_FRAME *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400403c0`

## callees

- `0x140040a20`
- `0x14008726c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140040a6f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140040aa3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140040a6f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140040aa3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140040a3f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140040a3f`

## pseudocode

```c

```
