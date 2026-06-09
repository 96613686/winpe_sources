# CTxMgr::ServiceQueues(void)

- ea: `0x140036270`
- end: `0x140036852`
- name: `?ServiceQueues@CTxMgr@@QEAAXXZ`
- size: `1506`
- prototype: `void __fastcall(CTxMgr *__hidden this)`
- caller_count: `5`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x14003010c`
- `0x140036860`
- `0x14003c054`
- `0x14003e538`
- `0x14003ff4c`

## callees

- `0x140034e04`
- `0x140034ec4`
- `0x140036270`
- `0x14003b1d8`
- `0x140049a68`
- `0x140085bd4`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140036441`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003650a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140036441`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003650a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003630a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003630a`

## pseudocode

```c
void __fastcall CTxMgr::ServiceQueues(CTxMgr *this)
{
  unsigned int i; // ebp
  CNdisSpinLock *m_TxMgrLock; // rdi
  CACList *m_pACList; // rcx
  _LIST_ENTRY *p_m_TxQueueList; // rax
  struct _LIST_ENTRY *v6; // rcx
  struct _LIST_ENTRY *v7; // rdx
  struct _LIST_ENTRY *v8; // rdx
  struct _WFC_TX_QUEUE *TxQueueFromMaxAC; // rsi
  unsigned __int8 Tid; // dl
  unsigned __int16 BacklogCount; // ax
  unsigned int m_CurActiveBacklog; // esi
  KIRQL v13; // dl
  __int64 m_ScheduledExtTid; // r9
  CAdapter *m_pAdapter; // rcx
  void (__fastcall *TxTalSendHandler)(_QWORD, _QWORD, _QWORD, _QWORD); // r10
  __int64 m_ScheduledPeerId; // r8
  KIRQL OldIrql; // dl
  struct _WFC_TX_QUEUE *Flink; // rcx
  struct _LIST_ENTRY *p_GlobalTxQueueListEntry; // rax
  struct _LIST_ENTRY *Blink; // rdx
  struct _LIST_ENTRY *v22; // rdx
  int v23; // r8d
  int PeerId; // edx
  int v25; // [rsp+20h] [rbp-58h]
  __int64 v26; // [rsp+28h] [rbp-50h]

  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      199,
      (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
  }
  if ( _InterlockedIncrement(&this->m_SendThreadActive) <= 1 )
  {
    ++this->m_SchedulingRound;
    for ( i = 0; ; ++i )
    {
      if ( i >= 0x400 )
        goto LABEL_34;
      m_TxMgrLock = this->m_TxMgrLock;
      m_TxMgrLock->m_SpinLock.OldIrql = KeAcquireSpinLockRaiseToDpc(&m_TxMgrLock->m_SpinLock.SpinLock);
      m_TxMgrLock->m_IsLocked = 1;
      m_pACList = this->m_pACList;
      if ( m_pACList )
      {
        if ( this->m_ServiceCounter % 0xA < 8 )
        {
          TxQueueFromMaxAC = CACList::GetTxQueueFromMaxAC(m_pACList);
          if ( TxQueueFromMaxAC )
          {
            if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
              && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
            {
              WPP_RECORDER_SF_(
                WPP_GLOBAL_Control->DeviceExtension,
                5,
                1,
                82,
                (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
            }
            Flink = (struct _WFC_TX_QUEUE *)TxQueueFromMaxAC->GlobalTxQueueListEntry.Flink;
            p_GlobalTxQueueListEntry = &TxQueueFromMaxAC->GlobalTxQueueListEntry;
            if ( Flink == (struct _WFC_TX_QUEUE *)&TxQueueFromMaxAC->GlobalTxQueueListEntry )
            {
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                WPP_RECORDER_SF_(
                  WPP_GLOBAL_Control->DeviceExtension,
                  4,
                  1,
                  84,
                  (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
              v23 = -1073676261;
            }
            else
            {
              if ( Flink->BacklogQueue.Blink != p_GlobalTxQueueListEntry
                || (Blink = TxQueueFromMaxAC->GlobalTxQueueListEntry.Blink, Blink->Flink != p_GlobalTxQueueListEntry)
                || (Blink->Flink = &Flink->BacklogQueue,
                    Flink->BacklogQueue.Blink = Blink,
                    v22 = this->m_CGlobalTxQueueList.m_TxQueueList.Blink,
                    v22->Flink != &this->m_CGlobalTxQueueList.m_TxQueueList) )
              {
LABEL_46:
                __fastfail(3u);
              }
              p_GlobalTxQueueListEntry->Flink = &this->m_CGlobalTxQueueList.m_TxQueueList;
              v23 = 0;
              TxQueueFromMaxAC->GlobalTxQueueListEntry.Blink = v22;
              v22->Flink = p_GlobalTxQueueListEntry;
              this->m_CGlobalTxQueueList.m_TxQueueList.Blink = p_GlobalTxQueueListEntry;
            }
            if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
              && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
            {
              LODWORD(v26) = v23;
              WPP_RECORDER_SF_D(
                WPP_GLOBAL_Control->DeviceExtension,
                5,
                1,
                85,
                (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
                v26);
            }
            goto LABEL_22;
          }
        }
      }
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          5,
          1,
          78,
          (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
      }
      p_m_TxQueueList = &this->m_CGlobalTxQueueList.m_TxQueueList;
      v6 = this->m_CGlobalTxQueueList.m_TxQueueList.Flink;
      if ( v6 == &this->m_CGlobalTxQueueList.m_TxQueueList )
        break;
      if ( v6->Blink != p_m_TxQueueList )
        goto LABEL_46;
      v7 = v6->Flink;
      if ( v6->Flink->Blink != v6 )
        goto LABEL_46;
      p_m_TxQueueList->Flink = v7;
      v7->Blink = p_m_TxQueueList;
      v8 = this->m_CGlobalTxQueueList.m_TxQueueList.Blink;
      if ( v8->Flink != p_m_TxQueueList )
        goto LABEL_46;
      v6->Flink = p_m_TxQueueList;
      TxQueueFromMaxAC = (struct _WFC_TX_QUEUE *)&v6[-1];
      v6->Blink = v8;
      v8->Flink = v6;
      this->m_CGlobalTxQueueList.m_TxQueueList.Blink = v6;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          PeerId = TxQueueFromMaxAC->PeerId;
          LOBYTE(PeerId) = 5;
          WPP_RECORDER_SF_DDD(
            WPP_GLOBAL_Control->DeviceExtension,
            PeerId,
            1,
            80,
            (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
            TxQueueFromMaxAC->PortId,
            TxQueueFromMaxAC->PeerId,
            TxQueueFromMaxAC->Tid);
        }
LABEL_18:
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          LODWORD(v26) = 0;
          WPP_RECORDER_SF_D(
            WPP_GLOBAL_Control->DeviceExtension,
            5,
            1,
            81,
            (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
            v26);
        }
      }
LABEL_21:
      if ( !TxQueueFromMaxAC )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            5,
            1,
            200,
            (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
        }
        OldIrql = m_TxMgrLock->m_SpinLock.OldIrql;
        m_TxMgrLock->m_IsLocked = 0;
        KeReleaseSpinLock(&m_TxMgrLock->m_SpinLock.SpinLock, OldIrql);
        goto LABEL_34;
      }
LABEL_22:
      this->m_ScheduledPortId = TxQueueFromMaxAC->PortId;
      this->m_ScheduledPeerId = TxQueueFromMaxAC->PeerId;
      Tid = TxQueueFromMaxAC->Tid;
      this->m_ScheduledExtTid = Tid;
      BacklogCount = TxQueueFromMaxAC->BacklogCount;
      m_CurActiveBacklog = this->m_CurActiveBacklog;
      this->m_ScheduledQueueLength = BacklogCount;
      ++this->m_ServiceCounter;
      this->m_ScheduledRobustnessFlag = Tid > 0x10u;
      v13 = m_TxMgrLock->m_SpinLock.OldIrql;
      m_TxMgrLock->m_IsLocked = 0;
      KeReleaseSpinLock(&m_TxMgrLock->m_SpinLock.SpinLock, v13);
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        WPP_RECORDER_SF_DDDDI(
          WPP_GLOBAL_Control->DeviceExtension,
          this->m_ScheduledQueueLength,
          this->m_ScheduledExtTid,
          this->m_ScheduledPeerId,
          v25,
          this->m_ScheduledPortId,
          this->m_ScheduledPeerId,
          this->m_ScheduledExtTid,
          this->m_ScheduledQueueLength,
          m_CurActiveBacklog);
      }
      m_ScheduledExtTid = this->m_ScheduledExtTid;
      m_pAdapter = this->m_pAdapter;
      if ( (unsigned __int8)m_ScheduledExtTid > 0x10u )
        TxTalSendHandler = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))m_pAdapter->m_MiniportDataHandlers.TxTalSendHandler;
      else
        TxTalSendHandler = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))m_pAdapter->m_MiniportDataHandlers.TxDataSendHandler;
      if ( this->m_QueueingMode == PORT_QUEUEING )
      {
        LOBYTE(m_ScheduledExtTid) = 31;
        m_ScheduledPeerId = 0xFFFF;
      }
      else
      {
        m_ScheduledPeerId = this->m_ScheduledPeerId;
      }
      LOWORD(v25) = this->m_ScheduledQueueLength;
      TxTalSendHandler(
        m_pAdapter->m_MiniportTalTxRxContext,
        this->m_ScheduledPortId,
        m_ScheduledPeerId,
        m_ScheduledExtTid);
    }
    TxQueueFromMaxAC = 0;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_21;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        1,
        79,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
    goto LABEL_18;
  }
LABEL_34:
  _InterlockedDecrement(&this->m_SendThreadActive);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v26) = 0;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      202,
      (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
      v26);
  }
}

```

