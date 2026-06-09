# AfdCompleteTPackets

- ea: `0x140042270`
- end: `0x140042904`
- name: `AfdCompleteTPackets`
- size: `1684`
- prototype: `void __fastcall(PIRP Irp)`
- caller_count: `10`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400343d0`
- `0x1400550a0`
- `0x14005544c`
- `0x140055e08`
- `0x140056170`
- `0x1400562a0`
- `0x140056704`
- `0x140056f20`
- `0x140057100`
- `0x140057a30`

## callees

- `0x14001c708`
- `0x14001ccdc`
- `0x14001d524`
- `0x14002dd90`
- `0x1400404a0`
- `0x140042270`
- `0x14004290c`
- `0x1400436b8`
- `0x140043ef8`
- `0x140043fcc`
- `0x1400559d4`
- `0x140055d74`
- `0x140055e08`
- `0x140056478`
- `0x140093008`
- `0x14009304c`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140042440`
- `ntoskrnl!IoFreeIrp` at `0x140042440`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400422c1`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400422c1`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400426b2`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400426b2`
- `ntoskrnl!IofCompleteRequest` at `0x14004273f`
- `ntoskrnl!IofCompleteRequest` at `0x14004273f`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400426a3`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400426a3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140042541`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140042592`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004262c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400426d5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400427fc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140042832`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140042541`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140042592`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004262c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400426d5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400427fc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140042832`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140042463`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400425b2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400426c5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140042463`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400425b2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400426c5`

## pseudocode

