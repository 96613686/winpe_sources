# AfdDoDatagramConnect

- ea: `0x14003a930`
- end: `0x14003ae48`
- name: `AfdDoDatagramConnect`
- size: `1304`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400398d0`

## callees

- `0x140003670`
- `0x14000f450`
- `0x14000fcd0`
- `0x140013030`
- `0x1400137a0`
- `0x140015990`
- `0x14001b0d0`
- `0x14001b0f8`
- `0x14001b800`
- `0x140026e80`
- `0x140030970`
- `0x14003a930`
- `0x140072980`
- `0x140072c80`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14003aae8`
- `ntoskrnl!IofCompleteRequest` at `0x14003ad25`
- `ntoskrnl!IofCompleteRequest` at `0x14003aae8`
- `ntoskrnl!IofCompleteRequest` at `0x14003ad25`
- `ntoskrnl!ObfDereferenceObject` at `0x14003acea`
- `ntoskrnl!ObfDereferenceObject` at `0x14003acea`
- `ntoskrnl!IofCallDriver` at `0x14003ae20`
- `ntoskrnl!IofCallDriver` at `0x14003ae20`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003ab72`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003ab72`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003a9dc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003a9dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ac3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ad04`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ac3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ad04`
- `NDIS!NdisAcquireRWLockWrite` at `0x14003ab29`
- `NDIS!NdisAcquireRWLockWrite` at `0x14003ab9c`
- `NDIS!NdisAcquireRWLockWrite` at `0x14003ab29`
- `NDIS!NdisAcquireRWLockWrite` at `0x14003ab9c`
- `NDIS!NdisReleaseRWLock` at `0x14003abea`
- `NDIS!NdisReleaseRWLock` at `0x14003abea`

## pseudocode

