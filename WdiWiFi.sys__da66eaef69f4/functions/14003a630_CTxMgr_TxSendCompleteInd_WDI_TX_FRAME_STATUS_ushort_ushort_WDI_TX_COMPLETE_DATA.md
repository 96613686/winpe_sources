# CTxMgr::TxSendCompleteInd(_WDI_TX_FRAME_STATUS,ushort,ushort *,_WDI_TX_COMPLETE_DATA *)

- ea: `0x14003a630`
- end: `0x14003b1a3`
- name: `?TxSendCompleteInd@CTxMgr@@QEAAXW4_WDI_TX_FRAME_STATUS@@GPEAGPEAU_WDI_TX_COMPLETE_DATA@@@Z`
- size: `2931`
- prototype: `void __usercall(PVOID WorkItemContext@<rcx>, enum _WDI_TX_FRAME_STATUS@<edx>, unsigned __int16@<r8w>, unsigned __int16 *@<r9>, struct _WDI_TX_COMPLETE_DATA *)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14003b1b0`

## callees

- `0x1400174e8`
- `0x140017a90`
- `0x14002aa28`
- `0x140034e04`
- `0x140034ec4`
- `0x140038df0`
- `0x140039a60`
- `0x14003a630`
- `0x14003b1d8`
- `0x14003b320`
- `0x14003b340`
- `0x14003d238`
- `0x14003d4b8`
- `0x14003ea84`
- `0x140085278`
- `0x140085974`
- `0x1400867b8`
- `0x140086834`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14003a7bb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003a979`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003aab3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003af97`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003a7bb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003a979`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003aab3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003af97`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003a745`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003a825`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003a745`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003a825`
- `NDIS!NdisSetEvent` at `0x14003b192`
- `NDIS!NdisSetEvent` at `0x14003b192`

## pseudocode

