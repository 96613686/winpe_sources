# CTxMgr::RemovePortId(ushort)

- ea: `0x140064cfc`
- end: `0x140065054`
- name: `?RemovePortId@CTxMgr@@QEAAHG@Z`
- size: `856`
- prototype: `__int64 __fastcall(PVOID WorkItemContext, unsigned __int16)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140064b28`

## callees

- `0x140023ae0`
- `0x140034e04`
- `0x140034ec4`
- `0x140038df0`
- `0x14003a200`
- `0x14003a4a0`
- `0x14003b620`
- `0x14003d8f0`
- `0x14003d930`
- `0x1400596d8`
- `0x140064cfc`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140064e3c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140064fd1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140064e3c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140064fd1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140064dd2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140064dd2`

## pseudocode

```c
__int64 __fastcall CTxMgr::RemovePortId(CTxMgr *WorkItemContext, unsigned __int16 a2)
{
  int v2; // r12d
  unsigned int v4; // ebx
  __int16 v5; // dx
  CNdisSpinLock *m_TxMgrLock; // rsi
  KIRQL v7; // al
  struct _WFC_TX_ENTRY *TxEntry; // rax
  __int16 v9; // dx
  struct _WFC_TX_ENTRY *v10; // r14
  KIRQL v11; // dl
  struct _NET_BUFFER_LIST *v12; // r13
  int v13; // ebp
  struct _WFC_TX_QUEUE *TxQueue; // rbx
  int BacklogCount; // edx
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *v18; // rcx
  struct _NET_BUFFER_LIST *v19; // rcx
  struct _NET_BUFFER_LIST *v20; // rax
  unsigned int v21; // eax
  KIRQL OldIrql; // dl
  __int64 v24; // [rsp+28h] [rbp-80h]
  struct _NET_BUFFER_LIST *v25; // [rsp+B0h] [rbp+8h]

  v2 = a2;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        187,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
    }
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        188,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
        v2);
    }
  }
  if ( WorkItemContext->m_QueueingMode )
  {
    m_TxMgrLock = WorkItemContext->m_TxMgrLock;
    v7 = KeAcquireSpinLockRaiseToDpc(&m_TxMgrLock->m_SpinLock.SpinLock);
    m_TxMgrLock->m_IsLocked = 1;
    m_TxMgrLock->m_SpinLock.OldIrql = v7;
    TxEntry = CTxEntryTable::GetTxEntry(&WorkItemContext->m_TxEntryTable, v2);
    v10 = TxEntry;
    if ( TxEntry )
    {
      v12 = 0;
      v25 = 0;
      v13 = 0;
      TxEntry->TxEntryState = TxEntry->TxEntryState & 0xFFFFFFFC | 1;
      while ( WorkItemContext->m_QueueingMode == PORT_QUEUEING
            ? (unsigned __int8)v13 < 2u
            : (unsigned __int8)v13 <= 0x18u )
      {
        TxQueue = CTxMgr::GetTxQueue(WorkItemContext, v10, v13);
        if ( TxQueue )
        {
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            BacklogCount = TxQueue->BacklogCount;
            LOBYTE(BacklogCount) = 4;
            WPP_RECORDER_SF_DDDDDD(
              WPP_GLOBAL_Control->DeviceExtension,
              BacklogCount,
              1,
              191,
              (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
              TxQueue->PortId,
              TxQueue->PeerId,
              TxQueue->Tid,
              TxQueue->BacklogCount,
              TxQueue->TransferPendingCount,
              TxQueue->TxPendingCount);
          }
          if ( !(unsigned int)CGlobalTxQueueList::RemoveTxQueue(&WorkItemContext->m_CGlobalTxQueueList, TxQueue) )
            WorkItemContext->m_CurActiveBacklog -= TxQueue->BacklogCount;
          CTxMgr::RemoveTxQueueFromAcEntry(WorkItemContext, TxQueue);
          while ( 1 )
          {
            Flink = TxQueue->BacklogQueue.Flink;
            if ( (struct _WFC_TX_QUEUE *)TxQueue->BacklogQueue.Flink == TxQueue )
              break;
            if ( (struct _WFC_TX_QUEUE *)Flink->Blink != TxQueue || (v18 = Flink->Flink, Flink->Flink->Blink != Flink) )
              __fastfail(3u);
            TxQueue->BacklogQueue.Flink = v18;
            v18->Blink = &TxQueue->BacklogQueue;
            v19 = (struct _NET_BUFFER_LIST *)Flink[1].Flink;
            BYTE4(Flink[-1].Flink) = 1;
            --TxQueue->BacklogCount;
            --v10->BacklogCount;
            if ( HIDWORD(Flink[-4].Flink) == 1 )
            {
              v20 = v12;
              v12 = v19;
            }
            else
            {
              v20 = v25;
              v25 = v19;
            }
            v19->Link.Alignment = (ULONGLONG)v20;
          }
          operator delete(TxQueue);
          v10->ppTxQueue[v13] = 0;
        }
        ++v13;
      }
      v21 = CTxEntryTable::RemoveTxEntry(&WorkItemContext->m_TxEntryTable, v2);
      OldIrql = m_TxMgrLock->m_SpinLock.OldIrql;
      v4 = v21;
      m_TxMgrLock->m_IsLocked = 0;
      KeReleaseSpinLock(&m_TxMgrLock->m_SpinLock.SpinLock, OldIrql);
      CTxMgr::CompleteNBLs(WorkItemContext, v12, v25, 1);
    }
    else
    {
      v4 = -1073741823;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = 2;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v9,
          1,
          190,
          (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
      }
      v11 = m_TxMgrLock->m_SpinLock.OldIrql;
      m_TxMgrLock->m_IsLocked = 0;
      KeReleaseSpinLock(&m_TxMgrLock->m_SpinLock.SpinLock, v11);
    }
  }
  else
  {
    v4 = 0;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return v4;
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      189,
      (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v24) = v4;
    LOBYTE(v5) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      1,
      192,
      (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
      v24);
  }
  return v4;
}