## disassembly

```asm
0x140036270  push    rbx
0x140036272  push    r12
0x140036274  push    r15
0x140036276  sub     rsp, 60h
0x14003627a  mov     rbx, rcx
0x14003627d  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140036284  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14003628b  lea     r12, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x140036292  jz      short loc_1400362B0
0x140036294  mov     rcx, cs:WPP_GLOBAL_Control
0x14003629b  cmp     byte ptr [rcx+29h], 5
0x14003629f  jnb     loc_1400367D9
0x1400362a5  cmp     word ptr [rcx+48h], 0
0x1400362aa  jnz     loc_1400367D9
0x1400362b0  mov     [rsp+78h+arg_0], rbp
0x1400362b8  mov     eax, 1
0x1400362bd  mov     [rsp+78h+arg_8], rsi
0x1400362c5  mov     [rsp+78h+arg_10], rdi
0x1400362cd  mov     [rsp+78h+var_20], r13
0x1400362d2  mov     [rsp+78h+var_28], r14
0x1400362d7  lock xadd [rbx+18h], eax
0x1400362dc  inc     eax
0x1400362de  cmp     eax, 1
0x1400362e1  jg      loc_140036516
0x1400362e7  inc     qword ptr [rbx+48h]
0x1400362eb  mov     r13, 0CCCCCCCCCCCCCCCDh
0x1400362f5  xor     ebp, ebp
0x1400362f7  cmp     ebp, 400h
0x1400362fd  jnb     loc_140036516
0x140036303  mov     rdi, [rbx+20h]
0x140036307  mov     rcx, rdi; SpinLock
0x14003630a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140036311  nop     dword ptr [rax+rax+00h]
0x140036316  mov     [rdi+8], al
0x140036319  mov     byte ptr [rdi+10h], 1
0x14003631d  mov     rcx, [rbx+100h]; this
0x140036324  test    rcx, rcx
0x140036327  jnz     loc_14003661D
0x14003632d  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140036334  jz      short loc_140036352
0x140036336  mov     rcx, cs:WPP_GLOBAL_Control
0x14003633d  cmp     byte ptr [rcx+29h], 5
0x140036341  jnb     loc_1400365CC
0x140036347  cmp     word ptr [rcx+48h], 0
0x14003634c  jnz     loc_1400365CC
0x140036352  lea     rax, [rbx+110h]
0x140036359  mov     rcx, [rax]
0x14003635c  cmp     rcx, rax
0x14003635f  jz      loc_14003656C
0x140036365  cmp     [rcx+8], rax
0x140036369  jnz     loc_140036616
0x14003636f  mov     rdx, [rcx]
0x140036372  cmp     [rdx+8], rcx
0x140036376  jnz     loc_140036616
0x14003637c  mov     [rax], rdx
0x14003637f  mov     [rdx+8], rax
0x140036383  mov     rdx, [rbx+118h]
0x14003638a  cmp     [rdx], rax
0x14003638d  jnz     loc_140036616
0x140036393  mov     [rcx], rax
0x140036396  lea     rsi, [rcx-10h]
0x14003639a  mov     [rcx+8], rdx
0x14003639e  mov     [rdx], rcx
0x1400363a1  mov     [rax+8], rcx
0x1400363a5  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400363ac  jz      short loc_1400363EF
0x1400363ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400363b5  cmp     byte ptr [rcx+29h], 5
0x1400363b9  jnb     loc_140036759
0x1400363bf  cmp     word ptr [rcx+48h], 0
0x1400363c4  jnz     loc_140036759
0x1400363ca  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400363d1  jz      short loc_1400363EF
0x1400363d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400363da  cmp     byte ptr [rcx+29h], 5
0x1400363de  jnb     loc_140036730
0x1400363e4  cmp     word ptr [rcx+48h], 0
0x1400363e9  jnz     loc_140036730
0x1400363ef  test    rsi, rsi
0x1400363f2  jz      loc_1400364DA
0x1400363f8  movzx   eax, word ptr [rsi+3Eh]
0x1400363fc  mov     rcx, rdi; SpinLock
0x1400363ff  mov     [rbx+120h], ax
0x140036406  movzx   eax, word ptr [rsi+40h]
0x14003640a  mov     [rbx+122h], ax
0x140036411  movzx   edx, byte ptr [rsi+3Ch]
0x140036415  mov     [rbx+124h], dl
0x14003641b  cmp     dl, 10h
0x14003641e  movzx   eax, word ptr [rsi+30h]
0x140036422  mov     esi, [rbx+58h]
0x140036425  mov     [rbx+126h], ax
0x14003642c  setnbe  al
0x14003642f  inc     qword ptr [rbx+50h]
0x140036433  mov     [rbx+128h], al
0x140036439  movzx   edx, byte ptr [rdi+8]; NewIrql
0x14003643d  mov     byte ptr [rdi+10h], 0
0x140036441  call    cs:__imp_KeReleaseSpinLock
0x140036448  nop     dword ptr [rax+rax+00h]
0x14003644d  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140036454  jz      short loc_140036472
0x140036456  mov     rcx, cs:WPP_GLOBAL_Control
0x14003645d  cmp     byte ptr [rcx+29h], 5
0x140036461  jnb     loc_140036794
0x140036467  cmp     word ptr [rcx+48h], 0
0x14003646c  jnz     loc_140036794
0x140036472  movzx   r9d, byte ptr [rbx+124h]
0x14003647a  mov     rcx, [rbx+10h]
0x14003647e  movzx   eax, byte ptr [rbx+128h]
0x140036485  movzx   edx, word ptr [rbx+126h]
0x14003648c  cmp     r9b, 10h
0x140036490  ja      loc_1400365B3
0x140036496  mov     r10, [rcx+3E5Ch]
0x14003649d  cmp     dword ptr [rbx+0F8h], 1
0x1400364a4  jnz     loc_1400365BF
0x1400364aa  mov     r9b, 1Fh
0x1400364ad  mov     r8d, 0FFFFh
0x1400364b3  mov     rcx, [rcx+70h]
0x1400364b7  mov     byte ptr [rsp+78h+var_48], al
0x1400364bb  mov     rax, r10
0x1400364be  mov     dword ptr [rsp+78h+var_50], esi
0x1400364c2  mov     word ptr [rsp+78h+var_58], dx
0x1400364c7  movzx   edx, word ptr [rbx+120h]
0x1400364ce  call    _guard_dispatch_icall
0x1400364d3  inc     ebp
0x1400364d5  jmp     loc_1400362F7
0x1400364da  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400364e1  jz      short loc_1400364FF
0x1400364e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400364ea  cmp     byte ptr [rcx+29h], 5
0x1400364ee  jnb     loc_140036831
0x1400364f4  cmp     word ptr [rcx+48h], 0
0x1400364f9  jnz     loc_140036831
0x1400364ff  movzx   edx, byte ptr [rdi+8]; NewIrql
0x140036503  mov     rcx, rdi; SpinLock
0x140036506  mov     byte ptr [rdi+10h], 0
0x14003650a  call    cs:__imp_KeReleaseSpinLock
0x140036511  nop     dword ptr [rax+rax+00h]
0x140036516  lock dec dword ptr [rbx+18h]
0x14003651a  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140036521  jz      short loc_14003653F
0x140036523  mov     rcx, cs:WPP_GLOBAL_Control
0x14003652a  cmp     byte ptr [rcx+29h], 5
0x14003652e  jnb     loc_1400365ED
0x140036534  cmp     word ptr [rcx+48h], 0
0x140036539  jnz     loc_1400365ED
0x14003653f  mov     r14, [rsp+78h+var_28]
0x140036544  mov     r13, [rsp+78h+var_20]
0x140036549  mov     rdi, [rsp+78h+arg_10]
0x140036551  mov     rsi, [rsp+78h+arg_8]
0x140036559  mov     rbp, [rsp+78h+arg_0]
0x140036561  add     rsp, 60h
0x140036565  pop     r15
0x140036567  pop     r12
0x140036569  pop     rbx
0x14003656a  retn
0x14003656c  xor     esi, esi
0x14003656e  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140036575  jz      loc_1400363EF
0x14003657b  mov     rcx, cs:WPP_GLOBAL_Control
0x140036582  cmp     byte ptr [rcx+29h], 5
0x140036586  jnb     short loc_140036592
0x140036588  cmp     [rcx+48h], si
0x14003658c  jz      loc_1400363CA
0x140036592  mov     rcx, [rcx+40h]
0x140036596  mov     r9d, 4Fh ; 'O'
0x14003659c  mov     r8d, 1
0x1400365a2  mov     [rsp+78h+var_58], r12
0x1400365a7  mov     dl, 5
0x1400365a9  call    WPP_RECORDER_SF_
0x1400365ae  jmp     loc_1400363CA
0x1400365b3  mov     r10, [rcx+3E64h]
0x1400365ba  jmp     loc_14003649D
0x1400365bf  movzx   r8d, word ptr [rbx+122h]
0x1400365c7  jmp     loc_1400364B3
0x1400365cc  mov     rcx, [rcx+40h]
0x1400365d0  mov     r9d, 4Eh ; 'N'
0x1400365d6  mov     r8d, 1
0x1400365dc  mov     [rsp+78h+var_58], r12
0x1400365e1  mov     dl, 5
0x1400365e3  call    WPP_RECORDER_SF_
0x1400365e8  jmp     loc_140036352
0x1400365ed  mov     rcx, [rcx+40h]
0x1400365f1  mov     r9d, 0CAh
0x1400365f7  mov     dword ptr [rsp+78h+var_50], 0
0x1400365ff  mov     r8d, 1
0x140036605  mov     dl, 5
0x140036607  mov     [rsp+78h+var_58], r12
0x14003660c  call    WPP_RECORDER_SF_D
0x140036611  jmp     loc_14003653F
0x140036616  mov     ecx, 3
0x14003661b  int     29h; Win8: RtlFailFast(ecx)
0x14003661d  mov     r8, [rbx+50h]
0x140036621  mov     rax, r13
0x140036624  mul     r8
0x140036627  shr     rdx, 3
0x14003662b  lea     rax, [rdx+rdx*4]
0x14003662f  add     rax, rax
0x140036632  sub     r8, rax
0x140036635  cmp     r8, 8
0x140036639  jnb     loc_14003632D
0x14003663f  call    ?GetTxQueueFromMaxAC@CACList@@QEAAPEAU_WFC_TX_QUEUE@@XZ; CACList::GetTxQueueFromMaxAC(void)
0x140036644  mov     rsi, rax
0x140036647  test    rax, rax
0x14003664a  jz      loc_14003632D
0x140036650  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140036657  jz      short loc_140036675
0x140036659  mov     rcx, cs:WPP_GLOBAL_Control
0x140036660  cmp     byte ptr [rcx+29h], 5
0x140036664  jnb     loc_14003670F
0x14003666a  cmp     word ptr [rcx+48h], 0
0x14003666f  jnz     loc_14003670F
0x140036675  mov     rcx, [rsi+10h]
0x140036679  lea     rax, [rsi+10h]
0x14003667d  cmp     rcx, rax
0x140036680  jz      loc_1400367FA
0x140036686  cmp     [rcx+8], rax
0x14003668a  jnz     short loc_140036616
0x14003668c  mov     rdx, [rax+8]
0x140036690  cmp     [rdx], rax
0x140036693  jnz     short loc_140036616
0x140036695  mov     [rdx], rcx
0x140036698  mov     [rcx+8], rdx
0x14003669c  lea     rcx, [rbx+110h]
0x1400366a3  mov     rdx, [rbx+118h]
0x1400366aa  cmp     [rdx], rcx
0x1400366ad  jnz     loc_140036616
0x1400366b3  mov     [rax], rcx
0x1400366b6  xor     r8d, r8d
0x1400366b9  mov     [rax+8], rdx
0x1400366bd  mov     [rdx], rax
0x1400366c0  mov     [rcx+8], rax
0x1400366c4  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400366cb  jz      loc_1400363F8
0x1400366d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400366d8  cmp     byte ptr [rcx+29h], 5
0x1400366dc  jnb     short loc_1400366E9
0x1400366de  cmp     word ptr [rcx+48h], 0
0x1400366e3  jz      loc_1400363F8
0x1400366e9  mov     rcx, [rcx+40h]
0x1400366ed  mov     r9d, 55h ; 'U'
0x1400366f3  mov     dword ptr [rsp+78h+var_50], r8d
0x1400366f8  mov     dl, 5
0x1400366fa  mov     r8d, 1
0x140036700  mov     [rsp+78h+var_58], r12
0x140036705  call    WPP_RECORDER_SF_D
0x14003670a  jmp     loc_1400363F8
0x14003670f  mov     rcx, [rcx+40h]
0x140036713  mov     r9d, 52h ; 'R'
0x140036719  mov     r8d, 1
0x14003671f  mov     [rsp+78h+var_58], r12
0x140036724  mov     dl, 5
0x140036726  call    WPP_RECORDER_SF_
0x14003672b  jmp     loc_140036675
0x140036730  mov     rcx, [rcx+40h]
0x140036734  mov     r9d, 51h ; 'Q'
0x14003673a  mov     dword ptr [rsp+78h+var_50], 0
0x140036742  mov     r8d, 1
0x140036748  mov     dl, 5
0x14003674a  mov     [rsp+78h+var_58], r12
0x14003674f  call    WPP_RECORDER_SF_D
0x140036754  jmp     loc_1400363EF
0x140036759  movzx   edx, word ptr [rsi+40h]
0x14003675d  mov     r9d, 50h ; 'P'
0x140036763  movzx   r8d, word ptr [rsi+3Eh]
0x140036768  movzx   eax, byte ptr [rsi+3Ch]
0x14003676c  mov     rcx, [rcx+40h]
0x140036770  mov     [rsp+78h+var_40], eax
0x140036774  mov     [rsp+78h+var_48], edx
0x140036778  mov     dl, 5
0x14003677a  mov     dword ptr [rsp+78h+var_50], r8d
0x14003677f  mov     r8d, 1
0x140036785  mov     [rsp+78h+var_58], r12
0x14003678a  call    WPP_RECORDER_SF_DDD
0x14003678f  jmp     loc_1400363CA
0x140036794  movzx   edx, word ptr [rbx+126h]
0x14003679b  movzx   r8d, byte ptr [rbx+124h]
0x1400367a3  movzx   r9d, word ptr [rbx+122h]
0x1400367ab  movzx   r10d, word ptr [rbx+120h]
0x1400367b3  mov     rcx, [rcx+40h]
0x1400367b7  mov     [rsp+78h+var_30], rsi
0x1400367bc  mov     [rsp+78h+var_38], edx
0x1400367c0  mov     [rsp+78h+var_40], r8d
0x1400367c5  mov     [rsp+78h+var_48], r9d
0x1400367ca  mov     dword ptr [rsp+78h+var_50], r10d
0x1400367cf  call    WPP_RECORDER_SF_DDDDI
0x1400367d4  jmp     loc_140036472
0x1400367d9  mov     rcx, [rcx+40h]
0x1400367dd  mov     r9d, 0C7h
0x1400367e3  mov     r8d, 1
0x1400367e9  mov     [rsp+78h+var_58], r12
0x1400367ee  mov     dl, 5
0x1400367f0  call    WPP_RECORDER_SF_
0x1400367f5  jmp     loc_1400362B0
0x1400367fa  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140036801  jz      short loc_140036826
0x140036803  mov     rcx, cs:WPP_GLOBAL_Control
0x14003680a  mov     r9d, 54h ; 'T'
0x140036810  mov     r8d, 1
0x140036816  mov     [rsp+78h+var_58], r12
0x14003681b  mov     dl, 4
  ... truncated ...
```
