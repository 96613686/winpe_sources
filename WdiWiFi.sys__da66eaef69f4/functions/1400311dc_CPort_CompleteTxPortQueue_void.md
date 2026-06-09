# CPort::CompleteTxPortQueue(void)

- ea: `0x1400311dc`
- end: `0x1400313ac`
- name: `?CompleteTxPortQueue@CPort@@QEAAXXZ`
- size: `464`
- prototype: `void __fastcall(CPort *__hidden this)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140030bb0`
- `0x14003ff4c`
- `0x1400403c0`
- `0x1400b5f40`

## callees

- `0x140010730`
- `0x1400311dc`
- `0x140034e04`
- `0x140034ec4`
- `0x14003b77c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140031258`
- `ntoskrnl!KeReleaseSpinLock` at `0x140031258`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031231`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031231`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x140031377`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x140031377`

## pseudocode

```c
void __fastcall CPort::CompleteTxPortQueue(CPort *this)
{
  struct _NET_BUFFER_LIST *m_pNblHead; // rdi
  CNdisSpinLock *m_TxPrequeueLock; // rsi
  int v4; // edx
  int v5; // r8d
  unsigned int m_NblCnt; // ebp
  KIRQL OldIrql; // dl
  int v8; // edx
  int v9; // r8d
  struct _NET_BUFFER_LIST *Alignment; // rax
  __int64 v11; // [rsp+28h] [rbp-50h]

  m_pNblHead = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      65,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids);
  }
  m_TxPrequeueLock = this->m_pAdapter->m_TxMgr.m_TxPrequeueLock;
  m_TxPrequeueLock->m_SpinLock.OldIrql = KeAcquireSpinLockRaiseToDpc(&m_TxPrequeueLock->m_SpinLock.SpinLock);
  m_TxPrequeueLock->m_IsLocked = 1;
  m_NblCnt = this->m_TxPortQueue.m_NblCnt;
  if ( m_NblCnt )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = 4;
      WPP_RECORDER_SF_qDL(
        WPP_GLOBAL_Control->DeviceExtension,
        v4,
        v5,
        66,
        (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
        (char)this,
        this->m_WfcPortId,
        this->m_TxPortQueue.m_NblCnt);
    }
    m_pNblHead = this->m_TxPortQueue.m_pNblHead;
    this->m_TxPortQueue.m_pNblHead = 0;
    this->m_TxPortQueue.m_ppNblTail = &this->m_TxPortQueue.m_pNblHead;
    this->m_TxPortQueue.m_NblCnt = 0;
    _InterlockedAdd(&this->m_pAdapter->m_TxMgr.m_TotalPrequeueCount, -m_NblCnt);
  }
  OldIrql = m_TxPrequeueLock->m_SpinLock.OldIrql;
  m_TxPrequeueLock->m_IsLocked = 0;
  KeReleaseSpinLock(&m_TxPrequeueLock->m_SpinLock.SpinLock, OldIrql);
  if ( m_pNblHead )
  {
    Alignment = m_pNblHead;
    do
    {
      Alignment->Status = 0;
      Alignment = (struct _NET_BUFFER_LIST *)Alignment->Link.Alignment;
    }
    while ( Alignment );
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 4;
      WPP_RECORDER_SF_qDq(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        v9,
        67,
        (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
        (char)this,
        this->m_WfcPortId,
        (char)m_pNblHead);
    }
    NdisMSendNetBufferListsComplete(this->m_pAdapter->m_MiniportAdapterHandle, m_pNblHead, 0);
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v11) = 0;
    LOBYTE(v8) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      1,
      68,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
      v11);
  }
}

```

## disassembly

