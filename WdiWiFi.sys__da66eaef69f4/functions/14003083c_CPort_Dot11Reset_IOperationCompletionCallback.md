# CPort::Dot11Reset(IOperationCompletionCallback *)

- ea: `0x14003083c`
- end: `0x140030ba8`
- name: `?Dot11Reset@CPort@@QEAAHPEAVIOperationCompletionCallback@@@Z`
- size: `876`
- prototype: `__int64 __fastcall(CPort *__hidden this, struct IOperationCompletionCallback *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140030710`

## callees

- `0x1400297a0`
- `0x14002aa28`
- `0x14002fff4`
- `0x14003083c`
- `0x140030bb0`
- `0x140034e04`
- `0x140034ec4`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14003092e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400309bd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030a62`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003092e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400309bd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030a62`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400308e5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030956`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030a3e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400308e5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030956`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030a3e`

## pseudocode

```c
__int64 __fastcall CPort::Dot11Reset(CPort *this, struct IOperationCompletionCallback *a2, int a3)
{
  __int64 *v5; // rdx
  CNdisSpinLock *m_PortLock; // rbx
  KIRQL v7; // al
  bool *p_m_bIsTxAbortConfirm; // r14
  CPort::PauseWaitForRxReturn *p_m_fWaitForRxReturn; // rsi
  char v10; // bp
  KIRQL OldIrql; // dl
  CNdisSpinLock *v12; // rbx
  int v13; // edx
  int v14; // r8d
  unsigned int m_State; // eax
  unsigned int v16; // esi
  KIRQL v17; // dl
  int v18; // edx
  int v19; // r8d
  __int64 v21; // [rsp+28h] [rbp-70h]

  v5 = WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v5) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v5,
        1,
        38,
        (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids);
      v5 = WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids;
    }
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 4;
      WPP_RECORDER_SF_qDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v5,
        a3,
        39,
        (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
        (char)this,
        this->m_WfcPortId,
        this->m_NdisPortNumber,
        this->m_State);
    }
  }
  m_PortLock = this->m_PortLock;
  this->m_KeyConfigured = 0;
  this->m_bIsLinkDegraded = 0;
  v7 = KeAcquireSpinLockRaiseToDpc(&m_PortLock->m_SpinLock.SpinLock);
  m_PortLock->m_IsLocked = 1;
  p_m_bIsTxAbortConfirm = &this->m_bIsTxAbortConfirm;
  m_PortLock->m_SpinLock.OldIrql = v7;
  p_m_fWaitForRxReturn = &this->m_fWaitForRxReturn;
  if ( (this->m_State & 0x43) != 0 )
  {
    v10 = 0;
  }
  else
  {
    v10 = 1;
    *p_m_bIsTxAbortConfirm = 0;
    this->m_bIsRxFlushConfirm = 0;
    *p_m_fWaitForRxReturn = NoWaitForRxReturn;
  }
  OldIrql = m_PortLock->m_SpinLock.OldIrql;
  m_PortLock->m_IsLocked = 0;
  KeReleaseSpinLock(&m_PortLock->m_SpinLock.SpinLock, OldIrql);
  if ( v10 )
    CPort::StopSendAndReceivesLE(this, RxStopReasonDot11Reset);
  v12 = this->m_PortLock;
  v12->m_SpinLock.OldIrql = KeAcquireSpinLockRaiseToDpc(&v12->m_SpinLock.SpinLock);
  v12->m_IsLocked = 1;
  m_State = this->m_State;
  if ( (m_State & 0x18) != 0 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        v14,
        40,
        (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
        (char)this,
        this->m_WfcPortId);
    }
    v16 = -1071448018;
    goto LABEL_25;
  }
  if ( this->m_txPendingFrames
    || this->m_rxPendingFrames && *p_m_fWaitForRxReturn
    || !*p_m_bIsTxAbortConfirm
    || !this->m_bIsRxFlushConfirm )
  {
    this->m_Dot11ResetCallback = a2;
    this->m_State = m_State | 8;
    v16 = 259;
  }
  else
  {
    v16 = 0;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 4;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        v14,
        41,
        (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
        (char)this,
        this->m_WfcPortId);
    }
    this->m_State |= 0x10u;
  }
  v17 = v12->m_SpinLock.OldIrql;
  v12->m_IsLocked = 0;
  KeReleaseSpinLock(&v12->m_SpinLock.SpinLock, v17);
  if ( !v16 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v18) = 4;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v18,
        v19,
        42,
        (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
        (char)this,
        this->m_WfcPortId);
    }
    ((void (__fastcall *)(void *, _QWORD))this->m_pAdapter->m_MiniportDataHandlers.TalTxRxResetPortHandler)(
      this->m_pAdapter->m_MiniportTalTxRxContext,
      this->m_WfcPortId);
    if ( v10 )
      CPort::RestartSendAndReceivesLE(this);
    v12 = this->m_PortLock;
    v12->m_SpinLock.OldIrql = KeAcquireSpinLockRaiseToDpc(&v12->m_SpinLock.SpinLock);
    v12->m_IsLocked = 1;
    this->m_State &= ~0x10u;