```c
void __fastcall CTxMgr::TxSendCompleteInd(
        CTxMgr *WorkItemContext,
        enum _WDI_TX_FRAME_STATUS a2,
        unsigned __int16 a3,
        unsigned __int16 *a4,
        struct _WDI_TX_COMPLETE_DATA *a5)
{
  struct _NET_BUFFER_LIST *v5; // rdi
  CTxMgr *v6; // r14
  int v7; // ebx
  struct _NET_BUFFER_LIST *v8; // r10
  enum _WDI_TX_FRAME_STATUS v9; // r15d
  __int64 v10; // rax
  unsigned __int16 v11; // bp
  struct _NET_BUFFER_LIST *v12; // rsi
  CFrameIdLookupTable *p_m_FrameIdTable; // rbx
  _LIST_ENTRY *v14; // rdi
  CNdisSpinLock *m_FrameIdLock; // rbx
  KIRQL v16; // al
  int v17; // edx
  int v18; // r8d
  _LIST_ENTRY *Flink; // rcx
  KIRQL OldIrql; // dl
  int v21; // edi
  int v22; // r8d
  int v23; // r9d
  CNdisSpinLock *m_TxMgrLock; // r13
  char *v25; // rsi
  int v26; // edx
  unsigned __int16 *v27; // rdi
  bool v28; // zf
  unsigned __int16 *v29; // rdx
  _WFC_TX_QUEUE **ppTxQueue; // rdx
  CTxMgr *v31; // rcx
  struct _WFC_TX_ENTRY *TxEntry; // r12
  char v33; // r15
  struct _WFC_TX_QUEUE *v34; // r14
  int v35; // ecx
  struct _NET_BUFFER_LIST *v36; // rcx
  unsigned int TxQueueState; // r8d
  char v38; // si
  unsigned int TxEntryState; // ecx
  KIRQL v40; // dl
  __int64 v41; // r9
  unsigned __int16 v42; // r12
  unsigned __int16 v43; // r13
  char v44; // bl
  char v45; // di
  signed __int32 m_RefVal; // eax
  signed __int32 v47; // ett
  KIRQL v48; // dl
  int v49; // eax
  int v50; // edx
  struct _NET_BUFFER_LIST *v51; // r10
  struct _WDI_TX_COMPLETE_DATA *v52; // rcx
  unsigned int v53; // r8d
  int v54; // edx
  int v55; // edx
  unsigned int v56; // ecx
  KIRQL v57; // dl
  unsigned __int16 v58; // ax
  int v59; // edx
  int v60; // [rsp+20h] [rbp-A8h]
  __int64 v61; // [rsp+28h] [rbp-A0h]
  char Tid; // [rsp+50h] [rbp-78h]
  char v63; // [rsp+51h] [rbp-77h]
  unsigned __int8 v64[2]; // [rsp+52h] [rbp-76h] BYREF
  __int16 PortId; // [rsp+54h] [rbp-74h]
  __int16 PeerId; // [rsp+56h] [rbp-72h]
  struct _NET_BUFFER_LIST *v67; // [rsp+58h] [rbp-70h]
  enum _WDI_TX_FRAME_STATUS v68; // [rsp+60h] [rbp-68h]
  int v69; // [rsp+64h] [rbp-64h]
  struct _NET_BUFFER_LIST *v70; // [rsp+68h] [rbp-60h]
  int v71; // [rsp+70h] [rbp-58h]
  struct _NET_BUFFER_LIST *v72; // [rsp+78h] [rbp-50h]
  enum _WDI_TX_FRAME_STATUS v74; // [rsp+D8h] [rbp+10h]
  char v75; // [rsp+E0h] [rbp+18h]
  unsigned __int16 *v76; // [rsp+E8h] [rbp+20h]

  v76 = a4;
  v74 = a2;
  v5 = 0;
  v6 = WorkItemContext;
  v7 = a3;
  v70 = 0;
  v8 = 0;
  v63 = 0;
  v67 = 0;
  v9 = a2;
  PortId = -1;
  PeerId = -1;
  Tid = 31;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        248,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
      a4 = v76;
      v8 = 0;
    }
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        a3,
        249,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
        v9);
      a4 = v76;
      v8 = 0;
    }
  }
  if ( a5 )
  {
    v63 = 1;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        250,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
      a4 = v76;
      v8 = 0;
    }
  }
  v10 = 0;
  v71 = v7;
  v69 = 0;
  if ( !v7 )
    goto LABEL_55;
  do
  {
    v11 = a4[v10];
    v12 = 0;
    p_m_FrameIdTable = &v6->m_pAdapter->m_FrameIdTable;
    v64[0] = 0;
    v72 = 0;
    v14 = &p_m_FrameIdTable->m_FrameListHeadArray[((unsigned __int64)v11 >> 3) & 0x3F];
    m_FrameIdLock = p_m_FrameIdTable->m_FrameIdLock;
    v16 = KeAcquireSpinLockRaiseToDpc(&m_FrameIdLock->m_SpinLock.SpinLock);
    m_FrameIdLock->m_SpinLock.OldIrql = v16;
    m_FrameIdLock->m_IsLocked = 1;
    Flink = v14->Flink;
    if ( v14->Flink == v14 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v17) = 2;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v17,
          1,
          71,
          (__int64)WPP_9437762af08d3eac72fe4950abce8818_Traceguids);
      }
      OldIrql = m_FrameIdLock->m_SpinLock.OldIrql;
      v21 = -1073676261;
      m_FrameIdLock->m_IsLocked = 0;
    }
    else
    {
      while ( LOWORD(Flink[4].Blink) != v11 )
      {
        Flink = Flink->Flink;
        if ( Flink == v14 )
        {
          OldIrql = v16;
          m_FrameIdLock->m_IsLocked = 0;
          v21 = -1073676261;
          goto LABEL_17;
        }
      }
      v12 = (struct _NET_BUFFER_LIST *)Flink[4].Flink;
      v72 = v12;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v17) = 5;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v17,
          v18,
          72,
          (__int64)WPP_9437762af08d3eac72fe4950abce8818_Traceguids,
          (char)v12,
          v11);
      }
      OldIrql = m_FrameIdLock->m_SpinLock.OldIrql;
      v21 = 0;
      m_FrameIdLock->m_IsLocked = 0;
    }
LABEL_17:
    KeReleaseSpinLock(&m_FrameIdLock->m_SpinLock.SpinLock, OldIrql);
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LODWORD(v61) = v21;
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        73,
        (__int64)WPP_9437762af08d3eac72fe4950abce8818_Traceguids,
        v61);
    }
    if ( v12 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        WPP_RECORDER_SF_Dq(WPP_GLOBAL_Control->DeviceExtension, a2, v22, v23, v60, v11, (char)v12);
      }
      m_TxMgrLock = v6->m_TxMgrLock;
      v25 = (char *)v12->MiniportReserved[0];
      m_TxMgrLock->m_SpinLock.OldIrql = KeAcquireSpinLockRaiseToDpc(&m_TxMgrLock->m_SpinLock.SpinLock);
      m_TxMgrLock->m_IsLocked = 1;
      if ( *(v25 - 10) != 1 )
      {
        *(v25 - 10) = 1;
        *((_DWORD *)v25 - 4) = v9;
        v27 = (unsigned __int16 *)(v25 + 32);
        v28 = v6->m_QueueingMode == PORT_QUEUEING;
        v75 = 0;
        v68 = v9;
        if ( v28 )
          v29 = (unsigned __int16 *)(v25 + 32);
        else
          v29 = (unsigned __int16 *)(v25 + 34);
        TxEntry = CTxEntryTable::GetTxEntry(&v6->m_TxEntryTable, *v29);
        if ( TxEntry )
        {
          v33 = 1;
          v31 = (CTxMgr *)(unsigned __int8)v25[36];
          if ( v6->m_QueueingMode == PORT_QUEUEING )
          {
            LOBYTE(v31) = (unsigned __int8)v31 > 0x10u;
            goto LABEL_31;
          }
          if ( (unsigned __int8)v31 <= 0x18u )
          {
LABEL_31:
            ppTxQueue = TxEntry->ppTxQueue;
            if ( ppTxQueue )
            {
              v34 = ppTxQueue[(unsigned __int8)v31];
              goto LABEL_33;
            }
          }
          v34 = 0;
          goto LABEL_33;
        }
        v34 = 0;
        v33 = 0;
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          if ( WorkItemContext->m_QueueingMode != PORT_QUEUEING )
            v27 = (unsigned __int16 *)(v25 + 34);
          LODWORD(v61) = *v27;
          LOBYTE(ppTxQueue) = 4;
          WPP_RECORDER_SF_D(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)ppTxQueue,
            1,
            254,
            (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
            v61);
        }
LABEL_33:
        if ( v74 == WDI_TxFrameStatus_SendPostponed && v33 )
        {
          if ( v63 )
          {
            v52 = &a5[v69];
            *((_WORD *)v25 + 44) = v52->SeqCtl;
            v25[43] = v52->PnLength;
            *(WDI_TXRX_MPDU_PN *)(v25 + 56) = v52->MpduPN;
            *((_QWORD *)v25 + 9) = v52->ReplayIHVReserved0;
            *((_QWORD *)v25 + 10) = v52->ReplayIHVReserved1;
            *(v25 - 9) = 1;
          }
          CTxMgr::PausePeerEntry(WorkItemContext, TxEntry, 0x1FFFFFFu, WDI_TX_PAUSE_REASON_PS);
        }
        if ( !*(v25 - 11) )
          goto LABEL_38;
        if ( v33 )
        {
          --v34->TxPendingCount;
          --TxEntry->TxPendingCount;
        }
        if ( v74 == WDI_TxFrameStatus_SendPostponed && *(v25 - 11) && v33 )
        {
          v49 = CTxMgr::RequeueNbl(v31, TxEntry, v34, (struct _WFC_FRAME *)(v25 - 64), v64);
          v35 = 0;
          PortId = TxEntry->PortId;
          if ( !v49 )
            v35 = 5;
          PeerId = TxEntry->PeerId;
        }
        else
        {
LABEL_38:
          v35 = v68;
        }
        if ( *(v25 - 11) )
        {
          if ( v35 == 5 && v33 )
          {
LABEL_45:
            TxQueueState = v34->TxQueueState;
            if ( (TxQueueState & 1) != 0 && !v34->TransferPendingCount && !v34->TxPendingCount )
            {
              v53 = TxQueueState & 0xFFFFFFFC | 2;
              v34->TxQueueState = v53;
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              {
                v54 = v34->PortId;
                LOBYTE(v54) = 4;
                WPP_RECORDER_SF_DDDD(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v54,
                  1,
                  255,
                  (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
                  v34->PortId,
                  v34->PeerId,
                  v34->Tid,
                  v53);
              }
            }
            if ( (v34->TxQueueState & 8) == 0 || v34->TransferPendingCount || v34->TxPendingCount )
            {
              v38 = 0;
            }
            else
            {
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              {
                v55 = v34->PortId;
                LOBYTE(v55) = 4;
                WPP_RECORDER_SF_DDD(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v55,
                  1,
                  256,
                  (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
                  v34->PortId,
                  v34->PeerId,
                  v34->Tid);
              }
              v38 = 1;
              PortId = v34->PortId;
              PeerId = v34->PeerId;
              Tid = v34->Tid;
              v75 = 1;
            }
            TxEntryState = TxEntry->TxEntryState;
            if ( (TxEntryState & 1) != 0 && !TxEntry->TransferPendingCount && !TxEntry->TxPendingCount )
            {
              v56 = TxEntryState & 0xFFFFFFFC | 2;
              TxEntry->TxEntryState = v56;
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(ppTxQueue) = 4;
                WPP_RECORDER_SF_DD(
                  WPP_GLOBAL_Control->DeviceExtension,
                  (_DWORD)ppTxQueue,
                  1,
                  257,
                  (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
                  TxEntry->TxId,
                  v56);
              }
              if ( (TxEntry->TxEntryState & 0x20) != 0 )
              {
                v57 = m_TxMgrLock->m_SpinLock.OldIrql;
                v58 = TxEntry->PortId;
                v42 = TxEntry->PeerId;
                PeerId = v42;
                PortId = v58;
                m_TxMgrLock->m_IsLocked = 0;
                KeReleaseSpinLock(&m_TxMgrLock->m_SpinLock.SpinLock, v57);
                v43 = PortId;
                v44 = v42;
                v45 = PortId;
                if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v59) = 4;
                  WPP_RECORDER_SF_DD(
                    WPP_GLOBAL_Control->DeviceExtension,
                    v59,
                    1,
                    258,
                    (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
                    PortId,
                    v42);
                }
                v6 = WorkItemContext;
                CTxMgr::PeerDeleteConfirm(WorkItemContext, v43, v42);
                goto LABEL_50;
              }
            }
LABEL_49:
            v40 = m_TxMgrLock->m_SpinLock.OldIrql;
            m_TxMgrLock->m_IsLocked = 0;
            KeReleaseSpinLock(&m_TxMgrLock->m_SpinLock.SpinLock, v40);
            v42 = PeerId;
            v43 = PortId;
            v44 = PeerId;
            v6 = WorkItemContext;
            v45 = PortId;
            v38 = v75;
LABEL_50:
            if ( v64[0] )
            {
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(a2) = 4;
                WPP_RECORDER_SF_DD(
                  WPP_GLOBAL_Control->DeviceExtension,
                  a2,
                  1,
                  259,
                  (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
                  v45,
                  v44);
              }
              LOBYTE(v41) = 1;
              ((void (__fastcall *)(void *, _QWORD, _QWORD, __int64))v6->m_pAdapter->m_MiniportDataHandlers.TxPeerBacklogHandler)(
                v6->m_pAdapter->m_MiniportTalTxRxContext,
                v43,
                v42,
                v41);
            }
            if ( v38 )
            {
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(a2) = 4;
                WPP_RECORDER_SF_DDD(
                  WPP_GLOBAL_Control->DeviceExtension,
                  a2,
                  1,
                  260,
                  (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
                  v45,
                  v44,
                  Tid);
              }
              ((void (__fastcall *)(void *, _QWORD, _QWORD))v6->m_pAdapter->m_MiniportDataHandlers.TxTalQueueInOrderHandler)(
                v6->m_pAdapter->m_MiniportTalTxRxContext,
                v42,
                (unsigned int)(1 << Tid));
            }
            v9 = v74;
            goto LABEL_53;
          }
          if ( *((_DWORD *)v25 - 15) == 1 )
          {
            v36 = v67;
            v67 = v72;
          }
          else
          {
            v36 = v70;
            v70 = v72;
          }
          v72->Link.Alignment = (ULONGLONG)v36;
        }
        if ( v33 )
          goto LABEL_45;
        goto LABEL_49;
      }
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v26) = 2;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v26,
          1,
          253,
          (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
      }
      v48 = m_TxMgrLock->m_SpinLock.OldIrql;
      m_TxMgrLock->m_IsLocked = 0;
      KeReleaseSpinLock(&m_TxMgrLock->m_SpinLock.SpinLock, v48);
    }
    else if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        251,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
    }
LABEL_53:
    a4 = v76;
    v10 = (unsigned int)(v69 + 1);
    v69 = v10;
  }
  while ( (int)v10 < v71 );
  v5 = v70;
  v8 = v67;
LABEL_55:
  m_RefVal = v6->m_InlineCompletionRundown.m_RefVal;
  while ( (m_RefVal & 1) == 0 )
  {
    v47 = m_RefVal;
    m_RefVal = _InterlockedCompareExchange(&v6->m_InlineCompletionRundown.m_RefVal, m_RefVal + 2, m_RefVal);
    if ( v47 == m_RefVal )
    {
      if ( v8 )
        CTxMgr::CompleteIhvNbl(v6, v8);
      if ( v5 )
        CTxMgr::CompleteNdisNbl((char *)v6, v5, 0);
      if ( _InterlockedExchangeAdd(&v6->m_InlineCompletionRundown.m_RefVal, 0xFFFFFFFE) == 3 )
        NdisSetEvent(&v6->m_InlineCompletionRundown.m_NdisEvent);
      goto LABEL_64;
    }
  }
  if ( CDispatchRundown::Acquire(&v6->m_DivertCompletionRundown) )
  {
    CTxMgr::DivertNBLs(v6, v51, v5);
    CDispatchRundown::Release(&v6->m_DivertCompletionRundown);
  }
  else
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return;
    LOBYTE(v50) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v50,
      1,
      350,
      (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
  }
LABEL_64:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v61) = 0;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      261,
      (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
      v61);
  }
}

```

