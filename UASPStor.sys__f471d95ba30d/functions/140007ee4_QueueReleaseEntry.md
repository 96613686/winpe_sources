# QueueReleaseEntry

- ea: `0x140007ee4`
- end: `0x140007f71`
- name: `QueueReleaseEntry`
- size: `141`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140007f80`
- `0x1400081dc`
- `0x140008348`
- `0x140009c10`
- `0x14000be7c`

## callees

- `0x140007ee4`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140007f59`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140007f59`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140007f0f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140007f0f`

## pseudocode

```c
void __fastcall QueueReleaseEntry(__int64 *a1)
{
  __int64 v1; // rdi
  unsigned __int16 v3; // ax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  v1 = *a1;
  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v1 + 1240), &LockHandle);
  *(_DWORD *)(*(_QWORD *)(v1 + 1224) + 4LL * *((unsigned __int16 *)a1 + 20)) = 1;
  --*(_DWORD *)(v1 + 1388);
  v3 = *((_WORD *)a1 + 20);
  if ( v3 < *(_WORD *)(v1 + 1232) && (*(_QWORD *)(v1 + 104) || v3) )
    *(_WORD *)(v1 + 1232) = v3;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
}

```

## disassembly

```asm
0x140007ee4  mov     [rsp+arg_0], rbx
0x140007ee9  push    rdi
0x140007eea  sub     rsp, 40h
0x140007eee  mov     rdi, [rcx]
0x140007ef1  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x140007ef6  mov     rbx, rcx
0x140007ef9  xorps   xmm0, xmm0
0x140007efc  xor     eax, eax
0x140007efe  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x140007f03  lea     rcx, [rdi+4D8h]; SpinLock
0x140007f0a  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x140007f0f  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140007f16  nop     dword ptr [rax+rax+00h]
0x140007f1b  movzx   edx, word ptr [rbx+28h]
0x140007f1f  mov     rax, [rdi+4C8h]
0x140007f26  mov     dword ptr [rax+rdx*4], 1
0x140007f2d  dec     dword ptr [rdi+56Ch]
0x140007f33  movzx   eax, word ptr [rbx+28h]
0x140007f37  cmp     ax, [rdi+4D0h]
0x140007f3e  jnb     short loc_140007F54
0x140007f40  xor     ecx, ecx
0x140007f42  cmp     [rdi+68h], rcx
0x140007f46  jnz     short loc_140007F4D
0x140007f48  test    ax, ax
0x140007f4b  jz      short loc_140007F54
0x140007f4d  mov     [rdi+4D0h], ax
0x140007f54  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x140007f59  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140007f60  nop     dword ptr [rax+rax+00h]
0x140007f65  mov     rbx, [rsp+48h+arg_0]
0x140007f6a  add     rsp, 40h
0x140007f6e  pop     rdi
0x140007f6f  retn
```