LABEL_25:
    v12->m_IsLocked = 0;
    KeReleaseSpinLock(&v12->m_SpinLock.SpinLock, v12->m_SpinLock.OldIrql);
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v21) = v16;
    LOBYTE(v18) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v18,
      1,
      43,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
      v21);
  }
  return v16;
}

```

## disassembly

```asm
0x14003083c  push    rbx
0x14003083e  push    rbp
0x14003083f  push    rsi
0x140030840  push    rdi
0x140030841  push    r12
0x140030843  push    r13
0x140030845  push    r14
0x140030847  push    r15
0x140030849  sub     rsp, 58h
0x14003084d  mov     r15, rdx
0x140030850  mov     rdi, rcx
0x140030853  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003085a  xor     r12d, r12d
0x14003085d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140030864  lea     rdx, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x14003086b  jz      short loc_1400308CD
0x14003086d  mov     rcx, cs:WPP_GLOBAL_Control
0x140030874  cmp     byte ptr [rcx+29h], 5
0x140030878  jnb     loc_140030B23
0x14003087e  cmp     [rcx+48h], r12w
0x140030883  jnz     loc_140030B23
0x140030889  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140030890  jz      short loc_1400308CD
0x140030892  mov     eax, [rdi+368h]
0x140030898  mov     r9d, 27h ; '''
0x14003089e  movzx   ecx, word ptr [rdi+64h]
0x1400308a2  mov     [rsp+98h+var_58], eax
0x1400308a6  mov     eax, [rdi+60h]
0x1400308a9  mov     [rsp+98h+var_60], eax
0x1400308ad  mov     [rsp+98h+var_68], ecx
0x1400308b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400308b8  mov     [rsp+98h+var_70], rdi
0x1400308bd  mov     [rsp+98h+var_78], rdx
0x1400308c2  mov     dl, 4
0x1400308c4  mov     rcx, [rcx+40h]
0x1400308c8  call    WPP_RECORDER_SF_qDdd
0x1400308cd  mov     rbx, [rdi+3A0h]
0x1400308d4  mov     rcx, rbx; SpinLock
0x1400308d7  mov     [rdi+358h], r12b
0x1400308de  mov     [rdi+393h], r12b
0x1400308e5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400308ec  nop     dword ptr [rax+rax+00h]
0x1400308f1  mov     byte ptr [rbx+10h], 1
0x1400308f5  lea     r14, [rdi+391h]
0x1400308fc  mov     [rbx+8], al
0x1400308ff  lea     rsi, [rdi+30Ch]
0x140030906  mov     eax, [rdi+368h]
0x14003090c  test    al, 43h
0x14003090e  jnz     loc_140030AF8
0x140030914  mov     bpl, 1
0x140030917  mov     [r14], r12b
0x14003091a  mov     [rdi+392h], r12b
0x140030921  mov     [rsi], r12d
0x140030924  mov     dl, [rbx+8]; NewIrql
0x140030927  mov     rcx, rbx; SpinLock
0x14003092a  mov     [rbx+10h], r12b
0x14003092e  call    cs:__imp_KeReleaseSpinLock
0x140030935  nop     dword ptr [rax+rax+00h]
0x14003093a  test    bpl, bpl
0x14003093d  jz      short loc_14003094C
0x14003093f  mov     edx, 2; enum _WFC_RX_STOP_REASON
0x140030944  mov     rcx, rdi; this
0x140030947  call    ?StopSendAndReceivesLE@CPort@@AEAAXW4_WFC_RX_STOP_REASON@@@Z; CPort::StopSendAndReceivesLE(_WFC_RX_STOP_REASON)
0x14003094c  mov     rbx, [rdi+3A0h]
0x140030953  mov     rcx, rbx; SpinLock
0x140030956  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003095d  nop     dword ptr [rax+rax+00h]
0x140030962  mov     [rbx+8], al
0x140030965  mov     byte ptr [rbx+10h], 1
0x140030969  mov     eax, [rdi+368h]
0x14003096f  test    al, 18h
0x140030971  jnz     loc_140030B49
0x140030977  cmp     [rdi+370h], r12d
0x14003097e  jnz     short loc_140030997
0x140030980  cmp     [rdi+308h], r12d
0x140030987  jnz     loc_140030B8D
0x14003098d  cmp     byte ptr [r14], 1
0x140030991  jz      loc_140030A73
0x140030997  or      eax, 8
0x14003099a  mov     [rdi+218h], r15
0x1400309a1  mov     [rdi+368h], eax
0x1400309a7  lea     r14, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400309ae  mov     esi, 103h
0x1400309b3  mov     dl, [rbx+8]; NewIrql
0x1400309b6  mov     rcx, rbx; SpinLock
0x1400309b9  mov     [rbx+10h], r12b
0x1400309bd  call    cs:__imp_KeReleaseSpinLock
0x1400309c4  nop     dword ptr [rax+rax+00h]
0x1400309c9  test    esi, esi
0x1400309cb  jz      short loc_140030A06
0x1400309cd  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400309d4  jz      short loc_1400309F2
0x1400309d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400309dd  cmp     byte ptr [rcx+29h], 5
0x1400309e1  jnb     loc_140030B00
0x1400309e7  cmp     [rcx+48h], r12w
0x1400309ec  jnz     loc_140030B00
0x1400309f2  mov     eax, esi
0x1400309f4  add     rsp, 58h
0x1400309f8  pop     r15
0x1400309fa  pop     r14
0x1400309fc  pop     r13
0x1400309fe  pop     r12
0x140030a00  pop     rdi
0x140030a01  pop     rsi
0x140030a02  pop     rbp
0x140030a03  pop     rbx
0x140030a04  retn
0x140030a06  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140030a0d  jnz     loc_140030AC9
0x140030a13  mov     rcx, [rdi+58h]
0x140030a17  movzx   edx, word ptr [rdi+64h]
0x140030a1b  mov     rax, [rcx+3EECh]
0x140030a22  mov     rcx, [rcx+70h]
0x140030a26  call    _guard_dispatch_icall
0x140030a2b  test    bpl, bpl
0x140030a2e  jnz     loc_140030B9B
0x140030a34  mov     rbx, [rdi+3A0h]
0x140030a3b  mov     rcx, rbx; SpinLock
0x140030a3e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140030a45  nop     dword ptr [rax+rax+00h]
0x140030a4a  mov     [rbx+8], al
0x140030a4d  mov     byte ptr [rbx+10h], 1
0x140030a51  and     dword ptr [rdi+368h], 0FFFFFFEFh
0x140030a58  mov     [rbx+10h], r12b
0x140030a5c  mov     rcx, rbx; SpinLock
0x140030a5f  mov     dl, [rbx+8]; NewIrql
0x140030a62  call    cs:__imp_KeReleaseSpinLock
0x140030a69  nop     dword ptr [rax+rax+00h]
0x140030a6e  jmp     loc_1400309CD
0x140030a73  cmp     byte ptr [rdi+392h], 1
0x140030a7a  jnz     loc_140030997
0x140030a80  mov     esi, r12d
0x140030a83  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140030a8a  lea     r14, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x140030a91  jz      short loc_140030ABD
0x140030a93  mov     rcx, cs:WPP_GLOBAL_Control
0x140030a9a  mov     r9d, 29h ; ')'
0x140030aa0  movzx   eax, word ptr [rdi+64h]
0x140030aa4  mov     dl, 4
0x140030aa6  mov     [rsp+98h+var_68], eax
0x140030aaa  mov     [rsp+98h+var_70], rdi
0x140030aaf  mov     rcx, [rcx+40h]
0x140030ab3  mov     [rsp+98h+var_78], r14
0x140030ab8  call    WPP_RECORDER_SF_qD
0x140030abd  or      dword ptr [rdi+368h], 10h
0x140030ac4  jmp     loc_1400309B3
0x140030ac9  mov     rcx, cs:WPP_GLOBAL_Control
0x140030ad0  mov     r9d, 2Ah ; '*'
0x140030ad6  movzx   eax, word ptr [rdi+64h]
0x140030ada  mov     dl, 4
0x140030adc  mov     [rsp+98h+var_68], eax
0x140030ae0  mov     [rsp+98h+var_70], rdi
0x140030ae5  mov     rcx, [rcx+40h]
0x140030ae9  mov     [rsp+98h+var_78], r14
0x140030aee  call    WPP_RECORDER_SF_qD
0x140030af3  jmp     loc_140030A13
0x140030af8  mov     bpl, r12b
0x140030afb  jmp     loc_140030924
0x140030b00  mov     rcx, [rcx+40h]
0x140030b04  mov     r9d, 2Bh ; '+'
0x140030b0a  mov     dword ptr [rsp+98h+var_70], esi
0x140030b0e  mov     dl, 5
0x140030b10  mov     [rsp+98h+var_78], r14
0x140030b15  lea     r8d, [r9-2Ah]
0x140030b19  call    WPP_RECORDER_SF_D
0x140030b1e  jmp     loc_1400309F2
0x140030b23  mov     rcx, [rcx+40h]
0x140030b27  mov     r9d, 26h ; '&'
0x140030b2d  mov     [rsp+98h+var_78], rdx
0x140030b32  mov     dl, 5
0x140030b34  lea     r8d, [r9-25h]
0x140030b38  call    WPP_RECORDER_SF_
0x140030b3d  lea     rdx, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x140030b44  jmp     loc_140030889
0x140030b49  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140030b50  lea     r14, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x140030b57  jz      short loc_140030B83
0x140030b59  mov     rcx, cs:WPP_GLOBAL_Control
0x140030b60  mov     r9d, 28h ; '('
0x140030b66  movzx   eax, word ptr [rdi+64h]
0x140030b6a  mov     dl, 2
0x140030b6c  mov     [rsp+98h+var_68], eax
0x140030b70  mov     [rsp+98h+var_70], rdi
0x140030b75  mov     rcx, [rcx+40h]
0x140030b79  mov     [rsp+98h+var_78], r14
0x140030b7e  call    WPP_RECORDER_SF_qD
0x140030b83  mov     esi, 0C023002Eh
0x140030b88  jmp     loc_140030A58
0x140030b8d  cmp     [rsi], r12d
0x140030b90  jnz     loc_140030997
0x140030b96  jmp     loc_14003098D
0x140030b9b  mov     rcx, rdi; this
0x140030b9e  call    ?RestartSendAndReceivesLE@CPort@@AEAAXXZ; CPort::RestartSendAndReceivesLE(void)
0x140030ba3  jmp     loc_140030A34
```