```c
void __fastcall AfdCompleteTPackets(PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r13
  struct _IRP *MasterIrp; // rsi
  char *FsContext; // r15
  char v5; // bl
  KIRQL CurrentIrql; // al
  __int64 v7; // rdx
  union _IRP::$CBBBB9F4F0755A16DC8A369061485BEC *p_AssociatedIrp; // r13
  int i; // r12d
  __int64 v10; // rax
  struct _IRP *v11; // rcx
  bool v12; // cf
  bool v13; // zf
  struct _LIST_ENTRY **p_Blink; // rdx
  PIRP v15; // rdx
  __int64 (__fastcall *v16)(PIRP); // rcx
  struct _IRP *v17; // rcx
  struct _LIST_ENTRY **v18; // rdx
  IRP *Information; // rcx
  KSPIN_LOCK *v20; // r12
  __int64 v21; // rdx
  __int64 v22; // r14
  struct _LIST_ENTRY *Flink; // rcx
  __int64 v24; // r14
  __int64 v25; // rax
  __int64 v26; // r12
  IRP *v27; // rdx
  struct _LIST_ENTRY *v28; // rax
  __int64 v29; // rcx
  signed __int64 v30; // rax
  bool v31; // cc
  signed __int64 v32; // rax
  struct _LIST_ENTRY *Blink; // r15
  __int64 v34; // rdx
  __int64 v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-20h] BYREF
  KIRQL Irql; // [rsp+90h] [rbp+40h] BYREF
  struct _IO_STACK_LOCATION *v40; // [rsp+98h] [rbp+48h]

  while ( 1 )
  {
    memset(&LockHandle, 0, sizeof(LockHandle));
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    MasterIrp = Irp->AssociatedIrp.MasterIrp;
    v40 = CurrentStackLocation;
    FsContext = (char *)CurrentStackLocation->FileObject->FsContext;
    v5 = BYTE1(*((_DWORD *)FsContext + 2)) & 1;
    if ( MasterIrp )
    {
      CurrentIrql = KeGetCurrentIrql();
      v7 = CurrentIrql;
      Irql = CurrentIrql;
      if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
      {
        WPP_SF_qD(1042, 44, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids, MasterIrp, CurrentIrql);
        LOBYTE(v7) = Irql;
      }
      p_AssociatedIrp = &MasterIrp->AssociatedIrp;
      if ( MasterIrp->AssociatedIrp.MasterIrp )
      {
        MasterIrp->ThreadListEntry.Flink = (struct _LIST_ENTRY *)p_AssociatedIrp;
        LOBYTE(v7) = (unsigned __int8)v7 <= 1u;
        MasterIrp->IoStatus.Pointer = &MasterIrp->ThreadListEntry.Blink;
        if ( !(unsigned __int8)AfdCleanupPacketChain(Irp, v7) )
        {
LABEL_12:
          v15 = Irp;
          v16 = AfdCompleteTPackets;
LABEL_98:
          AfdStartTPacketsWorker(v16, v15);
          return;
        }
      }
      for ( i = 0; i < WORD2(MasterIrp->UserEvent); ++i )
      {
        v10 = *((_QWORD *)&MasterIrp->Tail.Overlay.OriginalFileObject + i);
        if ( v5 )
        {
          if ( v10 )
          {
            v11 = *(struct _IRP **)(v10 + 32);
            if ( v11 )
            {
              v12 = Irql == 0;
              v13 = Irql == 1;
              p_Blink = &MasterIrp->ThreadListEntry.Blink;
              p_AssociatedIrp->MasterIrp = v11;
              MasterIrp->ThreadListEntry.Flink = (struct _LIST_ENTRY *)p_AssociatedIrp;
              *(_QWORD *)(*((_QWORD *)&MasterIrp->Tail.Overlay.OriginalFileObject + i) + 32LL) = 0;
              MasterIrp->ThreadListEntry.Blink = *(struct _LIST_ENTRY **)(*((_QWORD *)&MasterIrp->Tail.Overlay.OriginalFileObject
                                                                          + i)
                                                                        + 40LL);
              MasterIrp->IoStatus.Pointer = &MasterIrp->ThreadListEntry.Blink;
              LOBYTE(p_Blink) = v12 || v13;
              *(_QWORD *)(*((_QWORD *)&MasterIrp->Tail.Overlay.OriginalFileObject + i) + 40LL) = 0;
              if ( !(unsigned __int8)AfdCleanupPacketChain(Irp, p_Blink) )
                goto LABEL_12;
            }
          }
        }
        else if ( v10 )
        {
          v17 = *(struct _IRP **)(v10 + 8);
          if ( v17 )
          {
            v12 = Irql == 0;
            v13 = Irql == 1;
            v18 = &MasterIrp->ThreadListEntry.Blink;
            p_AssociatedIrp->MasterIrp = v17;
            MasterIrp->ThreadListEntry.Flink = (struct _LIST_ENTRY *)p_AssociatedIrp;
            *(_QWORD *)(*((_QWORD *)&MasterIrp->Tail.Overlay.OriginalFileObject + i) + 8LL) = 0;
            MasterIrp->ThreadListEntry.Blink = *(struct _LIST_ENTRY **)(*((_QWORD *)&MasterIrp->Tail.Overlay.OriginalFileObject
                                                                        + i)
                                                                      + 96LL);
            MasterIrp->IoStatus.Pointer = &MasterIrp->ThreadListEntry.Blink;
            LOBYTE(v18) = v12 || v13;
            *(_QWORD *)(*((_QWORD *)&MasterIrp->Tail.Overlay.OriginalFileObject + i) + 96LL) = 0;
            if ( !(unsigned __int8)AfdCleanupPacketChain(Irp, v18) )
              goto LABEL_12;
          }
          *(_BYTE *)(*((_QWORD *)&MasterIrp->Tail.Overlay.OriginalFileObject + i) + 68LL) = 0;
        }
      }
      Information = (IRP *)MasterIrp->IoStatus.Information;
      if ( Information )
      {
        IoFreeIrp(Information);
        MasterIrp->IoStatus.Information = 0;
      }
      CurrentStackLocation = v40;
    }
    v20 = (KSPIN_LOCK *)(FsContext + 56);
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)FsContext + 7, &LockHandle);
    if ( Irp->IoStatus.Status >= 0 && (*(_DWORD *)(&Irp->Tail.CompletionKey + 1) & 2) != 0 )
    {
      v22 = *((_QWORD *)FsContext + 24);
      if ( v22 )
      {
        *(_DWORD *)(v22 + 4) |= 0x1100000u;
        *((_QWORD *)FsContext + 24) = 0;
        AfdCleanupConnectionTimerWheelEntry(v22, v21);
        *((_QWORD *)FsContext + 44) = v22;
        CurrentStackLocation->Parameters.CreatePipe.Parameters = (PNAMED_PIPE_CREATE_PARAMETERS)v22;
        Irp->AssociatedIrp.MasterIrp = (struct _IRP *)-1LL;
        if ( v5 || (*(_DWORD *)(v22 + 4) & 0x110) != 0 || (Irp->Tail.Overlay.DeviceQueueEntry.SortKey & 0x400) == 0 )
        {
          LOBYTE(v34) = 1;
          AfdDeleteConnectedReference(v22, v34);
          KeReleaseInStackQueuedSpinLock(&LockHandle);
        }
        else
        {
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          AfdCommonDisconnectEventHandler(v22, 0, 0, 0, 0, 0);
        }
        v35 = _InterlockedDecrement64((volatile signed __int64 *)(v22 + 48));
        if ( v35 <= 0 )
        {
          if ( v35 )
            __fastfail(0xEu);
          AfdCloseConnection(v22);
        }
        if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
          WPP_SF_q(1042, 45, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids, MasterIrp);
        if ( MasterIrp )
        {
          v36 = *(_QWORD *)&MasterIrp->Flags;
          if ( v36 )
          {
            v37 = _InterlockedDecrement64((volatile signed __int64 *)(v36 + 48));
            if ( v37 <= 0 )
            {
              if ( v37 )
                __fastfail(0xEu);
              AfdCloseConnection(*(_QWORD *)&MasterIrp->Flags);
            }
            *(_QWORD *)&MasterIrp->Flags = 0;
          }
          AfdReturnTpInfo(MasterIrp);
        }
        return;
      }
    }
    while ( 1 )
    {
      Flink = Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
      v24 = 0;
      if ( !Flink )
        break;
      v24 = (__int64)&Flink[-8].Blink;
      if ( (*((_DWORD *)FsContext + 2) & 0x800) != 0
        || (((__int64)Flink->Blink & 1) == 0 || *(_QWORD *)(v24 + 24))
        && ((*(_WORD *)FsContext + 20528) & 0xFFF9) == 0
        && (v25 = *((_QWORD *)FsContext + 24)) != 0
        && (*(_DWORD *)(v25 + 4) & 0x10) != 0 )
      {
        if ( ((__int64)Flink[1].Flink & 0x20) == 0 )
        {
          if ( (unsigned __int8)AfdGetTPacketsReference(&Flink[-8].Blink) )
          {
LABEL_43:
            *(_BYTE *)(v24 + 68) = 1;
            break;
          }
LABEL_44:
          v24 = 0;
          break;
        }
        LODWORD(Flink[1].Flink) &= ~0x20u;
        if ( ((__int64)Flink[1].Flink & 0x100) == 0 )
          goto LABEL_43;
        Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = Flink->Flink;
        HIDWORD(Flink->Blink) = 0;
        LODWORD(Flink[1].Flink) |= 1u;
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        AfdSendQueuedTPSend(FsContext, 0, v24);
      }
      else
      {
        if ( *((PIRP *)FsContext + 45) != Irp || ((__int64)Flink[1].Flink & 0x20) == 0 )
          goto LABEL_44;
        LODWORD(Flink[1].Flink) &= ~0x20u;
        if ( ((__int64)Flink[1].Flink & 0x100) == 0 )
          break;
        if ( (*(_WORD *)FsContext & 0xAFD2) == 0xAFD2 )
          v26 = *((_QWORD *)FsContext + 24);
        else
          v26 = 0;
        Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = Flink->Flink;
        HIDWORD(Flink->Blink) = 0;
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        AfdSendQueuedTPSend(FsContext, v26, v24);
        v20 = (KSPIN_LOCK *)(FsContext + 56);
      }
      KeAcquireInStackQueuedSpinLock(v20, &LockHandle);
    }
    v27 = (IRP *)*((_QWORD *)FsContext + 45);
    if ( v27 == Irp )
    {
      *((_QWORD *)FsContext + 45) = (__int64)&Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink[-8].Blink
                                  & -(__int64)(Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink != 0);
    }
    else
    {
      if ( (PIRP)&v27->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink[-8].Blink != Irp )
      {
        do
        {
          v28 = v27->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
          v27 = (IRP *)&v28[-8].Blink;
        }
        while ( (PIRP)&v28->Flink[-8].Blink != Irp );
      }
      v27->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( MasterIrp )
    {
      v29 = *(_QWORD *)&MasterIrp->Flags;
      if ( v29 )
      {
        v30 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v29 + 48), 0xFFFFFFFFFFFFFFFFuLL);
        v31 = v30 <= 1;
        v32 = v30 - 1;
        if ( v31 )
        {
          if ( v32 )
            __fastfail(0xEu);
          AfdCloseConnection(*(_QWORD *)&MasterIrp->Flags);
        }
        *(_QWORD *)&MasterIrp->Flags = 0;
      }
    }
    if ( (Irp->Tail.Overlay.DeviceQueueEntry.SortKey & 0x100) != 0 )
    {
      AfdSendQueuedTPSend(FsContext, 0, Irp);
    }
    else
    {
      if ( !_InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0) )
      {
        Irql = 0;
        IoAcquireCancelSpinLock(&Irql);
        IoReleaseCancelSpinLock(Irql);
        KeAcquireInStackQueuedSpinLock(v20, &LockHandle);
        KeReleaseInStackQueuedSpinLock(&LockHandle);
      }
      if ( (*(_DWORD *)(&Irp->Tail.CompletionKey + 1) & 1) != 0 )
        _InterlockedExchange((volatile __int32 *)FsContext + 92, 0);
      Blink = Irp->Tail.Overlay.ListEntry.Blink;
      if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
        WPP_SF_qq(1042, 46, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids, MasterIrp, Irp);
      if ( MasterIrp )
      {
        Irp->AssociatedIrp.MasterIrp = 0;
        AfdReturnTpInfo(MasterIrp);
      }
      IofCompleteRequest(Irp, AfdPriorityBoost);
      if ( AfdMaxActiveTransmitFileCount && !Blink )
        AfdStartNextQueuedTransmit();
    }
    if ( !v24 )
      return;
    if ( *(_BYTE *)(v24 + 68) )
    {
      AfdAbortTPackets(v24, -1073741536);
      goto LABEL_75;
    }
    if ( *(_QWORD *)(v24 + 24) )
      break;
    AfdPerformTpDisconnect(v24);
LABEL_75:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v24 + 132), 0xFFFFFFFF) != 1 )
      return;
    Irp = (PIRP)v24;
  }
  if ( !AfdMaxActiveTransmitFileCount || !(unsigned __int8)AfdQueueTransmit((PIRP)v24) )
  {
    v15 = (PIRP)v24;
    v16 = AfdTPacketsWorker;
    goto LABEL_98;
  }
}

```

