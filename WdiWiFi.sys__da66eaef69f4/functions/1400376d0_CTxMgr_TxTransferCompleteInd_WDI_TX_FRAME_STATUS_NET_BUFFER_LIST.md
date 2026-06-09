# CTxMgr::TxTransferCompleteInd(_WDI_TX_FRAME_STATUS,_NET_BUFFER_LIST *)

- ea: `0x1400376d0`
- end: `0x140037f71`
- name: `?TxTransferCompleteInd@CTxMgr@@QEAAXW4_WDI_TX_FRAME_STATUS@@PEAU_NET_BUFFER_LIST@@@Z`
- size: `2209`
- prototype: `void __fastcall(PVOID WorkItemContext, enum _WDI_TX_FRAME_STATUS, struct _NET_BUFFER_LIST *)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140042e50`

## callees

- `0x1400174e8`
- `0x140017a90`
- `0x140034e04`
- `0x140034ec4`
- `0x1400376d0`
- `0x140038df0`
- `0x140039a60`
- `0x14003b1d8`
- `0x14003b320`
- `0x14003b340`
- `0x14003d4b8`
- `0x14003ea84`
- `0x14004c4f4`
- `0x140085278`
- `0x140085974`
- `0x1400867b8`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140037935`
- `ntoskrnl!KeReleaseSpinLock` at `0x140037c1b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140037935`
- `ntoskrnl!KeReleaseSpinLock` at `0x140037c1b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400377d2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400377d2`
- `NDIS!NdisSetEvent` at `0x140037f60`
- `NDIS!NdisSetEvent` at `0x140037f60`

## pseudocode

```c
void __fastcall CTxMgr::TxTransferCompleteInd(CTxMgr *WorkItemContext, __int32 a2, struct _NET_BUFFER_LIST *a3)
{
  struct _NET_BUFFER_LIST *v3; // rbp
  struct _NET_BUFFER_LIST *v5; // r14
  struct _NET_BUFFER_LIST *v6; // rsi
  char v7; // r12
  CTxEntryTable *p_m_TxEntryTable; // r14
  _WORD *v9; // rbp
  CNdisSpinLock *m_TxMgrLock; // rdi
  bool v11; // zf
  unsigned __int16 *v12; // rdx
  CTxMgr *v13; // rcx
  struct _WFC_TX_ENTRY *TxEntry; // r14
  _WFC_TX_QUEUE **ppTxQueue; // rdx
  struct _WFC_TX_QUEUE *v16; // r13
  char v17; // r15
  struct _WFC_FRAME *v18; // rdx
  char v19; // bp
  ULONGLONG v20; // rax
  unsigned int TxQueueState; // r8d
  char v22; // bp
  unsigned __int16 v23; // r15
  unsigned int TxEntryState; // ecx
  KIRQL OldIrql; // dl
  __int64 v26; // r9
  unsigned __int16 v27; // r13
  char v28; // si
  char v29; // di
  signed __int32 m_RefVal; // eax
  signed __int32 v31; // ett
  int v32; // eax
  int v33; // edx
  unsigned int v34; // ecx
  KIRQL v35; // dl
  int v36; // edx
  int v37; // edx
  int v38; // edx
  unsigned int v39; // r8d
  int v40; // edx
  __int64 v41; // [rsp+28h] [rbp-A0h]
  char v42; // [rsp+28h] [rbp-A0h]
  __int16 PeerId; // [rsp+50h] [rbp-78h]
  __int16 PortId; // [rsp+52h] [rbp-76h]
  struct _NET_BUFFER_LIST *v45; // [rsp+58h] [rbp-70h]
  struct _NET_BUFFER_LIST *v46; // [rsp+60h] [rbp-68h]
  _WORD *v47; // [rsp+68h] [rbp-60h]
  struct _WFC_FRAME *v48; // [rsp+70h] [rbp-58h]
  struct _NET_BUFFER_LIST *Alignment; // [rsp+78h] [rbp-50h]
  char v50; // [rsp+D0h] [rbp+8h]
  enum _WDI_TX_FRAME_STATUS v51; // [rsp+D8h] [rbp+10h]
  char Tid; // [rsp+E0h] [rbp+18h]
  unsigned __int8 v53; // [rsp+E8h] [rbp+20h] BYREF

  v51 = a2;
  v3 = 0;
  Tid = 31;
  v5 = 0;
  PortId = -1;
  v46 = 0;
  v6 = a3;
  v7 = a2;
  PeerId = -1;
  v45 = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        237,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
    }
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        (_DWORD)a3,
        238,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
        v7);
    }
  }
  if ( !v6 )
    goto LABEL_41;
  p_m_TxEntryTable = &WorkItemContext->m_TxEntryTable;
  do
  {
    Alignment = (struct _NET_BUFFER_LIST *)v6->Link.Alignment;
    v6->Link.Alignment = 0;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        (_DWORD)a3,
        239,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
        (char)v6);
    }
    v9 = v6->MiniportReserved[0];
    m_TxMgrLock = WorkItemContext->m_TxMgrLock;
    v48 = (struct _WFC_FRAME *)(v9 - 32);
    m_TxMgrLock->m_SpinLock.OldIrql = KeAcquireSpinLockRaiseToDpc(&m_TxMgrLock->m_SpinLock.SpinLock);
    m_TxMgrLock->m_IsLocked = 1;
    v11 = WorkItemContext->m_QueueingMode == PORT_QUEUEING;
    v47 = v9 + 17;
    v50 = 0;
    v53 = 0;
    if ( v11 )
    {
      v12 = v9 + 16;
    }
    else
    {
      v12 = v9 + 17;
      v47 = v9 + 17;
    }
    TxEntry = CTxEntryTable::GetTxEntry(p_m_TxEntryTable, *v12);
    if ( TxEntry )
    {
      v13 = (CTxMgr *)*((unsigned __int8 *)v9 + 36);
      if ( WorkItemContext->m_QueueingMode == PORT_QUEUEING )
      {
        LOBYTE(v13) = (unsigned __int8)v13 > 0x10u;
      }
      else if ( (unsigned __int8)v13 > 0x18u )
      {
        goto LABEL_69;
      }
      ppTxQueue = TxEntry->ppTxQueue;
      if ( ppTxQueue )
      {
        v16 = ppTxQueue[(unsigned __int8)v13];
LABEL_20:
        --WorkItemContext->m_CurOutstandingTransfers;
        --TxEntry->TransferPendingCount;
        v17 = 1;
        --v16->TransferPendingCount;
        goto LABEL_21;
      }
LABEL_69:
      v16 = 0;
      goto LABEL_20;
    }
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
    {
      --WorkItemContext->m_CurOutstandingTransfers;
      v17 = 0;
      v16 = 0;
    }
    else
    {
      v16 = 0;
      v17 = 0;
      LOWORD(v37) = *v47;
      if ( WorkItemContext->m_QueueingMode == PORT_QUEUEING )
        LOWORD(v37) = v9[16];
      v37 = (unsigned __int16)v37;
      v42 = v37;
      LOBYTE(v37) = 4;
      WPP_RECORDER_SF_DDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v37,
        1,
        240,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
        v42,
        v9[16],
        *v47);
      --WorkItemContext->m_CurOutstandingTransfers;
    }