```c
NTSTATUS __fastcall AfdDoDatagramConnect(_QWORD *a1, IRP *a2, __int64 a3, unsigned int a4, char a5)
{
  __int64 v5; // rbx
  struct _IRP *MasterIrp; // r13
  unsigned int v9; // r14d
  unsigned int v10; // r15d
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rcx
  char v14; // r14
  unsigned int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rdx
  int v19; // ebx
  __int64 v20; // r8
  IRP *v21; // rcx
  LIST_ENTRY *p_ThreadListEntry; // r14
  void *v24; // r12
  __int64 Flink_low; // rdx
  __int64 PoolPriority; // rax
  struct _NDIS_RW_LOCK_EX *v27; // rcx
  int v28; // eax
  __int64 v29; // rcx
  char v30; // al
  struct _KLOCK_QUEUE_HANDLE *p_LockHandle; // rdx
  int v32; // ebx
  CCHAR v33; // dl
  struct _DEVICE_OBJECT *v34; // r12
  unsigned int v35; // eax
  int v36; // ecx
  __int64 v37; // rax
  struct _FILE_OBJECT *v38; // rdi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v40; // rdx
  unsigned int v41; // [rsp+38h] [rbp-61h]
  __int64 v42; // [rsp+40h] [rbp-59h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+48h] [rbp-51h] BYREF
  _QWORD v44[16]; // [rsp+68h] [rbp-31h] BYREF
  struct _FILE_OBJECT *Objecta; // [rsp+F8h] [rbp+5Fh]
  struct _LOCK_STATE_EX LockState; // [rsp+100h] [rbp+67h] BYREF
  unsigned int v48; // [rsp+110h] [rbp+77h]

  v48 = a4;
  v5 = a1[3];
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v5 + 368), 4, 0) )
  {
    v10 = 1;
    if ( (unsigned __int8)(*(_BYTE *)(v5 + 2) - 3) > 1u )
    {
      v9 = -1073741811;
      v11 = 5501;
LABEL_5:
      v10 = 0;
      v12 = 0;
LABEL_30:
      AFDETW_TRACECONNECT(v10, v11, v5, v9, v12);
      _InterlockedExchange((volatile __int32 *)(v5 + 368), 0);
      goto LABEL_31;
    }
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v5 + 56), &LockHandle);
    v13 = *(unsigned int *)(v5 + 192);
    v14 = a5;
    *(_DWORD *)(v5 + 8) &= 0xFFF0FFFF;
    *(_DWORD *)(v5 + 192) = v13 ^ ((unsigned __int8)v13 ^ (unsigned __int8)(16 * v14)) & 0x10;
    if ( (*(_DWORD *)(v5 + 8) & 0x100) != 0 )
    {
      memset(v44, 0, 0x50u);
      AFDETW_TRACECONNECT(0, 5502, v5, 0, a3);
      v15 = *(_DWORD *)(v5 + 72) & 0xFFFFFEFF;
      *(_DWORD *)(v5 + 436) = 0;
      *(_DWORD *)(v5 + 72) = v15;
      AfdNotifySockEventsChangedUnderLock(v5, 0, 256);
      AfdNotifySockIndicateEventsUnlock(v16, &LockHandle, 0);
      a2->Tail.Overlay.DriverContext[2] = 0;
      v17 = *(_QWORD *)(v5 + 24);
      v18 = *(_QWORD *)(v5 + 16);
      v44[0] = AfdTLDgramConnectComplete;
      v44[1] = a2;
      v44[2] = 0xFFFD00000000LL;
      LODWORD(v44[3]) = v14 != 0 ? 40 : 28;
      v44[5] = v48;
      v44[4] = a3;
      v19 = AfdTLIoControl(*(_QWORD *)(v17 + 8), v18, v44, v5);
      v21 = a2;
      if ( v19 == 259 )
      {
        LOBYTE(v20) = 1;
        if ( (unsigned __int8)AfdTLPendRequest(a2, v44[8], v20) )
          return v19;
        v21 = a2;
      }
      IofCompleteRequest(v21, AfdPriorityBoost);
      return v19;
    }
    if ( *(_QWORD *)(v5 + 184)
      && (p_ThreadListEntry = &MasterIrp->ThreadListEntry,
          *(_DWORD *)(v5 + 176) >= LODWORD(MasterIrp->ThreadListEntry.Flink)) )
    {
      v41 = 0;
      v24 = 0;
      NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v5 + 168), &LockState, 1u);
    }
    else
    {
      p_ThreadListEntry = &MasterIrp->ThreadListEntry;
      Flink_low = SLODWORD(MasterIrp->ThreadListEntry.Flink);
      if ( LODWORD(MasterIrp->ThreadListEntry.Flink) > (unsigned int)AfdStandardAddressLength )
        PoolPriority = AfdAllocatePoolPriority(64, Flink_low, 1382311489, 0);
      else
        PoolPriority = AfdAllocateZeroedFromLookasideList(v13, Flink_low);
      v42 = PoolPriority;
      if ( !PoolPriority )
      {
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        v11 = 5503;
        v9 = -1073741670;
        goto LABEL_5;
      }
      NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v5 + 168), &LockState, 1u);
      v24 = *(void **)(v5 + 184);
      v41 = *(_DWORD *)(v5 + 176);
      *(_QWORD *)(v5 + 184) = v42;
    }
    memmove(*(void **)(v5 + 184), MasterIrp->ThreadListEntry.Blink, SLODWORD(p_ThreadListEntry->Flink));
    v27 = *(struct _NDIS_RW_LOCK_EX **)(v5 + 168);
    *(_DWORD *)(v5 + 176) = p_ThreadListEntry->Flink;
    NdisReleaseRWLock(v27, &LockState);
    AFDETW_TRACECONNECT(0, 5504, v5, 0, *(_QWORD *)(v5 + 184));
    if ( v24 )
    {
      if ( v41 > (unsigned int)AfdStandardAddressLength )
        ExFreePoolWithTag(v24, 0x52646641u);
      else
        PplFreeToLookasideList(PplAddressPool, v24);
    }
    if ( (*(_DWORD *)(v5 + 8) & 0x100) == 0 && (*(_DWORD *)(v5 + 16) & 0x8000) == 0 )
    {
      v28 = *(_DWORD *)(v5 + 8) | 0x2000000;
      *(_BYTE *)(v5 + 2) = 4;
      *(_DWORD *)(v5 + 8) = v28;
      AfdIndicateEventSelectEvent(v5, 68, 0);
      AfdNotifySockEventsChangedUnderLock(v5, 4, 0);
      v30 = AfdIndicatePollEvent(v29, 68, 0, &LockHandle);
      p_LockHandle = &LockHandle;
      if ( v30 )
        p_LockHandle = 0;
      AfdNotifySockIndicateEventsUnlock(v5, p_LockHandle, 0);
      v12 = *(_QWORD *)(v5 + 184);
      v11 = 5505;
      v9 = 0;
      goto LABEL_30;
    }
    v34 = *(struct _DEVICE_OBJECT **)(v5 + 40);
    Objecta = *(struct _FILE_OBJECT **)(v5 + 24);
    v35 = *(_DWORD *)(v5 + 72) & 0xFFFFFEFF;
    *(_DWORD *)(v5 + 436) = 0;
    *(_DWORD *)(v5 + 72) = v35;
    AfdNotifySockEventsChangedUnderLock(v5, 0, 256);
    v36 = *(_DWORD *)(v5 + 8);
    if ( (v36 & 0x400000) != 0 )
    {
      if ( (unsigned __int8)AfdTdi_TA6toTA4_InPlace(MasterIrp->ThreadListEntry.Blink, p_ThreadListEntry) )
      {
        v37 = *(_QWORD *)(v5 + 280);
        v38 = *(struct _FILE_OBJECT **)(v37 + 8);
        v34 = *(struct _DEVICE_OBJECT **)(v37 + 16);
        *(_DWORD *)(v5 + 192) |= 0x20u;
LABEL_41:
        AfdNotifySockIndicateEventsUnlock(v5, &LockHandle, 0);
        CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
        CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)AfdRestartDgConnect;
        CurrentStackLocation[-1].Context = (PVOID)v5;
        CurrentStackLocation[-1].Control = -32;
        v40 = a2->Tail.Overlay.CurrentStackLocation;
        v40[-1].Parameters.Read.ByteOffset.QuadPart = (LONGLONG)&MasterIrp->IoStatus;
        v40[-1].Parameters.CreatePipe.Parameters = (PNAMED_PIPE_CREATE_PARAMETERS)&AfdInfiniteTimeout;
        *(_WORD *)&v40[-1].MajorFunction = 783;
        v40[-1].DeviceObject = v34;
        v40[-1].FileObject = v38;
        v40[-1].Parameters.QueryDirectory.FileName = (PUNICODE_STRING)MasterIrp;
        _InterlockedAdd((volatile signed __int32 *)(v5 + 248), 1u);
        return IofCallDriver(v34, a2);
      }
      *(_DWORD *)(v5 + 192) = *(_DWORD *)(v5 + 192) & 0xFFFFFF9F | 0x40;
    }
    else if ( (v36 & 0x200000) != 0 )
    {
      AfdTdi_TA6toTA4_InPlace(MasterIrp->ThreadListEntry.Blink, p_ThreadListEntry);
    }
    v38 = Objecta;
    goto LABEL_41;
  }
  v9 = -1073741811;
  AFDETW_TRACECONNECT(0, 5500, v5, 3221225485LL, 0);
LABEL_31:
  v32 = *(_DWORD *)(v5 + 8);
  ObfDereferenceObject(a1);
  if ( (v32 & 0x100) == 0 )
  {
    ExFreePoolWithTag(MasterIrp, 0x49646641u);
    a2->AssociatedIrp.MasterIrp = 0;
  }
  v33 = AfdPriorityBoost;
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = v9;
  IofCompleteRequest(a2, v33);
  return v9;
}

```