```

## disassembly

```asm
0x140064cfc  push    rbx
0x140064cfe  push    rbp
0x140064cff  push    rsi
0x140064d00  push    rdi
0x140064d01  push    r12
0x140064d03  push    r13
0x140064d05  push    r14
0x140064d07  push    r15
0x140064d09  sub     rsp, 68h
0x140064d0d  movzx   r12d, dx
0x140064d11  mov     rdi, rcx
0x140064d14  xor     r15d, r15d; __annotation("TMF:",
0x140064d17  lea     r13, WPP_RECORDER_INITIALIZED
0x140064d1e  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140064d25  lea     rsi, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x140064d2c  lea     ebp, [r15+1]
0x140064d30  jz      short loc_140064D8D
0x140064d32  mov     rcx, cs:WPP_GLOBAL_Control
0x140064d39  cmp     byte ptr [rcx+29h], 5
0x140064d3d  jnb     short loc_140064D46
0x140064d3f  cmp     [rcx+48h], r15w
0x140064d44  jz      short loc_140064D5F
0x140064d46  mov     rcx, [rcx+40h]
0x140064d4a  mov     r9d, 0BBh
0x140064d50  mov     r8d, ebp
0x140064d53  mov     [rsp+0A8h+var_88], rsi
0x140064d58  mov     dl, 5
0x140064d5a  call    WPP_RECORDER_SF_
0x140064d5f  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140064d66  jz      short loc_140064D8D
0x140064d68  mov     rcx, cs:WPP_GLOBAL_Control
0x140064d6f  mov     r9d, 0BCh
0x140064d75  mov     dword ptr [rsp+0A8h+var_80], r12d
0x140064d7a  mov     r8d, ebp
0x140064d7d  mov     dl, 4
0x140064d7f  mov     [rsp+0A8h+var_88], rsi
0x140064d84  mov     rcx, [rcx+40h]
0x140064d88  call    WPP_RECORDER_SF_D
0x140064d8d  cmp     [rdi+0F8h], r15d
0x140064d94  jnz     short loc_140064DCB
0x140064d96  mov     ebx, r15d
0x140064d99  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140064da0  jz      loc_140065040
0x140064da6  mov     rcx, cs:WPP_GLOBAL_Control
0x140064dad  mov     r9d, 0BDh
0x140064db3  mov     r8d, ebp
0x140064db6  mov     [rsp+0A8h+var_88], rsi
0x140064dbb  mov     dl, 4
0x140064dbd  mov     rcx, [rcx+40h]
0x140064dc1  call    WPP_RECORDER_SF_
0x140064dc6  jmp     loc_140065006
0x140064dcb  mov     rsi, [rdi+20h]
0x140064dcf  mov     rcx, rsi; SpinLock
0x140064dd2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140064dd9  nop     dword ptr [rax+rax+00h]
0x140064dde  lea     rcx, [rdi+130h]; this
0x140064de5  mov     [rsi+10h], bpl
0x140064de9  movzx   edx, r12w; unsigned __int16
0x140064ded  mov     [rsi+8], al
0x140064df0  call    ?GetTxEntry@CTxEntryTable@@QEAAPEAU_WFC_TX_ENTRY@@G@Z; CTxEntryTable::GetTxEntry(ushort)
0x140064df5  mov     r14, rax
0x140064df8  test    rax, rax
0x140064dfb  jnz     short loc_140064E4D
0x140064dfd  mov     ebx, 0C0000001h
0x140064e02  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140064e09  jz      short loc_140064E32
0x140064e0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140064e12  lea     rax, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x140064e19  mov     r9d, 0BEh
0x140064e1f  mov     [rsp+0A8h+var_88], rax
0x140064e24  mov     r8d, ebp
0x140064e27  mov     dl, 2
0x140064e29  mov     rcx, [rcx+40h]
0x140064e2d  call    WPP_RECORDER_SF_
0x140064e32  mov     dl, [rsi+8]; NewIrql
0x140064e35  mov     rcx, rsi; SpinLock
0x140064e38  mov     [rsi+10h], r15b
0x140064e3c  call    cs:__imp_KeReleaseSpinLock
0x140064e43  nop     dword ptr [rax+rax+00h]
0x140064e48  jmp     loc_140064FFF
0x140064e4d  mov     eax, [rax+8]
0x140064e50  mov     r13, r15
0x140064e53  and     eax, 0FFFFFFFDh
0x140064e56  mov     [rsp+0A8h+arg_0], r15
0x140064e5e  or      eax, ebp
0x140064e60  mov     ebp, r15d
0x140064e63  mov     [r14+8], eax
0x140064e67  cmp     dword ptr [rdi+0F8h], 1
0x140064e6e  jnz     short loc_140064E79
0x140064e70  cmp     bpl, 2
0x140064e74  setb    al
0x140064e77  jmp     short loc_140064E80
0x140064e79  cmp     bpl, 18h
0x140064e7d  setbe   al
0x140064e80  test    al, al
0x140064e82  jz      loc_140064FB5
0x140064e88  mov     r8b, bpl; unsigned __int8
0x140064e8b  mov     rdx, r14; struct _WFC_TX_ENTRY *
0x140064e8e  mov     rcx, rdi; this
0x140064e91  call    ?GetTxQueue@CTxMgr@@AEAAPEAU_WFC_TX_QUEUE@@PEAU_WFC_TX_ENTRY@@E@Z; CTxMgr::GetTxQueue(_WFC_TX_ENTRY *,uchar)
0x140064e96  mov     rbx, rax
0x140064e99  test    rax, rax
0x140064e9c  jz      loc_140064FA7
0x140064ea2  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140064ea9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140064eb0  jz      short loc_140064F12
0x140064eb2  movzx   eax, word ptr [rbx+34h]
0x140064eb6  mov     r9d, 0BFh
0x140064ebc  movzx   ecx, word ptr [rbx+32h]
0x140064ec0  movzx   edx, word ptr [rbx+30h]
0x140064ec4  movzx   r8d, byte ptr [rbx+3Ch]
0x140064ec9  movzx   r10d, word ptr [rbx+40h]
0x140064ece  movzx   r11d, word ptr [rbx+3Eh]
0x140064ed3  mov     [rsp+0A8h+var_58], eax
0x140064ed7  lea     rax, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x140064ede  mov     [rsp+0A8h+var_60], ecx
0x140064ee2  mov     rcx, cs:WPP_GLOBAL_Control
0x140064ee9  mov     [rsp+0A8h+var_68], edx
0x140064eed  mov     dl, 4
0x140064eef  mov     [rsp+0A8h+var_70], r8d
0x140064ef4  mov     r8d, 1
0x140064efa  mov     [rsp+0A8h+var_78], r10d
0x140064eff  mov     rcx, [rcx+40h]
0x140064f03  mov     dword ptr [rsp+0A8h+var_80], r11d
0x140064f08  mov     [rsp+0A8h+var_88], rax
0x140064f0d  call    WPP_RECORDER_SF_DDDDDD
0x140064f12  lea     rcx, [rdi+108h]; this
0x140064f19  mov     rdx, rbx; struct _WFC_TX_QUEUE *
0x140064f1c  call    ?RemoveTxQueue@CGlobalTxQueueList@@QEAAHPEAU_WFC_TX_QUEUE@@@Z; CGlobalTxQueueList::RemoveTxQueue(_WFC_TX_QUEUE *)
0x140064f21  test    eax, eax
0x140064f23  jnz     short loc_140064F2C
0x140064f25  movzx   eax, word ptr [rbx+30h]
0x140064f29  sub     [rdi+58h], eax
0x140064f2c  mov     rdx, rbx; struct _WFC_TX_QUEUE *
0x140064f2f  mov     rcx, rdi; this
0x140064f32  call    ?RemoveTxQueueFromAcEntry@CTxMgr@@AEAAHPEAU_WFC_TX_QUEUE@@@Z; CTxMgr::RemoveTxQueueFromAcEntry(_WFC_TX_QUEUE *)
0x140064f37  mov     edx, 0FFFFh
0x140064f3c  mov     rax, [rbx]
0x140064f3f  cmp     rax, rbx
0x140064f42  jz      short loc_140064F8E
0x140064f44  cmp     [rax+8], rbx
0x140064f48  jnz     short loc_140064FAE
0x140064f4a  mov     rcx, [rax]
0x140064f4d  cmp     [rcx+8], rax
0x140064f51  jnz     short loc_140064FAE
0x140064f53  mov     [rbx], rcx
0x140064f56  mov     [rcx+8], rbx
0x140064f5a  mov     rcx, [rax+10h]
0x140064f5e  mov     byte ptr [rax-0Ch], 1
0x140064f62  add     [rbx+30h], dx
0x140064f66  add     [r14+18h], dx
0x140064f6b  cmp     dword ptr [rax-3Ch], 1
0x140064f6f  jnz     short loc_140064F79
0x140064f71  mov     rax, r13
0x140064f74  mov     r13, rcx
0x140064f77  jmp     short loc_140064F89
0x140064f79  mov     rax, [rsp+0A8h+arg_0]
0x140064f81  mov     [rsp+0A8h+arg_0], rcx
0x140064f89  mov     [rcx], rax
0x140064f8c  jmp     short loc_140064F3C
0x140064f8e  mov     rcx, rbx; void *
0x140064f91  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140064f96  mov     rax, [r14+88h]
0x140064f9d  xor     r15d, r15d
0x140064fa0  movsxd  rcx, ebp
0x140064fa3  mov     [rax+rcx*8], r15
0x140064fa7  inc     ebp
0x140064fa9  jmp     loc_140064E67
0x140064fae  mov     ecx, 3
0x140064fb3  int     29h; Win8: RtlFailFast(ecx)
0x140064fb5  movzx   edx, r12w; unsigned __int16
0x140064fb9  lea     rcx, [rdi+130h]; this
0x140064fc0  call    ?RemoveTxEntry@CTxEntryTable@@QEAAHG@Z; CTxEntryTable::RemoveTxEntry(ushort)
0x140064fc5  mov     dl, [rsi+8]; NewIrql
0x140064fc8  mov     rcx, rsi; SpinLock
0x140064fcb  mov     ebx, eax
0x140064fcd  mov     [rsi+10h], r15b
0x140064fd1  call    cs:__imp_KeReleaseSpinLock
0x140064fd8  nop     dword ptr [rax+rax+00h]
0x140064fdd  mov     r8, [rsp+0A8h+arg_0]; struct _NET_BUFFER_LIST *
0x140064fe5  mov     ebp, 1
0x140064fea  mov     r9b, bpl; bool
0x140064fed  mov     rdx, r13; struct _NET_BUFFER_LIST *
0x140064ff0  mov     rcx, rdi; WorkItemContext
0x140064ff3  call    ?CompleteNBLs@CTxMgr@@AEAAXPEAU_NET_BUFFER_LIST@@0_N@Z; CTxMgr::CompleteNBLs(_NET_BUFFER_LIST *,_NET_BUFFER_LIST *,bool)
0x140064ff8  lea     r13, WPP_RECORDER_INITIALIZED
0x140064fff  lea     rsi, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x140065006  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14006500d  jz      short loc_140065040
0x14006500f  mov     rcx, cs:WPP_GLOBAL_Control
0x140065016  cmp     byte ptr [rcx+29h], 5
0x14006501a  jnb     short loc_140065023
0x14006501c  cmp     [rcx+48h], r15w
0x140065021  jz      short loc_140065040
0x140065023  mov     rcx, [rcx+40h]
0x140065027  mov     r9d, 0C0h
0x14006502d  mov     dword ptr [rsp+0A8h+var_80], ebx
0x140065031  mov     r8d, ebp
0x140065034  mov     dl, 5
0x140065036  mov     [rsp+0A8h+var_88], rsi
0x14006503b  call    WPP_RECORDER_SF_D
0x140065040  mov     eax, ebx
0x140065042  add     rsp, 68h
0x140065046  pop     r15
0x140065048  pop     r14
0x14006504a  pop     r13
0x14006504c  pop     r12
0x14006504e  pop     rdi
0x14006504f  pop     rsi
0x140065050  pop     rbp
0x140065051  pop     rbx
0x140065052  retn
```