LABEL_21:
    v18 = (struct _WFC_FRAME *)(v9 - 32);
    v18->u.Tx.bIsTransferStatusSet = 1;
    v18->u.Tx.TransferStatus = v51;
    if ( (v51 || *((_BYTE *)v9 + 42) != 1)
      && ((LOBYTE(v13) = 0, v51) || WorkItemContext->m_pDatapathCapabilities->TxExplicitSendCompleteFlagRequired)
      || (LOBYTE(v13) = 1, v18->u.Tx.bIsSendStatusSet) )
    {
      v19 = 1;
    }
    else
    {
      if ( v17 )
      {
        ++v16->TxPendingCount;
        ++TxEntry->TxPendingCount;
      }
      v19 = 0;
    }
    if ( v17 && (_BYTE)v13 && v18->u.Tx.bIsSendStatusSet && v18->u.Tx.SendStatus == WDI_TxFrameStatus_SendPostponed )
    {
      v32 = CTxMgr::RequeueNbl(v13, TxEntry, v16, v18, &v53);
      v18 = v48;
      PortId = TxEntry->PortId;
      if ( !v32 )
        v19 = 0;
      PeerId = TxEntry->PeerId;
    }
    if ( v19 )
    {
      if ( v18->FrameType == TX_INJECTED_FRAME )
      {
        v20 = (ULONGLONG)v46;
        v46 = v6;
      }
      else
      {
        v20 = (ULONGLONG)v45;
        v45 = v6;
      }
      v6->Link.Alignment = v20;
    }
    if ( !v17 )
    {
      v23 = PeerId;
LABEL_36:
      OldIrql = m_TxMgrLock->m_SpinLock.OldIrql;
      m_TxMgrLock->m_IsLocked = 0;
      KeReleaseSpinLock(&m_TxMgrLock->m_SpinLock.SpinLock, OldIrql);
      v27 = PortId;
      v22 = v50;
      v28 = PortId;
      v29 = v23;
      goto LABEL_37;
    }
    TxQueueState = v16->TxQueueState;
    if ( (TxQueueState & 1) != 0 && !v16->TransferPendingCount && !v16->TxPendingCount )
    {
      v39 = TxQueueState & 0xFFFFFFFC | 2;
      v16->TxQueueState = v39;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v40 = v16->PortId;
        LOBYTE(v40) = 4;
        WPP_RECORDER_SF_DDDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v40,
          1,
          241,
          (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
          v16->PortId,
          v16->PeerId,
          v16->Tid,
          v39);
      }
    }
    if ( (v16->TxQueueState & 8) == 0 || v16->TransferPendingCount || v16->TxPendingCount )
    {
      v22 = 0;
      v23 = PeerId;
    }
    else
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v38 = v16->PortId;
        LOBYTE(v38) = 4;
        WPP_RECORDER_SF_DDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v38,
          1,
          242,
          (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
          v16->PortId,
          v16->PeerId,
          v16->Tid);
      }
      v22 = 1;
      v23 = v16->PeerId;
      PortId = v16->PortId;
      Tid = v16->Tid;
      v50 = 1;
      PeerId = v23;
    }
    TxEntryState = TxEntry->TxEntryState;
    if ( (TxEntryState & 1) == 0 || TxEntry->TransferPendingCount || TxEntry->TxPendingCount )
      goto LABEL_36;
    v34 = TxEntryState & 0xFFFFFFFC | 2;
    TxEntry->TxEntryState = v34;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v18) = 4;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v18,
        1,
        243,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
        TxEntry->TxId,
        v34);
    }
    if ( (TxEntry->TxEntryState & 0x20) == 0 )
      goto LABEL_36;
    v27 = TxEntry->PortId;
    v23 = TxEntry->PeerId;
    v35 = m_TxMgrLock->m_SpinLock.OldIrql;
    PortId = v27;
    PeerId = v23;
    m_TxMgrLock->m_IsLocked = 0;
    KeReleaseSpinLock(&m_TxMgrLock->m_SpinLock.SpinLock, v35);
    v29 = v23;
    v28 = v27;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v36) = 4;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v36,
        1,
        244,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
        v27,
        v23);
    }
    CTxMgr::PeerDeleteConfirm(WorkItemContext, v27, v23);
