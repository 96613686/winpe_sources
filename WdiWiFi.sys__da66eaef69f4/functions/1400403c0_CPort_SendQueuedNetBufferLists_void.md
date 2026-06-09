# CPort::SendQueuedNetBufferLists(void)

- ea: `0x1400403c0`
- end: `0x140040947`
- name: `?SendQueuedNetBufferLists@CPort@@QEAAHXZ`
- size: `1415`
- prototype: `__int64 __fastcall(CPort *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14003ff4c`

## callees

- `0x1400122e0`
- `0x14002aa28`
- `0x1400311dc`
- `0x1400330a0`
- `0x140033730`
- `0x140034e04`
- `0x140034ec4`
- `0x140036ec0`
- `0x140037f80`
- `0x1400403c0`
- `0x1400409ec`
- `0x140040a20`
- `0x1400b7e2c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400404a6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400405c9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004070f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400404a6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400405c9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004070f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004045c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140040549`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004066d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140040731`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004045c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140040549`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004066d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140040731`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x1400408c2`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x1400408c2`

## pseudocode

```c
__int64 __fastcall CPort::SendQueuedNetBufferLists(CPort *this, __int64 a2, int a3, int a4)
{
  unsigned int v4; // r12d
  unsigned int m_State; // edx
  CAdapter **p_m_pAdapter; // r15
  char v8; // r13
  CNdisSpinLock *m_TxPrequeueLock; // rbx
  int v10; // edx
  int v11; // r8d
  NblChain *p_m_TxPortQueue; // r14
  struct _NET_BUFFER_LIST *v13; // rax
  struct _NET_BUFFER_LIST *v14; // rsi
  CAdapter *v15; // rbx
  int v16; // edx
  int v17; // r8d
  int v18; // edx
  int v19; // r8d
  KIRQL OldIrql; // dl
  int v21; // r9d
  KIRQL v22; // al
  KIRQL v23; // al
  int v24; // edx
  int v25; // r8d
  int v26; // edx
  int v28; // [rsp+20h] [rbp-50h]
  __int64 v29; // [rsp+28h] [rbp-48h]
  PNET_BUFFER_LIST NetBufferList; // [rsp+50h] [rbp-20h] BYREF
  PNET_BUFFER_LIST *p_NetBufferList; // [rsp+58h] [rbp-18h]
  int v32; // [rsp+60h] [rbp-10h]
  unsigned __int8 v33; // [rsp+B0h] [rbp+40h] BYREF
  unsigned __int8 v34; // [rsp+B8h] [rbp+48h] BYREF

  v4 = 0;
  NetBufferList = 0;
  p_NetBufferList = &NetBufferList;
  v32 = 0;
  v34 = 0;
  v33 = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      85,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids);
  }
  m_State = this->m_State;
  if ( m_State )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(m_State) = 5;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        m_State,
        a3,
        86,
        (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
        (char)this,
        this->m_WfcPortId,
        this->m_State);
    }
    v8 = 0;
    p_m_pAdapter = &this->m_pAdapter;
  }
  else
  {
    p_m_pAdapter = &this->m_pAdapter;
    v8 = 1;
    m_TxPrequeueLock = this->m_pAdapter->m_TxMgr.m_TxPrequeueLock;
    m_TxPrequeueLock->m_SpinLock.OldIrql = KeAcquireSpinLockRaiseToDpc(&m_TxPrequeueLock->m_SpinLock.SpinLock);
    m_TxPrequeueLock->m_IsLocked = 1;
    if ( this->m_pAdapter->m_TxMgr.m_TotalPrequeueCount )
    {
      p_m_TxPortQueue = &this->m_TxPortQueue;
      if ( this->m_TxPortQueue.m_NblCnt )
      {
        v13 = NblChain::RemoveHead(&this->m_TxPortQueue);
        for ( m_TxPrequeueLock->m_IsLocked = 0; ; m_TxPrequeueLock->m_IsLocked = 0 )
        {
          v14 = v13;
          KeReleaseSpinLock(&m_TxPrequeueLock->m_SpinLock.SpinLock, m_TxPrequeueLock->m_SpinLock.OldIrql);
          v15 = *p_m_pAdapter;
          if ( !v14 )
          {
            m_TxPrequeueLock = v15->m_TxMgr.m_TxPrequeueLock;
            v23 = KeAcquireSpinLockRaiseToDpc(&m_TxPrequeueLock->m_SpinLock.SpinLock);
            m_TxPrequeueLock->m_IsLocked = 1;
            m_TxPrequeueLock->m_SpinLock.OldIrql = v23;
            if ( this->m_TxPortQueue.m_NblCnt )
            {
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v24) = 4;
                WPP_RECORDER_SF_qD(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v24,
                  v25,
                  93,
                  (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
                  (char)this,
                  this->m_WfcPortId);
              }
              v4 = 259;
            }
            else if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v24) = 4;
              WPP_RECORDER_SF_qD(
                WPP_GLOBAL_Control->DeviceExtension,
                v24,
                v25,
                92,
                (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
                (char)this,
                this->m_WfcPortId);
            }
            goto LABEL_31;
          }
          v4 = CTxMgr::InitializeTxWfcFrame(&v15->m_TxMgr, v14, this->m_WfcPortId, this->m_KeyConfigured);
          if ( v4 )
            break;
          v4 = CPort::AddWfcFrameToPendingCount(this, (struct _WFC_FRAME *)((char *)v14->MiniportReserved[0] - 64));
          if ( v4 || (v4 = CTxMgr::ProcessNBL(&(*p_m_pAdapter)->m_TxMgr, v14, &v33)) != 0 )
          {
            if ( v14->MiniportReserved[0] )
              CPort::FreeTxWfcFrame(this, v14, &v34);
            if ( !v33 )
            {
              v14->Status = 0;
              *p_NetBufferList = v14;
              ++v32;
              p_NetBufferList = &v14->Next;
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
                goto LABEL_25;
              v21 = 90;
LABEL_24:
              LOBYTE(v16) = 2;
              WPP_RECORDER_SF_qDD(
                WPP_GLOBAL_Control->DeviceExtension,
                v16,
                v17,
                v21,
                (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
                (char)this,
                this->m_WfcPortId,
                v4);
              goto LABEL_25;
            }
            m_TxPrequeueLock = (*p_m_pAdapter)->m_TxMgr.m_TxPrequeueLock;
            m_TxPrequeueLock->m_SpinLock.OldIrql = KeAcquireSpinLockRaiseToDpc(&m_TxPrequeueLock->m_SpinLock.SpinLock);
            m_TxPrequeueLock->m_IsLocked = 1;
            if ( this->m_bIsTxPortQueueAllowed )
            {
              if ( this->m_TxPortQueue.m_NblCnt )
              {
                v14->Link.Alignment = (ULONGLONG)p_m_TxPortQueue->m_pNblHead;
                p_m_TxPortQueue->m_pNblHead = v14;
              }
              else
              {
                *this->m_TxPortQueue.m_ppNblTail = v14;
                this->m_TxPortQueue.m_ppNblTail = (_NET_BUFFER_LIST **)*this->m_TxPortQueue.m_ppNblTail;
              }
              ++this->m_TxPortQueue.m_NblCnt;
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v18) = 4;
                WPP_RECORDER_SF_qD(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v18,
                  v19,
                  88,
                  (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
                  (char)this,
                  this->m_WfcPortId);
              }
              goto LABEL_31;
            }
            v14->Status = 0;
            *p_NetBufferList = v14;
            ++v32;
            p_NetBufferList = &v14->Next;
            if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v18) = 4;
              WPP_RECORDER_SF_qD(
                WPP_GLOBAL_Control->DeviceExtension,
                v18,
                v19,
                89,
                (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
                (char)this,
                this->m_WfcPortId);
            }
            OldIrql = m_TxPrequeueLock->m_SpinLock.OldIrql;
            m_TxPrequeueLock->m_IsLocked = 0;
            KeReleaseSpinLock(&m_TxPrequeueLock->m_SpinLock.SpinLock, OldIrql);
          }
LABEL_25:
          m_TxPrequeueLock = (*p_m_pAdapter)->m_TxMgr.m_TxPrequeueLock;
          v22 = KeAcquireSpinLockRaiseToDpc(&m_TxPrequeueLock->m_SpinLock.SpinLock);
          m_TxPrequeueLock->m_IsLocked = 1;
          m_TxPrequeueLock->m_SpinLock.OldIrql = v22;
          _InterlockedDecrement(&(*p_m_pAdapter)->m_TxMgr.m_TotalPrequeueCount);
          v13 = NblChain::RemoveHead(&this->m_TxPortQueue);
        }
        v14->Status = 0;
        *p_NetBufferList = v14;
        ++v32;
        p_NetBufferList = &v14->Next;
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_25;
        v21 = 91;
        goto LABEL_24;
      }
    }
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v10) = 5;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        v11,
        87,
        (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
        (char)this,
        this->m_WfcPortId);
    }