## disassembly

```asm
0x14003a630  mov     rax, rsp
0x14003a633  mov     [rax+20h], r9
0x14003a637  mov     [rax+10h], edx
0x14003a63a  mov     [rax+8], rcx
0x14003a63e  push    rbx
0x14003a63f  push    rsi
0x14003a640  push    rdi
0x14003a641  push    r12
0x14003a643  push    r14
0x14003a645  sub     rsp, 0A0h
0x14003a64c  xor     edi, edi
0x14003a64e  mov     [rax-40h], r15
0x14003a652  mov     r14, rcx
0x14003a655  movzx   ebx, r8w
0x14003a659  mov     ecx, 0FFFFh
0x14003a65e  mov     [rsp+0C8h+var_60], rdi
0x14003a663  xor     r10d, r10d
0x14003a666  mov     [rsp+0C8h+var_77], dil
0x14003a66b  mov     [rsp+0C8h+var_70], r10
0x14003a670  mov     r15d, edx
0x14003a673  mov     [rsp+0C8h+var_74], cx
0x14003a678  mov     [rsp+0C8h+var_72], cx
0x14003a67d  mov     [rsp+0C8h+var_78], 1Fh
0x14003a682  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003a689  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14003a690  lea     rsi, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x14003a697  jz      short loc_14003A6D8
0x14003a699  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a6a0  cmp     byte ptr [rcx+29h], 5
0x14003a6a4  jnb     loc_14003B0E2
0x14003a6aa  cmp     [rcx+48h], di
0x14003a6ae  jnz     loc_14003B0E2
0x14003a6b4  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14003a6bb  jz      short loc_14003A6D8
0x14003a6bd  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a6c4  cmp     byte ptr [rcx+29h], 5
0x14003a6c8  jnb     loc_14003B10E
0x14003a6ce  cmp     [rcx+48h], di
0x14003a6d2  jnz     loc_14003B10E
0x14003a6d8  cmp     [rsp+0C8h+arg_20], rdi
0x14003a6e0  jnz     loc_14003B139
0x14003a6e6  xor     eax, eax
0x14003a6e8  mov     [rsp+0C8h+var_58], ebx
0x14003a6ec  mov     [rsp+0C8h+var_64], eax
0x14003a6f0  test    ebx, ebx
0x14003a6f2  jz      loc_14003AA15
0x14003a6f8  mov     [rsp+0C8h+var_30], rbp
0x14003a700  mov     [rsp+0C8h+var_38], r13
0x14003a708  lea     r13, WPP_9437762af08d3eac72fe4950abce8818_Traceguids
0x14003a70f  movzx   ebp, word ptr [r9+rax*2]
0x14003a714  xor     esi, esi
0x14003a716  mov     rbx, [r14+10h]
0x14003a71a  mov     edi, ebp
0x14003a71c  shr     rdi, 3
0x14003a720  add     rbx, 15E0h
0x14003a727  and     edi, 3Fh
0x14003a72a  mov     [rsp+0C8h+var_76], 0
0x14003a72f  shl     rdi, 4
0x14003a733  add     rdi, 18h
0x14003a737  mov     [rsp+0C8h+var_50], rsi
0x14003a73c  add     rdi, rbx
0x14003a73f  mov     rbx, [rbx]
0x14003a742  mov     rcx, rbx; SpinLock
0x14003a745  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003a74c  nop     dword ptr [rax+rax+00h]
0x14003a751  mov     [rbx+8], al
0x14003a754  mov     byte ptr [rbx+10h], 1
0x14003a758  mov     rcx, [rdi]
0x14003a75b  cmp     rcx, rdi
0x14003a75e  jz      loc_14003AC8E
0x14003a764  cmp     [rcx+48h], bp
0x14003a768  jz      short loc_14003A780
0x14003a76a  mov     rcx, [rcx]
0x14003a76d  cmp     rcx, rdi
0x14003a770  jnz     short loc_14003A764
0x14003a772  movzx   edx, al
0x14003a775  mov     [rbx+10h], sil
0x14003a779  mov     edi, 0C001001Bh
0x14003a77e  jmp     short loc_14003A7B8
0x14003a780  mov     rsi, [rcx+40h]
0x14003a784  mov     [rsp+0C8h+var_50], rsi
0x14003a789  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14003a790  jz      short loc_14003A7AE
0x14003a792  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a799  cmp     byte ptr [rcx+29h], 5
0x14003a79d  jnb     loc_14003AB64
0x14003a7a3  cmp     word ptr [rcx+48h], 0
0x14003a7a8  jnz     loc_14003AB64
0x14003a7ae  movzx   edx, byte ptr [rbx+8]; NewIrql
0x14003a7b2  xor     edi, edi
0x14003a7b4  mov     [rbx+10h], dil
0x14003a7b8  mov     rcx, rbx; SpinLock
0x14003a7bb  call    cs:__imp_KeReleaseSpinLock
0x14003a7c2  nop     dword ptr [rax+rax+00h]
0x14003a7c7  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14003a7ce  jz      short loc_14003A7EC
0x14003a7d0  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a7d7  cmp     byte ptr [rcx+29h], 5
0x14003a7db  jnb     loc_14003AC5A
0x14003a7e1  cmp     word ptr [rcx+48h], 0
0x14003a7e6  jnz     loc_14003AC5A
0x14003a7ec  test    rsi, rsi
0x14003a7ef  jz      loc_14003ACD0
0x14003a7f5  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14003a7fc  jz      short loc_14003A81A
0x14003a7fe  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a805  cmp     byte ptr [rcx+29h], 5
0x14003a809  jnb     loc_14003AD10
0x14003a80f  cmp     word ptr [rcx+48h], 0
0x14003a814  jnz     loc_14003AD10
0x14003a81a  mov     r13, [r14+20h]
0x14003a81e  mov     rsi, [rsi+60h]
0x14003a822  mov     rcx, r13; SpinLock
0x14003a825  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003a82c  nop     dword ptr [rax+rax+00h]
0x14003a831  mov     [r13+8], al
0x14003a835  mov     byte ptr [r13+10h], 1
0x14003a83a  cmp     byte ptr [rsi-0Ah], 1
0x14003a83e  jz      loc_14003AA99
0x14003a844  mov     byte ptr [rsi-0Ah], 1
0x14003a848  lea     rcx, [r14+130h]; this
0x14003a84f  mov     [rsi-10h], r15d
0x14003a853  lea     rdi, [rsi+20h]
0x14003a857  cmp     dword ptr [r14+0F8h], 1
0x14003a85f  mov     [rsp+0C8h+arg_10], 0
0x14003a867  mov     [rsp+0C8h+var_68], r15d
0x14003a86c  jnz     loc_14003AB12
0x14003a872  mov     rdx, rdi
0x14003a875  movzx   edx, word ptr [rdx]; unsigned __int16
0x14003a878  call    ?GetTxEntry@CTxEntryTable@@QEAAPEAU_WFC_TX_ENTRY@@G@Z; CTxEntryTable::GetTxEntry(ushort)
0x14003a87d  mov     r12, rax
0x14003a880  test    rax, rax
0x14003a883  jz      loc_14003ABC0
0x14003a889  cmp     dword ptr [r14+0F8h], 1
0x14003a891  mov     r15b, 1
0x14003a894  movzx   ecx, byte ptr [rsi+24h]; this
0x14003a898  jnz     short loc_14003A8A2
0x14003a89a  cmp     cl, 10h
0x14003a89d  setnbe  cl
0x14003a8a0  jmp     short loc_14003A8B0
0x14003a8a2  cmp     cl, 18h
0x14003a8a5  setbe   al
0x14003a8a8  test    al, al
0x14003a8aa  jz      loc_14003AB1B
0x14003a8b0  mov     rdx, [r12+88h]
0x14003a8b8  test    rdx, rdx
0x14003a8bb  jz      loc_14003AB1B
0x14003a8c1  movzx   eax, cl
0x14003a8c4  mov     r14, [rdx+rax*8]
0x14003a8c8  mov     edi, [rsp+0C8h+arg_8]
0x14003a8cf  cmp     edi, 5
0x14003a8d2  jz      loc_14003AD5A
0x14003a8d8  cmp     byte ptr [rsi-0Bh], 0
0x14003a8dc  jz      short loc_14003A8FC
0x14003a8de  test    r15b, r15b
0x14003a8e1  jz      short loc_14003A8F3
0x14003a8e3  mov     eax, 0FFFFh
0x14003a8e8  add     [r14+34h], ax
0x14003a8ed  add     [r12+1Ch], ax
0x14003a8f3  cmp     edi, 5
0x14003a8f6  jz      loc_14003AAC4
0x14003a8fc  mov     ecx, [rsp+0C8h+var_68]
0x14003a900  cmp     byte ptr [rsi-0Bh], 0
0x14003a904  jz      short loc_14003A92B
0x14003a906  cmp     ecx, 5
0x14003a909  jz      loc_14003AB23
0x14003a90f  cmp     dword ptr [rsi-3Ch], 1
0x14003a913  mov     rax, [rsp+0C8h+var_50]
0x14003a918  jz      loc_14003AC7F
0x14003a91e  mov     rcx, [rsp+0C8h+var_60]
0x14003a923  mov     [rsp+0C8h+var_60], rax
0x14003a928  mov     [rax], rcx
0x14003a92b  test    r15b, r15b
0x14003a92e  jz      short loc_14003A96C
0x14003a930  mov     r8d, [r14+38h]
0x14003a934  test    r8b, 1
0x14003a938  jnz     loc_14003ADC9
0x14003a93e  lea     rbp, WPP_RECORDER_INITIALIZED
0x14003a945  test    r15b, r15b
0x14003a948  jz      short loc_14003A96C
0x14003a94a  mov     eax, [r14+38h]
0x14003a94e  test    al, 8
0x14003a950  jnz     loc_14003AE50
0x14003a956  movzx   esi, [rsp+0C8h+arg_10]
0x14003a95e  mov     ecx, [r12+8]
0x14003a963  test    cl, 1
0x14003a966  jnz     loc_14003AEE3
0x14003a96c  movzx   edx, byte ptr [r13+8]; NewIrql
0x14003a971  mov     rcx, r13; SpinLock
0x14003a974  mov     byte ptr [r13+10h], 0
0x14003a979  call    cs:__imp_KeReleaseSpinLock
0x14003a980  nop     dword ptr [rax+rax+00h]
0x14003a985  movzx   r12d, [rsp+0C8h+var_72]
0x14003a98b  lea     rbp, WPP_RECORDER_INITIALIZED
0x14003a992  movzx   r13d, [rsp+0C8h+var_74]
0x14003a998  mov     ebx, r12d
0x14003a99b  mov     r14, [rsp+0C8h+WorkItemContext]
0x14003a9a3  mov     edi, r13d
0x14003a9a6  movzx   esi, [rsp+0C8h+arg_10]
0x14003a9ae  cmp     [rsp+0C8h+var_76], 0
0x14003a9b3  jnz     loc_14003B001
0x14003a9b9  test    sil, sil
0x14003a9bc  jnz     loc_14003AB88
0x14003a9c2  mov     r15d, [rsp+0C8h+arg_8]
0x14003a9ca  lea     r12, WPP_RECORDER_INITIALIZED
0x14003a9d1  lea     r13, WPP_9437762af08d3eac72fe4950abce8818_Traceguids
0x14003a9d8  mov     eax, [rsp+0C8h+var_64]
0x14003a9dc  mov     r9, [rsp+0C8h+arg_18]
0x14003a9e4  inc     eax
0x14003a9e6  mov     [rsp+0C8h+var_64], eax
0x14003a9ea  cmp     eax, [rsp+0C8h+var_58]
0x14003a9ee  jl      loc_14003A70F
0x14003a9f4  mov     r13, [rsp+0C8h+var_38]
0x14003a9fc  lea     rsi, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x14003aa03  mov     rbp, [rsp+0C8h+var_30]
0x14003aa0b  mov     rdi, [rsp+0C8h+var_60]
0x14003aa10  mov     r10, [rsp+0C8h+var_70]
0x14003aa15  mov     eax, [r14+70h]
0x14003aa19  mov     r15, [rsp+0C8h+var_40]
0x14003aa21  test    al, 1
0x14003aa23  jnz     loc_14003AB31
0x14003aa29  lea     ecx, [rax+2]
0x14003aa2c  lock cmpxchg [r14+70h], ecx
0x14003aa32  jnz     short loc_14003AA21
0x14003aa34  test    r10, r10
0x14003aa37  jnz     loc_14003B0A0
0x14003aa3d  test    rdi, rdi
0x14003aa40  jz      short loc_14003AA50
0x14003aa42  xor     r8d, r8d; unsigned __int8
0x14003aa45  mov     rdx, rdi; struct _NET_BUFFER_LIST *
0x14003aa48  mov     rcx, r14; WorkItemContext
0x14003aa4b  call    ?CompleteNdisNbl@CTxMgr@@AEAAXPEAU_NET_BUFFER_LIST@@E@Z; CTxMgr::CompleteNdisNbl(_NET_BUFFER_LIST *,uchar)
0x14003aa50  mov     eax, 0FFFFFFFEh
0x14003aa55  lock xadd [r14+70h], eax
0x14003aa5b  cmp     eax, 3
0x14003aa5e  jz      loc_14003B18E
0x14003aa64  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14003aa6b  jz      short loc_14003AA89
0x14003aa6d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aa74  cmp     byte ptr [rcx+29h], 5
0x14003aa78  jnb     loc_14003B0B9
0x14003aa7e  cmp     word ptr [rcx+48h], 0
0x14003aa83  jnz     loc_14003B0B9
0x14003aa89  add     rsp, 0A0h
0x14003aa90  pop     r14
0x14003aa92  pop     r12
0x14003aa94  pop     rdi
0x14003aa95  pop     rsi
0x14003aa96  pop     rbx
0x14003aa97  retn
0x14003aa99  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14003aaa0  jnz     loc_14003AD27
0x14003aaa6  movzx   edx, byte ptr [r13+8]; NewIrql
0x14003aaab  mov     rcx, r13; SpinLock
0x14003aaae  mov     byte ptr [r13+10h], 0
0x14003aab3  call    cs:__imp_KeReleaseSpinLock
0x14003aaba  nop     dword ptr [rax+rax+00h]
0x14003aabf  jmp     loc_14003A9D1
0x14003aac4  cmp     byte ptr [rsi-0Bh], 0
0x14003aac8  jz      loc_14003A8FC
0x14003aace  test    r15b, r15b
0x14003aad1  jz      loc_14003A8FC
0x14003aad7  lea     rax, [rsp+0C8h+var_76]
0x14003aadc  mov     r8, r14; struct _WFC_TX_QUEUE *
0x14003aadf  lea     r9, [rsi-40h]; struct _WFC_FRAME *
0x14003aae3  mov     [rsp+0C8h+var_A8], rax; unsigned __int8 *
0x14003aae8  mov     rdx, r12; struct _WFC_TX_ENTRY *
0x14003aaeb  call    ?RequeueNbl@CTxMgr@@AEAAHPEAU_WFC_TX_ENTRY@@PEAU_WFC_TX_QUEUE@@PEAU_WFC_FRAME@@PEAE@Z; CTxMgr::RequeueNbl(_WFC_TX_ENTRY *,_WFC_TX_QUEUE *,_WFC_FRAME *,uchar *)
0x14003aaf0  xor     ecx, ecx
0x14003aaf2  test    eax, eax
0x14003aaf4  movzx   eax, word ptr [r12+4]
0x14003aafa  mov     [rsp+0C8h+var_74], ax
0x14003aaff  movzx   eax, word ptr [r12+6]
0x14003ab05  cmovz   ecx, edi
0x14003ab08  mov     [rsp+0C8h+var_72], ax
0x14003ab0d  jmp     loc_14003A900
0x14003ab12  lea     rdx, [rsi+22h]
0x14003ab16  jmp     loc_14003A875
0x14003ab1b  xor     r14d, r14d
0x14003ab1e  jmp     loc_14003A8C8
0x14003ab23  test    r15b, r15b
0x14003ab26  jz      loc_14003A90F
0x14003ab2c  jmp     loc_14003A930
0x14003ab31  lea     rcx, [r14+90h]; this
0x14003ab38  call    ?Acquire@CDispatchRundown@@QEAA_NXZ; CDispatchRundown::Acquire(void)
0x14003ab3d  test    al, al
0x14003ab3f  jz      loc_14003AC25
0x14003ab45  mov     r8, rdi; struct _NET_BUFFER_LIST *
0x14003ab48  mov     rdx, r10; struct _NET_BUFFER_LIST *
0x14003ab4b  mov     rcx, r14; this
0x14003ab4e  call    ?DivertNBLs@CTxMgr@@AEAAXPEAU_NET_BUFFER_LIST@@0@Z; CTxMgr::DivertNBLs(_NET_BUFFER_LIST *,_NET_BUFFER_LIST *)
0x14003ab53  lea     rcx, [r14+90h]; this
0x14003ab5a  call    ?Release@CDispatchRundown@@QEAAXXZ; CDispatchRundown::Release(void)
0x14003ab5f  jmp     loc_14003AA64
0x14003ab64  mov     rcx, [rcx+40h]
0x14003ab68  mov     r9d, 48h ; 'H'
0x14003ab6e  mov     dword ptr [rsp+0C8h+var_98], ebp
0x14003ab72  mov     dl, 5
0x14003ab74  mov     [rsp+0C8h+var_A0], rsi
0x14003ab79  mov     [rsp+0C8h+var_A8], r13
  ... truncated ...
```
