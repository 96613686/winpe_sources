# MbbReqMgrLockManager(_MBB_REQUEST_MANAGER *)

- ea: `0x14001a87c`
- end: `0x14001a8a5`
- name: `?MbbReqMgrLockManager@@YAXPEAU_MBB_REQUEST_MANAGER@@@Z`
- size: `41`
- prototype: `void __fastcall(struct _MBB_REQUEST_MANAGER *)`
- caller_count: `22`
- callee_count: `0`
- tags: ``

## callers

- `0x14000b030`
- `0x14000cc8c`
- `0x140018ce0`
- `0x140018ff0`
- `0x1400193bc`
- `0x1400196ac`
- `0x140019b6c`
- `0x140019f78`
- `0x14001a234`
- `0x14001a8ac`
- `0x14001a9ec`
- `0x14001abec`
- `0x14001acf8`
- `0x14001ae10`
- `0x14001aeb8`
- `0x14001b1c0`
- `0x14001b348`
- `0x14001b47c`
- `0x14001ffa4`
- `0x140020330`
- `0x140026698`
- `0x140026e44`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a88c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a88c`

## pseudocode

```c
void __fastcall MbbReqMgrLockManager(struct _MBB_REQUEST_MANAGER *a1)
{
  *((_BYTE *)a1 + 184) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 22);
}

```

## disassembly

```asm
0x14001a87c  push    rbx
0x14001a87e  sub     rsp, 20h
0x14001a882  mov     rbx, rcx
0x14001a885  add     rcx, 0B0h; SpinLock
0x14001a88c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001a893  nop     dword ptr [rax+rax+00h]
0x14001a898  mov     [rbx+0B8h], al
0x14001a89e  add     rsp, 20h
0x14001a8a2  pop     rbx
0x14001a8a3  retn
```
