# UsbQueueRestart

- ea: `0x14000b2e8`
- end: `0x14000b356`
- name: `UsbQueueRestart`
- size: `110`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140004ed0`
- `0x14000b0bc`
- `0x14000ced4`

## callees

- `0x140003b90`
- `0x14000b2e8`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000b319`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000b319`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000b330`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000b330`

## pseudocode

```c
void __fastcall UsbQueueRestart(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v2; // rbx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  v1 = *(_QWORD *)(a1 + 64);
  memset(&LockHandle, 0, sizeof(LockHandle));
  v2 = *(_QWORD *)(*(_QWORD *)(v1 + 16) + 64LL);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v2 + 144), &LockHandle);
  LODWORD(v2) = *(_DWORD *)(v2 + 128);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( (v2 & 8) == 0 )
    UsbStorPumpNextRequest(v1);
}

```

## disassembly

```asm
0x14000b2e8  mov     [rsp+arg_0], rbx
0x14000b2ed  push    rdi
0x14000b2ee  sub     rsp, 40h
0x14000b2f2  mov     rdi, [rcx+40h]
0x14000b2f6  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x14000b2fb  xor     eax, eax
0x14000b2fd  xorps   xmm0, xmm0
0x14000b300  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x14000b305  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x14000b30a  mov     rax, [rdi+10h]
0x14000b30e  mov     rbx, [rax+40h]
0x14000b312  lea     rcx, [rbx+90h]; SpinLock
0x14000b319  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000b320  nop     dword ptr [rax+rax+00h]
0x14000b325  mov     ebx, [rbx+80h]
0x14000b32b  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x14000b330  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000b337  nop     dword ptr [rax+rax+00h]
0x14000b33c  bt      ebx, 3
0x14000b340  jb      short loc_14000B34A
0x14000b342  mov     rcx, rdi
0x14000b345  call    UsbStorPumpNextRequest
0x14000b34a  mov     rbx, [rsp+48h+arg_0]
0x14000b34f  add     rsp, 40h
0x14000b353  pop     rdi
0x14000b354  retn
```
