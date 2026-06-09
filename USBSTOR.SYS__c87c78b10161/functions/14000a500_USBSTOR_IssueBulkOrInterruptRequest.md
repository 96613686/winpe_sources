# USBSTOR_IssueBulkOrInterruptRequest

- ea: `0x14000a500`
- end: `0x14000a843`
- name: `USBSTOR_IssueBulkOrInterruptRequest`
- size: `835`
- prototype: `__int64 __usercall@<rax>(PVOID Object@<rcx>, PIRP Irp@<rdx>, int, __int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000a3f4`
- `0x14000ea94`
- `0x14000fd74`
- `0x140011e3c`

## callees

- `0x140001008`
- `0x140003630`
- `0x14000a500`
- `0x1400105e8`
- `0x140010664`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14000a6c7`
- `ntoskrnl!IofCallDriver` at `0x14000a6c7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000a565`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000a67f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000a713`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000a565`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000a67f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000a713`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000a5c7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000a6b4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000a771`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000a5c7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000a6b4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000a771`

## pseudocode

```c
__int64 __fastcall USBSTOR_IssueBulkOrInterruptRequest(
        _QWORD *Object,
        PIRP Irp,
        __int64 a3,
        int a4,
        int a5,
        __int64 a6,
        __int64 a7,
        IO_COMPLETION_ROUTINE *a8,
        void *a9)
{
  __int64 v13; // rax
  __int64 v14; // rdi
  PUNICODE_STRING FileName; // r15
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v17; // rcx
  int v18; // eax
  bool v19; // bp
  __int64 v20; // rdi
  __int64 v21; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-68h] BYREF
  struct _KLOCK_QUEUE_HANDLE v24; // [rsp+38h] [rbp-50h] BYREF

  memset(&v24, 0, sizeof(v24));
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
      v13 = qword_14001A198 - 32;
    else
      v13 = qword_14001A190 - 32;
    qword_14001A190 = v13;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  v14 = Object[8];
  FileName = Irp->Tail.Overlay.CurrentStackLocation->Parameters.QueryDirectory.FileName;
  *(_OWORD *)(v14 + 392) = 0;
  *(_OWORD *)(v14 + 408) = 0;
  *(_OWORD *)(v14 + 424) = 0;
  *(_OWORD *)(v14 + 440) = 0;
  *(_OWORD *)(v14 + 456) = 0;
  *(_OWORD *)(v14 + 472) = 0;
  *(_OWORD *)(v14 + 488) = 0;
  *(_OWORD *)(v14 + 504) = 0;
  *(_DWORD *)(v14 + 428) = a5;
  *(_QWORD *)(v14 + 432) = a6;
  *(_QWORD *)(v14 + 440) = a7;
  *(_DWORD *)(v14 + 392) = 589952;
  *(_QWORD *)(v14 + 416) = a3;
  *(_DWORD *)(v14 + 424) = a4;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].Parameters.WMI.ProviderId = v14 + 392;
  CurrentStackLocation[-1].MajorFunction = 15;
  CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 2228227;
  v17 = Irp->Tail.Overlay.CurrentStackLocation;
  v17[-1].CompletionRoutine = a8;
  v17[-1].Context = a9;
  v17[-1].Control = -32;
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v14 + 144), &v24);
  v18 = *(_DWORD *)(v14 + 128) | 2;
  *(_QWORD *)(v14 + 328) = Irp;
  v19 = (v18 & 0x40) != 0 && (v18 & 8) == 0;
  *(_DWORD *)(v14 + 128) = v18 & 0xFFFFFFBF;
  KeReleaseInStackQueuedSpinLock(&v24);
  v20 = IofCallDriver(*(PDEVICE_OBJECT *)(v14 + 24), Irp);
  if ( v19 )
  {
    USBSTOR_LogEntry(1330923842, (__int64)Object, (__int64)Irp, (__int64)FileName);
    USBSTOR_QueueResetDevice(Object, FileName);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x59u,
      (__int64)WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids,
      v20);
  }
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( P )
  {
    KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
    *(_DWORD *)qword_14001A190 = 1919509097;
    *(_QWORD *)(qword_14001A190 + 8) = Object;
    *(_QWORD *)(qword_14001A190 + 16) = Irp;
    *(_QWORD *)(qword_14001A190 + 24) = v20;
    if ( qword_14001A190 <= (unsigned __int64)P )
      v21 = qword_14001A198 - 32;
    else
      v21 = qword_14001A190 - 32;
    qword_14001A190 = v21;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x14000a500  push    rbx
0x14000a502  push    rbp
0x14000a503  push    rsi
0x14000a504  push    rdi
0x14000a505  push    r12
0x14000a507  push    r14
0x14000a509  push    r15
0x14000a50b  sub     rsp, 50h
0x14000a50f  xorps   xmm0, xmm0
0x14000a512  xor     eax, eax
0x14000a514  movups  xmmword ptr [rsp+88h+var_50.LockQueue.Next], xmm0
0x14000a519  mov     qword ptr [rsp+88h+var_50.OldIrql], rax
0x14000a51e  mov     ebp, r9d
0x14000a521  mov     r14, r8
0x14000a524  mov     rbx, rdx
0x14000a527  mov     rsi, rcx
0x14000a52a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a531  lea     r12, WPP_GLOBAL_Control
0x14000a538  cmp     rcx, r12
0x14000a53b  jnz     loc_14000A7C1
0x14000a541  xor     eax, eax
0x14000a543  xorps   xmm0, xmm0
0x14000a546  cmp     cs:P, rax
0x14000a54d  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x14000a552  mov     qword ptr [rsp+88h+LockHandle.OldIrql], rax
0x14000a557  jz      short loc_14000A5D3
0x14000a559  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x14000a55e  lea     rcx, SpinLock; SpinLock
0x14000a565  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000a56c  nop     dword ptr [rax+rax+00h]
0x14000a571  mov     rax, cs:qword_14001A190
0x14000a578  mov     dword ptr [rax], 52494249h
0x14000a57e  mov     rax, cs:qword_14001A190
0x14000a585  mov     [rax+8], rsi
0x14000a589  mov     rax, cs:qword_14001A190
0x14000a590  mov     [rax+10h], rbx
0x14000a594  mov     rax, cs:qword_14001A190
0x14000a59b  mov     qword ptr [rax+18h], 0
0x14000a5a3  mov     rax, cs:qword_14001A190
0x14000a5aa  cmp     rax, cs:P
0x14000a5b1  jbe     loc_14000A7F0
0x14000a5b7  sub     rax, 20h ; ' '
0x14000a5bb  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x14000a5c0  mov     cs:qword_14001A190, rax
0x14000a5c7  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000a5ce  nop     dword ptr [rax+rax+00h]
0x14000a5d3  mov     rax, [rbx+0B8h]
0x14000a5da  lea     rdx, [rsp+88h+var_50]; LockHandle
0x14000a5df  mov     rdi, [rsi+40h]
0x14000a5e3  xorps   xmm0, xmm0
0x14000a5e6  mov     r15, [rax+10h]
0x14000a5ea  mov     eax, [rsp+88h+arg_20]
0x14000a5f1  lea     rcx, [rdi+188h]
0x14000a5f8  movups  xmmword ptr [rcx], xmm0
0x14000a5fb  movups  xmmword ptr [rcx+10h], xmm0
0x14000a5ff  movups  xmmword ptr [rcx+20h], xmm0
0x14000a603  movups  xmmword ptr [rcx+30h], xmm0
0x14000a607  movups  xmmword ptr [rcx+40h], xmm0
0x14000a60b  movups  xmmword ptr [rcx+50h], xmm0
0x14000a60f  movups  xmmword ptr [rcx+60h], xmm0
0x14000a613  movups  xmmword ptr [rcx+70h], xmm0
0x14000a617  mov     [rcx+24h], eax
0x14000a61a  mov     rax, [rsp+88h+arg_28]
0x14000a622  mov     [rcx+28h], rax
0x14000a626  mov     rax, [rsp+88h+arg_30]
0x14000a62e  mov     [rcx+30h], rax
0x14000a632  mov     dword ptr [rcx], 90080h
0x14000a638  mov     [rcx+18h], r14
0x14000a63c  mov     [rcx+20h], ebp
0x14000a63f  mov     rax, [rbx+0B8h]
0x14000a646  mov     [rax-40h], rcx
0x14000a64a  mov     byte ptr [rax-48h], 0Fh
0x14000a64e  mov     dword ptr [rax-30h], 220003h
0x14000a655  mov     rcx, [rbx+0B8h]
0x14000a65c  mov     rax, [rsp+88h+arg_38]
0x14000a664  mov     [rcx-10h], rax
0x14000a668  mov     rax, [rsp+88h+arg_40]
0x14000a670  mov     [rcx-8], rax
0x14000a674  mov     byte ptr [rcx-45h], 0E0h
0x14000a678  lea     rcx, [rdi+90h]; SpinLock
0x14000a67f  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000a686  nop     dword ptr [rax+rax+00h]
0x14000a68b  mov     eax, [rdi+80h]
0x14000a691  or      eax, 2
0x14000a694  mov     [rdi+148h], rbx
0x14000a69b  test    al, 40h
0x14000a69d  jnz     loc_14000A810
0x14000a6a3  xor     bpl, bpl
0x14000a6a6  and     eax, 0FFFFFFBFh
0x14000a6a9  lea     rcx, [rsp+88h+var_50]; LockHandle
0x14000a6ae  mov     [rdi+80h], eax
0x14000a6b4  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000a6bb  nop     dword ptr [rax+rax+00h]
0x14000a6c0  mov     rcx, [rdi+18h]; DeviceObject
0x14000a6c4  mov     rdx, rbx; Irp
0x14000a6c7  call    cs:__imp_IofCallDriver
0x14000a6ce  nop     dword ptr [rax+rax+00h]
0x14000a6d3  movsxd  rdi, eax
0x14000a6d6  test    bpl, bpl
0x14000a6d9  jnz     loc_14000A820
0x14000a6df  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a6e6  cmp     rcx, r12
0x14000a6e9  jnz     loc_14000A78F
0x14000a6ef  xor     eax, eax
0x14000a6f1  xorps   xmm0, xmm0
0x14000a6f4  cmp     cs:P, rax
0x14000a6fb  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x14000a700  mov     qword ptr [rsp+88h+LockHandle.OldIrql], rax
0x14000a705  jz      short loc_14000A77D
0x14000a707  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x14000a70c  lea     rcx, SpinLock; SpinLock
0x14000a713  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000a71a  nop     dword ptr [rax+rax+00h]
0x14000a71f  mov     rax, cs:qword_14001A190
0x14000a726  mov     dword ptr [rax], 72696269h
0x14000a72c  mov     rax, cs:qword_14001A190
0x14000a733  mov     [rax+8], rsi
0x14000a737  mov     rax, cs:qword_14001A190
0x14000a73e  mov     [rax+10h], rbx
0x14000a742  mov     rax, cs:qword_14001A190
0x14000a749  mov     [rax+18h], rdi
0x14000a74d  mov     rax, cs:qword_14001A190
0x14000a754  cmp     rax, cs:P
0x14000a75b  jbe     loc_14000A800
0x14000a761  sub     rax, 20h ; ' '
0x14000a765  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x14000a76a  mov     cs:qword_14001A190, rax
0x14000a771  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000a778  nop     dword ptr [rax+rax+00h]
0x14000a77d  mov     eax, edi
0x14000a77f  add     rsp, 50h
0x14000a783  pop     r15
0x14000a785  pop     r14
0x14000a787  pop     r12
0x14000a789  pop     rdi
0x14000a78a  pop     rsi
0x14000a78b  pop     rbp
0x14000a78c  pop     rbx
0x14000a78d  retn
0x14000a78f  mov     eax, [rcx+2Ch]
0x14000a792  test    al, 1
0x14000a794  jz      loc_14000A6EF
0x14000a79a  cmp     byte ptr [rcx+29h], 5
0x14000a79e  jb      loc_14000A6EF
0x14000a7a4  mov     rcx, [rcx+18h]
0x14000a7a8  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x14000a7af  mov     edx, 59h ; 'Y'
0x14000a7b4  mov     r9d, edi
0x14000a7b7  call    WPP_SF_d
0x14000a7bc  jmp     loc_14000A6EF
0x14000a7c1  mov     eax, [rcx+2Ch]
0x14000a7c4  test    al, 1
0x14000a7c6  jz      loc_14000A541
0x14000a7cc  cmp     byte ptr [rcx+29h], 5
0x14000a7d0  jb      loc_14000A541
0x14000a7d6  mov     rcx, [rcx+18h]
0x14000a7da  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x14000a7e1  mov     edx, 58h ; 'X'
0x14000a7e6  call    WPP_SF_
0x14000a7eb  jmp     loc_14000A541
0x14000a7f0  mov     rax, cs:qword_14001A198
0x14000a7f7  add     rax, 0FFFFFFFFFFFFFFE0h
0x14000a7fb  jmp     loc_14000A5BB
0x14000a800  mov     rax, cs:qword_14001A198
0x14000a807  add     rax, 0FFFFFFFFFFFFFFE0h
0x14000a80b  jmp     loc_14000A765
0x14000a810  test    al, 8
0x14000a812  jnz     loc_14000A6A3
0x14000a818  mov     bpl, 1
0x14000a81b  jmp     loc_14000A6A6
0x14000a820  mov     r9, r15
0x14000a823  mov     r8, rbx
0x14000a826  mov     rdx, rsi
0x14000a829  mov     ecx, 4F544942h
0x14000a82e  call    USBSTOR_LogEntry
0x14000a833  mov     rdx, r15; Context
0x14000a836  mov     rcx, rsi; Object
0x14000a839  call    USBSTOR_QueueResetDevice
0x14000a83e  jmp     loc_14000A6DF
```