LABEL_37:
    if ( v53 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 4;
        WPP_RECORDER_SF_DD(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          1,
          245,
          (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
          v28,
          v29);
      }
      LOBYTE(v26) = 1;
      ((void (__fastcall *)(void *, _QWORD, _QWORD, __int64))WorkItemContext->m_pAdapter->m_MiniportDataHandlers.TxPeerBacklogHandler)(
        WorkItemContext->m_pAdapter->m_MiniportTalTxRxContext,
        v27,
        v23,
        v26);
    }
    if ( v22 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 4;
        WPP_RECORDER_SF_DDD(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          1,
          246,
          (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
          v28,
          v29,
          Tid);
      }
      ((void (__fastcall *)(void *, _QWORD, _QWORD))WorkItemContext->m_pAdapter->m_MiniportDataHandlers.TxTalQueueInOrderHandler)(
        WorkItemContext->m_pAdapter->m_MiniportTalTxRxContext,
        v23,
        (unsigned int)(1 << Tid));
    }
    p_m_TxEntryTable = &WorkItemContext->m_TxEntryTable;
    v6 = Alignment;
  }
  while ( Alignment );
  v3 = v45;
  v5 = v46;
LABEL_41:
  m_RefVal = WorkItemContext->m_InlineCompletionRundown.m_RefVal;
  while ( (m_RefVal & 1) == 0 )
  {
    v31 = m_RefVal;
    m_RefVal = _InterlockedCompareExchange(&WorkItemContext->m_InlineCompletionRundown.m_RefVal, m_RefVal + 2, m_RefVal);
    if ( v31 == m_RefVal )
    {
      if ( v5 )
        CTxMgr::CompleteIhvNbl(WorkItemContext, v5);
      if ( v3 )
        CTxMgr::CompleteNdisNbl((char *)WorkItemContext, v3, 0);
      if ( _InterlockedExchangeAdd(&WorkItemContext->m_InlineCompletionRundown.m_RefVal, 0xFFFFFFFE) == 3 )
        NdisSetEvent(&WorkItemContext->m_InlineCompletionRundown.m_NdisEvent);
      goto LABEL_50;
    }
  }
  if ( CDispatchRundown::Acquire(&WorkItemContext->m_DivertCompletionRundown) )
  {
    CTxMgr::DivertNBLs(WorkItemContext, v5, v3);
    CDispatchRundown::Release(&WorkItemContext->m_DivertCompletionRundown);
  }
  else
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return;
    LOBYTE(v33) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v33,
      1,
      350,
      (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
  }
