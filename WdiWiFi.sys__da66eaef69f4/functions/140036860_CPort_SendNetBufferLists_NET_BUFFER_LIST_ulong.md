# CPort::SendNetBufferLists(_NET_BUFFER_LIST *,ulong)

- ea: `0x140036860`
- end: `0x140036eb5`
- name: `?SendNetBufferLists@CPort@@QEAAXPEAU_NET_BUFFER_LIST@@K@Z`
- size: `1621`
- prototype: `void __fastcall(CPort *__hidden this, struct _NET_BUFFER_LIST *, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140035eb0`

## callees

- `0x140010730`
- `0x1400122e0`
- `0x14002aa28`
- `0x1400330a0`
- `0x140033730`
- `0x140034e04`
- `0x140034ec4`
- `0x140036270`
- `0x140036860`
- `0x140036ec0`
- `0x140037f80`
- `0x140086a5c`
- `0x1400871bc`
- `0x14008726c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14003697e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140036a7e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140036b43`
- `ntoskrnl!KeReleaseSpinLock` at `0x140036c55`
- `ntoskrnl!KeReleaseSpinLock` at `0x140036d0c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140036d69`
- `ntoskrnl!KeReleaseSpinLock` at `0x140036dd8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003697e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140036a7e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140036b43`
- `ntoskrnl!KeReleaseSpinLock` at `0x140036c55`
- `ntoskrnl!KeReleaseSpinLock` at `0x140036d0c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140036d69`
- `ntoskrnl!KeReleaseSpinLock` at `0x140036dd8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140036948`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400369d4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140036be3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140036948`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400369d4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140036be3`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x140036c97`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x140036c97`

## pseudocode