## disassembly

```asm
0x140042270  mov     [rsp-38h+arg_10], rbx
0x140042275  push    rbp
0x140042276  push    rsi
0x140042277  push    rdi
0x140042278  push    r12
0x14004227a  push    r13
0x14004227c  push    r14
0x14004227e  push    r15
0x140042280  mov     rbp, rsp
0x140042283  sub     rsp, 50h
0x140042287  mov     rdi, rcx
0x14004228a  xor     eax, eax
0x14004228c  xorps   xmm0, xmm0
0x14004228f  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140042293  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140042297  mov     r13, [rdi+0B8h]
0x14004229e  mov     rsi, [rdi+18h]
0x1400422a2  mov     [rbp+arg_8], r13
0x1400422a6  mov     rax, [r13+30h]
0x1400422aa  mov     r15, [rax+18h]
0x1400422ae  mov     ebx, [r15+8]
0x1400422b2  shr     ebx, 8
0x1400422b5  and     bl, 1
0x1400422b8  test    rsi, rsi
0x1400422bb  jz      loc_140042458
0x1400422c1  call    cs:__imp_KeGetCurrentIrql
0x1400422c8  nop     dword ptr [rax+rax+00h]
0x1400422cd  movzx   edx, al
0x1400422d0  mov     [rbp+Irql], dl
0x1400422d3  test    byte ptr cs:xmmword_1400875E0+2, 4
0x1400422da  jz      short loc_140042300
0x1400422dc  mov     r8d, edx
0x1400422df  mov     ecx, 412h
0x1400422e4  mov     dword ptr [rsp+50h+var_30], r8d
0x1400422e9  mov     edx, 2Ch ; ','
0x1400422ee  lea     r8, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids
0x1400422f5  mov     r9, rsi
0x1400422f8  call    WPP_SF_qD
0x1400422fd  mov     dl, [rbp+Irql]
0x140042300  lea     r13, [rsi+18h]
0x140042304  cmp     qword ptr [r13+0], 0
0x140042309  jz      short loc_14004232D
0x14004230b  cmp     dl, 1
0x14004230e  mov     [rsi+20h], r13
0x140042312  lea     rax, [rsi+28h]
0x140042316  mov     rcx, rdi
0x140042319  setbe   dl
0x14004231c  mov     [rsi+30h], rax
0x140042320  call    AfdCleanupPacketChain
0x140042325  test    al, al
0x140042327  jz      loc_1400423B4
0x14004232d  xor     r12d, r12d
0x140042330  movzx   eax, word ptr [rsi+54h]
0x140042334  cmp     r12d, eax
0x140042337  jge     loc_140042437
0x14004233d  movsxd  r14, r12d
0x140042340  mov     rax, [rsi+r14*8+0C0h]
0x140042348  test    bl, bl
0x14004234a  jz      short loc_1400423C3
0x14004234c  test    rax, rax
0x14004234f  jz      loc_14004242F
0x140042355  mov     rcx, [rax+20h]
0x140042359  test    rcx, rcx
0x14004235c  jz      loc_14004242F
0x140042362  cmp     [rbp+Irql], 1
0x140042366  lea     rdx, [rsi+28h]
0x14004236a  mov     [r13+0], rcx
0x14004236e  mov     [rsi+20h], r13
0x140042372  mov     rax, [rsi+r14*8+0C0h]
0x14004237a  mov     qword ptr [rax+20h], 0
0x140042382  mov     rax, [rsi+r14*8+0C0h]
0x14004238a  mov     rcx, [rax+28h]
0x14004238e  mov     [rdx], rcx
0x140042391  mov     rcx, rdi
0x140042394  mov     [rsi+30h], rdx
0x140042398  setbe   dl
0x14004239b  mov     rax, [rsi+r14*8+0C0h]
0x1400423a3  mov     qword ptr [rax+28h], 0
0x1400423ab  call    AfdCleanupPacketChain
0x1400423b0  test    al, al
0x1400423b2  jnz     short loc_14004242F
0x1400423b4  mov     rdx, rdi
0x1400423b7  lea     rcx, AfdCompleteTPackets
0x1400423be  jmp     loc_1400428E6
0x1400423c3  test    rax, rax
0x1400423c6  jz      short loc_14004242F
0x1400423c8  mov     rcx, [rax+8]
0x1400423cc  test    rcx, rcx
0x1400423cf  jz      short loc_140042423
0x1400423d1  cmp     [rbp+Irql], 1
0x1400423d5  lea     rdx, [rsi+28h]
0x1400423d9  mov     [r13+0], rcx
0x1400423dd  mov     [rsi+20h], r13
0x1400423e1  mov     rax, [rsi+r14*8+0C0h]
0x1400423e9  mov     qword ptr [rax+8], 0
0x1400423f1  mov     rax, [rsi+r14*8+0C0h]
0x1400423f9  mov     rcx, [rax+60h]
0x1400423fd  mov     [rdx], rcx
0x140042400  mov     rcx, rdi
0x140042403  mov     [rsi+30h], rdx
0x140042407  setbe   dl
0x14004240a  mov     rax, [rsi+r14*8+0C0h]
0x140042412  mov     qword ptr [rax+60h], 0
0x14004241a  call    AfdCleanupPacketChain
0x14004241f  test    al, al
0x140042421  jz      short loc_1400423B4
0x140042423  mov     rax, [rsi+r14*8+0C0h]
0x14004242b  mov     byte ptr [rax+44h], 0
0x14004242f  inc     r12d
0x140042432  jmp     loc_140042330
0x140042437  mov     rcx, [rsi+38h]; Irp
0x14004243b  test    rcx, rcx
0x14004243e  jz      short loc_140042454
0x140042440  call    cs:__imp_IoFreeIrp
0x140042447  nop     dword ptr [rax+rax+00h]
0x14004244c  mov     qword ptr [rsi+38h], 0
0x140042454  mov     r13, [rbp+arg_8]
0x140042458  lea     r12, [r15+38h]
0x14004245c  mov     rcx, r12; SpinLock
0x14004245f  lea     rdx, [rbp+LockHandle]; LockHandle
0x140042463  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004246a  nop     dword ptr [rax+rax+00h]
0x14004246f  cmp     dword ptr [rdi+30h], 0
0x140042473  jl      short loc_14004248F
0x140042475  mov     eax, [rdi+80h]
0x14004247b  test    al, 2
0x14004247d  jz      short loc_14004248F
0x14004247f  mov     r14, [r15+0C0h]
0x140042486  test    r14, r14
0x140042489  jnz     loc_1400427AB
0x14004248f  xor     r13d, r13d
0x140042492  mov     rcx, [rdi+78h]
0x140042496  mov     r14, r13
0x140042499  test    rcx, rcx
0x14004249c  jz      loc_1400425D9
0x1400424a2  test    dword ptr [r15+8], 800h
0x1400424aa  lea     r14, [rcx-78h]
0x1400424ae  jnz     loc_140042561
0x1400424b4  mov     eax, [rcx+8]
0x1400424b7  test    al, 1
0x1400424b9  jz      short loc_1400424C1
0x1400424bb  cmp     [r14+18h], r13
0x1400424bf  jz      short loc_1400424E7
0x1400424c1  mov     eax, 5030h
0x1400424c6  mov     edx, 0FFF9h
0x1400424cb  add     ax, [r15]
0x1400424cf  test    dx, ax
0x1400424d2  jnz     short loc_1400424E7
0x1400424d4  mov     rax, [r15+0C0h]
0x1400424db  test    rax, rax
0x1400424de  jz      short loc_1400424E7
0x1400424e0  mov     eax, [rax+4]
0x1400424e3  test    al, 10h
0x1400424e5  jnz     short loc_140042561
0x1400424e7  cmp     [r15+168h], rdi
0x1400424ee  jnz     loc_1400425D6
0x1400424f4  mov     eax, [rcx+10h]
0x1400424f7  test    al, 20h
0x1400424f9  jz      loc_1400425D6
0x1400424ff  mov     eax, [rcx+10h]
0x140042502  and     eax, 0FFFFFFDFh
0x140042505  mov     [rcx+10h], eax
0x140042508  mov     eax, [rcx+10h]
0x14004250b  bt      eax, 8
0x14004250f  jnb     loc_1400425D9
0x140042515  movzx   eax, word ptr [r15]
0x140042519  mov     edx, 0AFD2h
0x14004251e  and     ax, dx
0x140042521  cmp     ax, dx
0x140042524  jnz     short loc_14004252F
0x140042526  mov     r12, [r15+0C0h]
0x14004252d  jmp     short loc_140042532
0x14004252f  mov     r12, r13
0x140042532  mov     rax, [rcx]
0x140042535  mov     [rdi+78h], rax
0x140042539  mov     [rcx+0Ch], r13d
0x14004253d  lea     rcx, [rbp+LockHandle]; LockHandle
0x140042541  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140042548  nop     dword ptr [rax+rax+00h]
0x14004254d  mov     r8, r14
0x140042550  mov     rdx, r12
0x140042553  mov     rcx, r15
0x140042556  call    AfdSendQueuedTPSend
0x14004255b  lea     r12, [r15+38h]
0x14004255f  jmp     short loc_1400425AB
0x140042561  mov     eax, [rcx+10h]
0x140042564  test    al, 20h
0x140042566  jz      short loc_1400425C3
0x140042568  mov     eax, [rcx+10h]
0x14004256b  and     eax, 0FFFFFFDFh
0x14004256e  mov     [rcx+10h], eax
0x140042571  mov     eax, [rcx+10h]
0x140042574  bt      eax, 8
0x140042578  jnb     short loc_1400425CF
0x14004257a  mov     rax, [rcx]
0x14004257d  mov     [rdi+78h], rax
0x140042581  mov     [rcx+0Ch], r13d
0x140042585  mov     eax, [rcx+10h]
0x140042588  or      eax, 1
0x14004258b  mov     [rcx+10h], eax
0x14004258e  lea     rcx, [rbp+LockHandle]; LockHandle
0x140042592  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140042599  nop     dword ptr [rax+rax+00h]
0x14004259e  mov     r8, r14
0x1400425a1  xor     edx, edx
0x1400425a3  mov     rcx, r15
0x1400425a6  call    AfdSendQueuedTPSend
0x1400425ab  lea     rdx, [rbp+LockHandle]; LockHandle
0x1400425af  mov     rcx, r12; SpinLock
0x1400425b2  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400425b9  nop     dword ptr [rax+rax+00h]
0x1400425be  jmp     loc_140042492
0x1400425c3  mov     rcx, r14
0x1400425c6  call    AfdGetTPacketsReference
0x1400425cb  test    al, al
0x1400425cd  jz      short loc_1400425D6
0x1400425cf  mov     byte ptr [r14+44h], 1
0x1400425d4  jmp     short loc_1400425D9
0x1400425d6  mov     r14, r13
0x1400425d9  mov     rdx, [r15+168h]
0x1400425e0  cmp     rdx, rdi
0x1400425e3  jnz     short loc_1400425FF
0x1400425e5  mov     rax, [rdi+78h]
0x1400425e9  lea     rcx, [rax-78h]
0x1400425ed  neg     rax
0x1400425f0  sbb     rax, rax
0x1400425f3  and     rax, rcx
0x1400425f6  mov     [r15+168h], rax
0x1400425fd  jmp     short loc_140042628
0x1400425ff  mov     rax, [rdx+78h]
0x140042603  sub     rax, 78h ; 'x'
0x140042607  cmp     rax, rdi
0x14004260a  jz      short loc_140042620
0x14004260c  mov     rax, [rdx+78h]
0x140042610  mov     rcx, [rax]
0x140042613  lea     rdx, [rax-78h]
0x140042617  sub     rcx, 78h ; 'x'
0x14004261b  cmp     rcx, rdi
0x14004261e  jnz     short loc_14004260C
0x140042620  mov     rax, [rdi+78h]
0x140042624  mov     [rdx+78h], rax
0x140042628  lea     rcx, [rbp+LockHandle]; LockHandle
0x14004262c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140042633  nop     dword ptr [rax+rax+00h]
0x140042638  test    rsi, rsi
0x14004263b  jz      short loc_140042671
0x14004263d  mov     rcx, [rsi+10h]
0x140042641  test    rcx, rcx
0x140042644  jz      short loc_140042671
0x140042646  or      rax, 0FFFFFFFFFFFFFFFFh
0x14004264a  lock xadd [rcx+30h], rax
0x140042650  sub     rax, 1
0x140042654  jg      short loc_14004266D
0x140042656  test    rax, rax
0x140042659  jnz     short loc_140042666
0x14004265b  mov     rcx, [rsi+10h]
0x14004265f  call    AfdCloseConnection
0x140042664  jmp     short loc_14004266D
0x140042666  mov     ecx, 0Eh
0x14004266b  int     29h; Win8: RtlFailFast(ecx)
0x14004266d  mov     [rsi+10h], r13
0x140042671  mov     eax, [rdi+88h]
0x140042677  bt      eax, 8
0x14004267b  jnb     short loc_14004268F
0x14004267d  mov     r8, rdi
0x140042680  xor     edx, edx
0x140042682  mov     rcx, r15
0x140042685  call    AfdSendQueuedTPSend
0x14004268a  jmp     loc_14004275E
0x14004268f  mov     rax, r13
0x140042692  xchg    rax, [rdi+68h]
0x140042696  test    rax, rax
0x140042699  jnz     short loc_1400426E1
0x14004269b  lea     rcx, [rbp+Irql]; Irql
0x14004269f  mov     [rbp+Irql], r13b
0x1400426a3  call    cs:__imp_IoAcquireCancelSpinLock
0x1400426aa  nop     dword ptr [rax+rax+00h]
0x1400426af  mov     cl, [rbp+Irql]; Irql
0x1400426b2  call    cs:__imp_IoReleaseCancelSpinLock
0x1400426b9  nop     dword ptr [rax+rax+00h]
0x1400426be  lea     rdx, [rbp+LockHandle]; LockHandle
0x1400426c2  mov     rcx, r12; SpinLock
0x1400426c5  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400426cc  nop     dword ptr [rax+rax+00h]
0x1400426d1  lea     rcx, [rbp+LockHandle]; LockHandle
0x1400426d5  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400426dc  nop     dword ptr [rax+rax+00h]
0x1400426e1  mov     eax, [rdi+80h]
0x1400426e7  test    al, 1
0x1400426e9  jz      short loc_1400426F5
0x1400426eb  mov     eax, r13d
0x1400426ee  xchg    eax, [r15+170h]
0x1400426f5  mov     r15, [rdi+0B0h]
0x1400426fc  test    byte ptr cs:xmmword_1400875E0+2, 4
0x140042703  jz      short loc_140042723
0x140042705  mov     edx, 2Eh ; '.'
0x14004270a  mov     [rsp+50h+var_30], rdi
0x14004270f  mov     ecx, 412h
0x140042714  lea     r8, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids
0x14004271b  mov     r9, rsi
  ... truncated ...
```
