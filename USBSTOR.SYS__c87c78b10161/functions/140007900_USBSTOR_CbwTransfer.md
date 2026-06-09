# USBSTOR_CbwTransfer

- ea: `0x140007900`
- end: `0x140007fde`
- name: `USBSTOR_CbwTransfer`
- size: `1758`
- prototype: `__int64 __fastcall(PVOID Object, PIRP Irp)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003e10`
- `0x140006ff0`

## callees

- `0x140001008`
- `0x140003630`
- `0x140007900`
- `0x1400105e8`
- `0x140010664`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140007ccf`
- `ntoskrnl!IofCallDriver` at `0x140007ccf`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140007961`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400079f5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140007a84`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140007b83`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140007c88`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140007d1f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140007dc0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140007961`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400079f5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140007a84`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140007b83`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140007c88`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140007d1f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140007dc0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400079be`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140007a0c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140007ae5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140007be4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140007cbc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140007d7c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140007e1d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400079be`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140007a0c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140007ae5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140007be4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140007cbc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140007d7c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140007e1d`

## pseudocode

```c
__int64 __fastcall USBSTOR_CbwTransfer(_QWORD *Object, PIRP Irp)
{
  __int64 v4; // rax
  __int64 v5; // rsi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  PDEVICE_OBJECT DeviceObject; // r14
  PIO_SECURITY_CONTEXT SecurityContext; // r13
  int v9; // r12d
  _BYTE *DeviceExtension; // rax
  unsigned __int8 SecurityQos_high; // r15
  __int64 result; // rax
  __int64 v13; // rax
  __int64 v14; // r14
  char v15; // al
  __int64 v16; // rax
  __int64 v17; // r13
  __int64 v18; // r15
  __int64 v19; // rax
  __int64 v20; // rsi
  PUNICODE_STRING FileName; // rax
  struct _IO_STACK_LOCATION *v22; // rax
  struct _IO_STACK_LOCATION *v23; // rax
  int v24; // eax
  bool v25; // r14
  __int64 v26; // rsi
  __int64 v27; // rax
  __int64 v28; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-30h] BYREF
  struct _KLOCK_QUEUE_HANDLE v30; // [rsp+38h] [rbp-18h] BYREF
  PUNICODE_STRING Context; // [rsp+80h] [rbp+30h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x90u,
      (__int64)WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( P )
  {
    KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
    *(_DWORD *)qword_14001A190 = 1463960393;
    *(_QWORD *)(qword_14001A190 + 8) = Object;
    *(_QWORD *)(qword_14001A190 + 16) = Irp;
    *(_QWORD *)(qword_14001A190 + 24) = 0;
    if ( qword_14001A190 <= (unsigned __int64)P )
      v4 = qword_14001A198 - 32;
    else
      v4 = qword_14001A190 - 32;
    qword_14001A190 = v4;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  v5 = Object[8];
  LockHandle.LockQueue = 0;
  *(_DWORD *)(v5 + 1712) = 0;
  *(_QWORD *)&LockHandle.OldIrql = 0;
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v5 + 144), &LockHandle);
  *(_DWORD *)(v5 + 128) |= 0x20u;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  DeviceObject = CurrentStackLocation->DeviceObject;
  SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
  v9 = *(_BYTE *)(v5 + 1876) != 0 ? 0x10 : 0;
  DeviceExtension = DeviceObject->DeviceExtension;
  if ( *(_DWORD *)DeviceExtension == 558842960 )
  {
    SecurityQos_high = DeviceExtension[71];
    result = 0;
  }
  else if ( *(_DWORD *)DeviceExtension == 558842950 )
  {
    SecurityQos_high = HIBYTE(SecurityContext->SecurityQos);
    result = 0;
  }
  else
  {
    SecurityQos_high = 0;
    result = 3221225659LL;
  }
  if ( *(_QWORD *)(v5 + 104) )
  {
    if ( (int)result >= 0 )
    {
      memset(&LockHandle, 0, sizeof(LockHandle));
      if ( P )
      {
        KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
        *(_DWORD *)qword_14001A190 = 1818387305;
        *(_QWORD *)(qword_14001A190 + 8) = Object;
        *(_QWORD *)(qword_14001A190 + 16) = DeviceObject;
        *(_QWORD *)(qword_14001A190 + 24) = SecurityQos_high;
        if ( qword_14001A190 <= (unsigned __int64)P )
          v13 = qword_14001A198 - 32;
        else
          v13 = qword_14001A190 - 32;
        qword_14001A190 = v13;
        KeReleaseInStackQueuedSpinLock(&LockHandle);
      }
      v14 = v5 + 1192;
      *(_DWORD *)(v5 + 1192) = 1128420181;
      *(_DWORD *)(v5 + 1196) = (_DWORD)Irp;
      *(_DWORD *)(v5 + 1200) = SecurityContext->DesiredAccess;
      v15 = BYTE4(SecurityContext->AccessState);
      *(_BYTE *)(v5 + 1205) = SecurityQos_high;
      *(_BYTE *)(v5 + 1204) = 2 * (v15 & 0xC0);
      *(_BYTE *)(v5 + 1206) = BYTE2(SecurityContext->AccessState);
      *(_OWORD *)(v5 + 1207) = *(_OWORD *)&SecurityContext[3].SecurityQos;
      v16 = *(_QWORD *)(v5 + 104);
      v17 = *(_QWORD *)(v5 + 1704);
      memset(&v30, 0, sizeof(v30));
      v18 = *(_QWORD *)(v16 + 8);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x58u,
          (__int64)WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
      }
      memset(&LockHandle, 0, sizeof(LockHandle));
      if ( P )
      {
        KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
        *(_DWORD *)qword_14001A190 = 1380532809;
        *(_QWORD *)(qword_14001A190 + 8) = Object;
        *(_QWORD *)(qword_14001A190 + 16) = Irp;
        *(_QWORD *)(qword_14001A190 + 24) = 0;
        if ( qword_14001A190 <= (unsigned __int64)P )
          v19 = qword_14001A198 - 32;
        else
          v19 = qword_14001A190 - 32;
        qword_14001A190 = v19;
        KeReleaseInStackQueuedSpinLock(&LockHandle);
      }
      v20 = Object[8];
      FileName = Irp->Tail.Overlay.CurrentStackLocation->Parameters.QueryDirectory.FileName;
      *(_OWORD *)(v20 + 392) = 0;
      Context = FileName;
      *(_OWORD *)(v20 + 408) = 0;
      *(_OWORD *)(v20 + 424) = 0;
      *(_OWORD *)(v20 + 440) = 0;
      *(_OWORD *)(v20 + 456) = 0;
      *(_OWORD *)(v20 + 472) = 0;
      *(_OWORD *)(v20 + 488) = 0;
      *(_OWORD *)(v20 + 504) = 0;
      *(_DWORD *)(v20 + 392) = 589952;
      *(_QWORD *)(v20 + 416) = v18;
      *(_DWORD *)(v20 + 424) = v9;
      *(_DWORD *)(v20 + 428) = 31;
      *(_QWORD *)(v20 + 432) = v14;
      *(_QWORD *)(v20 + 440) = v17;
      v22 = Irp->Tail.Overlay.CurrentStackLocation;
      v22[-1].Parameters.WMI.ProviderId = v20 + 392;
      v22[-1].MajorFunction = 15;
      v22[-1].Parameters.Read.ByteOffset.LowPart = 2228227;
      v23 = Irp->Tail.Overlay.CurrentStackLocation;
      v23[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)USBSTOR_CbwCompletion;
      v23[-1].Context = 0;
      v23[-1].Control = -32;
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v20 + 144), &v30);
      v24 = *(_DWORD *)(v20 + 128) | 2;
      *(_QWORD *)(v20 + 328) = Irp;
      v25 = (v24 & 0x40) != 0 && (v24 & 8) == 0;
      *(_DWORD *)(v20 + 128) = v24 & 0xFFFFFFBF;
      KeReleaseInStackQueuedSpinLock(&v30);
      v26 = IofCallDriver(*(PDEVICE_OBJECT *)(v20 + 24), Irp);
      if ( v25 )
      {
        USBSTOR_LogEntry(1330923842, (__int64)Object, (__int64)Irp, (__int64)Context);
        USBSTOR_QueueResetDevice(Object, Context);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_d(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x59u,
          (__int64)WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids,
          v26);
      }
      memset(&LockHandle, 0, sizeof(LockHandle));
      if ( P )
      {
        KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
        *(_DWORD *)qword_14001A190 = 1919509097;
        *(_QWORD *)(qword_14001A190 + 8) = Object;
        *(_QWORD *)(qword_14001A190 + 16) = Irp;
        *(_QWORD *)(qword_14001A190 + 24) = v26;
        if ( qword_14001A190 <= (unsigned __int64)P )
          v27 = qword_14001A198 - 32;
        else
          v27 = qword_14001A190 - 32;
        qword_14001A190 = v27;
        KeReleaseInStackQueuedSpinLock(&LockHandle);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_d(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x92u,
          (__int64)WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids,
          v26);
      }
      memset(&v30, 0, sizeof(v30));
      if ( P )
      {
        KeAcquireInStackQueuedSpinLock(&SpinLock, &v30);
        *(_DWORD *)qword_14001A190 = 2002936681;
        *(_QWORD *)(qword_14001A190 + 8) = Object;
        *(_QWORD *)(qword_14001A190 + 16) = Irp;
        *(_QWORD *)(qword_14001A190 + 24) = v26;
        if ( qword_14001A190 <= (unsigned __int64)P )
          v28 = qword_14001A198 - 32;
        else
          v28 = qword_14001A190 - 32;
        qword_14001A190 = v28;
        KeReleaseInStackQueuedSpinLock(&v30);
      }
      return (unsigned int)v26;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x91u,
        (__int64)WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
    }
    return 3221225858LL;
  }
  return result;
}

```