```c
void __fastcall CPort::SendNetBufferLists(CPort *this, struct _NET_BUFFER_LIST *a2, int a3)
{
  NDIS_STATUS v5; // ebp
  unsigned __int8 v6; // r12
  char v7; // r15
  __int64 *v8; // rdx
  unsigned int m_State; // ecx
  CAdapter **p_m_pAdapter; // r14
  struct _NET_BUFFER_LIST *Alignment; // r13
  int v12; // edx
  int v13; // r8d
  CNdisSpinLock *m_PortLock; // r15
  char *v15; // rbp
  NDIS_STATUS v16; // eax
  KIRQL v17; // dl
  CNdisSpinLock *v18; // rsi
  int v19; // edx
  int v20; // r8d
  unsigned int m_NblCnt; // ebp
  int v22; // r8d
  unsigned int v23; // edx
  KIRQL v24; // dl
  NDIS_STATUS PortErrorStatus; // esi
  int v26; // edx
  KIRQL v27; // dl
  CNdisSpinLock *m_TxPrequeueLock; // rsi
  int v29; // edx
  int v30; // r8d
  unsigned int v31; // r15d
  int v32; // r8d
  KIRQL v33; // dl
  struct _NET_BUFFER_LIST *v34; // rcx
  int m_WfcPortId; // edx
  KIRQL OldIrql; // dl
  KIRQL v37; // dl
  KIRQL v38; // dl
  __int64 v39; // [rsp+28h] [rbp-60h]
  unsigned __int8 v40; // [rsp+90h] [rbp+8h] BYREF
  int v41; // [rsp+A0h] [rbp+18h]
  unsigned __int8 v42; // [rsp+A8h] [rbp+20h] BYREF

  v41 = a3;
  v5 = 0;
  v6 = 0;
  v42 = 0;
  v40 = 0;
  v7 = a3;
  v8 = WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v8) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v8,
      1,
      77,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids);
    v8 = WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids;
  }
  m_State = this->m_State;
  if ( m_State )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v8) = 5;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v8,
        (_DWORD)WPP_GLOBAL_Control,
        78,
        (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
        (char)this,
        this->m_WfcPortId,
        m_State);
    }
    PortErrorStatus = CPort::GetPortErrorStatus(this);
    p_m_pAdapter = &this->m_pAdapter;
  }
  else
  {
    p_m_pAdapter = &this->m_pAdapter;
    if ( this->m_pAdapter->m_TxMgr.m_TotalPrequeueCount <= 0 )
      goto LABEL_6;
    m_TxPrequeueLock = (*p_m_pAdapter)->m_TxMgr.m_TxPrequeueLock;
    m_TxPrequeueLock->m_SpinLock.OldIrql = KeAcquireSpinLockRaiseToDpc(&m_TxPrequeueLock->m_SpinLock.SpinLock);
    m_TxPrequeueLock->m_IsLocked = 1;
    if ( (*p_m_pAdapter)->m_TxMgr.m_TotalPrequeueCount <= 0 )
    {
      if ( this->m_bIsTxPortQueueAllowed )
      {
        OldIrql = m_TxPrequeueLock->m_SpinLock.OldIrql;
        m_TxPrequeueLock->m_IsLocked = 0;
        KeReleaseSpinLock(&m_TxPrequeueLock->m_SpinLock.SpinLock, OldIrql);
LABEL_6:
        while ( a2 )
        {
          Alignment = (struct _NET_BUFFER_LIST *)a2->Link.Alignment;
          a2->Link.Alignment = 0;
          v5 = CTxMgr::InitializeTxWfcFrame(&(*p_m_pAdapter)->m_TxMgr, a2, this->m_WfcPortId, this->m_KeyConfigured);
          if ( v5 )
            goto LABEL_10;
          m_PortLock = this->m_PortLock;
          v15 = (char *)a2->MiniportReserved[0];
          m_PortLock->m_SpinLock.OldIrql = KeAcquireSpinLockRaiseToDpc(&m_PortLock->m_SpinLock.SpinLock);
          m_PortLock->m_IsLocked = 1;
          if ( this->m_State )
          {
            v16 = CPort::GetPortErrorStatus(this);
            m_PortLock->m_IsLocked = 0;
            v5 = v16;
            KeReleaseSpinLock(&m_PortLock->m_SpinLock.SpinLock, v17);
            if ( v5 )
              goto LABEL_10;
          }
          else
          {
            ++this->m_txPendingFrames;
            *(v15 - 8) = 1;
            v27 = m_PortLock->m_SpinLock.OldIrql;
            m_PortLock->m_IsLocked = 0;
            KeReleaseSpinLock(&m_PortLock->m_SpinLock.SpinLock, v27);
          }
          v5 = CTxMgr::ProcessNBL(&(*p_m_pAdapter)->m_TxMgr, a2, &v42);
          if ( v5 )
          {
LABEL_10:
            if ( a2->MiniportReserved[0] )
            {
              CPort::FreeTxWfcFrame(this, a2, &v40);
              v6 = v40;
            }
            a2->Link.Alignment = (ULONGLONG)Alignment;
            if ( v42 )
            {
              v18 = this->m_pAdapter->m_TxMgr.m_TxPrequeueLock;
              v18->m_SpinLock.OldIrql = KeAcquireSpinLockRaiseToDpc(&v18->m_SpinLock.SpinLock);
              v18->m_IsLocked = 1;
              if ( this->m_bIsTxPortQueueAllowed )
              {
                m_NblCnt = this->m_TxPortQueue.m_NblCnt;
                NblChain::AddChainTail(&this->m_TxPortQueue, a2);
                if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
                  && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
                {
                  v23 = this->m_TxPortQueue.m_NblCnt - m_NblCnt;
                  LOBYTE(v23) = 5;
                  WPP_RECORDER_SF_qDL(
                    WPP_GLOBAL_Control->DeviceExtension,
                    v23,
                    v22,
                    81,
                    (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
                    (char)this,
                    this->m_WfcPortId,
                    LOBYTE(this->m_TxPortQueue.m_NblCnt) - m_NblCnt);
                }
                _InterlockedAdd(
                  &this->m_pAdapter->m_TxMgr.m_TotalPrequeueCount,
                  this->m_TxPortQueue.m_NblCnt - m_NblCnt);
                v24 = v18->m_SpinLock.OldIrql;
                v18->m_IsLocked = 0;
                KeReleaseSpinLock(&v18->m_SpinLock.SpinLock, v24);
                CTxMgr::SchedulePrequeueWorkitem(&(*p_m_pAdapter)->m_TxMgr);
                a2 = 0;
              }
              else
              {
                if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
                  && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
                {
                  LOBYTE(v19) = 5;
                  WPP_RECORDER_SF_qD(
                    WPP_GLOBAL_Control->DeviceExtension,
                    v19,
                    v20,
                    82,
                    (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
                    (char)this,
                    this->m_WfcPortId);
                }
                a2->Link.Alignment = (ULONGLONG)Alignment;
                v38 = v18->m_SpinLock.OldIrql;
                v18->m_IsLocked = 0;
                KeReleaseSpinLock(&v18->m_SpinLock.SpinLock, v38);
              }
              v5 = 0;
              PortErrorStatus = 0;
              goto LABEL_21;
            }
            PortErrorStatus = v5;
            if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v12) = 2;
              WPP_RECORDER_SF_qDD(
                WPP_GLOBAL_Control->DeviceExtension,
                v12,
                v13,
                83,
                (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
                (char)this,
                this->m_WfcPortId,
                v5);
              CTxMgr::ServiceQueues(&(*p_m_pAdapter)->m_TxMgr);
              v7 = v41;
              goto LABEL_38;
            }
LABEL_21:
            v7 = v41;
            goto LABEL_22;
          }
          a2 = Alignment;
        }
        a2 = 0;
        PortErrorStatus = 0;
        goto LABEL_21;
      }
    }
    else if ( this->m_bIsTxPortQueueAllowed )
    {
      v31 = this->m_TxPortQueue.m_NblCnt;
      NblChain::AddChainTail(&this->m_TxPortQueue, a2);
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        m_WfcPortId = this->m_WfcPortId;
        LOBYTE(m_WfcPortId) = 5;
        WPP_RECORDER_SF_qDL(
          WPP_GLOBAL_Control->DeviceExtension,
          m_WfcPortId,
          v32,
          79,
          (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
          (char)this,
          this->m_WfcPortId,
          this->m_TxPortQueue.m_NblCnt);
      }
      _InterlockedAdd(&(*p_m_pAdapter)->m_TxMgr.m_TotalPrequeueCount, this->m_TxPortQueue.m_NblCnt - v31);
      v33 = m_TxPrequeueLock->m_SpinLock.OldIrql;
      m_TxPrequeueLock->m_IsLocked = 0;
      KeReleaseSpinLock(&m_TxPrequeueLock->m_SpinLock.SpinLock, v33);
      CTxMgr::ServiceQueues(&(*p_m_pAdapter)->m_TxMgr);
      goto LABEL_23;
    }
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v29) = 4;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v29,
        v30,
        80,
        (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
        (char)this,
        this->m_WfcPortId);
    }
    v37 = m_TxPrequeueLock->m_SpinLock.OldIrql;
    m_TxPrequeueLock->m_IsLocked = 0;
    KeReleaseSpinLock(&m_TxPrequeueLock->m_SpinLock.SpinLock, v37);
    PortErrorStatus = 0;
  }
LABEL_22:
  CTxMgr::ServiceQueues(&(*p_m_pAdapter)->m_TxMgr);
  if ( a2 )
  {
LABEL_38:
    v34 = a2;
    do
    {
      v34->Status = PortErrorStatus;
      v34 = (struct _NET_BUFFER_LIST *)v34->Link.Alignment;
    }
    while ( v34 );
    NdisMSendNetBufferListsComplete((*p_m_pAdapter)->m_MiniportAdapterHandle, a2, v7 & 1);
  }
LABEL_23:
  if ( v6 )
    CPort::CompletePendingCancelSendsOrHaltJobs(this);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v39) = v5;
    LOBYTE(v26) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v26,
      1,
      84,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
      v39);
  }
}

```

