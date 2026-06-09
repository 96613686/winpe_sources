# UsbStorStartNextPacket

- ea: `0x140007ff0`
- end: `0x140008115`
- name: `UsbStorStartNextPacket`
- size: `293`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x140003e10`
- `0x140004ed0`
- `0x140006ff0`
- `0x1400084c0`
- `0x1400090e0`
- `0x1400094b0`
- `0x140009860`
- `0x14000f640`
- `0x14000fafc`
- `0x140012730`

## callees

- `0x140007ff0`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000804e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000804e`
- `ntoskrnl!IoStartNextPacket` at `0x1400080bb`
- `ntoskrnl!IoStartNextPacket` at `0x1400080bb`
- `ntoskrnl!KeGetCurrentIrql` at `0x140008003`
- `ntoskrnl!KeGetCurrentIrql` at `0x140008003`
- `ntoskrnl!KeLowerIrql` at `0x1400080fa`
- `ntoskrnl!KeLowerIrql` at `0x1400080fa`
- `ntoskrnl!KfRaiseIrql` at `0x1400080df`
- `ntoskrnl!KfRaiseIrql` at `0x1400080df`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400080aa`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400080aa`

## pseudocode

```c
void __fastcall UsbStorStartNextPacket(PDEVICE_OBJECT DeviceObject)
{
  KIRQL v2; // si
  char v3; // di
  __int64 v4; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  if ( KeGetCurrentIrql() < 2u )
  {
    v2 = KfRaiseIrql(2u);
    v3 = 1;
  }
  else
  {
    v2 = 0;
    v3 = 0;
  }
  if ( DeviceObject->DeviceQueue.Busy )
  {
    memset(&LockHandle, 0, sizeof(LockHandle));
    if ( P )
    {
      KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
      *(_DWORD *)qword_14001A190 = 1347310409;
      *(_QWORD *)(qword_14001A190 + 8) = DeviceObject;
      *(_QWORD *)(qword_14001A190 + 16) = 0;
      *(_QWORD *)(qword_14001A190 + 24) = 0;
      if ( qword_14001A190 <= (unsigned __int64)P )
        v4 = qword_14001A198 - 32;
      else
        v4 = qword_14001A190 - 32;
      qword_14001A190 = v4;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
    IoStartNextPacket(DeviceObject, 1u);
  }
  if ( v3 )
    KeLowerIrql(v2);
}

```

## disassembly

```asm
0x140007ff0  push    rsi
0x140007ff2  sub     rsp, 40h
0x140007ff6  mov     [rsp+48h+arg_0], rbx
0x140007ffb  mov     rbx, rcx
0x140007ffe  mov     [rsp+48h+arg_8], rdi
0x140008003  call    cs:__imp_KeGetCurrentIrql
0x14000800a  nop     dword ptr [rax+rax+00h]
0x14000800f  cmp     al, 2
0x140008011  jb      loc_1400080DD
0x140008017  xor     sil, sil
0x14000801a  xor     dil, dil
0x14000801d  cmp     byte ptr [rbx+0C0h], 0
0x140008024  jz      loc_1400080C7
0x14000802a  xor     eax, eax
0x14000802c  xorps   xmm0, xmm0
0x14000802f  cmp     cs:P, rax
0x140008036  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x14000803b  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x140008040  jz      short loc_1400080B6
0x140008042  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x140008047  lea     rcx, SpinLock; SpinLock
0x14000804e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140008055  nop     dword ptr [rax+rax+00h]
0x14000805a  mov     rax, cs:qword_14001A190
0x140008061  xor     ecx, ecx
0x140008063  mov     dword ptr [rax], 504E5349h
0x140008069  mov     rax, cs:qword_14001A190
0x140008070  mov     [rax+8], rbx
0x140008074  mov     rax, cs:qword_14001A190
0x14000807b  mov     [rax+10h], rcx
0x14000807f  mov     rax, cs:qword_14001A190
0x140008086  mov     [rax+18h], rcx
0x14000808a  mov     rax, cs:qword_14001A190
0x140008091  cmp     rax, cs:P
0x140008098  jbe     short loc_140008108
0x14000809a  sub     rax, 20h ; ' '
0x14000809e  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x1400080a3  mov     cs:qword_14001A190, rax
0x1400080aa  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400080b1  nop     dword ptr [rax+rax+00h]
0x1400080b6  mov     dl, 1; Cancelable
0x1400080b8  mov     rcx, rbx; DeviceObject
0x1400080bb  call    cs:__imp_IoStartNextPacket
0x1400080c2  nop     dword ptr [rax+rax+00h]
0x1400080c7  mov     rbx, [rsp+48h+arg_0]
0x1400080cc  test    dil, dil
0x1400080cf  mov     rdi, [rsp+48h+arg_8]
0x1400080d4  jnz     short loc_1400080F6
0x1400080d6  add     rsp, 40h
0x1400080da  pop     rsi
0x1400080db  retn
0x1400080dd  mov     cl, 2; NewIrql
0x1400080df  call    cs:__imp_KfRaiseIrql
0x1400080e6  nop     dword ptr [rax+rax+00h]
0x1400080eb  movzx   esi, al
0x1400080ee  mov     dil, 1
0x1400080f1  jmp     loc_14000801D
0x1400080f6  movzx   ecx, sil; NewIrql
0x1400080fa  call    cs:__imp_KeLowerIrql
0x140008101  nop     dword ptr [rax+rax+00h]
0x140008106  jmp     short loc_1400080D6
0x140008108  mov     rax, cs:qword_14001A198
0x14000810f  add     rax, 0FFFFFFFFFFFFFFE0h
0x140008113  jmp     short loc_14000809E
```
