# CPort::CompletePendingCancelSendsOrHaltJobs(void)

- ea: `0x1400330a0`
- end: `0x140033587`
- name: `?CompletePendingCancelSendsOrHaltJobs@CPort@@AEAAXXZ`
- size: `1255`
- prototype: `void __fastcall(CPort *__hidden this)`
- caller_count: `9`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001fa44`
- `0x140031890`
- `0x1400329b0`
- `0x140033590`
- `0x140033c40`
- `0x140036860`
- `0x140039a60`
- `0x14003e1c8`
- `0x1400403c0`

## callees

- `0x140005ec8`
- `0x1400122e0`
- `0x14002aa28`
- `0x14002fff4`
- `0x1400330a0`
- `0x140034e04`
- `0x140034ec4`
- `0x14003b77c`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140033174`
- `ntoskrnl!KeReleaseSpinLock` at `0x140033201`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003337b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140033403`
- `ntoskrnl!KeReleaseSpinLock` at `0x140033174`
- `ntoskrnl!KeReleaseSpinLock` at `0x140033201`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003337b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140033403`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400330eb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400333de`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400330eb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400333de`

## pseudocode

```c
void __fastcall CPort::CompletePendingCancelSendsOrHaltJobs(CPort *this)
{
  CNdisSpinLock *m_PortLock; // rbx
  KIRQL v3; // al
  int v4; // edx
  int v5; // r8d
  unsigned int m_State; // ecx
  bool v7; // r14
  IOperationCompletionCallback *v8; // r15
  IOperationCompletionCallback *m_PauseCallback; // rbp
  KIRQL v10; // dl
  int v11; // edx
  int v12; // r8d
  unsigned __int16 *p_m_WfcPortId; // rsi
  CAdapter *m_pAdapter; // r12
  unsigned __int16 *v15; // rbx
  unsigned __int16 *v16; // rsi
  IOperationCompletionCallback *m_Dot11ResetCallback; // rax
  KIRQL OldIrql; // dl
  int v19; // edx
  int v20; // r8d
  CNdisSpinLock *v21; // rbx
  KIRQL v22; // al
  KIRQL v23; // dl
  int v24; // eax
  struct Event *v25; // [rsp+28h] [rbp-40h]
  __int64 v26; // [rsp+38h] [rbp-30h]

  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      29,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids);
  }
  m_PortLock = this->m_PortLock;
  v3 = KeAcquireSpinLockRaiseToDpc(&m_PortLock->m_SpinLock.SpinLock);
  m_PortLock->m_SpinLock.OldIrql = v3;
  m_PortLock->m_IsLocked = 1;
  if ( this->m_txPendingFrames <= 0
    && (this->m_rxPendingFrames <= 0 || this->m_fWaitForRxReturn == NoWaitForRxReturn)
    && this->m_bIsTxAbortConfirm
    && this->m_bIsRxFlushConfirm )
  {
    m_State = this->m_State;
    v7 = 0;
    v8 = 0;
    if ( (m_State & 0x40) != 0 )
    {
      if ( !this->m_PauseCallback && *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v4) = 2;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v4,
          v5,
          30,
          (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
          (char)this,
          this->m_WfcPortId,
          this->m_State);
      }
      m_PauseCallback = this->m_PauseCallback;
      m_State = this->m_State & 0xFFFFFFBD | 2;
      this->m_PauseCallback = 0;
      this->m_State = m_State;
    }
    else
    {
      m_PauseCallback = 0;
    }
    if ( (m_State & 8) != 0 && (m_Dot11ResetCallback = this->m_Dot11ResetCallback) != 0 )
    {
      this->m_Dot11ResetCallback = 0;
      OldIrql = m_PortLock->m_SpinLock.OldIrql;
      v8 = m_Dot11ResetCallback;
      m_PortLock->m_IsLocked = 0;
      v7 = (m_State & 2) == 0;
      KeReleaseSpinLock(&m_PortLock->m_SpinLock.SpinLock, OldIrql);
      p_m_WfcPortId = &this->m_WfcPortId;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v19) = 4;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v19,
          v20,
          31,
          (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
          (char)this,
          *p_m_WfcPortId);
      }
      ((void (__fastcall *)(void *, _QWORD))this->m_pAdapter->m_MiniportDataHandlers.TalTxRxResetPortHandler)(
        this->m_pAdapter->m_MiniportTalTxRxContext,
        *p_m_WfcPortId);
      v21 = this->m_PortLock;
      v22 = KeAcquireSpinLockRaiseToDpc(&v21->m_SpinLock.SpinLock);
      v21->m_IsLocked = 1;
      v21->m_SpinLock.OldIrql = v22;
      this->m_State &= ~8u;
      v23 = v21->m_SpinLock.OldIrql;
      v21->m_IsLocked = 0;
      KeReleaseSpinLock(&v21->m_SpinLock.SpinLock, v23);
    }
    else
    {
      v10 = m_PortLock->m_SpinLock.OldIrql;
      m_PortLock->m_IsLocked = 0;
      KeReleaseSpinLock(&m_PortLock->m_SpinLock.SpinLock, v10);
      p_m_WfcPortId = &this->m_WfcPortId;
    }
    m_pAdapter = this->m_pAdapter;
    if ( m_PauseCallback )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      {
        v15 = p_m_WfcPortId;
      }
      else
      {
        LOBYTE(v11) = 4;
        WPP_RECORDER_SF_qDq(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          v12,
          32,
          (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
          (char)this,
          *p_m_WfcPortId,
          (char)m_PauseCallback);
        v15 = &this->m_WfcPortId;
      }
      v24 = EventQueue::PopulateAndQueueDeferredCallback(
              &m_pAdapter->m_EventQueue,
              WiFiEventDeferredOperationCompletion,
              (void *)m_PauseCallback,
              this,
              0,
              &this->m_PauseCallbackEvent);
      LODWORD(m_PauseCallback) = v24;
      if ( v24 && *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v26) = v24;
        LOBYTE(v11) = 2;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          v12,
          33,
          (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
          (char)this,
          *p_m_WfcPortId,
          v26);
      }
    }
    else
    {
      v15 = p_m_WfcPortId;
    }
    if ( v8 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      {
        v16 = v15;
      }
      else
      {
        LOBYTE(v11) = 4;
        WPP_RECORDER_SF_qDq(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          v12,
          34,
          (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
          (char)this,
          *v15,
          (char)v8);
        v16 = &this->m_WfcPortId;
      }
      LODWORD(m_PauseCallback) = EventQueue::PopulateAndQueueDeferredCallback(
                                   &m_pAdapter->m_EventQueue,
                                   WiFiEventDeferredOperationCompletion,
                                   (void *)v8,
                                   this,
                                   0,
                                   &this->m_Dot11ResetCallbackEvent);
      if ( (_DWORD)m_PauseCallback && *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v26) = (_DWORD)m_PauseCallback;
        LOBYTE(v11) = 2;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          v12,
          35,
          (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
          (char)this,
          *v15,
          v26);
      }
    }
    else
    {
      v16 = v15;
    }
    if ( v7 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = 4;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          v12,
          36,
          (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
          (char)this,
          *v16);
      }
      CPort::RestartSendAndReceivesLE(this);
    }
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LODWORD(v25) = (_DWORD)m_PauseCallback;
      LOBYTE(v11) = 5;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        1,
        37,
        (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
        v25);
    }
  }
  else
  {
    m_PortLock->m_IsLocked = 0;
    KeReleaseSpinLock(&m_PortLock->m_SpinLock.SpinLock, v3);
  }
}

```

