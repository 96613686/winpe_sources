# USBSTOR_CswTransfer

- ea: `0x140002a70`
- end: `0x140002fc0`
- name: `USBSTOR_CswTransfer`
- size: `1360`
- prototype: `__int64 __fastcall(PVOID Object, PIRP Irp)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140001510`
- `0x140001de0`
- `0x1400023b0`

## callees

- `0x140001008`
- `0x140002a70`
- `0x140003630`
- `0x1400105e8`
- `0x140010664`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140002d12`
- `ntoskrnl!IofCallDriver` at `0x140002d12`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002ac2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002bbc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002cca`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002d65`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002e03`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002ac2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002bbc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002cca`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002d65`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002e03`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002b24`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002c1e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002cff`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002dc3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002e61`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002b24`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002c1e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002cff`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002dc3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002e61`

## pseudocode

```c
__int64 __fastcall USBSTOR_CswTransfer(_QWORD *Object, PIRP Irp)
{
  __int64 v4; // rax
  __int64 v5; // r14
  int v6; // r15d
  int v7; // ecx
  __int16 *v8; // rax
  __int64 v9; // r13
  __int16 v10; // dx
  __int64 v11; // r12
  int v12; // ebp
  int v13; // ebp
  __int64 v14; // rax
  __int64 v15; // rsi
  PUNICODE_STRING FileName; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v18; // rax
  int v19; // eax
  bool v20; // bp
  __int64 v21; // rsi
  __int64 v22; // rax
  __int64 v23; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-78h] BYREF
  struct _KLOCK_QUEUE_HANDLE v26; // [rsp+38h] [rbp-60h] BYREF
  PUNICODE_STRING Context; // [rsp+A0h] [rbp+8h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x9Fu,
      (__int64)WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( P )
  {
    KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
    *(_DWORD *)qword_14001A190 = 1465074505;
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
  v6 = 512;
  v7 = 2;
  v26.LockQueue = 0;
  v8 = *(__int16 **)(v5 + 96);
  v9 = *(_QWORD *)(v5 + 1704);
  v10 = *v8;
  v11 = *((_QWORD *)v8 + 1);
  if ( *v8 != 512 )
    v6 = 13;
  v12 = *(_BYTE *)(v5 + 1876) != 0 ? 0x10 : 0;
  *(_QWORD *)&v26.OldIrql = 0;
  if ( v10 != 512 )
    v7 = 0;
  v13 = v7 | v12;
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
      v14 = qword_14001A198 - 32;
    else
      v14 = qword_14001A190 - 32;
    qword_14001A190 = v14;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  v15 = Object[8];
  FileName = Irp->Tail.Overlay.CurrentStackLocation->Parameters.QueryDirectory.FileName;
  *(_OWORD *)(v15 + 392) = 0;
  Context = FileName;
  *(_OWORD *)(v15 + 408) = 0;
  *(_OWORD *)(v15 + 424) = 0;
  *(_OWORD *)(v15 + 440) = 0;
  *(_OWORD *)(v15 + 456) = 0;
  *(_OWORD *)(v15 + 472) = 0;
  *(_OWORD *)(v15 + 488) = 0;
  *(_OWORD *)(v15 + 504) = 0;
  *(_DWORD *)(v15 + 392) = 589952;
  *(_QWORD *)(v15 + 416) = v11;
  *(_DWORD *)(v15 + 424) = v13;
  *(_DWORD *)(v15 + 428) = v6;
  *(_QWORD *)(v15 + 432) = v5 + 1192;
  *(_QWORD *)(v15 + 440) = v9;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].Parameters.WMI.ProviderId = v15 + 392;
  CurrentStackLocation[-1].MajorFunction = 15;
  CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 2228227;
  v18 = Irp->Tail.Overlay.CurrentStackLocation;
  v18[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)USBSTOR_CswCompletion;
  v18[-1].Context = 0;
  v18[-1].Control = -32;
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v15 + 144), &v26);
  v19 = *(_DWORD *)(v15 + 128) | 2;
  *(_QWORD *)(v15 + 328) = Irp;
  v20 = (v19 & 0x40) != 0 && (v19 & 8) == 0;
  *(_DWORD *)(v15 + 128) = v19 & 0xFFFFFFBF;
  KeReleaseInStackQueuedSpinLock(&v26);
  v21 = IofCallDriver(*(PDEVICE_OBJECT *)(v15 + 24), Irp);
  if ( v20 )
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
      v21);
  }
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( P )
  {
    KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
    *(_DWORD *)qword_14001A190 = 1919509097;
    *(_QWORD *)(qword_14001A190 + 8) = Object;
    *(_QWORD *)(qword_14001A190 + 16) = Irp;
    *(_QWORD *)(qword_14001A190 + 24) = v21;
    if ( qword_14001A190 <= (unsigned __int64)P )
      v22 = qword_14001A198 - 32;
    else
      v22 = qword_14001A190 - 32;
    qword_14001A190 = v22;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0xA0u,
      (__int64)WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids,
      v21);
  }
  memset(&v26, 0, sizeof(v26));
  if ( P )
  {
    KeAcquireInStackQueuedSpinLock(&SpinLock, &v26);
    *(_DWORD *)qword_14001A190 = 2004050793;
    *(_QWORD *)(qword_14001A190 + 8) = Object;
    *(_QWORD *)(qword_14001A190 + 16) = Irp;
    *(_QWORD *)(qword_14001A190 + 24) = v21;
    if ( qword_14001A190 <= (unsigned __int64)P )
      v23 = qword_14001A198 - 32;
    else
      v23 = qword_14001A190 - 32;
    qword_14001A190 = v23;
    KeReleaseInStackQueuedSpinLock(&v26);
  }
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x140002a70  push    rbx
0x140002a72  push    rbp
0x140002a73  push    rsi
0x140002a74  push    rdi
0x140002a75  push    r12
0x140002a77  push    r13
0x140002a79  push    r14
0x140002a7b  push    r15
0x140002a7d  sub     rsp, 58h
0x140002a81  mov     rbx, rdx
0x140002a84  mov     rdi, rcx
0x140002a87  mov     rcx, cs:WPP_GLOBAL_Control
0x140002a8e  lea     rsi, WPP_GLOBAL_Control
0x140002a95  cmp     rcx, rsi
0x140002a98  jnz     loc_140002EE2
0x140002a9e  xor     eax, eax
0x140002aa0  xorps   xmm0, xmm0
0x140002aa3  cmp     cs:P, rax
0x140002aaa  movups  xmmword ptr [rsp+98h+LockHandle.LockQueue.Next], xmm0
0x140002aaf  mov     qword ptr [rsp+98h+LockHandle.OldIrql], rax
0x140002ab4  jz      short loc_140002B30
0x140002ab6  lea     rdx, [rsp+98h+LockHandle]; LockHandle
0x140002abb  lea     rcx, SpinLock; SpinLock
0x140002ac2  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140002ac9  nop     dword ptr [rax+rax+00h]
0x140002ace  mov     rax, cs:qword_14001A190
0x140002ad5  mov     dword ptr [rax], 57534349h
0x140002adb  mov     rax, cs:qword_14001A190
0x140002ae2  mov     [rax+8], rdi
0x140002ae6  mov     rax, cs:qword_14001A190
0x140002aed  mov     [rax+10h], rbx
0x140002af1  mov     rax, cs:qword_14001A190
0x140002af8  mov     qword ptr [rax+18h], 0
0x140002b00  mov     rax, cs:qword_14001A190
0x140002b07  cmp     rax, cs:P
0x140002b0e  jbe     loc_140002F43
0x140002b14  sub     rax, 20h ; ' '
0x140002b18  lea     rcx, [rsp+98h+LockHandle]; LockHandle
0x140002b1d  mov     cs:qword_14001A190, rax
0x140002b24  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140002b2b  nop     dword ptr [rax+rax+00h]
0x140002b30  mov     r14, [rdi+40h]
0x140002b34  mov     r8d, 200h
0x140002b3a  mov     r15d, r8d
0x140002b3d  mov     ecx, 2
0x140002b42  xorps   xmm0, xmm0
0x140002b45  movups  xmmword ptr [rsp+98h+var_60.LockQueue.Next], xmm0
0x140002b4a  mov     rax, [r14+60h]
0x140002b4e  mov     r13, [r14+6A8h]
0x140002b55  movzx   edx, word ptr [rax]
0x140002b58  mov     r12, [rax+8]
0x140002b5c  cmp     dx, r8w
0x140002b60  mov     eax, 0Dh
0x140002b65  cmovnz  r15d, eax
0x140002b69  movzx   eax, byte ptr [r14+754h]
0x140002b71  neg     al
0x140002b73  sbb     ebp, ebp
0x140002b75  xor     eax, eax
0x140002b77  and     ebp, 10h
0x140002b7a  mov     qword ptr [rsp+98h+var_60.OldIrql], rax
0x140002b7f  cmp     dx, r8w
0x140002b83  cmovnz  ecx, eax
0x140002b86  or      ebp, ecx
0x140002b88  mov     rcx, cs:WPP_GLOBAL_Control
0x140002b8f  cmp     rcx, rsi
0x140002b92  jnz     loc_140002EB3
0x140002b98  xor     eax, eax
0x140002b9a  xorps   xmm0, xmm0
0x140002b9d  cmp     cs:P, rax
0x140002ba4  movups  xmmword ptr [rsp+98h+LockHandle.LockQueue.Next], xmm0
0x140002ba9  mov     qword ptr [rsp+98h+LockHandle.OldIrql], rax
0x140002bae  jz      short loc_140002C2A
0x140002bb0  lea     rdx, [rsp+98h+LockHandle]; LockHandle
0x140002bb5  lea     rcx, SpinLock; SpinLock
0x140002bbc  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140002bc3  nop     dword ptr [rax+rax+00h]
0x140002bc8  mov     rax, cs:qword_14001A190
0x140002bcf  mov     dword ptr [rax], 52494249h
0x140002bd5  mov     rax, cs:qword_14001A190
0x140002bdc  mov     [rax+8], rdi
0x140002be0  mov     rax, cs:qword_14001A190
0x140002be7  mov     [rax+10h], rbx
0x140002beb  mov     rax, cs:qword_14001A190
0x140002bf2  mov     qword ptr [rax+18h], 0
0x140002bfa  mov     rax, cs:qword_14001A190
0x140002c01  cmp     rax, cs:P
0x140002c08  jbe     loc_140002F53
0x140002c0e  sub     rax, 20h ; ' '
0x140002c12  lea     rcx, [rsp+98h+LockHandle]; LockHandle
0x140002c17  mov     cs:qword_14001A190, rax
0x140002c1e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140002c25  nop     dword ptr [rax+rax+00h]
0x140002c2a  mov     rsi, [rdi+40h]
0x140002c2e  lea     rdx, [rsp+98h+var_60]; LockHandle
0x140002c33  mov     rax, [rbx+0B8h]
0x140002c3a  xorps   xmm0, xmm0
0x140002c3d  lea     rcx, [rsi+188h]
0x140002c44  mov     rax, [rax+10h]
0x140002c48  movups  xmmword ptr [rcx], xmm0
0x140002c4b  mov     [rsp+98h+Context], rax
0x140002c53  lea     rax, [r14+4A8h]
0x140002c5a  movups  xmmword ptr [rcx+10h], xmm0
0x140002c5e  movups  xmmword ptr [rcx+20h], xmm0
0x140002c62  movups  xmmword ptr [rcx+30h], xmm0
0x140002c66  movups  xmmword ptr [rcx+40h], xmm0
0x140002c6a  movups  xmmword ptr [rcx+50h], xmm0
0x140002c6e  movups  xmmword ptr [rcx+60h], xmm0
0x140002c72  movups  xmmword ptr [rcx+70h], xmm0
0x140002c76  mov     dword ptr [rcx], 90080h
0x140002c7c  mov     [rcx+18h], r12
0x140002c80  mov     [rcx+20h], ebp
0x140002c83  mov     [rcx+24h], r15d
0x140002c87  mov     [rcx+28h], rax
0x140002c8b  mov     [rcx+30h], r13
0x140002c8f  mov     rax, [rbx+0B8h]
0x140002c96  mov     [rax-40h], rcx
0x140002c9a  lea     rcx, USBSTOR_CswCompletion
0x140002ca1  mov     byte ptr [rax-48h], 0Fh
0x140002ca5  mov     dword ptr [rax-30h], 220003h
0x140002cac  mov     rax, [rbx+0B8h]
0x140002cb3  mov     [rax-10h], rcx
0x140002cb7  lea     rcx, [rsi+90h]; SpinLock
0x140002cbe  mov     qword ptr [rax-8], 0
0x140002cc6  mov     byte ptr [rax-45h], 0E0h
0x140002cca  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140002cd1  nop     dword ptr [rax+rax+00h]
0x140002cd6  mov     eax, [rsi+80h]
0x140002cdc  or      eax, 2
0x140002cdf  mov     [rsi+148h], rbx
0x140002ce6  test    al, 40h
0x140002ce8  jnz     loc_140002F83
0x140002cee  xor     bpl, bpl
0x140002cf1  and     eax, 0FFFFFFBFh
0x140002cf4  lea     rcx, [rsp+98h+var_60]; LockHandle
0x140002cf9  mov     [rsi+80h], eax
0x140002cff  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140002d06  nop     dword ptr [rax+rax+00h]
0x140002d0b  mov     rcx, [rsi+18h]; DeviceObject
0x140002d0f  mov     rdx, rbx; Irp
0x140002d12  call    cs:__imp_IofCallDriver
0x140002d19  nop     dword ptr [rax+rax+00h]
0x140002d1e  movsxd  rsi, eax
0x140002d21  test    bpl, bpl
0x140002d24  jnz     loc_140002F93
0x140002d2a  mov     rcx, cs:WPP_GLOBAL_Control
0x140002d31  lea     rbp, WPP_GLOBAL_Control
0x140002d38  cmp     rcx, rbp
0x140002d3b  jnz     loc_140002E81
0x140002d41  xor     eax, eax
0x140002d43  xorps   xmm0, xmm0
0x140002d46  cmp     cs:P, rax
0x140002d4d  movups  xmmword ptr [rsp+98h+LockHandle.LockQueue.Next], xmm0
0x140002d52  mov     qword ptr [rsp+98h+LockHandle.OldIrql], rax
0x140002d57  jz      short loc_140002DCF
0x140002d59  lea     rdx, [rsp+98h+LockHandle]; LockHandle
0x140002d5e  lea     rcx, SpinLock; SpinLock
0x140002d65  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140002d6c  nop     dword ptr [rax+rax+00h]
0x140002d71  mov     rax, cs:qword_14001A190
0x140002d78  mov     dword ptr [rax], 72696269h
0x140002d7e  mov     rax, cs:qword_14001A190
0x140002d85  mov     [rax+8], rdi
0x140002d89  mov     rax, cs:qword_14001A190
0x140002d90  mov     [rax+10h], rbx
0x140002d94  mov     rax, cs:qword_14001A190
0x140002d9b  mov     [rax+18h], rsi
0x140002d9f  mov     rax, cs:qword_14001A190
0x140002da6  cmp     rax, cs:P
0x140002dad  jbe     loc_140002F63
0x140002db3  sub     rax, 20h ; ' '
0x140002db7  lea     rcx, [rsp+98h+LockHandle]; LockHandle
0x140002dbc  mov     cs:qword_14001A190, rax
0x140002dc3  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140002dca  nop     dword ptr [rax+rax+00h]
0x140002dcf  mov     rcx, cs:WPP_GLOBAL_Control
0x140002dd6  cmp     rcx, rbp
0x140002dd9  jnz     loc_140002F11
0x140002ddf  xor     eax, eax
0x140002de1  xorps   xmm0, xmm0
0x140002de4  cmp     cs:P, rax
0x140002deb  movups  xmmword ptr [rsp+98h+var_60.LockQueue.Next], xmm0
0x140002df0  mov     qword ptr [rsp+98h+var_60.OldIrql], rax
0x140002df5  jz      short loc_140002E6D
0x140002df7  lea     rdx, [rsp+98h+var_60]; LockHandle
0x140002dfc  lea     rcx, SpinLock; SpinLock
0x140002e03  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140002e0a  nop     dword ptr [rax+rax+00h]
0x140002e0f  mov     rax, cs:qword_14001A190
0x140002e16  mov     dword ptr [rax], 77736369h
0x140002e1c  mov     rax, cs:qword_14001A190
0x140002e23  mov     [rax+8], rdi
0x140002e27  mov     rax, cs:qword_14001A190
0x140002e2e  mov     [rax+10h], rbx
0x140002e32  mov     rax, cs:qword_14001A190
0x140002e39  mov     [rax+18h], rsi
0x140002e3d  mov     rax, cs:qword_14001A190
0x140002e44  cmp     rax, cs:P
0x140002e4b  jbe     loc_140002F73
0x140002e51  sub     rax, 20h ; ' '
0x140002e55  lea     rcx, [rsp+98h+var_60]; LockHandle
0x140002e5a  mov     cs:qword_14001A190, rax
0x140002e61  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140002e68  nop     dword ptr [rax+rax+00h]
0x140002e6d  mov     eax, esi
0x140002e6f  add     rsp, 58h
0x140002e73  pop     r15
0x140002e75  pop     r14
0x140002e77  pop     r13
0x140002e79  pop     r12
0x140002e7b  pop     rdi
0x140002e7c  pop     rsi
0x140002e7d  pop     rbp
0x140002e7e  pop     rbx
0x140002e7f  retn
0x140002e81  mov     eax, [rcx+2Ch]
0x140002e84  test    al, 1
0x140002e86  jz      loc_140002D41
0x140002e8c  cmp     byte ptr [rcx+29h], 5
0x140002e90  jb      loc_140002D41
0x140002e96  mov     rcx, [rcx+18h]
0x140002e9a  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140002ea1  mov     edx, 59h ; 'Y'
0x140002ea6  mov     r9d, esi
0x140002ea9  call    WPP_SF_d
0x140002eae  jmp     loc_140002D41
0x140002eb3  mov     eax, [rcx+2Ch]
0x140002eb6  test    al, 1
0x140002eb8  jz      loc_140002B98
0x140002ebe  cmp     byte ptr [rcx+29h], 5
0x140002ec2  jb      loc_140002B98
0x140002ec8  mov     rcx, [rcx+18h]
0x140002ecc  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140002ed3  mov     edx, 58h ; 'X'
0x140002ed8  call    WPP_SF_
0x140002edd  jmp     loc_140002B98
0x140002ee2  mov     eax, [rcx+2Ch]
0x140002ee5  test    al, 1
0x140002ee7  jz      loc_140002A9E
0x140002eed  cmp     byte ptr [rcx+29h], 5
0x140002ef1  jb      loc_140002A9E
0x140002ef7  mov     rcx, [rcx+18h]
0x140002efb  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140002f02  mov     edx, 9Fh
0x140002f07  call    WPP_SF_
0x140002f0c  jmp     loc_140002A9E
0x140002f11  mov     eax, [rcx+2Ch]
0x140002f14  test    al, 1
0x140002f16  jz      loc_140002DDF
0x140002f1c  cmp     byte ptr [rcx+29h], 5
0x140002f20  jb      loc_140002DDF
0x140002f26  mov     rcx, [rcx+18h]
0x140002f2a  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140002f31  mov     edx, 0A0h
0x140002f36  mov     r9d, esi
0x140002f39  call    WPP_SF_d
0x140002f3e  jmp     loc_140002DDF
0x140002f43  mov     rax, cs:qword_14001A198
0x140002f4a  add     rax, 0FFFFFFFFFFFFFFE0h
0x140002f4e  jmp     loc_140002B18
0x140002f53  mov     rax, cs:qword_14001A198
0x140002f5a  add     rax, 0FFFFFFFFFFFFFFE0h
0x140002f5e  jmp     loc_140002C12
0x140002f63  mov     rax, cs:qword_14001A198
0x140002f6a  add     rax, 0FFFFFFFFFFFFFFE0h
0x140002f6e  jmp     loc_140002DB7
0x140002f73  mov     rax, cs:qword_14001A198
0x140002f7a  add     rax, 0FFFFFFFFFFFFFFE0h
0x140002f7e  jmp     loc_140002E55
0x140002f83  test    al, 8
0x140002f85  jnz     loc_140002CEE
0x140002f8b  mov     bpl, 1
0x140002f8e  jmp     loc_140002CF1
0x140002f93  mov     r9, [rsp+98h+Context]
0x140002f9b  mov     r8, rbx
0x140002f9e  mov     rdx, rdi
0x140002fa1  mov     ecx, 4F544942h
0x140002fa6  call    USBSTOR_LogEntry
0x140002fab  mov     rdx, [rsp+98h+Context]; Context
0x140002fb3  mov     rcx, rdi; Object
0x140002fb6  call    USBSTOR_QueueResetDevice
0x140002fbb  jmp     loc_140002D2A
```
