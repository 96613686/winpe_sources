# CancelStatusIrp

- ea: `0x140009b78`
- end: `0x140009c07`
- name: `CancelStatusIrp`
- size: `143`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400072c0`
- `0x140007f80`
- `0x140009c10`

## callees

- `0x140009b78`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009bd2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009bd2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140009bad`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140009bad`
- `ntoskrnl!IoCancelIrp` at `0x140009bef`
- `ntoskrnl!IoCancelIrp` at `0x140009bef`

## pseudocode

```c
void __fastcall CancelStatusIrp(__int64 *a1)
{
  __int64 v2; // rcx
  IRP *v3; // rbx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  v2 = *a1;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( *(_BYTE *)(v2 + 985) )
  {
    v3 = 0;
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v2 + 1136), &LockHandle);
    if ( *((_DWORD *)a1 + 4) == 2 )
    {
      v3 = (IRP *)a1[16];
      *((_BYTE *)a1 + 202) = 1;
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  else
  {
    v3 = (IRP *)a1[16];
  }
  if ( v3 )
    IoCancelIrp(v3);
}

```

## disassembly

```asm
0x140009b78  mov     [rsp+arg_0], rbx
0x140009b7d  push    rdi
0x140009b7e  sub     rsp, 40h
0x140009b82  xor     eax, eax
0x140009b84  mov     rdi, rcx
0x140009b87  mov     rcx, [rcx]
0x140009b8a  xorps   xmm0, xmm0
0x140009b8d  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x140009b92  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x140009b97  cmp     [rcx+3D9h], al
0x140009b9d  jz      short loc_140009BE0
0x140009b9f  add     rcx, 470h; SpinLock
0x140009ba6  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x140009bab  xor     ebx, ebx
0x140009bad  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140009bb4  nop     dword ptr [rax+rax+00h]
0x140009bb9  cmp     dword ptr [rdi+10h], 2
0x140009bbd  jnz     short loc_140009BCD
0x140009bbf  mov     rbx, [rdi+80h]
0x140009bc6  mov     byte ptr [rdi+0CAh], 1
0x140009bcd  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x140009bd2  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140009bd9  nop     dword ptr [rax+rax+00h]
0x140009bde  jmp     short loc_140009BE7
0x140009be0  mov     rbx, [rdi+80h]
0x140009be7  test    rbx, rbx
0x140009bea  jz      short loc_140009BFB
0x140009bec  mov     rcx, rbx; Irp
0x140009bef  call    cs:__imp_IoCancelIrp
0x140009bf6  nop     dword ptr [rax+rax+00h]
0x140009bfb  mov     rbx, [rsp+48h+arg_0]
0x140009c00  add     rsp, 40h
0x140009c04  pop     rdi
0x140009c05  retn
```
