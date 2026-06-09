# UsbStorPumpNextRequest

- ea: `0x140003b90`
- end: `0x140003e01`
- name: `UsbStorPumpNextRequest`
- size: `625`
- prototype: ``
- caller_count: `11`
- callee_count: `4`
- tags: ``

## callers

- `0x140003e10`
- `0x140004ed0`
- `0x140006ff0`
- `0x1400090e0`
- `0x1400094b0`
- `0x140009860`
- `0x14000b2e8`
- `0x14000f640`
- `0x14000fafc`
- `0x140011900`
- `0x140012730`

## callees

- `0x1400036f0`
- `0x140003b90`
- `0x140010664`
- `0x140012a84`

## import_xrefs

- `ntoskrnl!IoStartPacket` at `0x140003cac`
- `ntoskrnl!IoStartPacket` at `0x140003cac`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003c20`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003d07`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003c20`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003d07`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003c7e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003d65`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003c7e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003d65`

## pseudocode

```c
IRP *__fastcall UsbStorPumpNextRequest(__int64 a1)
{
  IRP *v1; // rbx
  __int64 v3; // rsi
  __int64 *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rbp
  __int64 v8; // rax
  __int64 v10; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  v1 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0xC7u,
      (__int64)WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  if ( a1 )
  {
    v3 = a1 + 368;
    v4 = UsbQueueRemove(a1 + 368);
    v1 = (IRP *)v4;
    LockHandle.LockQueue = 0;
    if ( v4 )
    {
      v7 = *(_QWORD *)(v4[23] + 8);
      *(_QWORD *)&LockHandle.OldIrql = 0;
      if ( P )
      {
        KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
        *(_DWORD *)qword_14001A190 = 1886221648;
        *(_QWORD *)(qword_14001A190 + 8) = a1;
        *(_QWORD *)(qword_14001A190 + 16) = v3;
        *(_QWORD *)(qword_14001A190 + 24) = v1;
        if ( qword_14001A190 <= (unsigned __int64)P )
          v8 = qword_14001A198 - 32;
        else
          v8 = qword_14001A190 - 32;
        qword_14001A190 = v8;
        KeReleaseInStackQueuedSpinLock(&LockHandle);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_i(
          WPP_GLOBAL_Control->AttachedDevice,
          v5,
          v6,
          v1,
          LockHandle.LockQueue.Next,
          LockHandle.LockQueue.Lock,
          *(_QWORD *)&LockHandle.OldIrql);
      }
      IoStartPacket(*(PDEVICE_OBJECT *)(a1 + 16), v1, (PULONG)(v7 + 64), (PDRIVER_CANCEL)USBSTOR_CancelIo);
    }
    else
    {
      *(_QWORD *)&LockHandle.OldIrql = 0;
      if ( P )
      {
        KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
        *(_DWORD *)qword_14001A190 = 829451600;
        *(_QWORD *)(qword_14001A190 + 8) = a1;
        *(_QWORD *)(qword_14001A190 + 16) = v3;
        *(_QWORD *)(qword_14001A190 + 24) = 0;
        if ( qword_14001A190 <= (unsigned __int64)P )
          v10 = qword_14001A198 - 32;
        else
          v10 = qword_14001A190 - 32;
        qword_14001A190 = v10;
        KeReleaseInStackQueuedSpinLock(&LockHandle);
      }
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0xC9u,
      (__int64)WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  return v1;
}

```

## disassembly