```asm
0x1400311dc  push    rbx
0x1400311de  push    rbp
0x1400311df  push    rsi
0x1400311e0  push    rdi
0x1400311e1  push    r12
0x1400311e3  push    r14
0x1400311e5  push    r15
0x1400311e7  sub     rsp, 40h
0x1400311eb  xor     r14d, r14d
0x1400311ee  mov     rbx, rcx
0x1400311f1  mov     edi, r14d
0x1400311f4  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400311fb  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140031202  lea     r12, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x140031209  jz      short loc_140031223
0x14003120b  mov     rcx, cs:WPP_GLOBAL_Control
0x140031212  cmp     byte ptr [rcx+29h], 5
0x140031216  jnb     loc_1400312A2
0x14003121c  cmp     [rcx+48h], r14w
0x140031221  jnz     short loc_1400312A2
0x140031223  mov     rax, [rbx+58h]
0x140031227  mov     rsi, [rax+3A48h]
0x14003122e  mov     rcx, rsi; SpinLock
0x140031231  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140031238  nop     dword ptr [rax+rax+00h]
0x14003123d  mov     [rsi+8], al
0x140031240  mov     byte ptr [rsi+10h], 1
0x140031244  mov     ebp, [rbx+388h]
0x14003124a  test    ebp, ebp
0x14003124c  jnz     short loc_1400312C1
0x14003124e  mov     dl, [rsi+8]; NewIrql
0x140031251  mov     rcx, rsi; SpinLock
0x140031254  mov     [rsi+10h], r14b
0x140031258  call    cs:__imp_KeReleaseSpinLock
0x14003125f  nop     dword ptr [rax+rax+00h]
0x140031264  test    rdi, rdi
0x140031267  jnz     loc_14003131F
0x14003126d  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140031274  jz      short loc_140031292
0x140031276  mov     rcx, cs:WPP_GLOBAL_Control
0x14003127d  cmp     byte ptr [rcx+29h], 5
0x140031281  jnb     loc_140031388
0x140031287  cmp     [rcx+48h], r14w
0x14003128c  jnz     loc_140031388
0x140031292  add     rsp, 40h
0x140031296  pop     r15
0x140031298  pop     r14
0x14003129a  pop     r12
0x14003129c  pop     rdi
0x14003129d  pop     rsi
0x14003129e  pop     rbp
0x14003129f  pop     rbx
0x1400312a0  retn
0x1400312a2  mov     rcx, [rcx+40h]
0x1400312a6  mov     r9d, 41h ; 'A'
0x1400312ac  mov     dl, 5
0x1400312ae  mov     [rsp+78h+var_58], r12
0x1400312b3  lea     r8d, [r9-40h]
0x1400312b7  call    WPP_RECORDER_SF_
0x1400312bc  jmp     loc_140031223
0x1400312c1  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400312c8  jz      short loc_1400312F8
0x1400312ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400312d1  mov     r9d, 42h ; 'B'
0x1400312d7  movzx   eax, word ptr [rbx+64h]
0x1400312db  mov     dl, 4
0x1400312dd  mov     dword ptr [rsp+78h+var_40], ebp
0x1400312e1  mov     [rsp+78h+var_48], eax
0x1400312e5  mov     rcx, [rcx+40h]
0x1400312e9  mov     [rsp+78h+var_50], rbx
0x1400312ee  mov     [rsp+78h+var_58], r12
0x1400312f3  call    WPP_RECORDER_SF_qDL
0x1400312f8  lea     rax, [rbx+378h]
0x1400312ff  neg     ebp
0x140031301  mov     rdi, [rax]
0x140031304  mov     [rax], r14
0x140031307  mov     [rax+8], rax
0x14003130b  mov     [rax+10h], r14d
0x14003130f  mov     rax, [rbx+58h]
0x140031313  lock add [rax+3A18h], ebp
0x14003131a  jmp     loc_14003124E
0x14003131f  mov     rax, rdi
0x140031322  mov     [rax+8Ch], r14d
0x140031329  mov     rax, [rax]
0x14003132c  test    rax, rax
0x14003132f  jnz     short loc_140031322
0x140031331  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140031338  jz      short loc_140031369
0x14003133a  mov     rcx, cs:WPP_GLOBAL_Control
0x140031341  mov     r9d, 43h ; 'C'
0x140031347  movzx   eax, word ptr [rbx+64h]
0x14003134b  mov     dl, 4
0x14003134d  mov     [rsp+78h+var_40], rdi
0x140031352  mov     [rsp+78h+var_48], eax
0x140031356  mov     rcx, [rcx+40h]
0x14003135a  mov     [rsp+78h+var_50], rbx
0x14003135f  mov     [rsp+78h+var_58], r12
0x140031364  call    WPP_RECORDER_SF_qDq
0x140031369  mov     rcx, [rbx+58h]
0x14003136d  xor     r8d, r8d; SendCompleteFlags
0x140031370  mov     rdx, rdi; NetBufferList
0x140031373  mov     rcx, [rcx+58h]; MiniportAdapterHandle
0x140031377  call    cs:__imp_NdisMSendNetBufferListsComplete
0x14003137e  nop     dword ptr [rax+rax+00h]
0x140031383  jmp     loc_14003126D
0x140031388  mov     rcx, [rcx+40h]
0x14003138c  mov     r9d, 44h ; 'D'
0x140031392  mov     dword ptr [rsp+78h+var_50], r14d
0x140031397  mov     dl, 5
0x140031399  mov     [rsp+78h+var_58], r12
0x14003139e  lea     r8d, [r9-43h]
0x1400313a2  call    WPP_RECORDER_SF_D
0x1400313a7  jmp     loc_140031292
```
