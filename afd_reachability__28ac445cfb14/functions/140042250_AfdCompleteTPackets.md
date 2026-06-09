# AfdCompleteTPackets

- ea: `0x140042250`
- end: `0x1400428e4`
- name: `AfdCompleteTPackets`
- size: `1684`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `10`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400343b0`
- `0x140055000`
- `0x1400553ac`
- `0x140055d68`
- `0x1400560d0`
- `0x140056200`
- `0x140056664`
- `0x140056e80`
- `0x140057060`
- `0x140057940`

## callees

- `0x14001c708`
- `0x14001ccdc`
- `0x14001d524`
- `0x14002dd90`
- `0x140040480`
- `0x140042250`
- `0x1400428ec`
- `0x140043698`
- `0x140043ed8`
- `0x140043fac`
- `0x140055934`
- `0x140055cd4`
- `0x140055d68`
- `0x1400563d8`
- `0x140093008`
- `0x14009304c`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140042420`
- `ntoskrnl!IoFreeIrp` at `0x140042420`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400422a1`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400422a1`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140042692`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140042692`
- `ntoskrnl!IofCompleteRequest` at `0x14004271f`
- `ntoskrnl!IofCompleteRequest` at `0x14004271f`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140042683`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140042683`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140042521`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140042572`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004260c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400426b5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400427dc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140042812`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140042521`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140042572`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004260c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400426b5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400427dc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140042812`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140042443`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140042592`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400426a5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140042443`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140042592`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400426a5`

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
  struct _LIST_ENTRY **v24; // r14
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
        WPP_SF_qD(1042, 44, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids, MasterIrp, CurrentIrql);
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
          WPP_SF_q(1042, 45, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids, MasterIrp);
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
      v24 = &Flink[-8].Blink;
      if ( (*((_DWORD *)FsContext + 2) & 0x800) != 0
        || (((__int64)Flink->Blink & 1) == 0 || v24[3])
        && ((*(_WORD *)FsContext + 20528) & 0xFFF9) == 0
        && (v25 = *((_QWORD *)FsContext + 24)) != 0
        && (*(_DWORD *)(v25 + 4) & 0x10) != 0 )
      {
        if ( ((__int64)Flink[1].Flink & 0x20) == 0 )
        {
          if ( (unsigned __int8)AfdGetTPacketsReference(&Flink[-8].Blink) )
          {
LABEL_43:
            *((_BYTE *)v24 + 68) = 1;
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
        WPP_SF_qq(1042, 46, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids, MasterIrp, Irp);
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
    if ( *((_BYTE *)v24 + 68) )
    {
      AfdAbortTPackets(v24, 3221225760LL);
      goto LABEL_75;
    }
    if ( v24[3] )
      break;
    AfdPerformTpDisconnect(v24);
LABEL_75:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 33, 0xFFFFFFFF) != 1 )
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
0x140042250  mov     [rsp-38h+arg_10], rbx
0x140042255  push    rbp
0x140042256  push    rsi
0x140042257  push    rdi
0x140042258  push    r12
0x14004225a  push    r13
0x14004225c  push    r14
0x14004225e  push    r15
0x140042260  mov     rbp, rsp
0x140042263  sub     rsp, 50h
0x140042267  mov     rdi, rcx
0x14004226a  xor     eax, eax
0x14004226c  xorps   xmm0, xmm0
0x14004226f  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140042273  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140042277  mov     r13, [rdi+0B8h]
0x14004227e  mov     rsi, [rdi+18h]
0x140042282  mov     [rbp+arg_8], r13
0x140042286  mov     rax, [r13+30h]
0x14004228a  mov     r15, [rax+18h]
0x14004228e  mov     ebx, [r15+8]
0x140042292  shr     ebx, 8
0x140042295  and     bl, 1
0x140042298  test    rsi, rsi
0x14004229b  jz      loc_140042438
0x1400422a1  call    cs:__imp_KeGetCurrentIrql
0x1400422a8  nop     dword ptr [rax+rax+00h]
0x1400422ad  movzx   edx, al
0x1400422b0  mov     [rbp+Irql], dl
0x1400422b3  test    byte ptr cs:xmmword_1400875E0+2, 4
0x1400422ba  jz      short loc_1400422E0
0x1400422bc  mov     r8d, edx
0x1400422bf  mov     ecx, 412h
0x1400422c4  mov     dword ptr [rsp+50h+var_30], r8d
0x1400422c9  mov     edx, 2Ch ; ','
0x1400422ce  lea     r8, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids
0x1400422d5  mov     r9, rsi
0x1400422d8  call    WPP_SF_qD
0x1400422dd  mov     dl, [rbp+Irql]
0x1400422e0  lea     r13, [rsi+18h]
0x1400422e4  cmp     qword ptr [r13+0], 0
0x1400422e9  jz      short loc_14004230D
0x1400422eb  cmp     dl, 1
0x1400422ee  mov     [rsi+20h], r13
0x1400422f2  lea     rax, [rsi+28h]
0x1400422f6  mov     rcx, rdi
0x1400422f9  setbe   dl
0x1400422fc  mov     [rsi+30h], rax
0x140042300  call    AfdCleanupPacketChain
0x140042305  test    al, al
0x140042307  jz      loc_140042394
0x14004230d  xor     r12d, r12d
0x140042310  movzx   eax, word ptr [rsi+54h]
0x140042314  cmp     r12d, eax
0x140042317  jge     loc_140042417
0x14004231d  movsxd  r14, r12d
0x140042320  mov     rax, [rsi+r14*8+0C0h]
0x140042328  test    bl, bl
0x14004232a  jz      short loc_1400423A3
0x14004232c  test    rax, rax
0x14004232f  jz      loc_14004240F
0x140042335  mov     rcx, [rax+20h]
0x140042339  test    rcx, rcx
0x14004233c  jz      loc_14004240F
0x140042342  cmp     [rbp+Irql], 1
0x140042346  lea     rdx, [rsi+28h]
0x14004234a  mov     [r13+0], rcx
0x14004234e  mov     [rsi+20h], r13
0x140042352  mov     rax, [rsi+r14*8+0C0h]
0x14004235a  mov     qword ptr [rax+20h], 0
0x140042362  mov     rax, [rsi+r14*8+0C0h]
0x14004236a  mov     rcx, [rax+28h]
0x14004236e  mov     [rdx], rcx
0x140042371  mov     rcx, rdi
0x140042374  mov     [rsi+30h], rdx
0x140042378  setbe   dl
0x14004237b  mov     rax, [rsi+r14*8+0C0h]
0x140042383  mov     qword ptr [rax+28h], 0
0x14004238b  call    AfdCleanupPacketChain
0x140042390  test    al, al
0x140042392  jnz     short loc_14004240F
0x140042394  mov     rdx, rdi
0x140042397  lea     rcx, AfdCompleteTPackets
0x14004239e  jmp     loc_1400428C6
0x1400423a3  test    rax, rax
0x1400423a6  jz      short loc_14004240F
0x1400423a8  mov     rcx, [rax+8]
0x1400423ac  test    rcx, rcx
0x1400423af  jz      short loc_140042403
0x1400423b1  cmp     [rbp+Irql], 1
0x1400423b5  lea     rdx, [rsi+28h]
0x1400423b9  mov     [r13+0], rcx
0x1400423bd  mov     [rsi+20h], r13
0x1400423c1  mov     rax, [rsi+r14*8+0C0h]
0x1400423c9  mov     qword ptr [rax+8], 0
0x1400423d1  mov     rax, [rsi+r14*8+0C0h]
0x1400423d9  mov     rcx, [rax+60h]
0x1400423dd  mov     [rdx], rcx
0x1400423e0  mov     rcx, rdi
0x1400423e3  mov     [rsi+30h], rdx
0x1400423e7  setbe   dl
0x1400423ea  mov     rax, [rsi+r14*8+0C0h]
0x1400423f2  mov     qword ptr [rax+60h], 0
0x1400423fa  call    AfdCleanupPacketChain
0x1400423ff  test    al, al
0x140042401  jz      short loc_140042394
0x140042403  mov     rax, [rsi+r14*8+0C0h]
0x14004240b  mov     byte ptr [rax+44h], 0
0x14004240f  inc     r12d
0x140042412  jmp     loc_140042310
0x140042417  mov     rcx, [rsi+38h]; Irp
0x14004241b  test    rcx, rcx
0x14004241e  jz      short loc_140042434
0x140042420  call    cs:__imp_IoFreeIrp
0x140042427  nop     dword ptr [rax+rax+00h]
0x14004242c  mov     qword ptr [rsi+38h], 0
0x140042434  mov     r13, [rbp+arg_8]
0x140042438  lea     r12, [r15+38h]
0x14004243c  mov     rcx, r12; SpinLock
0x14004243f  lea     rdx, [rbp+LockHandle]; LockHandle
0x140042443  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004244a  nop     dword ptr [rax+rax+00h]
0x14004244f  cmp     dword ptr [rdi+30h], 0
0x140042453  jl      short loc_14004246F
0x140042455  mov     eax, [rdi+80h]
0x14004245b  test    al, 2
0x14004245d  jz      short loc_14004246F
0x14004245f  mov     r14, [r15+0C0h]
0x140042466  test    r14, r14
0x140042469  jnz     loc_14004278B
0x14004246f  xor     r13d, r13d
0x140042472  mov     rcx, [rdi+78h]
0x140042476  mov     r14, r13
0x140042479  test    rcx, rcx
0x14004247c  jz      loc_1400425B9
0x140042482  test    dword ptr [r15+8], 800h
0x14004248a  lea     r14, [rcx-78h]
0x14004248e  jnz     loc_140042541
0x140042494  mov     eax, [rcx+8]
0x140042497  test    al, 1
0x140042499  jz      short loc_1400424A1
0x14004249b  cmp     [r14+18h], r13
0x14004249f  jz      short loc_1400424C7
0x1400424a1  mov     eax, 5030h
0x1400424a6  mov     edx, 0FFF9h
0x1400424ab  add     ax, [r15]
0x1400424af  test    dx, ax
0x1400424b2  jnz     short loc_1400424C7
0x1400424b4  mov     rax, [r15+0C0h]
0x1400424bb  test    rax, rax
0x1400424be  jz      short loc_1400424C7
0x1400424c0  mov     eax, [rax+4]
0x1400424c3  test    al, 10h
0x1400424c5  jnz     short loc_140042541
0x1400424c7  cmp     [r15+168h], rdi
0x1400424ce  jnz     loc_1400425B6
0x1400424d4  mov     eax, [rcx+10h]
0x1400424d7  test    al, 20h
0x1400424d9  jz      loc_1400425B6
0x1400424df  mov     eax, [rcx+10h]
0x1400424e2  and     eax, 0FFFFFFDFh
0x1400424e5  mov     [rcx+10h], eax
0x1400424e8  mov     eax, [rcx+10h]
0x1400424eb  bt      eax, 8
0x1400424ef  jnb     loc_1400425B9
0x1400424f5  movzx   eax, word ptr [r15]
0x1400424f9  mov     edx, 0AFD2h
0x1400424fe  and     ax, dx
0x140042501  cmp     ax, dx
0x140042504  jnz     short loc_14004250F
0x140042506  mov     r12, [r15+0C0h]
0x14004250d  jmp     short loc_140042512
0x14004250f  mov     r12, r13
0x140042512  mov     rax, [rcx]
0x140042515  mov     [rdi+78h], rax
0x140042519  mov     [rcx+0Ch], r13d
0x14004251d  lea     rcx, [rbp+LockHandle]; LockHandle
0x140042521  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140042528  nop     dword ptr [rax+rax+00h]
0x14004252d  mov     r8, r14
0x140042530  mov     rdx, r12
0x140042533  mov     rcx, r15
0x140042536  call    AfdSendQueuedTPSend
0x14004253b  lea     r12, [r15+38h]
0x14004253f  jmp     short loc_14004258B
0x140042541  mov     eax, [rcx+10h]
0x140042544  test    al, 20h
0x140042546  jz      short loc_1400425A3
0x140042548  mov     eax, [rcx+10h]
0x14004254b  and     eax, 0FFFFFFDFh
0x14004254e  mov     [rcx+10h], eax
0x140042551  mov     eax, [rcx+10h]
0x140042554  bt      eax, 8
0x140042558  jnb     short loc_1400425AF
0x14004255a  mov     rax, [rcx]
0x14004255d  mov     [rdi+78h], rax
0x140042561  mov     [rcx+0Ch], r13d
0x140042565  mov     eax, [rcx+10h]
0x140042568  or      eax, 1
0x14004256b  mov     [rcx+10h], eax
0x14004256e  lea     rcx, [rbp+LockHandle]; LockHandle
0x140042572  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140042579  nop     dword ptr [rax+rax+00h]
0x14004257e  mov     r8, r14
0x140042581  xor     edx, edx
0x140042583  mov     rcx, r15
0x140042586  call    AfdSendQueuedTPSend
0x14004258b  lea     rdx, [rbp+LockHandle]; LockHandle
0x14004258f  mov     rcx, r12; SpinLock
0x140042592  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140042599  nop     dword ptr [rax+rax+00h]
0x14004259e  jmp     loc_140042472
0x1400425a3  mov     rcx, r14
0x1400425a6  call    AfdGetTPacketsReference
0x1400425ab  test    al, al
0x1400425ad  jz      short loc_1400425B6
0x1400425af  mov     byte ptr [r14+44h], 1
0x1400425b4  jmp     short loc_1400425B9
0x1400425b6  mov     r14, r13
0x1400425b9  mov     rdx, [r15+168h]
0x1400425c0  cmp     rdx, rdi
0x1400425c3  jnz     short loc_1400425DF
0x1400425c5  mov     rax, [rdi+78h]
0x1400425c9  lea     rcx, [rax-78h]
0x1400425cd  neg     rax
0x1400425d0  sbb     rax, rax
0x1400425d3  and     rax, rcx
0x1400425d6  mov     [r15+168h], rax
0x1400425dd  jmp     short loc_140042608
0x1400425df  mov     rax, [rdx+78h]
0x1400425e3  sub     rax, 78h ; 'x'
0x1400425e7  cmp     rax, rdi
0x1400425ea  jz      short loc_140042600
0x1400425ec  mov     rax, [rdx+78h]
0x1400425f0  mov     rcx, [rax]
0x1400425f3  lea     rdx, [rax-78h]
0x1400425f7  sub     rcx, 78h ; 'x'
0x1400425fb  cmp     rcx, rdi
0x1400425fe  jnz     short loc_1400425EC
0x140042600  mov     rax, [rdi+78h]
0x140042604  mov     [rdx+78h], rax
0x140042608  lea     rcx, [rbp+LockHandle]; LockHandle
0x14004260c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140042613  nop     dword ptr [rax+rax+00h]
0x140042618  test    rsi, rsi
0x14004261b  jz      short loc_140042651
0x14004261d  mov     rcx, [rsi+10h]
0x140042621  test    rcx, rcx
0x140042624  jz      short loc_140042651
0x140042626  or      rax, 0FFFFFFFFFFFFFFFFh
0x14004262a  lock xadd [rcx+30h], rax
0x140042630  sub     rax, 1
0x140042634  jg      short loc_14004264D
0x140042636  test    rax, rax
0x140042639  jnz     short loc_140042646
0x14004263b  mov     rcx, [rsi+10h]
0x14004263f  call    AfdCloseConnection
0x140042644  jmp     short loc_14004264D
0x140042646  mov     ecx, 0Eh
0x14004264b  int     29h; Win8: RtlFailFast(ecx)
0x14004264d  mov     [rsi+10h], r13
0x140042651  mov     eax, [rdi+88h]
0x140042657  bt      eax, 8
0x14004265b  jnb     short loc_14004266F
0x14004265d  mov     r8, rdi
0x140042660  xor     edx, edx
0x140042662  mov     rcx, r15
0x140042665  call    AfdSendQueuedTPSend
0x14004266a  jmp     loc_14004273E
0x14004266f  mov     rax, r13
0x140042672  xchg    rax, [rdi+68h]
0x140042676  test    rax, rax
0x140042679  jnz     short loc_1400426C1
0x14004267b  lea     rcx, [rbp+Irql]; Irql
0x14004267f  mov     [rbp+Irql], r13b
0x140042683  call    cs:__imp_IoAcquireCancelSpinLock
0x14004268a  nop     dword ptr [rax+rax+00h]
0x14004268f  mov     cl, [rbp+Irql]; Irql
0x140042692  call    cs:__imp_IoReleaseCancelSpinLock
0x140042699  nop     dword ptr [rax+rax+00h]
0x14004269e  lea     rdx, [rbp+LockHandle]; LockHandle
0x1400426a2  mov     rcx, r12; SpinLock
0x1400426a5  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400426ac  nop     dword ptr [rax+rax+00h]
0x1400426b1  lea     rcx, [rbp+LockHandle]; LockHandle
0x1400426b5  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400426bc  nop     dword ptr [rax+rax+00h]
0x1400426c1  mov     eax, [rdi+80h]
0x1400426c7  test    al, 1
0x1400426c9  jz      short loc_1400426D5
0x1400426cb  mov     eax, r13d
0x1400426ce  xchg    eax, [r15+170h]
0x1400426d5  mov     r15, [rdi+0B0h]
0x1400426dc  test    byte ptr cs:xmmword_1400875E0+2, 4
0x1400426e3  jz      short loc_140042703
0x1400426e5  mov     edx, 2Eh ; '.'
0x1400426ea  mov     [rsp+50h+var_30], rdi
0x1400426ef  mov     ecx, 412h
0x1400426f4  lea     r8, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids
0x1400426fb  mov     r9, rsi
  ... truncated ...
```