## disassembly

```asm
0x14003a930  mov     rax, rsp
0x14003a933  mov     [rax+18h], rbx
0x14003a937  mov     [rax+20h], r9d
0x14003a93b  mov     [rax+8], rcx
0x14003a93f  push    rbp
0x14003a940  push    rsi
0x14003a941  push    rdi
0x14003a942  push    r12
0x14003a944  push    r13
0x14003a946  push    r14
0x14003a948  push    r15
0x14003a94a  lea     rbp, [rax-57h]
0x14003a94e  sub     rsp, 0B0h
0x14003a955  mov     rbx, [rcx+18h]
0x14003a959  xorps   xmm0, xmm0
0x14003a95c  mov     r13, [rdx+18h]
0x14003a960  xor     ecx, ecx
0x14003a962  mov     qword ptr [rbp+4Fh+LockHandle.OldIrql], rcx
0x14003a966  mov     r12, r8
0x14003a969  mov     word ptr [rbp+4Fh+LockState.OldIrql], cx
0x14003a96d  mov     rsi, rdx
0x14003a970  mov     [rbp+4Fh+LockState.Flags], cl
0x14003a973  xor     eax, eax
0x14003a975  mov     ecx, 4
0x14003a97a  movups  xmmword ptr [rbp+4Fh+LockHandle.LockQueue.Next], xmm0
0x14003a97e  lock cmpxchg [rbx+170h], ecx
0x14003a986  jz      short loc_14003A9AC
0x14003a988  xor     edi, edi
0x14003a98a  mov     r14d, 0C000000Dh
0x14003a990  mov     r9d, r14d
0x14003a993  mov     [rsp+20h], rdi
0x14003a998  mov     r8, rbx
0x14003a99b  mov     edx, 157Ch
0x14003a9a0  xor     ecx, ecx
0x14003a9a2  call    AFDETW_TRACECONNECT
0x14003a9a7  jmp     loc_14003ACE3
0x14003a9ac  mov     al, [rbx+2]
0x14003a9af  mov     r15d, 1
0x14003a9b5  sub     al, 3
0x14003a9b7  cmp     al, r15b
0x14003a9ba  jbe     short loc_14003A9D4
0x14003a9bc  xor     edi, edi
0x14003a9be  mov     r14d, 0C000000Dh
0x14003a9c4  mov     edx, 157Dh
0x14003a9c9  mov     r15d, edi
0x14003a9cc  mov     rax, rdi
0x14003a9cf  jmp     loc_14003ACC8
0x14003a9d4  lea     rcx, [rbx+38h]; SpinLock
0x14003a9d8  lea     rdx, [rbp+4Fh+LockHandle]; LockHandle
0x14003a9dc  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14003a9e3  nop     dword ptr [rax+rax+00h]
0x14003a9e8  mov     ecx, [rbx+0C0h]
0x14003a9ee  mov     eax, [rbx+8]
0x14003a9f1  movzx   r14d, [rbp+4Fh+arg_20]
0x14003a9f6  and     eax, 0FFF0FFFFh
0x14003a9fb  mov     [rbx+8], eax
0x14003a9fe  mov     eax, r14d
0x14003aa01  shl     eax, 4
0x14003aa04  xor     eax, ecx
0x14003aa06  and     eax, 10h
0x14003aa09  xor     eax, ecx
0x14003aa0b  mov     [rbx+0C0h], eax
0x14003aa11  mov     eax, [rbx+8]
0x14003aa14  bt      eax, 8
0x14003aa18  jnb     loc_14003AAFB
0x14003aa1e  xor     edx, edx; Val
0x14003aa20  lea     rcx, [rbp+4Fh+var_80]; void *
0x14003aa24  lea     r8d, [rdx+50h]; Size
0x14003aa28  call    memset
0x14003aa2d  xor     r9d, r9d
0x14003aa30  mov     [rsp+20h], r12
0x14003aa35  mov     r8, rbx
0x14003aa38  mov     edx, 157Eh
0x14003aa3d  xor     ecx, ecx
0x14003aa3f  call    AFDETW_TRACECONNECT
0x14003aa44  mov     eax, [rbx+48h]
0x14003aa47  xor     edi, edi
0x14003aa49  btr     eax, 8
0x14003aa4d  mov     [rbx+1B4h], edi
0x14003aa53  xor     edx, edx
0x14003aa55  mov     [rbx+48h], eax
0x14003aa58  mov     r8d, 100h
0x14003aa5e  mov     rcx, rbx
0x14003aa61  call    AfdNotifySockEventsChangedUnderLock
0x14003aa66  xor     r8d, r8d
0x14003aa69  lea     rdx, [rbp+4Fh+LockHandle]
0x14003aa6d  call    AfdNotifySockIndicateEventsUnlock
0x14003aa72  mov     [rsi+88h], rdi
0x14003aa79  lea     rax, AfdTLDgramConnectComplete
0x14003aa80  mov     rcx, [rbx+18h]
0x14003aa84  lea     r8, [rbp+4Fh+var_80]
0x14003aa88  mov     rdx, [rbx+10h]
0x14003aa8c  neg     r14b
0x14003aa8f  mov     [rbp+4Fh+var_80], rax
0x14003aa93  mov     r9, rbx
0x14003aa96  sbb     eax, eax
0x14003aa98  mov     [rbp+4Fh+var_78], rsi
0x14003aa9c  and     eax, 0Ch
0x14003aa9f  mov     [rbp+4Fh+var_70], edi
0x14003aaa2  add     eax, 1Ch
0x14003aaa5  mov     [rbp+4Fh+var_6C], 0FFFDh
0x14003aaac  mov     [rbp+4Fh+var_68], eax
0x14003aaaf  mov     eax, [rbp+4Fh+arg_18]
0x14003aab2  mov     [rbp+4Fh+var_58], rax
0x14003aab6  mov     [rbp+4Fh+var_60], r12
0x14003aaba  mov     rcx, [rcx+8]
0x14003aabe  call    AfdTLIoControl
0x14003aac3  mov     ebx, eax
0x14003aac5  mov     rcx, rsi
0x14003aac8  cmp     eax, 103h
0x14003aacd  jnz     short loc_14003AAE2
0x14003aacf  mov     rdx, [rbp+4Fh+var_40]
0x14003aad3  mov     r8b, r15b
0x14003aad6  call    AfdTLPendRequest
0x14003aadb  test    al, al
0x14003aadd  jnz     short loc_14003AAF4
0x14003aadf  mov     rcx, rsi; Irp
0x14003aae2  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14003aae8  call    cs:__imp_IofCompleteRequest
0x14003aaef  nop     dword ptr [rax+rax+00h]
0x14003aaf4  mov     eax, ebx
0x14003aaf6  jmp     loc_14003AE2C
0x14003aafb  xor     edi, edi
0x14003aafd  cmp     [rbx+0B8h], rdi
0x14003ab04  jz      short loc_14003AB3A
0x14003ab06  lea     r14, [r13+20h]
0x14003ab0a  mov     eax, [r14]
0x14003ab0d  cmp     [rbx+0B0h], eax
0x14003ab13  jb      short loc_14003AB3A
0x14003ab15  mov     rcx, [rbx+0A8h]; Lock
0x14003ab1c  lea     rdx, [rbp+4Fh+LockState]; LockState
0x14003ab20  mov     r8b, r15b; Flags
0x14003ab23  mov     [rbp+4Fh+var_B0], edi
0x14003ab26  mov     r12d, edi
0x14003ab29  call    cs:__imp_NdisAcquireRWLockWrite
0x14003ab30  nop     dword ptr [rax+rax+00h]
0x14003ab35  jmp     loc_14003ABC3
0x14003ab3a  lea     r14, [r13+20h]
0x14003ab3e  movsxd  rax, dword ptr [r14]
0x14003ab41  cmp     eax, cs:AfdStandardAddressLength
0x14003ab47  mov     rdx, rax
0x14003ab4a  ja      short loc_14003AB53
0x14003ab4c  call    AfdAllocateZeroedFromLookasideList
0x14003ab51  jmp     short loc_14003AB65
0x14003ab53  xor     r9d, r9d
0x14003ab56  mov     r8d, 52646641h
0x14003ab5c  lea     ecx, [r9+40h]
0x14003ab60  call    AfdAllocatePoolPriority
0x14003ab65  mov     [rbp+4Fh+var_A8], rax
0x14003ab69  test    rax, rax
0x14003ab6c  jnz     short loc_14003AB8E
0x14003ab6e  lea     rcx, [rbp+4Fh+LockHandle]; LockHandle
0x14003ab72  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003ab79  nop     dword ptr [rax+rax+00h]
0x14003ab7e  mov     edx, 157Fh
0x14003ab83  mov     r14d, 0C000009Ah
0x14003ab89  jmp     loc_14003A9C9
0x14003ab8e  mov     rcx, [rbx+0A8h]; Lock
0x14003ab95  lea     rdx, [rbp+4Fh+LockState]; LockState
0x14003ab99  mov     r8b, r15b; Flags
0x14003ab9c  call    cs:__imp_NdisAcquireRWLockWrite
0x14003aba3  nop     dword ptr [rax+rax+00h]
0x14003aba8  mov     eax, [rbx+0B0h]
0x14003abae  mov     r12, [rbx+0B8h]
0x14003abb5  mov     [rbp+4Fh+var_B0], eax
0x14003abb8  mov     rax, [rbp+4Fh+var_A8]
0x14003abbc  mov     [rbx+0B8h], rax
0x14003abc3  movsxd  r8, dword ptr [r14]; Size
0x14003abc6  mov     rdx, [r13+28h]; Src
0x14003abca  mov     rcx, [rbx+0B8h]; void *
0x14003abd1  call    memmove
0x14003abd6  mov     eax, [r14]
0x14003abd9  lea     rdx, [rbp+4Fh+LockState]; LockState
0x14003abdd  mov     rcx, [rbx+0A8h]; Lock
0x14003abe4  mov     [rbx+0B0h], eax
0x14003abea  call    cs:__imp_NdisReleaseRWLock
0x14003abf1  nop     dword ptr [rax+rax+00h]
0x14003abf6  mov     rax, [rbx+0B8h]
0x14003abfd  xor     r9d, r9d
0x14003ac00  mov     r8, rbx
0x14003ac03  mov     [rsp+20h], rax
0x14003ac08  mov     edx, 1580h
0x14003ac0d  xor     ecx, ecx
0x14003ac0f  call    AFDETW_TRACECONNECT
0x14003ac14  test    r12, r12
0x14003ac17  jz      short loc_14003AC49
0x14003ac19  mov     eax, [rbp+4Fh+var_B0]
0x14003ac1c  cmp     eax, cs:AfdStandardAddressLength
0x14003ac22  ja      short loc_14003AC35
0x14003ac24  mov     rcx, cs:PplAddressPool
0x14003ac2b  mov     rdx, r12
0x14003ac2e  call    PplFreeToLookasideList
0x14003ac33  jmp     short loc_14003AC49
0x14003ac35  mov     edx, 52646641h; Tag
0x14003ac3a  mov     rcx, r12; P
0x14003ac3d  call    cs:__imp_ExFreePoolWithTag
0x14003ac44  nop     dword ptr [rax+rax+00h]
0x14003ac49  mov     eax, [rbx+8]
0x14003ac4c  mov     ecx, 100h
0x14003ac51  test    ecx, eax
0x14003ac53  jnz     loc_14003AD39
0x14003ac59  test    dword ptr [rbx+10h], 8000h
0x14003ac60  jnz     loc_14003AD39
0x14003ac66  mov     eax, [rbx+8]
0x14003ac69  xor     r8d, r8d
0x14003ac6c  bts     eax, 19h
0x14003ac70  mov     byte ptr [rbx+2], 4
0x14003ac74  mov     rcx, rbx
0x14003ac77  mov     [rbx+8], eax
0x14003ac7a  lea     r14d, [r8+44h]
0x14003ac7e  mov     edx, r14d
0x14003ac81  call    AfdIndicateEventSelectEvent
0x14003ac86  xor     r8d, r8d
0x14003ac89  lea     edx, [r14-40h]
0x14003ac8d  mov     rcx, rbx
0x14003ac90  call    AfdNotifySockEventsChangedUnderLock
0x14003ac95  xor     r8d, r8d
0x14003ac98  lea     r9, [rbp+4Fh+LockHandle]
0x14003ac9c  mov     edx, r14d
0x14003ac9f  call    AfdIndicatePollEvent
0x14003aca4  test    al, al
0x14003aca6  lea     rdx, [rbp+4Fh+LockHandle]
0x14003acaa  mov     rcx, rbx
0x14003acad  cmovnz  rdx, rdi
0x14003acb1  xor     r8d, r8d
0x14003acb4  call    AfdNotifySockIndicateEventsUnlock
0x14003acb9  mov     rax, [rbx+0B8h]
0x14003acc0  mov     edx, 1581h
0x14003acc5  mov     r14d, edi
0x14003acc8  mov     r9d, r14d
0x14003accb  mov     [rsp+20h], rax
0x14003acd0  mov     r8, rbx
0x14003acd3  mov     ecx, r15d
0x14003acd6  call    AFDETW_TRACECONNECT
0x14003acdb  mov     eax, edi
0x14003acdd  xchg    eax, [rbx+170h]
0x14003ace3  mov     rcx, [rbp+4Fh+Object]; Object
0x14003ace7  mov     ebx, [rbx+8]
0x14003acea  call    cs:__imp_ObfDereferenceObject
0x14003acf1  nop     dword ptr [rax+rax+00h]
0x14003acf6  bt      ebx, 8
0x14003acfa  jb      short loc_14003AD14
0x14003acfc  mov     edx, 49646641h; Tag
0x14003ad01  mov     rcx, r13; P
0x14003ad04  call    cs:__imp_ExFreePoolWithTag
0x14003ad0b  nop     dword ptr [rax+rax+00h]
0x14003ad10  mov     [rsi+18h], rdi
0x14003ad14  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14003ad1a  mov     rcx, rsi; Irp
0x14003ad1d  mov     [rsi+38h], rdi
0x14003ad21  mov     [rsi+30h], r14d
0x14003ad25  call    cs:__imp_IofCompleteRequest
0x14003ad2c  nop     dword ptr [rax+rax+00h]
0x14003ad31  mov     eax, r14d
0x14003ad34  jmp     loc_14003AE2C
0x14003ad39  mov     rax, [rbx+18h]
0x14003ad3d  mov     r8d, ecx
0x14003ad40  mov     r12, [rbx+28h]
0x14003ad44  xor     edx, edx
0x14003ad46  mov     [rbp+4Fh+Object], rax
0x14003ad4a  mov     rcx, rbx
0x14003ad4d  mov     eax, [rbx+48h]
0x14003ad50  btr     eax, 8
0x14003ad54  mov     [rbx+1B4h], edi
0x14003ad5a  mov     [rbx+48h], eax
0x14003ad5d  call    AfdNotifySockEventsChangedUnderLock
0x14003ad62  mov     ecx, [rbx+8]
0x14003ad65  bt      ecx, 16h
0x14003ad69  jnb     short loc_14003ADA7
0x14003ad6b  mov     rcx, [r13+28h]
0x14003ad6f  mov     rdx, r14
0x14003ad72  call    AfdTdi_TA6toTA4_InPlace
0x14003ad77  test    al, al
0x14003ad79  jz      short loc_14003AD93
0x14003ad7b  mov     rax, [rbx+118h]
0x14003ad82  mov     rdi, [rax+8]
0x14003ad86  mov     r12, [rax+10h]
0x14003ad8a  or      dword ptr [rbx+0C0h], 20h
0x14003ad91  jmp     short loc_14003ADBD
0x14003ad93  mov     eax, [rbx+0C0h]
0x14003ad99  and     eax, 0FFFFFFDFh
0x14003ad9c  or      eax, 40h
0x14003ad9f  mov     [rbx+0C0h], eax
0x14003ada5  jmp     short loc_14003ADB9
0x14003ada7  bt      ecx, 15h
0x14003adab  jnb     short loc_14003ADB9
0x14003adad  mov     rcx, [r13+28h]
0x14003adb1  mov     rdx, r14
0x14003adb4  call    AfdTdi_TA6toTA4_InPlace
0x14003adb9  mov     rdi, [rbp+4Fh+Object]
0x14003adbd  xor     r8d, r8d
0x14003adc0  lea     rdx, [rbp+4Fh+LockHandle]
0x14003adc4  mov     rcx, rbx
0x14003adc7  call    AfdNotifySockIndicateEventsUnlock
0x14003adcc  mov     rax, [rsi+0B8h]
0x14003add3  lea     rcx, AfdRestartDgConnect
0x14003adda  mov     [rax-10h], rcx
0x14003adde  mov     [rax-8], rbx
0x14003ade2  mov     byte ptr [rax-45h], 0E0h
0x14003ade6  lea     rax, [r13+30h]
  ... truncated ...
```