LABEL_50:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v41) = 0;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      247,
      (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
      v41);
  }
}

```

## disassembly

```asm
0x1400376d0  mov     rax, rsp
0x1400376d3  mov     [rax+10h], edx
0x1400376d6  push    rbx
0x1400376d7  push    rbp
0x1400376d8  push    r13
0x1400376da  push    r14
0x1400376dc  push    r15
0x1400376de  sub     rsp, 0A0h
0x1400376e5  xor     ebp, ebp
0x1400376e7  mov     [rax-30h], rsi
0x1400376eb  mov     rbx, rcx
0x1400376ee  mov     [rax-40h], r12
0x1400376f2  mov     ecx, 0FFFFh
0x1400376f7  mov     [rsp+0C8h+arg_10], 1Fh
0x1400376ff  xor     r14d, r14d
0x140037702  mov     [rsp+0C8h+var_76], cx
0x140037707  mov     [rsp+0C8h+var_68], r14
0x14003770c  mov     rsi, r8
0x14003770f  mov     r12d, edx
0x140037712  mov     [rsp+0C8h+var_78], cx
0x140037717  mov     [rsp+0C8h+var_70], rbp
0x14003771c  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140037723  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14003772a  lea     r13, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x140037731  jz      short loc_140037772
0x140037733  mov     rcx, cs:WPP_GLOBAL_Control
0x14003773a  cmp     byte ptr [rcx+29h], 5
0x14003773e  jnb     loc_140037B08
0x140037744  cmp     [rcx+48h], bp
0x140037748  jnz     loc_140037B08
0x14003774e  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140037755  jz      short loc_140037772
0x140037757  mov     rcx, cs:WPP_GLOBAL_Control
0x14003775e  cmp     byte ptr [rcx+29h], 5
0x140037762  jnb     loc_140037CEE
0x140037768  cmp     [rcx+48h], bp
0x14003776c  jnz     loc_140037CEE
0x140037772  mov     [rsp+0C8h+var_38], rdi
0x14003777a  test    rsi, rsi
0x14003777d  jz      loc_1400379AB
0x140037783  lea     r14, [rbx+130h]
0x14003778a  mov     rax, [rsi]
0x14003778d  mov     [rsp+0C8h+var_50], rax
0x140037792  mov     qword ptr [rsi], 0
0x140037799  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400377a0  jz      short loc_1400377BE
0x1400377a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400377a9  cmp     byte ptr [rcx+29h], 5
0x1400377ad  jnb     loc_140037B29
0x1400377b3  cmp     word ptr [rcx+48h], 0
0x1400377b8  jnz     loc_140037B29
0x1400377be  mov     rbp, [rsi+60h]
0x1400377c2  mov     rdi, [rbx+20h]
0x1400377c6  mov     rcx, rdi; SpinLock
0x1400377c9  lea     rax, [rbp-40h]
0x1400377cd  mov     [rsp+0C8h+var_58], rax
0x1400377d2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400377d9  nop     dword ptr [rax+rax+00h]
0x1400377de  mov     [rdi+8], al
0x1400377e1  lea     rax, [rbp+22h]
0x1400377e5  mov     byte ptr [rdi+10h], 1
0x1400377e9  cmp     dword ptr [rbx+0F8h], 1
0x1400377f0  mov     [rsp+0C8h+var_60], rax
0x1400377f5  mov     byte ptr [rsp+0C8h+var_74], 1
0x1400377fa  mov     [rsp+0C8h+arg_0], 0
0x140037802  mov     [rsp+0C8h+arg_18], 0
0x14003780a  jnz     loc_140037AFB
0x140037810  lea     rdx, [rbp+20h]
0x140037814  movzx   edx, word ptr [rdx]; unsigned __int16
0x140037817  mov     rcx, r14; this
0x14003781a  call    ?GetTxEntry@CTxEntryTable@@QEAAPEAU_WFC_TX_ENTRY@@G@Z; CTxEntryTable::GetTxEntry(ushort)
0x14003781f  mov     r14, rax
0x140037822  test    rax, rax
0x140037825  jz      loc_140037C7F
0x14003782b  cmp     dword ptr [rbx+0F8h], 1
0x140037832  movzx   ecx, byte ptr [rbp+24h]
0x140037836  jnz     short loc_140037840
0x140037838  cmp     cl, 10h
0x14003783b  setnbe  cl
0x14003783e  jmp     short loc_14003784E
0x140037840  cmp     cl, 18h
0x140037843  setbe   al
0x140037846  test    al, al
0x140037848  jz      loc_140037B49
0x14003784e  mov     rdx, [r14+88h]
0x140037855  test    rdx, rdx
0x140037858  jz      loc_140037B49
0x14003785e  movzx   eax, cl
0x140037861  mov     r13, [rdx+rax*8]
0x140037865  dec     qword ptr [rbx+60h]
0x140037869  mov     eax, 0FFFFh
0x14003786e  add     [r14+1Ah], ax
0x140037873  mov     r15b, 1
0x140037876  add     [r13+32h], ax
0x14003787b  mov     r12d, [rsp+0C8h+arg_8]
0x140037883  lea     rdx, [rbp-40h]
0x140037887  mov     byte ptr [rdx+35h], 1
0x14003788b  mov     [rdx+2Ch], r12d
0x14003788f  test    r12d, r12d
0x140037892  jnz     short loc_14003789E
0x140037894  cmp     byte ptr [rbp+2Ah], 1
0x140037898  jz      loc_140037AD8
0x14003789e  xor     cl, cl; this
0x1400378a0  test    r12d, r12d
0x1400378a3  jnz     short loc_1400378B5
0x1400378a5  mov     rax, [rbx+150h]
0x1400378ac  cmp     [rax+8], cl
0x1400378af  jz      loc_140037AD8
0x1400378b5  mov     ebp, [rsp+0C8h+var_74]
0x1400378b9  test    r15b, r15b
0x1400378bc  jnz     loc_140037A25
0x1400378c2  test    bpl, bpl
0x1400378c5  jz      short loc_1400378DE
0x1400378c7  cmp     dword ptr [rdx+4], 1
0x1400378cb  jz      loc_140037DD3
0x1400378d1  mov     rax, [rsp+0C8h+var_70]
0x1400378d6  mov     [rsp+0C8h+var_70], rsi
0x1400378db  mov     [rsi], rax
0x1400378de  test    r15b, r15b
0x1400378e1  jz      loc_140037A85
0x1400378e7  mov     r8d, [r13+38h]
0x1400378eb  test    r8b, 1
0x1400378ef  jnz     loc_140037DE2
0x1400378f5  lea     rsi, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x1400378fc  lea     r12, WPP_RECORDER_INITIALIZED
0x140037903  mov     eax, [r13+38h]
0x140037907  test    al, 8
0x140037909  jnz     loc_140037D0E
0x14003790f  movzx   ebp, [rsp+0C8h+arg_0]
0x140037917  movzx   r15d, [rsp+0C8h+var_78]
0x14003791d  mov     ecx, [r14+8]
0x140037921  test    cl, 1
0x140037924  jnz     loc_140037B84
0x14003792a  movzx   edx, byte ptr [rdi+8]; NewIrql
0x14003792e  mov     rcx, rdi; SpinLock
0x140037931  mov     byte ptr [rdi+10h], 0
0x140037935  call    cs:__imp_KeReleaseSpinLock
0x14003793c  nop     dword ptr [rax+rax+00h]
0x140037941  movzx   r13d, [rsp+0C8h+var_76]
0x140037947  movzx   ebp, [rsp+0C8h+arg_0]
0x14003794f  mov     esi, r13d
0x140037952  movzx   edi, r15w
0x140037956  cmp     [rsp+0C8h+arg_18], 0
0x14003795e  jnz     loc_140037E88
0x140037964  test    bpl, bpl
0x140037967  jnz     loc_140037EE7
0x14003796d  mov     rax, [rsp+0C8h+var_50]
0x140037972  lea     r14, [rbx+130h]
0x140037979  lea     r15, WPP_RECORDER_INITIALIZED
0x140037980  mov     rsi, rax
0x140037983  lea     r13, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x14003798a  test    rax, rax
0x14003798d  jnz     loc_14003778A
0x140037993  mov     rbp, [rsp+0C8h+var_70]
0x140037998  lea     r15, WPP_RECORDER_INITIALIZED
0x14003799f  mov     r14, [rsp+0C8h+var_68]
0x1400379a4  lea     r13, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x1400379ab  mov     eax, [rbx+70h]
0x1400379ae  mov     r12, [rsp+0C8h+var_40]
0x1400379b6  mov     rsi, [rsp+0C8h+var_30]
0x1400379be  test    al, 1
0x1400379c0  jnz     loc_140037B51
0x1400379c6  lea     ecx, [rax+2]
0x1400379c9  lock cmpxchg [rbx+70h], ecx
0x1400379ce  jnz     short loc_1400379BE
0x1400379d0  test    r14, r14
0x1400379d3  jnz     loc_140037E69
0x1400379d9  test    rbp, rbp
0x1400379dc  jz      short loc_1400379EC
0x1400379de  xor     r8d, r8d; unsigned __int8
0x1400379e1  mov     rdx, rbp; struct _NET_BUFFER_LIST *
0x1400379e4  mov     rcx, rbx; WorkItemContext
0x1400379e7  call    ?CompleteNdisNbl@CTxMgr@@AEAAXPEAU_NET_BUFFER_LIST@@E@Z; CTxMgr::CompleteNdisNbl(_NET_BUFFER_LIST *,uchar)
0x1400379ec  mov     eax, 0FFFFFFFEh
0x1400379f1  lock xadd [rbx+70h], eax
0x1400379f6  cmp     eax, 3
0x1400379f9  jz      loc_140037F5C
0x1400379ff  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140037a06  jnz     loc_140037A97
0x140037a0c  mov     rdi, [rsp+0C8h+var_38]
0x140037a14  add     rsp, 0A0h
0x140037a1b  pop     r15
0x140037a1d  pop     r14
0x140037a1f  pop     r13
0x140037a21  pop     rbp
0x140037a22  pop     rbx
0x140037a23  retn
0x140037a25  test    cl, cl
0x140037a27  jz      loc_1400378C2
0x140037a2d  cmp     byte ptr [rdx+36h], 0
0x140037a31  jz      loc_1400378C2
0x140037a37  cmp     dword ptr [rdx+30h], 5
0x140037a3b  jnz     loc_1400378C2
0x140037a41  lea     rax, [rsp+0C8h+arg_18]
0x140037a49  mov     r9, rdx; struct _WFC_FRAME *
0x140037a4c  mov     rdx, r14; struct _WFC_TX_ENTRY *
0x140037a4f  mov     [rsp+0C8h+var_A8], rax; unsigned __int8 *
0x140037a54  mov     r8, r13; struct _WFC_TX_QUEUE *
0x140037a57  call    ?RequeueNbl@CTxMgr@@AEAAHPEAU_WFC_TX_ENTRY@@PEAU_WFC_TX_QUEUE@@PEAU_WFC_FRAME@@PEAE@Z; CTxMgr::RequeueNbl(_WFC_TX_ENTRY *,_WFC_TX_QUEUE *,_WFC_FRAME *,uchar *)
0x140037a5c  mov     rdx, [rsp+0C8h+var_58]
0x140037a61  xor     ecx, ecx
0x140037a63  test    eax, eax
0x140037a65  movzx   ebp, bpl
0x140037a69  movzx   eax, word ptr [r14+4]
0x140037a6e  mov     [rsp+0C8h+var_76], ax
0x140037a73  cmovz   ebp, ecx
0x140037a76  movzx   eax, word ptr [r14+6]
0x140037a7b  mov     [rsp+0C8h+var_78], ax
0x140037a80  jmp     loc_1400378C2
0x140037a85  movzx   r15d, [rsp+0C8h+var_78]
0x140037a8b  lea     r12, WPP_RECORDER_INITIALIZED
0x140037a92  jmp     loc_14003792A
0x140037a97  mov     rcx, cs:WPP_GLOBAL_Control
0x140037a9e  cmp     byte ptr [rcx+29h], 5
0x140037aa2  jnb     short loc_140037AAF
0x140037aa4  cmp     word ptr [rcx+48h], 0
0x140037aa9  jz      loc_140037A0C
0x140037aaf  mov     rcx, [rcx+40h]
0x140037ab3  mov     r9d, 0F7h
0x140037ab9  mov     dword ptr [rsp+0C8h+var_A0], 0
0x140037ac1  mov     r8d, 1
0x140037ac7  mov     dl, 5
0x140037ac9  mov     [rsp+0C8h+var_A8], r13
0x140037ace  call    WPP_RECORDER_SF_D
0x140037ad3  jmp     loc_140037A0C
0x140037ad8  cmp     byte ptr [rdx+36h], 0
0x140037adc  mov     cl, 1
0x140037ade  jnz     loc_1400378B5
0x140037ae4  test    r15b, r15b
0x140037ae7  jz      short loc_140037AF3
0x140037ae9  inc     word ptr [r13+34h]
0x140037aee  inc     word ptr [r14+1Ch]
0x140037af3  xor     bpl, bpl
0x140037af6  jmp     loc_1400378B9
0x140037afb  mov     rdx, rax
0x140037afe  mov     [rsp+0C8h+var_60], rax
0x140037b03  jmp     loc_140037814
0x140037b08  mov     rcx, [rcx+40h]
0x140037b0c  mov     r9d, 0EDh
0x140037b12  mov     r8d, 1
0x140037b18  mov     [rsp+0C8h+var_A8], r13
0x140037b1d  mov     dl, 5
0x140037b1f  call    WPP_RECORDER_SF_
0x140037b24  jmp     loc_14003774E
0x140037b29  mov     rcx, [rcx+40h]
0x140037b2d  mov     r9d, 0EFh
0x140037b33  mov     [rsp+0C8h+var_A0], rsi
0x140037b38  mov     dl, 5
0x140037b3a  mov     [rsp+0C8h+var_A8], r13
0x140037b3f  call    WPP_RECORDER_SF_q
0x140037b44  jmp     loc_1400377BE
0x140037b49  xor     r13d, r13d
0x140037b4c  jmp     loc_140037865
0x140037b51  lea     rcx, [rbx+90h]; this
0x140037b58  call    ?Acquire@CDispatchRundown@@QEAA_NXZ; CDispatchRundown::Acquire(void)
0x140037b5d  test    al, al
0x140037b5f  jz      loc_140037D9E
0x140037b65  mov     r8, rbp; struct _NET_BUFFER_LIST *
0x140037b68  mov     rdx, r14; struct _NET_BUFFER_LIST *
0x140037b6b  mov     rcx, rbx; this
0x140037b6e  call    ?DivertNBLs@CTxMgr@@AEAAXPEAU_NET_BUFFER_LIST@@0@Z; CTxMgr::DivertNBLs(_NET_BUFFER_LIST *,_NET_BUFFER_LIST *)
0x140037b73  lea     rcx, [rbx+90h]; this
0x140037b7a  call    ?Release@CDispatchRundown@@QEAAXXZ; CDispatchRundown::Release(void)
0x140037b7f  jmp     loc_1400379FF
0x140037b84  cmp     word ptr [r14+1Ah], 0
0x140037b8a  jnz     loc_14003792A
0x140037b90  cmp     word ptr [r14+1Ch], 0
0x140037b96  jnz     loc_14003792A
0x140037b9c  and     ecx, 0FFFFFFFEh
0x140037b9f  or      ecx, 2
0x140037ba2  mov     [r14+8], ecx
0x140037ba6  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140037bad  jz      short loc_140037BDF
0x140037baf  movzx   eax, word ptr [r14+2]
0x140037bb4  mov     r9d, 0F3h
0x140037bba  mov     [rsp+0C8h+var_98], ecx
0x140037bbe  mov     r8d, 1
0x140037bc4  mov     rcx, cs:WPP_GLOBAL_Control
0x140037bcb  mov     dl, 4
0x140037bcd  mov     dword ptr [rsp+0C8h+var_A0], eax
0x140037bd1  mov     [rsp+0C8h+var_A8], rsi
0x140037bd6  mov     rcx, [rcx+40h]
0x140037bda  call    WPP_RECORDER_SF_DD
0x140037bdf  mov     eax, [r14+8]
0x140037be3  test    al, 20h
0x140037be5  jz      loc_14003792A
0x140037beb  movzx   r13d, word ptr [r14+4]
0x140037bf0  mov     rcx, rdi; SpinLock
0x140037bf3  movzx   r15d, word ptr [r14+6]
0x140037bf8  movzx   eax, [rsp+0C8h+arg_10]
0x140037c00  movzx   edx, byte ptr [rdi+8]; NewIrql
0x140037c04  mov     [rsp+0C8h+arg_10], al
0x140037c0b  mov     [rsp+0C8h+var_76], r13w
0x140037c11  mov     [rsp+0C8h+var_78], r15w
0x140037c17  mov     byte ptr [rdi+10h], 0
0x140037c1b  call    cs:__imp_KeReleaseSpinLock
0x140037c22  nop     dword ptr [rax+rax+00h]
0x140037c27  mov     edi, r15d
0x140037c2a  mov     esi, r13d
0x140037c2d  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
  ... truncated ...
```