```asm
0x140003b90  push    rbx
0x140003b92  sub     rsp, 40h
0x140003b96  mov     [rsp+48h+arg_10], rdi
0x140003b9b  xor     ebx, ebx
0x140003b9d  mov     [rsp+48h+arg_18], r14
0x140003ba2  mov     rdi, rcx
0x140003ba5  mov     rcx, cs:WPP_GLOBAL_Control
0x140003bac  lea     r14, WPP_GLOBAL_Control
0x140003bb3  cmp     rcx, r14
0x140003bb6  jz      short loc_140003BC3
0x140003bb8  mov     eax, [rcx+2Ch]
0x140003bbb  test    al, 1
0x140003bbd  jnz     loc_140003DB9
0x140003bc3  test    rdi, rdi
0x140003bc6  jz      loc_140003CC2
0x140003bcc  mov     [rsp+48h+arg_8], rsi
0x140003bd1  lea     rsi, [rdi+170h]
0x140003bd8  mov     rcx, rsi
0x140003bdb  call    UsbQueueRemove
0x140003be0  xorps   xmm0, xmm0
0x140003be3  mov     rbx, rax
0x140003be6  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x140003beb  test    rax, rax
0x140003bee  jz      loc_140003CED
0x140003bf4  mov     rax, [rax+0B8h]
0x140003bfb  mov     [rsp+48h+arg_0], rbp
0x140003c00  mov     rbp, [rax+8]
0x140003c04  xor     eax, eax
0x140003c06  cmp     cs:P, rax
0x140003c0d  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x140003c12  jz      short loc_140003C8A
0x140003c14  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x140003c19  lea     rcx, SpinLock; SpinLock
0x140003c20  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140003c27  nop     dword ptr [rax+rax+00h]
0x140003c2c  mov     rax, cs:qword_14001A190
0x140003c33  mov     dword ptr [rax], 706D7550h
0x140003c39  mov     rax, cs:qword_14001A190
0x140003c40  mov     [rax+8], rdi
0x140003c44  mov     rax, cs:qword_14001A190
0x140003c4b  mov     [rax+10h], rsi
0x140003c4f  mov     rax, cs:qword_14001A190
0x140003c56  mov     [rax+18h], rbx
0x140003c5a  mov     rax, cs:qword_14001A190
0x140003c61  cmp     rax, cs:P
0x140003c68  jbe     loc_140003D9C
0x140003c6e  sub     rax, 20h ; ' '
0x140003c72  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x140003c77  mov     cs:qword_14001A190, rax
0x140003c7e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140003c85  nop     dword ptr [rax+rax+00h]
0x140003c8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140003c91  cmp     rcx, r14
0x140003c94  jnz     loc_140003D76
0x140003c9a  mov     rcx, [rdi+10h]; DeviceObject
0x140003c9e  lea     r8, [rbp+40h]; Key
0x140003ca2  lea     r9, USBSTOR_CancelIo; CancelFunction
0x140003ca9  mov     rdx, rbx; Irp
0x140003cac  call    cs:__imp_IoStartPacket
0x140003cb3  nop     dword ptr [rax+rax+00h]
0x140003cb8  mov     rbp, [rsp+48h+arg_0]
0x140003cbd  mov     rsi, [rsp+48h+arg_8]
0x140003cc2  mov     rcx, cs:WPP_GLOBAL_Control
0x140003cc9  mov     rdi, [rsp+48h+arg_10]
0x140003cce  cmp     rcx, r14
0x140003cd1  mov     r14, [rsp+48h+arg_18]
0x140003cd6  jz      short loc_140003CE3
0x140003cd8  mov     eax, [rcx+2Ch]
0x140003cdb  test    al, 1
0x140003cdd  jnz     loc_140003DDD
0x140003ce3  mov     rax, rbx
0x140003ce6  add     rsp, 40h
0x140003cea  pop     rbx
0x140003ceb  retn
0x140003ced  cmp     cs:P, rax
0x140003cf4  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x140003cf9  jz      short loc_140003CBD
0x140003cfb  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x140003d00  lea     rcx, SpinLock; SpinLock
0x140003d07  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140003d0e  nop     dword ptr [rax+rax+00h]
0x140003d13  mov     rax, cs:qword_14001A190
0x140003d1a  mov     dword ptr [rax], 31706D50h
0x140003d20  mov     rax, cs:qword_14001A190
0x140003d27  mov     [rax+8], rdi
0x140003d2b  mov     rax, cs:qword_14001A190
0x140003d32  mov     [rax+10h], rsi
0x140003d36  mov     rax, cs:qword_14001A190
0x140003d3d  mov     qword ptr [rax+18h], 0
0x140003d45  mov     rax, cs:qword_14001A190
0x140003d4c  cmp     rax, cs:P
0x140003d53  jbe     short loc_140003DAC
0x140003d55  sub     rax, 20h ; ' '
0x140003d59  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x140003d5e  mov     cs:qword_14001A190, rax
0x140003d65  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140003d6c  nop     dword ptr [rax+rax+00h]
0x140003d71  jmp     loc_140003CBD
0x140003d76  mov     eax, [rcx+2Ch]
0x140003d79  test    al, 1
0x140003d7b  jz      loc_140003C9A
0x140003d81  cmp     byte ptr [rcx+29h], 5
0x140003d85  jb      loc_140003C9A
0x140003d8b  mov     rcx, [rcx+18h]
0x140003d8f  mov     r9, rbx
0x140003d92  call    WPP_SF_i
0x140003d97  jmp     loc_140003C9A
0x140003d9c  mov     rax, cs:qword_14001A198
0x140003da3  add     rax, 0FFFFFFFFFFFFFFE0h
0x140003da7  jmp     loc_140003C72
0x140003dac  mov     rax, cs:qword_14001A198
0x140003db3  add     rax, 0FFFFFFFFFFFFFFE0h
0x140003db7  jmp     short loc_140003D59
0x140003db9  cmp     byte ptr [rcx+29h], 5
0x140003dbd  jb      loc_140003BC3
0x140003dc3  mov     rcx, [rcx+18h]
0x140003dc7  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140003dce  mov     edx, 0C7h
0x140003dd3  call    WPP_SF_
0x140003dd8  jmp     loc_140003BC3
0x140003ddd  cmp     byte ptr [rcx+29h], 5
0x140003de1  jb      loc_140003CE3
0x140003de7  mov     rcx, [rcx+18h]
0x140003deb  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140003df2  mov     edx, 0C9h
0x140003df7  call    WPP_SF_
0x140003dfc  jmp     loc_140003CE3
```