## disassembly

```asm
0x140007900  mov     [rsp-28h+arg_10], rbx
0x140007905  mov     [rsp-28h+arg_18], rsi
0x14000790a  push    rbp
0x14000790b  push    rdi
0x14000790c  push    r12
0x14000790e  push    r13
0x140007910  push    r14
0x140007912  mov     rbp, rsp
0x140007915  sub     rsp, 50h
0x140007919  mov     rbx, rdx
0x14000791c  mov     rdi, rcx
0x14000791f  mov     rcx, cs:WPP_GLOBAL_Control
0x140007926  lea     rax, WPP_GLOBAL_Control
0x14000792d  cmp     rcx, rax
0x140007930  jz      short loc_14000793D
0x140007932  mov     eax, [rcx+2Ch]
0x140007935  test    al, 1
0x140007937  jnz     loc_140007EFE
0x14000793d  xor     eax, eax
0x14000793f  xor     r14d, r14d
0x140007942  cmp     cs:P, rax
0x140007949  xorps   xmm0, xmm0
0x14000794c  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140007950  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140007954  jz      short loc_1400079CA
0x140007956  lea     rdx, [rbp+LockHandle]; LockHandle
0x14000795a  lea     rcx, SpinLock; SpinLock
0x140007961  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140007968  nop     dword ptr [rax+rax+00h]
0x14000796d  mov     rax, cs:qword_14001A190
0x140007974  mov     dword ptr [rax], 57424349h
0x14000797a  mov     rax, cs:qword_14001A190
0x140007981  mov     [rax+8], rdi
0x140007985  mov     rax, cs:qword_14001A190
0x14000798c  mov     [rax+10h], rbx
0x140007990  mov     rax, cs:qword_14001A190
0x140007997  mov     [rax+18h], r14
0x14000799b  mov     rax, cs:qword_14001A190
0x1400079a2  cmp     rax, cs:P
0x1400079a9  jbe     loc_140007EAE
0x1400079af  sub     rax, 20h ; ' '
0x1400079b3  lea     rcx, [rbp+LockHandle]; LockHandle
0x1400079b7  mov     cs:qword_14001A190, rax
0x1400079be  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400079c5  nop     dword ptr [rax+rax+00h]
0x1400079ca  mov     rsi, [rdi+40h]
0x1400079ce  lea     rdx, [rbp+LockHandle]; LockHandle
0x1400079d2  xorps   xmm0, xmm0
0x1400079d5  mov     [rsp+50h+arg_8], r15
0x1400079dd  xor     eax, eax
0x1400079df  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x1400079e3  lea     rcx, [rsi+90h]; SpinLock
0x1400079ea  mov     [rsi+6B0h], r14d
0x1400079f1  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x1400079f5  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400079fc  nop     dword ptr [rax+rax+00h]
0x140007a01  or      dword ptr [rsi+80h], 20h
0x140007a08  lea     rcx, [rbp+LockHandle]; LockHandle
0x140007a0c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140007a13  nop     dword ptr [rax+rax+00h]
0x140007a18  mov     rcx, [rbx+0B8h]
0x140007a1f  movzx   eax, byte ptr [rsi+754h]
0x140007a26  neg     al
0x140007a28  mov     r14, [rcx+28h]
0x140007a2c  sbb     r12d, r12d
0x140007a2f  mov     r13, [rcx+8]
0x140007a33  and     r12d, 10h
0x140007a37  mov     rax, [r14+40h]
0x140007a3b  mov     ecx, [rax]
0x140007a3d  cmp     ecx, 214F4450h
0x140007a43  jnz     loc_140007F22
0x140007a49  movzx   r15d, byte ptr [rax+47h]
0x140007a4e  xor     eax, eax
0x140007a50  cmp     qword ptr [rsi+68h], 0
0x140007a55  jz      loc_140007F43
0x140007a5b  test    eax, eax
0x140007a5d  js      loc_140007E2B
0x140007a63  xor     eax, eax
0x140007a65  xorps   xmm0, xmm0
0x140007a68  cmp     cs:P, rax
0x140007a6f  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140007a73  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140007a77  jz      short loc_140007AF1
0x140007a79  lea     rdx, [rbp+LockHandle]; LockHandle
0x140007a7d  lea     rcx, SpinLock; SpinLock
0x140007a84  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140007a8b  nop     dword ptr [rax+rax+00h]
0x140007a90  mov     rax, cs:qword_14001A190
0x140007a97  movzx   ecx, r15b
0x140007a9b  mov     dword ptr [rax], 6C626369h
0x140007aa1  mov     rax, cs:qword_14001A190
0x140007aa8  mov     [rax+8], rdi
0x140007aac  mov     rax, cs:qword_14001A190
0x140007ab3  mov     [rax+10h], r14
0x140007ab7  mov     rax, cs:qword_14001A190
0x140007abe  mov     [rax+18h], rcx
0x140007ac2  mov     rax, cs:qword_14001A190
0x140007ac9  cmp     rax, cs:P
0x140007ad0  jbe     loc_140007EBE
0x140007ad6  sub     rax, 20h ; ' '
0x140007ada  lea     rcx, [rbp+LockHandle]; LockHandle
0x140007ade  mov     cs:qword_14001A190, rax
0x140007ae5  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140007aec  nop     dword ptr [rax+rax+00h]
0x140007af1  lea     r14, [rsi+4A8h]
0x140007af8  mov     dword ptr [r14], 43425355h
0x140007aff  mov     [r14+4], ebx
0x140007b03  mov     eax, [r13+10h]
0x140007b07  mov     [r14+8], eax
0x140007b0b  movzx   eax, byte ptr [r13+0Ch]
0x140007b10  mov     [r14+0Dh], r15b
0x140007b14  and     al, 0C0h
0x140007b16  add     al, al
0x140007b18  mov     [r14+0Ch], al
0x140007b1c  movzx   eax, byte ptr [r13+0Ah]
0x140007b21  mov     [r14+0Eh], al
0x140007b25  movups  xmm0, xmmword ptr [r13+48h]
0x140007b2a  movups  xmmword ptr [r14+0Fh], xmm0
0x140007b2f  mov     rax, [rsi+68h]
0x140007b33  mov     r13, [rsi+6A8h]
0x140007b3a  xorps   xmm0, xmm0
0x140007b3d  movups  xmmword ptr [rbp+var_18.LockQueue.Next], xmm0
0x140007b41  mov     r15, [rax+8]
0x140007b45  xor     eax, eax
0x140007b47  mov     qword ptr [rbp+var_18.OldIrql], rax
0x140007b4b  mov     rcx, cs:WPP_GLOBAL_Control
0x140007b52  lea     rax, WPP_GLOBAL_Control
0x140007b59  cmp     rcx, rax
0x140007b5c  jnz     loc_140007E7F
0x140007b62  xor     eax, eax
0x140007b64  xorps   xmm0, xmm0
0x140007b67  cmp     cs:P, rax
0x140007b6e  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140007b72  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140007b76  jz      short loc_140007BF0
0x140007b78  lea     rdx, [rbp+LockHandle]; LockHandle
0x140007b7c  lea     rcx, SpinLock; SpinLock
0x140007b83  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140007b8a  nop     dword ptr [rax+rax+00h]
0x140007b8f  mov     rax, cs:qword_14001A190
0x140007b96  mov     dword ptr [rax], 52494249h
0x140007b9c  mov     rax, cs:qword_14001A190
0x140007ba3  mov     [rax+8], rdi
0x140007ba7  mov     rax, cs:qword_14001A190
0x140007bae  mov     [rax+10h], rbx
0x140007bb2  mov     rax, cs:qword_14001A190
0x140007bb9  mov     qword ptr [rax+18h], 0
0x140007bc1  mov     rax, cs:qword_14001A190
0x140007bc8  cmp     rax, cs:P
0x140007bcf  jbe     loc_140007ECE
0x140007bd5  sub     rax, 20h ; ' '
0x140007bd9  lea     rcx, [rbp+LockHandle]; LockHandle
0x140007bdd  mov     cs:qword_14001A190, rax
0x140007be4  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140007beb  nop     dword ptr [rax+rax+00h]
0x140007bf0  mov     rsi, [rdi+40h]
0x140007bf4  lea     rdx, [rbp+var_18]; LockHandle
0x140007bf8  mov     rax, [rbx+0B8h]
0x140007bff  xorps   xmm0, xmm0
0x140007c02  lea     rcx, [rsi+188h]
0x140007c09  mov     rax, [rax+10h]
0x140007c0d  movups  xmmword ptr [rcx], xmm0
0x140007c10  mov     [rbp+Context], rax
0x140007c14  movups  xmmword ptr [rcx+10h], xmm0
0x140007c18  movups  xmmword ptr [rcx+20h], xmm0
0x140007c1c  movups  xmmword ptr [rcx+30h], xmm0
0x140007c20  movups  xmmword ptr [rcx+40h], xmm0
0x140007c24  movups  xmmword ptr [rcx+50h], xmm0
0x140007c28  movups  xmmword ptr [rcx+60h], xmm0
0x140007c2c  movups  xmmword ptr [rcx+70h], xmm0
0x140007c30  mov     dword ptr [rcx], 90080h
0x140007c36  mov     [rcx+18h], r15
0x140007c3a  mov     [rcx+20h], r12d
0x140007c3e  mov     dword ptr [rcx+24h], 1Fh
0x140007c45  mov     [rcx+28h], r14
0x140007c49  mov     [rcx+30h], r13
0x140007c4d  mov     rax, [rbx+0B8h]
0x140007c54  mov     [rax-40h], rcx
0x140007c58  lea     rcx, USBSTOR_CbwCompletion
0x140007c5f  mov     byte ptr [rax-48h], 0Fh
0x140007c63  mov     dword ptr [rax-30h], 220003h
0x140007c6a  mov     rax, [rbx+0B8h]
0x140007c71  mov     [rax-10h], rcx
0x140007c75  lea     rcx, [rsi+90h]; SpinLock
0x140007c7c  mov     qword ptr [rax-8], 0
0x140007c84  mov     byte ptr [rax-45h], 0E0h
0x140007c88  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140007c8f  nop     dword ptr [rax+rax+00h]
0x140007c94  mov     eax, [rsi+80h]
0x140007c9a  or      eax, 2
0x140007c9d  mov     [rsi+148h], rbx
0x140007ca4  test    al, 40h
0x140007ca6  jnz     loc_140007F82
0x140007cac  xor     r14b, r14b
0x140007caf  and     eax, 0FFFFFFBFh
0x140007cb2  lea     rcx, [rbp+var_18]; LockHandle
0x140007cb6  mov     [rsi+80h], eax
0x140007cbc  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140007cc3  nop     dword ptr [rax+rax+00h]
0x140007cc8  mov     rcx, [rsi+18h]; DeviceObject
0x140007ccc  mov     rdx, rbx; Irp
0x140007ccf  call    cs:__imp_IofCallDriver
0x140007cd6  nop     dword ptr [rax+rax+00h]
0x140007cdb  movsxd  rsi, eax
0x140007cde  test    r14b, r14b
0x140007ce1  jnz     loc_140007F92
0x140007ce7  mov     rcx, cs:WPP_GLOBAL_Control
0x140007cee  lea     r14, WPP_GLOBAL_Control
0x140007cf5  cmp     rcx, r14
0x140007cf8  jnz     loc_140007E4D
0x140007cfe  xor     eax, eax
0x140007d00  xorps   xmm0, xmm0
0x140007d03  cmp     cs:P, rax
0x140007d0a  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140007d0e  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140007d12  jz      short loc_140007D88
0x140007d14  lea     rdx, [rbp+LockHandle]; LockHandle
0x140007d18  lea     rcx, SpinLock; SpinLock
0x140007d1f  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140007d26  nop     dword ptr [rax+rax+00h]
0x140007d2b  mov     rax, cs:qword_14001A190
0x140007d32  mov     dword ptr [rax], 72696269h
0x140007d38  mov     rax, cs:qword_14001A190
0x140007d3f  mov     [rax+8], rdi
0x140007d43  mov     rax, cs:qword_14001A190
0x140007d4a  mov     [rax+10h], rbx
0x140007d4e  mov     rax, cs:qword_14001A190
0x140007d55  mov     [rax+18h], rsi
0x140007d59  mov     rax, cs:qword_14001A190
0x140007d60  cmp     rax, cs:P
0x140007d67  jbe     loc_140007EDE
0x140007d6d  sub     rax, 20h ; ' '
0x140007d71  lea     rcx, [rbp+LockHandle]; LockHandle
0x140007d75  mov     cs:qword_14001A190, rax
0x140007d7c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140007d83  nop     dword ptr [rax+rax+00h]
0x140007d88  mov     rcx, cs:WPP_GLOBAL_Control
0x140007d8f  cmp     rcx, r14
0x140007d92  jz      short loc_140007D9F
0x140007d94  mov     eax, [rcx+2Ch]
0x140007d97  test    al, 1
0x140007d99  jnz     loc_140007FB7
0x140007d9f  xor     eax, eax
0x140007da1  xorps   xmm0, xmm0
0x140007da4  cmp     cs:P, rax
0x140007dab  movups  xmmword ptr [rbp+var_18.LockQueue.Next], xmm0
0x140007daf  mov     qword ptr [rbp+var_18.OldIrql], rax
0x140007db3  jz      short loc_140007E29
0x140007db5  lea     rdx, [rbp+var_18]; LockHandle
0x140007db9  lea     rcx, SpinLock; SpinLock
0x140007dc0  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140007dc7  nop     dword ptr [rax+rax+00h]
0x140007dcc  mov     rax, cs:qword_14001A190
0x140007dd3  mov     dword ptr [rax], 77626369h
0x140007dd9  mov     rax, cs:qword_14001A190
0x140007de0  mov     [rax+8], rdi
0x140007de4  mov     rax, cs:qword_14001A190
0x140007deb  mov     [rax+10h], rbx
0x140007def  mov     rax, cs:qword_14001A190
0x140007df6  mov     [rax+18h], rsi
0x140007dfa  mov     rax, cs:qword_14001A190
0x140007e01  cmp     rax, cs:P
0x140007e08  jbe     loc_140007EEE
0x140007e0e  sub     rax, 20h ; ' '
0x140007e12  lea     rcx, [rbp+var_18]; LockHandle
0x140007e16  mov     cs:qword_14001A190, rax
0x140007e1d  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140007e24  nop     dword ptr [rax+rax+00h]
0x140007e29  mov     eax, esi
0x140007e2b  mov     r15, [rsp+50h+arg_8]
0x140007e33  lea     r11, [rsp+50h+var_s0]
0x140007e38  mov     rbx, [r11+40h]
0x140007e3c  mov     rsi, [r11+48h]
0x140007e40  mov     rsp, r11
0x140007e43  pop     r14
0x140007e45  pop     r13
0x140007e47  pop     r12
0x140007e49  pop     rdi
0x140007e4a  pop     rbp
0x140007e4b  retn
0x140007e4d  mov     eax, [rcx+2Ch]
0x140007e50  test    al, 1
0x140007e52  jz      loc_140007CFE
0x140007e58  cmp     byte ptr [rcx+29h], 5
0x140007e5c  jb      loc_140007CFE
0x140007e62  mov     rcx, [rcx+18h]
0x140007e66  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140007e6d  mov     edx, 59h ; 'Y'
0x140007e72  mov     r9d, esi
0x140007e75  call    WPP_SF_d
0x140007e7a  jmp     loc_140007CFE
0x140007e7f  mov     eax, [rcx+2Ch]
0x140007e82  test    al, 1
0x140007e84  jz      loc_140007B62
0x140007e8a  cmp     byte ptr [rcx+29h], 5
0x140007e8e  jb      loc_140007B62
0x140007e94  mov     rcx, [rcx+18h]
0x140007e98  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140007e9f  mov     edx, 58h ; 'X'
0x140007ea4  call    WPP_SF_
  ... truncated ...
```