LABEL_31:
    m_TxPrequeueLock->m_IsLocked = 0;
    KeReleaseSpinLock(&m_TxPrequeueLock->m_SpinLock.SpinLock, m_TxPrequeueLock->m_SpinLock.OldIrql);
  }
  v26 = (int)NetBufferList;
  if ( NetBufferList )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qDqL(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)NetBufferList,
        a3,
        a4,
        v28,
        (char)this,
        this->m_WfcPortId,
        (char)NetBufferList,
        v32);
    NdisMSendNetBufferListsComplete((*p_m_pAdapter)->m_MiniportAdapterHandle, NetBufferList, 0);
  }
  if ( v34 )
    CPort::CompletePendingCancelSendsOrHaltJobs(this);
  if ( !v8 )
    CPort::CompleteTxPortQueue(this);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v29) = v4;
    LOBYTE(v26) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v26,
      1,
      95,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
      v29);
  }
  return v4;
}

```

## disassembly

```asm
0x1400403c0  mov     [rsp-38h+arg_10], rbx
0x1400403c5  push    rbp
0x1400403c6  push    rsi
0x1400403c7  push    rdi
0x1400403c8  push    r12
0x1400403ca  push    r13
0x1400403cc  push    r14
0x1400403ce  push    r15
0x1400403d0  mov     rbp, rsp
0x1400403d3  sub     rsp, 70h
0x1400403d7  xor     esi, esi
0x1400403d9  lea     rax, [rbp+NetBufferList]
0x1400403dd  mov     r12d, esi
0x1400403e0  mov     [rbp+NetBufferList], rsi
0x1400403e4  mov     [rbp+var_18], rax
0x1400403e8  mov     rdi, rcx
0x1400403eb  mov     [rbp+var_10], esi
0x1400403ee  mov     [rbp+arg_8], sil
0x1400403f2  mov     [rbp+arg_0], sil
0x1400403f6  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400403fd  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140040404  lea     r14, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x14004040b  jz      short loc_14004043A
0x14004040d  mov     rcx, cs:WPP_GLOBAL_Control
0x140040414  cmp     byte ptr [rcx+29h], 5
0x140040418  jnb     short loc_140040420
0x14004041a  cmp     [rcx+48h], si
0x14004041e  jz      short loc_14004043A
0x140040420  mov     rcx, [rcx+40h]
0x140040424  mov     r9d, 55h ; 'U'
0x14004042a  mov     dl, 5
0x14004042c  mov     [rsp+70h+var_50], r14
0x140040431  lea     r8d, [r9-54h]
0x140040435  call    WPP_RECORDER_SF_
0x14004043a  mov     edx, [rdi+368h]
0x140040440  test    edx, edx
0x140040442  jnz     loc_14004082F
0x140040448  lea     r15, [rdi+58h]
0x14004044c  mov     r13b, 1
0x14004044f  mov     rax, [r15]
0x140040452  mov     rbx, [rax+3A48h]
0x140040459  mov     rcx, rbx; SpinLock
0x14004045c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140040463  nop     dword ptr [rax+rax+00h]
0x140040468  mov     [rbx+8], al
0x14004046b  mov     [rbx+10h], r13b
0x14004046f  mov     rax, [r15]
0x140040472  mov     ecx, [rax+3A18h]
0x140040478  test    ecx, ecx
0x14004047a  jz      loc_1400407E5
0x140040480  lea     r14, [rdi+378h]
0x140040487  cmp     [r14+10h], esi
0x14004048b  jz      loc_1400407DE
0x140040491  mov     rcx, r14; this
0x140040494  call    ?RemoveHead@NblChain@@QEAAPEAU_NET_BUFFER_LIST@@XZ; NblChain::RemoveHead(void)
0x140040499  mov     [rbx+10h], r12b
0x14004049d  mov     dl, [rbx+8]; NewIrql
0x1400404a0  mov     rcx, rbx; SpinLock
0x1400404a3  mov     rsi, rax
0x1400404a6  call    cs:__imp_KeReleaseSpinLock
0x1400404ad  nop     dword ptr [rax+rax+00h]
0x1400404b2  mov     rbx, [r15]
0x1400404b5  test    rsi, rsi
0x1400404b8  jz      loc_140040727
0x1400404be  mov     r9b, [rdi+358h]; unsigned __int8
0x1400404c5  lea     rcx, [rbx+3A10h]; this
0x1400404cc  movzx   r8d, word ptr [rdi+64h]; unsigned __int16
0x1400404d1  mov     rdx, rsi; struct _NET_BUFFER_LIST *
0x1400404d4  call    ?InitializeTxWfcFrame@CTxMgr@@QEAAHPEAU_NET_BUFFER_LIST@@GE@Z; CTxMgr::InitializeTxWfcFrame(_NET_BUFFER_LIST *,ushort,uchar)
0x1400404d9  xor     ebx, ebx
0x1400404db  mov     r12d, eax
0x1400404de  test    eax, eax
0x1400404e0  jnz     loc_140040606
0x1400404e6  mov     rdx, [rsi+60h]
0x1400404ea  mov     rcx, rdi; this
0x1400404ed  sub     rdx, 40h ; '@'; struct _WFC_FRAME *
0x1400404f1  call    ?AddWfcFrameToPendingCount@CPort@@AEAAHPEAU_WFC_FRAME@@@Z; CPort::AddWfcFrameToPendingCount(_WFC_FRAME *)
0x1400404f6  mov     r12d, eax
0x1400404f9  test    eax, eax
0x1400404fb  jnz     short loc_14004051E
0x1400404fd  mov     rcx, [r15]
0x140040500  lea     r8, [rbp+arg_0]; unsigned __int8 *
0x140040504  add     rcx, 3A10h; this
0x14004050b  mov     rdx, rsi; struct _NET_BUFFER_LIST *
0x14004050e  call    ?ProcessNBL@CTxMgr@@QEAAHPEAU_NET_BUFFER_LIST@@PEAE@Z; CTxMgr::ProcessNBL(_NET_BUFFER_LIST *,uchar *)
0x140040513  mov     r12d, eax
0x140040516  test    eax, eax
0x140040518  jz      loc_140040660
0x14004051e  cmp     [rsi+60h], rbx
0x140040522  jz      short loc_140040533
0x140040524  lea     r8, [rbp+arg_8]; unsigned __int8 *
0x140040528  mov     rdx, rsi; struct _NET_BUFFER_LIST *
0x14004052b  mov     rcx, rdi; this
0x14004052e  call    ?FreeTxWfcFrame@CPort@@AEAAHPEAU_NET_BUFFER_LIST@@PEAE@Z; CPort::FreeTxWfcFrame(_NET_BUFFER_LIST *,uchar *)
0x140040533  cmp     [rbp+arg_0], bl
0x140040536  jz      loc_1400405DA
0x14004053c  mov     rax, [r15]
0x14004053f  mov     rbx, [rax+3A48h]
0x140040546  mov     rcx, rbx; SpinLock
0x140040549  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140040550  nop     dword ptr [rax+rax+00h]
0x140040555  mov     [rbx+8], al
0x140040558  xor     eax, eax
0x14004055a  mov     [rbx+10h], r13b
0x14004055e  cmp     [rdi+390h], al
0x140040564  jnz     loc_14004069B
0x14004056a  mov     [rsi+8Ch], eax
0x140040570  mov     rax, [rbp+var_18]
0x140040574  mov     [rax], rsi
0x140040577  inc     [rbp+var_10]
0x14004057a  mov     [rbp+var_18], rsi
0x14004057e  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140040585  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004058c  jz      short loc_1400405BF
0x14004058e  movzx   eax, word ptr [rdi+64h]
0x140040592  mov     r9d, 59h ; 'Y'
0x140040598  mov     rcx, cs:WPP_GLOBAL_Control
0x14004059f  mov     dl, 4
0x1400405a1  mov     [rsp+70h+var_40], eax
0x1400405a5  lea     rax, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400405ac  mov     [rsp+70h+var_48], rdi
0x1400405b1  mov     [rsp+70h+var_50], rax
0x1400405b6  mov     rcx, [rcx+40h]
0x1400405ba  call    WPP_RECORDER_SF_qD
0x1400405bf  mov     dl, [rbx+8]; NewIrql
0x1400405c2  mov     rcx, rbx; SpinLock
0x1400405c5  mov     byte ptr [rbx+10h], 0
0x1400405c9  call    cs:__imp_KeReleaseSpinLock
0x1400405d0  nop     dword ptr [rax+rax+00h]
0x1400405d5  jmp     loc_140040660
0x1400405da  mov     [rsi+8Ch], ebx
0x1400405e0  mov     rax, [rbp+var_18]
0x1400405e4  mov     [rax], rsi
0x1400405e7  inc     [rbp+var_10]
0x1400405ea  mov     [rbp+var_18], rsi
0x1400405ee  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400405f5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400405fc  jz      short loc_140040660
0x1400405fe  mov     r9d, 5Ah ; 'Z'
0x140040604  jmp     short loc_140040630
0x140040606  mov     [rsi+8Ch], ebx
0x14004060c  mov     rax, [rbp+var_18]
0x140040610  mov     [rax], rsi
0x140040613  inc     [rbp+var_10]
0x140040616  mov     [rbp+var_18], rsi
0x14004061a  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140040621  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140040628  jz      short loc_140040660
0x14004062a  mov     r9d, 5Bh ; '['
0x140040630  movzx   eax, word ptr [rdi+64h]
0x140040634  mov     dl, 2
0x140040636  mov     rcx, cs:WPP_GLOBAL_Control
0x14004063d  mov     dword ptr [rsp+70h+var_38], r12d
0x140040642  mov     [rsp+70h+var_40], eax
0x140040646  lea     rax, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x14004064d  mov     [rsp+70h+var_48], rdi
0x140040652  mov     rcx, [rcx+40h]
0x140040656  mov     [rsp+70h+var_50], rax
0x14004065b  call    WPP_RECORDER_SF_qDD
0x140040660  mov     rax, [r15]
0x140040663  mov     rbx, [rax+3A48h]
0x14004066a  mov     rcx, rbx; SpinLock
0x14004066d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140040674  nop     dword ptr [rax+rax+00h]
0x140040679  mov     [rbx+10h], r13b
0x14004067d  mov     rcx, r14; this
0x140040680  mov     [rbx+8], al
0x140040683  mov     rax, [r15]
0x140040686  lock dec dword ptr [rax+3A18h]
0x14004068d  call    ?RemoveHead@NblChain@@QEAAPEAU_NET_BUFFER_LIST@@XZ; NblChain::RemoveHead(void)
0x140040692  mov     byte ptr [rbx+10h], 0
0x140040696  jmp     loc_14004049D
0x14004069b  cmp     [r14+10h], eax
0x14004069f  jnz     short loc_1400406B5
0x1400406a1  mov     rax, [r14+8]
0x1400406a5  mov     [rax], rsi
0x1400406a8  mov     rax, [r14+8]
0x1400406ac  mov     rcx, [rax]
0x1400406af  mov     [r14+8], rcx
0x1400406b3  jmp     short loc_1400406BE
0x1400406b5  mov     rax, [r14]
0x1400406b8  mov     [rsi], rax
0x1400406bb  mov     [r14], rsi
0x1400406be  inc     dword ptr [r14+10h]
0x1400406c2  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400406c9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400406d0  jz      short loc_140040703
0x1400406d2  movzx   eax, word ptr [rdi+64h]
0x1400406d6  mov     r9d, 58h ; 'X'
0x1400406dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400406e3  mov     dl, 4
0x1400406e5  mov     [rsp+70h+var_40], eax
0x1400406e9  lea     rax, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400406f0  mov     [rsp+70h+var_48], rdi
0x1400406f5  mov     [rsp+70h+var_50], rax
0x1400406fa  mov     rcx, [rcx+40h]
0x1400406fe  call    WPP_RECORDER_SF_qD
0x140040703  xor     esi, esi
0x140040705  mov     [rbx+10h], sil
0x140040709  mov     rcx, rbx; SpinLock
0x14004070c  mov     dl, [rbx+8]; NewIrql
0x14004070f  call    cs:__imp_KeReleaseSpinLock
0x140040716  nop     dword ptr [rax+rax+00h]
0x14004071b  lea     rbx, WPP_RECORDER_INITIALIZED
0x140040722  jmp     loc_140040879
0x140040727  mov     rbx, [rbx+3A48h]
0x14004072e  mov     rcx, rbx; SpinLock
0x140040731  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140040738  nop     dword ptr [rax+rax+00h]
0x14004073d  xor     esi, esi
0x14004073f  mov     [rbx+10h], r13b
0x140040743  mov     [rbx+8], al
0x140040746  cmp     [rdi+388h], esi
0x14004074c  jnz     short loc_140040792
0x14004074e  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140040755  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004075c  jz      short loc_140040705
0x14004075e  movzx   eax, word ptr [rdi+64h]
0x140040762  lea     r9d, [rsi+5Ch]
0x140040766  mov     rcx, cs:WPP_GLOBAL_Control
0x14004076d  mov     dl, 4
0x14004076f  mov     [rsp+70h+var_40], eax
0x140040773  lea     rax, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x14004077a  mov     [rsp+70h+var_48], rdi
0x14004077f  mov     [rsp+70h+var_50], rax
0x140040784  mov     rcx, [rcx+40h]
0x140040788  call    WPP_RECORDER_SF_qD
0x14004078d  jmp     loc_140040705
0x140040792  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140040799  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400407a0  jz      short loc_1400407D3
0x1400407a2  movzx   eax, word ptr [rdi+64h]
0x1400407a6  mov     r9d, 5Dh ; ']'
0x1400407ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400407b3  mov     dl, 4
0x1400407b5  mov     [rsp+70h+var_40], eax
0x1400407b9  lea     rax, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400407c0  mov     [rsp+70h+var_48], rdi
0x1400407c5  mov     [rsp+70h+var_50], rax
0x1400407ca  mov     rcx, [rcx+40h]
0x1400407ce  call    WPP_RECORDER_SF_qD
0x1400407d3  mov     r12d, 103h
0x1400407d9  jmp     loc_140040705
0x1400407de  lea     r14, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400407e5  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400407ec  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400407f3  jz      loc_140040705
0x1400407f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140040800  cmp     byte ptr [rcx+29h], 5
0x140040804  jnb     short loc_140040810
0x140040806  cmp     [rcx+48h], si
0x14004080a  jz      loc_140040705
0x140040810  movzx   eax, word ptr [rdi+64h]
0x140040814  mov     r9d, 57h ; 'W'
0x14004081a  mov     [rsp+70h+var_40], eax
0x14004081e  mov     dl, 5
0x140040820  mov     [rsp+70h+var_48], rdi
0x140040825  mov     [rsp+70h+var_50], r14
0x14004082a  jmp     loc_140040784
0x14004082f  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x140040836  jz      short loc_140040872
0x140040838  mov     rcx, cs:WPP_GLOBAL_Control
0x14004083f  cmp     byte ptr [rcx+29h], 5
0x140040843  jnb     short loc_14004084B
0x140040845  cmp     [rcx+48h], si
0x140040849  jz      short loc_140040872
0x14004084b  movzx   eax, word ptr [rdi+64h]
0x14004084f  mov     r9d, 56h ; 'V'
0x140040855  mov     rcx, [rcx+40h]
0x140040859  mov     dword ptr [rsp+70h+var_38], edx
0x14004085d  mov     dl, 5
0x14004085f  mov     [rsp+70h+var_40], eax
0x140040863  mov     [rsp+70h+var_48], rdi
0x140040868  mov     [rsp+70h+var_50], r14
0x14004086d  call    WPP_RECORDER_SF_qDD
0x140040872  mov     r13b, sil
0x140040875  lea     r15, [rdi+58h]
0x140040879  mov     rdx, [rbp+NetBufferList]
0x14004087d  test    rdx, rdx
0x140040880  jz      short loc_1400408CE
0x140040882  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x140040889  jz      short loc_1400408B4
0x14004088b  movzx   ecx, word ptr [rdi+64h]
0x14004088f  mov     eax, [rbp+var_10]
0x140040892  mov     [rsp+70h+var_30], eax
0x140040896  mov     [rsp+70h+var_38], rdx
0x14004089b  mov     [rsp+70h+var_40], ecx
0x14004089f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400408a6  mov     [rsp+70h+var_48], rdi
0x1400408ab  mov     rcx, [rcx+40h]
0x1400408af  call    WPP_RECORDER_SF_qDqL
0x1400408b4  mov     rcx, [r15]
0x1400408b7  xor     r8d, r8d; SendCompleteFlags
0x1400408ba  mov     rdx, [rbp+NetBufferList]; NetBufferList
0x1400408be  mov     rcx, [rcx+58h]; MiniportAdapterHandle
0x1400408c2  call    cs:__imp_NdisMSendNetBufferListsComplete
0x1400408c9  nop     dword ptr [rax+rax+00h]
0x1400408ce  cmp     [rbp+arg_8], sil
0x1400408d2  jz      short loc_1400408DC
0x1400408d4  mov     rcx, rdi; this
  ... truncated ...
```