## disassembly

```asm
0x1400330a0  push    rbx
0x1400330a2  push    rdi
0x1400330a3  push    r12
0x1400330a5  push    r13
0x1400330a7  sub     rsp, 48h
0x1400330ab  mov     rdi, rcx
0x1400330ae  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400330b5  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400330bc  lea     r12, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400330c3  jz      short loc_1400330E1
0x1400330c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400330cc  cmp     byte ptr [rcx+29h], 5
0x1400330d0  jnb     loc_140033219
0x1400330d6  cmp     word ptr [rcx+48h], 0
0x1400330db  jnz     loc_140033219
0x1400330e1  mov     rbx, [rdi+3A0h]
0x1400330e8  mov     rcx, rbx; SpinLock
0x1400330eb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400330f2  nop     dword ptr [rax+rax+00h]
0x1400330f7  mov     [rbx+8], al
0x1400330fa  mov     byte ptr [rbx+10h], 1
0x1400330fe  cmp     dword ptr [rdi+370h], 0
0x140033105  jg      loc_1400331F7
0x14003310b  cmp     dword ptr [rdi+308h], 0
0x140033112  jg      loc_14003323A
0x140033118  cmp     byte ptr [rdi+391h], 1
0x14003311f  jnz     loc_1400331F7
0x140033125  cmp     byte ptr [rdi+392h], 1
0x14003312c  jnz     loc_1400331F7
0x140033132  mov     ecx, [rdi+368h]
0x140033138  mov     [rsp+68h+arg_0], rbp
0x14003313d  mov     [rsp+68h+arg_10], r14
0x140033145  xor     r14b, r14b
0x140033148  mov     [rsp+68h+var_28], r15
0x14003314d  xor     r15d, r15d
0x140033150  test    cl, 40h
0x140033153  jnz     loc_1400334A0
0x140033159  xor     ebp, ebp
0x14003315b  mov     [rsp+68h+arg_8], rsi
0x140033160  test    cl, 8
0x140033163  jnz     loc_140033345
0x140033169  movzx   edx, byte ptr [rbx+8]; NewIrql
0x14003316d  mov     rcx, rbx; SpinLock
0x140033170  mov     [rbx+10h], r14b
0x140033174  call    cs:__imp_KeReleaseSpinLock
0x14003317b  nop     dword ptr [rax+rax+00h]
0x140033180  lea     rsi, [rdi+64h]
0x140033184  mov     r12, [rdi+58h]
0x140033188  test    rbp, rbp
0x14003318b  jnz     loc_140033414
0x140033191  mov     rbx, rsi
0x140033194  lea     rsi, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x14003319b  test    r15, r15
0x14003319e  jnz     loc_14003327A
0x1400331a4  mov     rsi, rbx
0x1400331a7  lea     rbx, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400331ae  mov     r15, [rsp+68h+var_28]
0x1400331b3  test    r14b, r14b
0x1400331b6  mov     r14, [rsp+68h+arg_10]
0x1400331be  jnz     loc_140033306
0x1400331c4  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400331cb  mov     rsi, [rsp+68h+arg_8]
0x1400331d0  jz      short loc_1400331E6
0x1400331d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400331d9  cmp     byte ptr [rcx+29h], 5
0x1400331dd  jnb     short loc_140033249
0x1400331df  cmp     word ptr [rcx+48h], 0
0x1400331e4  jnz     short loc_140033249
0x1400331e6  mov     rbp, [rsp+68h+arg_0]
0x1400331eb  add     rsp, 48h
0x1400331ef  pop     r13
0x1400331f1  pop     r12
0x1400331f3  pop     rdi
0x1400331f4  pop     rbx
0x1400331f5  retn
0x1400331f7  movzx   edx, al; NewIrql
0x1400331fa  mov     byte ptr [rbx+10h], 0
0x1400331fe  mov     rcx, rbx; SpinLock
0x140033201  call    cs:__imp_KeReleaseSpinLock
0x140033208  nop     dword ptr [rax+rax+00h]
0x14003320d  add     rsp, 48h
0x140033211  pop     r13
0x140033213  pop     r12
0x140033215  pop     rdi
0x140033216  pop     rbx
0x140033217  retn
0x140033219  mov     rcx, [rcx+40h]
0x14003321d  mov     r9d, 1Dh
0x140033223  mov     r8d, 1
0x140033229  mov     qword ptr [rsp+68h+var_48], r12
0x14003322e  mov     dl, 5
0x140033230  call    WPP_RECORDER_SF_
0x140033235  jmp     loc_1400330E1
0x14003323a  cmp     dword ptr [rdi+30Ch], 0
0x140033241  jz      loc_140033118
0x140033247  jmp     short loc_1400331F7
0x140033249  mov     rcx, [rcx+40h]
0x14003324d  mov     r9d, 25h ; '%'
0x140033253  mov     dword ptr [rsp+68h+var_40], ebp
0x140033257  mov     r8d, 1
0x14003325d  mov     dl, 5
0x14003325f  mov     qword ptr [rsp+68h+var_48], rbx
0x140033264  call    WPP_RECORDER_SF_D
0x140033269  mov     rbp, [rsp+68h+arg_0]
0x14003326e  add     rsp, 48h
0x140033272  pop     r13
0x140033274  pop     r12
0x140033276  pop     rdi
0x140033277  pop     rbx
0x140033278  retn
0x14003327a  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140033281  jnz     loc_140033510
0x140033287  mov     rsi, rbx
0x14003328a  lea     rax, [rdi+230h]
0x140033291  mov     r9, rdi; void *
0x140033294  mov     [rsp+68h+var_40], rax; struct Event *
0x140033299  lea     rcx, [r12+328h]; this
0x1400332a1  mov     r8, r15; void *
0x1400332a4  mov     [rsp+68h+var_48], 0; int
0x1400332ac  mov     edx, 1; enum _WFC_EVENT_TYPE
0x1400332b1  call    ?PopulateAndQueueDeferredCallback@EventQueue@@IEAAHW4_WFC_EVENT_TYPE@@PEAX1HPEAVEvent@@@Z; EventQueue::PopulateAndQueueDeferredCallback(_WFC_EVENT_TYPE,void *,void *,int,Event *)
0x1400332b6  mov     ebp, eax
0x1400332b8  test    eax, eax
0x1400332ba  jz      loc_1400331A7
0x1400332c0  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400332c7  jz      loc_1400331A7
0x1400332cd  movzx   eax, word ptr [rbx]
0x1400332d0  mov     r9d, 23h ; '#'
0x1400332d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400332dd  lea     rbx, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400332e4  mov     dword ptr [rsp+68h+var_30], ebp
0x1400332e8  mov     dl, 2
0x1400332ea  mov     [rsp+68h+var_38], eax
0x1400332ee  mov     [rsp+68h+var_40], rdi
0x1400332f3  mov     rcx, [rcx+40h]
0x1400332f7  mov     qword ptr [rsp+68h+var_48], rbx
0x1400332fc  call    WPP_RECORDER_SF_qDD
0x140033301  jmp     loc_1400331AE
0x140033306  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14003330d  jz      short loc_140033338
0x14003330f  mov     rcx, cs:WPP_GLOBAL_Control
0x140033316  mov     r9d, 24h ; '$'
0x14003331c  movzx   eax, word ptr [rsi]
0x14003331f  mov     dl, 4
0x140033321  mov     [rsp+68h+var_38], eax
0x140033325  mov     [rsp+68h+var_40], rdi
0x14003332a  mov     rcx, [rcx+40h]
0x14003332e  mov     qword ptr [rsp+68h+var_48], rbx
0x140033333  call    WPP_RECORDER_SF_qD
0x140033338  mov     rcx, rdi; this
0x14003333b  call    ?RestartSendAndReceivesLE@CPort@@AEAAXXZ; CPort::RestartSendAndReceivesLE(void)
0x140033340  jmp     loc_1400331C4
0x140033345  mov     rax, [rdi+218h]
0x14003334c  test    rax, rax
0x14003334f  jz      loc_140033169
0x140033355  mov     r14d, ecx
0x140033358  mov     qword ptr [rdi+218h], 0
0x140033363  movzx   edx, byte ptr [rbx+8]; NewIrql
0x140033367  mov     rcx, rbx; SpinLock
0x14003336a  shr     r14d, 1
0x14003336d  mov     r15, rax
0x140033370  not     r14b
0x140033373  mov     byte ptr [rbx+10h], 0
0x140033377  and     r14b, 1
0x14003337b  call    cs:__imp_KeReleaseSpinLock
0x140033382  nop     dword ptr [rax+rax+00h]
0x140033387  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14003338e  lea     rsi, [rdi+64h]
0x140033392  jz      short loc_1400333BD
0x140033394  mov     rcx, cs:WPP_GLOBAL_Control
0x14003339b  mov     r9d, 1Fh
0x1400333a1  movzx   eax, word ptr [rsi]
0x1400333a4  mov     dl, 4
0x1400333a6  mov     [rsp+68h+var_38], eax
0x1400333aa  mov     [rsp+68h+var_40], rdi
0x1400333af  mov     rcx, [rcx+40h]
0x1400333b3  mov     qword ptr [rsp+68h+var_48], r12
0x1400333b8  call    WPP_RECORDER_SF_qD
0x1400333bd  mov     rcx, [rdi+58h]
0x1400333c1  movzx   edx, word ptr [rsi]
0x1400333c4  mov     rax, [rcx+3EECh]
0x1400333cb  mov     rcx, [rcx+70h]
0x1400333cf  call    _guard_dispatch_icall
0x1400333d4  mov     rbx, [rdi+3A0h]
0x1400333db  mov     rcx, rbx; SpinLock
0x1400333de  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400333e5  nop     dword ptr [rax+rax+00h]
0x1400333ea  mov     byte ptr [rbx+10h], 1
0x1400333ee  mov     rcx, rbx; SpinLock
0x1400333f1  mov     [rbx+8], al
0x1400333f4  and     dword ptr [rdi+368h], 0FFFFFFF7h
0x1400333fb  movzx   edx, byte ptr [rbx+8]; NewIrql
0x1400333ff  mov     byte ptr [rbx+10h], 0
0x140033403  call    cs:__imp_KeReleaseSpinLock
0x14003340a  nop     dword ptr [rax+rax+00h]
0x14003340f  jmp     loc_140033184
0x140033414  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14003341b  jnz     loc_1400334D2
0x140033421  mov     rbx, rsi
0x140033424  lea     rax, [rdi+278h]
0x14003342b  mov     r9, rdi; void *
0x14003342e  mov     [rsp+68h+var_40], rax; struct Event *
0x140033433  lea     rcx, [r12+328h]; this
0x14003343b  mov     r8, rbp; void *
0x14003343e  mov     [rsp+68h+var_48], 0; int
0x140033446  mov     edx, 1; enum _WFC_EVENT_TYPE
0x14003344b  call    ?PopulateAndQueueDeferredCallback@EventQueue@@IEAAHW4_WFC_EVENT_TYPE@@PEAX1HPEAVEvent@@@Z; EventQueue::PopulateAndQueueDeferredCallback(_WFC_EVENT_TYPE,void *,void *,int,Event *)
0x140033450  mov     ebp, eax
0x140033452  test    eax, eax
0x140033454  jz      loc_140033194
0x14003345a  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140033461  jz      loc_140033194
0x140033467  movzx   ecx, word ptr [rsi]
0x14003346a  mov     r9d, 21h ; '!'
0x140033470  mov     dword ptr [rsp+68h+var_30], eax
0x140033474  lea     rsi, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x14003347b  mov     [rsp+68h+var_38], ecx
0x14003347f  mov     dl, 2
0x140033481  mov     rcx, cs:WPP_GLOBAL_Control
0x140033488  mov     [rsp+68h+var_40], rdi
0x14003348d  mov     qword ptr [rsp+68h+var_48], rsi
0x140033492  mov     rcx, [rcx+40h]
0x140033496  call    WPP_RECORDER_SF_qDD
0x14003349b  jmp     loc_14003319B
0x1400334a0  cmp     [rdi+220h], r15
0x1400334a7  jz      loc_140033547
0x1400334ad  mov     ecx, [rdi+368h]
0x1400334b3  mov     rbp, [rdi+220h]
0x1400334ba  and     ecx, 0FFFFFFBFh
0x1400334bd  or      ecx, 2
0x1400334c0  mov     [rdi+220h], r15
0x1400334c7  mov     [rdi+368h], ecx
0x1400334cd  jmp     loc_14003315B
0x1400334d2  movzx   eax, word ptr [rsi]
0x1400334d5  mov     r9d, 20h ; ' '
0x1400334db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400334e2  mov     dl, 4
0x1400334e4  mov     [rsp+68h+var_30], rbp
0x1400334e9  mov     [rsp+68h+var_38], eax
0x1400334ed  lea     rax, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400334f4  mov     [rsp+68h+var_40], rdi
0x1400334f9  mov     rcx, [rcx+40h]
0x1400334fd  mov     qword ptr [rsp+68h+var_48], rax
0x140033502  call    WPP_RECORDER_SF_qDq
0x140033507  lea     rbx, [rdi+64h]
0x14003350b  jmp     loc_140033424
0x140033510  mov     rcx, cs:WPP_GLOBAL_Control
0x140033517  mov     r9d, 22h ; '"'
0x14003351d  movzx   eax, word ptr [rbx]
0x140033520  mov     dl, 4
0x140033522  mov     [rsp+68h+var_30], r15
0x140033527  mov     [rsp+68h+var_38], eax
0x14003352b  mov     rcx, [rcx+40h]
0x14003352f  mov     [rsp+68h+var_40], rdi
0x140033534  mov     qword ptr [rsp+68h+var_48], rsi
0x140033539  call    WPP_RECORDER_SF_qDq
0x14003353e  lea     rsi, [rdi+64h]
0x140033542  jmp     loc_14003328A
0x140033547  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14003354e  jz      loc_1400334AD
0x140033554  movzx   eax, word ptr [rdi+64h]
0x140033558  mov     r9d, 1Eh
0x14003355e  mov     dword ptr [rsp+68h+var_30], ecx
0x140033562  mov     dl, 2
0x140033564  mov     rcx, cs:WPP_GLOBAL_Control
0x14003356b  mov     [rsp+68h+var_38], eax
0x14003356f  mov     [rsp+68h+var_40], rdi
0x140033574  mov     qword ptr [rsp+68h+var_48], r12
0x140033579  mov     rcx, [rcx+40h]
0x14003357d  call    WPP_RECORDER_SF_qDD
0x140033582  jmp     loc_1400334AD
```