## disassembly

```asm
0x140036860  mov     rax, rsp
0x140036863  mov     [rax+18h], r8d
0x140036867  push    rbp
0x140036868  sub     rsp, 80h
0x14003686f  mov     [rax+10h], rbx
0x140036873  mov     rbx, rdx
0x140036876  mov     [rax-18h], rdi
0x14003687a  mov     rdi, rcx
0x14003687d  mov     [rax-20h], r12
0x140036881  mov     [rax-28h], r13
0x140036885  xor     r13d, r13d
0x140036888  mov     ebp, r13d
0x14003688b  mov     [rax-38h], r15
0x14003688f  xor     r12b, r12b
0x140036892  mov     [rax+20h], bpl
0x140036896  mov     [rax+8], r12b
0x14003689a  mov     r15d, r8d
0x14003689d  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400368a4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400368ab  lea     rdx, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400368b2  jz      short loc_1400368CF
0x1400368b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400368bb  cmp     byte ptr [rcx+29h], 5
0x1400368bf  jnb     loc_140036B7B
0x1400368c5  cmp     [rcx+48h], bp
0x1400368c9  jnz     loc_140036B7B
0x1400368cf  mov     ecx, [rdi+368h]
0x1400368d5  mov     [rsp+88h+var_10], rsi
0x1400368da  mov     [rsp+88h+var_30], r14
0x1400368df  test    ecx, ecx
0x1400368e1  jnz     loc_140036E50
0x1400368e7  mov     rax, [rdi+58h]
0x1400368eb  lea     r14, [rdi+58h]
0x1400368ef  mov     ecx, [rax+3A18h]
0x1400368f5  test    ecx, ecx
0x1400368f7  jg      loc_140036BD6
0x1400368fd  mov     [rsp+88h+var_40], r13
0x140036902  test    rbx, rbx
0x140036905  jz      loc_140036AA1
0x14003690b  mov     r13, [rbx]
0x14003690e  mov     rdx, rbx; struct _NET_BUFFER_LIST *
0x140036911  mov     qword ptr [rbx], 0
0x140036918  mov     rcx, [r14]
0x14003691b  movzx   r9d, byte ptr [rdi+358h]; unsigned __int8
0x140036923  add     rcx, 3A10h; this
0x14003692a  movzx   r8d, word ptr [rdi+64h]; unsigned __int16
0x14003692f  call    ?InitializeTxWfcFrame@CTxMgr@@QEAAHPEAU_NET_BUFFER_LIST@@GE@Z; CTxMgr::InitializeTxWfcFrame(_NET_BUFFER_LIST *,ushort,uchar)
0x140036934  mov     ebp, eax
0x140036936  test    eax, eax
0x140036938  jnz     short loc_140036992
0x14003693a  mov     r15, [rdi+3A0h]
0x140036941  mov     rbp, [rbx+60h]
0x140036945  mov     rcx, r15; SpinLock
0x140036948  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003694f  nop     dword ptr [rax+rax+00h]
0x140036954  mov     [r15+8], al
0x140036958  movzx   edx, al
0x14003695b  mov     byte ptr [r15+10h], 1
0x140036960  cmp     dword ptr [rdi+368h], 0
0x140036967  jz      loc_140036B2D
0x14003696d  mov     rcx, rdi; this
0x140036970  call    ?GetPortErrorStatus@CPort@@AEAAHXZ; CPort::GetPortErrorStatus(void)
0x140036975  mov     rcx, r15; SpinLock
0x140036978  mov     [r15+10h], r12b
0x14003697c  mov     ebp, eax
0x14003697e  call    cs:__imp_KeReleaseSpinLock
0x140036985  nop     dword ptr [rax+rax+00h]
0x14003698a  test    ebp, ebp
0x14003698c  jz      loc_140036B4F
0x140036992  cmp     qword ptr [rbx+60h], 0
0x140036997  jz      short loc_1400369B5
0x140036999  lea     r8, [rsp+88h+arg_0]; unsigned __int8 *
0x1400369a1  mov     rdx, rbx; struct _NET_BUFFER_LIST *
0x1400369a4  mov     rcx, rdi; this
0x1400369a7  call    ?FreeTxWfcFrame@CPort@@AEAAHPEAU_NET_BUFFER_LIST@@PEAE@Z; CPort::FreeTxWfcFrame(_NET_BUFFER_LIST *,uchar *)
0x1400369ac  movzx   r12d, [rsp+88h+arg_0]
0x1400369b5  mov     [rbx], r13
0x1400369b8  cmp     [rsp+88h+arg_18], 0
0x1400369c0  jz      loc_140036DE9
0x1400369c6  mov     rax, [rdi+58h]
0x1400369ca  mov     rsi, [rax+3A48h]
0x1400369d1  mov     rcx, rsi; SpinLock
0x1400369d4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400369db  nop     dword ptr [rax+rax+00h]
0x1400369e0  mov     [rsi+8], al
0x1400369e3  mov     byte ptr [rsi+10h], 1
0x1400369e7  cmp     byte ptr [rdi+390h], 0
0x1400369ee  jz      loc_140036D7C
0x1400369f4  lea     rcx, [rdi+378h]; this
0x1400369fb  mov     rdx, rbx; struct _NET_BUFFER_LIST *
0x1400369fe  mov     ebp, [rcx+10h]
0x140036a01  call    ?AddChainTail@NblChain@@QEAAXPEAU_NET_BUFFER_LIST@@@Z; NblChain::AddChainTail(_NET_BUFFER_LIST *)
0x140036a06  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140036a0d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140036a14  jz      short loc_140036A60
0x140036a16  mov     rcx, cs:WPP_GLOBAL_Control
0x140036a1d  cmp     byte ptr [rcx+29h], 5
0x140036a21  jnb     short loc_140036A2A
0x140036a23  cmp     word ptr [rcx+48h], 0
0x140036a28  jz      short loc_140036A60
0x140036a2a  movzx   eax, word ptr [rdi+64h]
0x140036a2e  mov     r9d, 51h ; 'Q'
0x140036a34  mov     edx, [rdi+388h]
0x140036a3a  mov     rcx, [rcx+40h]
0x140036a3e  sub     edx, ebp
0x140036a40  mov     [rsp+88h+var_50], edx
0x140036a44  mov     dl, 5
0x140036a46  mov     [rsp+88h+var_58], eax
0x140036a4a  lea     rax, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x140036a51  mov     [rsp+88h+var_60], rdi
0x140036a56  mov     [rsp+88h+var_68], rax
0x140036a5b  call    WPP_RECORDER_SF_qDL
0x140036a60  mov     edx, [rdi+388h]
0x140036a66  mov     rax, [rdi+58h]
0x140036a6a  sub     edx, ebp
0x140036a6c  lock add [rax+3A18h], edx
0x140036a73  movzx   edx, byte ptr [rsi+8]; NewIrql
0x140036a77  mov     rcx, rsi; SpinLock
0x140036a7a  mov     byte ptr [rsi+10h], 0
0x140036a7e  call    cs:__imp_KeReleaseSpinLock
0x140036a85  nop     dword ptr [rax+rax+00h]
0x140036a8a  mov     rcx, [r14]
0x140036a8d  add     rcx, 3A10h; WorkItemContext
0x140036a94  call    ?SchedulePrequeueWorkitem@CTxMgr@@QEAAXXZ; CTxMgr::SchedulePrequeueWorkitem(void)
0x140036a99  xor     ebx, ebx
0x140036a9b  xor     ebp, ebp
0x140036a9d  xor     esi, esi
0x140036a9f  jmp     short loc_140036AA8
0x140036aa1  mov     rbx, [rsp+88h+var_40]
0x140036aa6  mov     esi, ebx
0x140036aa8  mov     r15d, [rsp+88h+arg_10]
0x140036ab0  mov     rcx, [r14]
0x140036ab3  add     rcx, 3A10h; this
0x140036aba  call    ?ServiceQueues@CTxMgr@@QEAAXXZ; CTxMgr::ServiceQueues(void)
0x140036abf  test    rbx, rbx
0x140036ac2  jnz     loc_140036C75
0x140036ac8  lea     rbx, WPP_RECORDER_INITIALIZED
0x140036acf  mov     r15, [rsp+88h+var_38]
0x140036ad4  test    r12b, r12b
0x140036ad7  mov     r12, [rsp+88h+var_20]
0x140036adc  mov     r14, [rsp+88h+var_30]
0x140036ae1  mov     r13, [rsp+88h+var_28]
0x140036ae6  mov     rsi, [rsp+88h+var_10]
0x140036aeb  jnz     loc_140036EA8
0x140036af1  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x140036af8  mov     rbx, [rsp+88h+arg_8]
0x140036b00  mov     rdi, [rsp+88h+var_18]
0x140036b05  jz      short loc_140036B23
0x140036b07  mov     rcx, cs:WPP_GLOBAL_Control
0x140036b0e  cmp     byte ptr [rcx+29h], 5
0x140036b12  jnb     loc_140036BAA
0x140036b18  cmp     word ptr [rcx+48h], 0
0x140036b1d  jnz     loc_140036BAA
0x140036b23  add     rsp, 80h
0x140036b2a  pop     rbp
0x140036b2b  retn
0x140036b2d  inc     dword ptr [rdi+370h]
0x140036b33  mov     rcx, r15; SpinLock
0x140036b36  mov     byte ptr [rbp-8], 1
0x140036b3a  movzx   edx, byte ptr [r15+8]; NewIrql
0x140036b3f  mov     [r15+10h], r12b
0x140036b43  call    cs:__imp_KeReleaseSpinLock
0x140036b4a  nop     dword ptr [rax+rax+00h]
0x140036b4f  mov     rcx, [r14]
0x140036b52  lea     r8, [rsp+88h+arg_18]; unsigned __int8 *
0x140036b5a  add     rcx, 3A10h; this
0x140036b61  mov     rdx, rbx; struct _NET_BUFFER_LIST *
0x140036b64  call    ?ProcessNBL@CTxMgr@@QEAAHPEAU_NET_BUFFER_LIST@@PEAE@Z; CTxMgr::ProcessNBL(_NET_BUFFER_LIST *,uchar *)
0x140036b69  mov     ebp, eax
0x140036b6b  test    eax, eax
0x140036b6d  jnz     loc_140036992
0x140036b73  mov     rbx, r13
0x140036b76  jmp     loc_140036902
0x140036b7b  mov     rcx, [rcx+40h]
0x140036b7f  mov     r9d, 4Dh ; 'M'
0x140036b85  mov     [rsp+88h+var_68], rdx
0x140036b8a  mov     r8d, 1
0x140036b90  mov     dl, 5
0x140036b92  call    WPP_RECORDER_SF_
0x140036b97  lea     rax, WPP_RECORDER_INITIALIZED
0x140036b9e  lea     rdx, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x140036ba5  jmp     loc_1400368CF
0x140036baa  mov     rcx, [rcx+40h]
0x140036bae  lea     rax, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x140036bb5  mov     r9d, 54h ; 'T'
0x140036bbb  mov     dword ptr [rsp+88h+var_60], ebp
0x140036bbf  mov     r8d, 1
0x140036bc5  mov     [rsp+88h+var_68], rax
0x140036bca  mov     dl, 5
0x140036bcc  call    WPP_RECORDER_SF_D
0x140036bd1  jmp     loc_140036B23
0x140036bd6  mov     rax, [r14]
0x140036bd9  mov     rsi, [rax+3A48h]
0x140036be0  mov     rcx, rsi; SpinLock
0x140036be3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140036bea  nop     dword ptr [rax+rax+00h]
0x140036bef  mov     [rsi+8], al
0x140036bf2  mov     byte ptr [rsi+10h], 1
0x140036bf6  mov     rax, [r14]
0x140036bf9  mov     ecx, [rax+3A18h]
0x140036bff  test    ecx, ecx
0x140036c01  jle     loc_140036CF8
0x140036c07  cmp     [rdi+390h], bpl
0x140036c0e  jz      loc_140036D1D
0x140036c14  lea     rcx, [rdi+378h]; this
0x140036c1b  mov     rdx, rbx; struct _NET_BUFFER_LIST *
0x140036c1e  mov     r15d, [rcx+10h]
0x140036c22  call    ?AddChainTail@NblChain@@QEAAXPEAU_NET_BUFFER_LIST@@@Z; NblChain::AddChainTail(_NET_BUFFER_LIST *)
0x140036c27  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140036c2e  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140036c35  jnz     short loc_140036CA8
0x140036c37  mov     edx, [rdi+388h]
0x140036c3d  mov     rax, [r14]
0x140036c40  sub     edx, r15d
0x140036c43  lock add [rax+3A18h], edx
0x140036c4a  movzx   edx, byte ptr [rsi+8]; NewIrql
0x140036c4e  mov     rcx, rsi; SpinLock
0x140036c51  mov     [rsi+10h], bpl
0x140036c55  call    cs:__imp_KeReleaseSpinLock
0x140036c5c  nop     dword ptr [rax+rax+00h]
0x140036c61  mov     rcx, [r14]
0x140036c64  add     rcx, 3A10h; this
0x140036c6b  call    ?ServiceQueues@CTxMgr@@QEAAXXZ; CTxMgr::ServiceQueues(void)
0x140036c70  jmp     loc_140036ACF
0x140036c75  mov     rcx, rbx
0x140036c78  mov     [rcx+8Ch], esi
0x140036c7e  mov     rcx, [rcx]
0x140036c81  test    rcx, rcx
0x140036c84  jnz     short loc_140036C78
0x140036c86  mov     rcx, [r14]
0x140036c89  and     r15d, 1
0x140036c8d  mov     r8d, r15d; SendCompleteFlags
0x140036c90  mov     rdx, rbx; NetBufferList
0x140036c93  mov     rcx, [rcx+58h]; MiniportAdapterHandle
0x140036c97  call    cs:__imp_NdisMSendNetBufferListsComplete
0x140036c9e  nop     dword ptr [rax+rax+00h]
0x140036ca3  jmp     loc_140036AC8
0x140036ca8  mov     rcx, cs:WPP_GLOBAL_Control
0x140036caf  cmp     byte ptr [rcx+29h], 5
0x140036cb3  jnb     short loc_140036CBF
0x140036cb5  cmp     [rcx+48h], bp
0x140036cb9  jz      loc_140036C37
0x140036cbf  movzx   edx, word ptr [rdi+64h]
0x140036cc3  mov     r9d, 4Fh ; 'O'
0x140036cc9  mov     eax, [rdi+388h]
0x140036ccf  mov     rcx, [rcx+40h]
0x140036cd3  mov     [rsp+88h+var_50], eax
0x140036cd7  lea     rax, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x140036cde  mov     [rsp+88h+var_58], edx
0x140036ce2  mov     dl, 5
0x140036ce4  mov     [rsp+88h+var_60], rdi
0x140036ce9  mov     [rsp+88h+var_68], rax
0x140036cee  call    WPP_RECORDER_SF_qDL
0x140036cf3  jmp     loc_140036C37
0x140036cf8  cmp     [rdi+390h], bpl
0x140036cff  jz      short loc_140036D1D
0x140036d01  movzx   edx, byte ptr [rsi+8]; NewIrql
0x140036d05  mov     rcx, rsi; SpinLock
0x140036d08  mov     [rsi+10h], bpl
0x140036d0c  call    cs:__imp_KeReleaseSpinLock
0x140036d13  nop     dword ptr [rax+rax+00h]
0x140036d18  jmp     loc_1400368FD
0x140036d1d  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140036d24  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140036d2b  jz      short loc_140036D5E
0x140036d2d  movzx   eax, word ptr [rdi+64h]
0x140036d31  mov     r9d, 50h ; 'P'
0x140036d37  mov     rcx, cs:WPP_GLOBAL_Control
0x140036d3e  mov     dl, 4
0x140036d40  mov     [rsp+88h+var_58], eax
0x140036d44  lea     rax, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x140036d4b  mov     [rsp+88h+var_60], rdi
0x140036d50  mov     [rsp+88h+var_68], rax
0x140036d55  mov     rcx, [rcx+40h]
0x140036d59  call    WPP_RECORDER_SF_qD
0x140036d5e  movzx   edx, byte ptr [rsi+8]; NewIrql
0x140036d62  mov     rcx, rsi; SpinLock
0x140036d65  mov     [rsi+10h], bpl
0x140036d69  call    cs:__imp_KeReleaseSpinLock
0x140036d70  nop     dword ptr [rax+rax+00h]
0x140036d75  mov     esi, ebp
0x140036d77  jmp     loc_140036AB0
0x140036d7c  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140036d83  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140036d8a  jz      short loc_140036DCA
0x140036d8c  mov     rcx, cs:WPP_GLOBAL_Control
0x140036d93  cmp     byte ptr [rcx+29h], 5
0x140036d97  jnb     short loc_140036DA0
0x140036d99  cmp     word ptr [rcx+48h], 0
0x140036d9e  jz      short loc_140036DCA
0x140036da0  movzx   eax, word ptr [rdi+64h]
0x140036da4  mov     r9d, 52h ; 'R'
0x140036daa  mov     rcx, [rcx+40h]
0x140036dae  mov     dl, 5
0x140036db0  mov     [rsp+88h+var_58], eax
0x140036db4  lea     rax, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x140036dbb  mov     [rsp+88h+var_60], rdi
0x140036dc0  mov     [rsp+88h+var_68], rax
0x140036dc5  call    WPP_RECORDER_SF_qD
0x140036dca  mov     [rbx], r13
  ... truncated ...
```
