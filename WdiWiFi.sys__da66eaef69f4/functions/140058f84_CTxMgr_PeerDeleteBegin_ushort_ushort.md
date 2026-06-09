# CTxMgr::PeerDeleteBegin(ushort,ushort)

- ea: `0x140058f84`
- end: `0x140059315`
- name: `?PeerDeleteBegin@CTxMgr@@QEAAHGG@Z`
- size: `913`
- prototype: `__int64 __fastcall(PVOID WorkItemContext, unsigned __int16, unsigned __int16)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14004dc60`
- `0x140058ab0`

## callees

- `0x1400174e8`
- `0x140023ae0`
- `0x140034e04`
- `0x140034ec4`
- `0x140038df0`
- `0x14003a200`
- `0x14003a4a0`
- `0x14003b620`
- `0x14003b888`
- `0x14003d930`
- `0x140058f84`
- `0x1400596d8`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400590df`
- `ntoskrnl!KeReleaseSpinLock` at `0x140059297`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400590df`
- `ntoskrnl!KeReleaseSpinLock` at `0x140059297`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140059075`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140059075`

## pseudocode

```c
__int64 __fastcall CTxMgr::PeerDeleteBegin(CTxMgr *WorkItemContext, __int16 a2, __int16 a3)
{
  __int16 v5; // bx
  int v6; // ebp
  unsigned int v7; // ebx
  int v8; // edx
  int v9; // eax
  CNdisSpinLock *m_TxMgrLock; // rdi
  int v11; // ebx
  KIRQL v12; // al
  struct _WFC_TX_ENTRY *TxEntry; // rax
  __int16 v14; // dx
  struct _WFC_TX_ENTRY *v15; // r14
  KIRQL v16; // dl
  struct _NET_BUFFER_LIST *v17; // r12
  struct _NET_BUFFER_LIST *v18; // r13
  _WFC_TX_QUEUEING_MODE m_QueueingMode; // ecx
  bool v21; // al
  struct _WFC_TX_QUEUE *ppTxQueue; // rbx
  int BacklogCount; // edx
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *v25; // rcx
  struct _NET_BUFFER_LIST *v26; // rcx
  struct _NET_BUFFER_LIST *v27; // rax
  KIRQL OldIrql; // dl
  __int64 v30; // [rsp+28h] [rbp-80h]

  v5 = a2;
  v6 = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        169,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
    }
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        170,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
        v5,
        a3);
    }
  }
  if ( WorkItemContext->m_QueueingMode == PORT_QUEUEING )
  {
    v7 = 0;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return v7;
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      171,
      (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
  }
  else
  {
    v9 = CTxMgr::StopCancelSend(WorkItemContext, v5, a3, TxStopReasonPeerDelete);
    m_TxMgrLock = WorkItemContext->m_TxMgrLock;
    v11 = v9;
    v12 = KeAcquireSpinLockRaiseToDpc(&m_TxMgrLock->m_SpinLock.SpinLock);
    m_TxMgrLock->m_IsLocked = 1;
    m_TxMgrLock->m_SpinLock.OldIrql = v12;
    TxEntry = CTxEntryTable::GetTxEntry(&WorkItemContext->m_TxEntryTable, a3);
    v15 = TxEntry;
    if ( TxEntry )
    {
      v17 = 0;
      v18 = 0;
      if ( v11 )
        TxEntry->TxEntryState |= 0x10u;
      if ( (TxEntry->TxEntryState & 0x12) == 2 )
      {
        while ( 1 )
        {
          m_QueueingMode = WorkItemContext->m_QueueingMode;
          if ( !(m_QueueingMode == PORT_QUEUEING ? (unsigned __int8)v6 < 2u : (unsigned __int8)v6 <= 0x18u) )
            break;
          if ( m_QueueingMode == PORT_QUEUEING )
            v21 = (unsigned __int8)v6 < 2u;
          else
            v21 = (unsigned __int8)v6 <= 0x18u;
          if ( v21 )
          {
            ppTxQueue = (struct _WFC_TX_QUEUE *)v15->ppTxQueue;
            if ( ppTxQueue )
              ppTxQueue = (struct _WFC_TX_QUEUE *)*((_QWORD *)&ppTxQueue->BacklogQueue.Flink + (unsigned __int8)v6);
            if ( ppTxQueue )
            {
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              {
                BacklogCount = ppTxQueue->BacklogCount;
                LOBYTE(BacklogCount) = 4;
                WPP_RECORDER_SF_DDDDDD(
                  WPP_GLOBAL_Control->DeviceExtension,
                  BacklogCount,
                  1,
                  173,
                  (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
                  ppTxQueue->PortId,
                  ppTxQueue->PeerId,
                  ppTxQueue->Tid,
                  ppTxQueue->BacklogCount,
                  ppTxQueue->TransferPendingCount,
                  ppTxQueue->TxPendingCount);
              }
              if ( !(unsigned int)CGlobalTxQueueList::RemoveTxQueue(&WorkItemContext->m_CGlobalTxQueueList, ppTxQueue) )
                WorkItemContext->m_CurActiveBacklog -= ppTxQueue->BacklogCount;
              CTxMgr::RemoveTxQueueFromAcEntry(WorkItemContext, ppTxQueue);
              while ( 1 )
              {
                Flink = ppTxQueue->BacklogQueue.Flink;
                if ( (struct _WFC_TX_QUEUE *)ppTxQueue->BacklogQueue.Flink == ppTxQueue )
                  break;
                if ( (struct _WFC_TX_QUEUE *)Flink->Blink != ppTxQueue
                  || (v25 = Flink->Flink, Flink->Flink->Blink != Flink) )
                {
                  __fastfail(3u);
                }
                ppTxQueue->BacklogQueue.Flink = v25;
                v25->Blink = &ppTxQueue->BacklogQueue;
                v26 = (struct _NET_BUFFER_LIST *)Flink[1].Flink;
                BYTE4(Flink[-1].Flink) = 1;
                --ppTxQueue->BacklogCount;
                --v15->BacklogCount;
                if ( HIDWORD(Flink[-4].Flink) == 1 )
                {
                  v27 = v17;
                  v17 = v26;
                }
                else
                {
                  v27 = v18;
                  v18 = v26;
                }
                v26->Link.Alignment = (ULONGLONG)v27;
              }
              operator delete(ppTxQueue);
              v15->ppTxQueue[v6] = 0;
            }
          }
          ++v6;
        }
        v7 = CTxEntryTable::RemoveTxEntry(&WorkItemContext->m_TxEntryTable, a3);
      }
      else
      {
        v7 = 259;
      }
      OldIrql = m_TxMgrLock->m_SpinLock.OldIrql;
      m_TxMgrLock->m_IsLocked = 0;
      KeReleaseSpinLock(&m_TxMgrLock->m_SpinLock.SpinLock, OldIrql);
      CTxMgr::CompleteNBLs(WorkItemContext, v17, v18, 1);
    }
    else
    {
      v7 = -1073741823;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v14) = 2;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v14,
          1,
          172,
          (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
      }
      v16 = m_TxMgrLock->m_SpinLock.OldIrql;
      m_TxMgrLock->m_IsLocked = 0;
      KeReleaseSpinLock(&m_TxMgrLock->m_SpinLock.SpinLock, v16);
    }
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v30) = v7;
    LOBYTE(v8) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      1,
      174,
      (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
      v30);
  }
  return v7;
}

```

## disassembly

```asm
0x140058f84  push    rbx
0x140058f86  push    rbp
0x140058f87  push    rsi
0x140058f88  push    rdi
0x140058f89  push    r12
0x140058f8b  push    r13
0x140058f8d  push    r14
0x140058f8f  push    r15
0x140058f91  sub     rsp, 68h
0x140058f95  movzx   r15d, r8w
0x140058f99  mov     rsi, rcx
0x140058f9c  movzx   ebx, dx
0x140058f9f  xor     ebp, ebp; __annotation("TMF:",
0x140058fa1  lea     r13, WPP_RECORDER_INITIALIZED
0x140058fa8  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140058faf  lea     rdi, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x140058fb6  lea     r12d, [rbp+1]
0x140058fba  jz      short loc_14005901A
0x140058fbc  mov     rcx, cs:WPP_GLOBAL_Control
0x140058fc3  cmp     byte ptr [rcx+29h], 5
0x140058fc7  jnb     short loc_140058FCF
0x140058fc9  cmp     [rcx+48h], bp
0x140058fcd  jz      short loc_140058FE8
0x140058fcf  mov     rcx, [rcx+40h]
0x140058fd3  mov     r9d, 0A9h
0x140058fd9  mov     r8d, r12d
0x140058fdc  mov     [rsp+0A8h+var_88], rdi
0x140058fe1  mov     dl, 5
0x140058fe3  call    WPP_RECORDER_SF_
0x140058fe8  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140058fef  jz      short loc_14005901A
0x140058ff1  mov     rcx, cs:WPP_GLOBAL_Control
0x140058ff8  mov     r9d, 0AAh
0x140058ffe  mov     [rsp+0A8h+var_78], r15d
0x140059003  mov     r8d, r12d
0x140059006  mov     dword ptr [rsp+0A8h+var_80], ebx
0x14005900a  mov     dl, 4
0x14005900c  mov     [rsp+0A8h+var_88], rdi
0x140059011  mov     rcx, [rcx+40h]
0x140059015  call    WPP_RECORDER_SF_DD
0x14005901a  cmp     [rsi+0F8h], r12d
0x140059021  jnz     short loc_140059057
0x140059023  mov     ebx, ebp
0x140059025  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14005902c  jz      loc_140059301
0x140059032  mov     rcx, cs:WPP_GLOBAL_Control
0x140059039  mov     r9d, 0ABh
0x14005903f  mov     r8d, r12d
0x140059042  mov     [rsp+0A8h+var_88], rdi
0x140059047  mov     dl, 4
0x140059049  mov     rcx, [rcx+40h]
0x14005904d  call    WPP_RECORDER_SF_
0x140059052  jmp     loc_1400592C8
0x140059057  mov     r9d, 2; enum _WFC_TX_STOP_REASON
0x14005905d  movzx   r8d, r15w; unsigned __int16
0x140059061  movzx   edx, bx; unsigned __int16
0x140059064  mov     rcx, rsi; WorkItemContext
0x140059067  call    ?StopCancelSend@CTxMgr@@QEAAHGGW4_WFC_TX_STOP_REASON@@@Z; CTxMgr::StopCancelSend(ushort,ushort,_WFC_TX_STOP_REASON)
0x14005906c  mov     rdi, [rsi+20h]
0x140059070  mov     ebx, eax
0x140059072  mov     rcx, rdi; SpinLock
0x140059075  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14005907c  nop     dword ptr [rax+rax+00h]
0x140059081  lea     rcx, [rsi+130h]; this
0x140059088  mov     [rdi+10h], r12b
0x14005908c  movzx   edx, r15w; unsigned __int16
0x140059090  mov     [rdi+8], al
0x140059093  call    ?GetTxEntry@CTxEntryTable@@QEAAPEAU_WFC_TX_ENTRY@@G@Z; CTxEntryTable::GetTxEntry(ushort)
0x140059098  mov     r14, rax
0x14005909b  test    rax, rax
0x14005909e  jnz     short loc_1400590F0
0x1400590a0  mov     ebx, 0C0000001h
0x1400590a5  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400590ac  jz      short loc_1400590D5
0x1400590ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400590b5  lea     rax, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x1400590bc  mov     r9d, 0ACh
0x1400590c2  mov     [rsp+0A8h+var_88], rax
0x1400590c7  mov     r8d, r12d
0x1400590ca  mov     dl, 2
0x1400590cc  mov     rcx, [rcx+40h]
0x1400590d0  call    WPP_RECORDER_SF_
0x1400590d5  mov     dl, [rdi+8]; NewIrql
0x1400590d8  mov     rcx, rdi; SpinLock
0x1400590db  mov     [rdi+10h], bpl
0x1400590df  call    cs:__imp_KeReleaseSpinLock
0x1400590e6  nop     dword ptr [rax+rax+00h]
0x1400590eb  jmp     loc_1400592C1
0x1400590f0  mov     r12, rbp
0x1400590f3  mov     r13, rbp
0x1400590f6  test    ebx, ebx
0x1400590f8  jz      short loc_1400590FE
0x1400590fa  or      dword ptr [rax+8], 10h
0x1400590fe  mov     eax, [rax+8]
0x140059101  and     al, 12h
0x140059103  cmp     al, 2
0x140059105  jnz     loc_140059288
0x14005910b  mov     ecx, [rsi+0F8h]
0x140059111  cmp     ecx, 1
0x140059114  jnz     short loc_14005911F
0x140059116  cmp     bpl, 2
0x14005911a  setb    al
0x14005911d  jmp     short loc_140059126
0x14005911f  cmp     bpl, 18h
0x140059123  setbe   al
0x140059126  test    al, al
0x140059128  jz      loc_140059272
0x14005912e  cmp     ecx, 1
0x140059131  jnz     short loc_14005913C
0x140059133  cmp     bpl, 2
0x140059137  setb    al
0x14005913a  jmp     short loc_140059143
0x14005913c  cmp     bpl, 18h
0x140059140  setbe   al
0x140059143  test    al, al
0x140059145  jz      loc_140059264
0x14005914b  mov     rbx, [r14+88h]
0x140059152  test    rbx, rbx
0x140059155  jz      short loc_14005915F
0x140059157  movzx   eax, bpl
0x14005915b  mov     rbx, [rbx+rax*8]
0x14005915f  test    rbx, rbx
0x140059162  jz      loc_140059264
0x140059168  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14005916f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140059176  jz      short loc_1400591D8
0x140059178  movzx   eax, word ptr [rbx+34h]
0x14005917c  mov     r9d, 0ADh
0x140059182  movzx   ecx, word ptr [rbx+32h]
0x140059186  movzx   edx, word ptr [rbx+30h]
0x14005918a  movzx   r8d, byte ptr [rbx+3Ch]
0x14005918f  movzx   r10d, word ptr [rbx+40h]
0x140059194  movzx   r11d, word ptr [rbx+3Eh]
0x140059199  mov     [rsp+0A8h+var_58], eax
0x14005919d  lea     rax, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x1400591a4  mov     [rsp+0A8h+var_60], ecx
0x1400591a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400591af  mov     [rsp+0A8h+var_68], edx
0x1400591b3  mov     dl, 4
0x1400591b5  mov     [rsp+0A8h+var_70], r8d
0x1400591ba  mov     r8d, 1
0x1400591c0  mov     [rsp+0A8h+var_78], r10d
0x1400591c5  mov     rcx, [rcx+40h]
0x1400591c9  mov     dword ptr [rsp+0A8h+var_80], r11d
0x1400591ce  mov     [rsp+0A8h+var_88], rax
0x1400591d3  call    WPP_RECORDER_SF_DDDDDD
0x1400591d8  lea     rcx, [rsi+108h]; this
0x1400591df  mov     rdx, rbx; struct _WFC_TX_QUEUE *
0x1400591e2  call    ?RemoveTxQueue@CGlobalTxQueueList@@QEAAHPEAU_WFC_TX_QUEUE@@@Z; CGlobalTxQueueList::RemoveTxQueue(_WFC_TX_QUEUE *)
0x1400591e7  test    eax, eax
0x1400591e9  jnz     short loc_1400591F2
0x1400591eb  movzx   eax, word ptr [rbx+30h]
0x1400591ef  sub     [rsi+58h], eax
0x1400591f2  mov     rdx, rbx; struct _WFC_TX_QUEUE *
0x1400591f5  mov     rcx, rsi; this
0x1400591f8  call    ?RemoveTxQueueFromAcEntry@CTxMgr@@AEAAHPEAU_WFC_TX_QUEUE@@@Z; CTxMgr::RemoveTxQueueFromAcEntry(_WFC_TX_QUEUE *)
0x1400591fd  mov     edx, 0FFFFh
0x140059202  mov     rax, [rbx]
0x140059205  cmp     rax, rbx
0x140059208  jz      short loc_14005924A
0x14005920a  cmp     [rax+8], rbx
0x14005920e  jnz     short loc_14005926B
0x140059210  mov     rcx, [rax]
0x140059213  cmp     [rcx+8], rax
0x140059217  jnz     short loc_14005926B
0x140059219  mov     [rbx], rcx
0x14005921c  mov     [rcx+8], rbx
0x140059220  mov     rcx, [rax+10h]
0x140059224  mov     byte ptr [rax-0Ch], 1
0x140059228  add     [rbx+30h], dx
0x14005922c  add     [r14+18h], dx
0x140059231  cmp     dword ptr [rax-3Ch], 1
0x140059235  jnz     short loc_14005923F
0x140059237  mov     rax, r12
0x14005923a  mov     r12, rcx
0x14005923d  jmp     short loc_140059245
0x14005923f  mov     rax, r13
0x140059242  mov     r13, rcx
0x140059245  mov     [rcx], rax
0x140059248  jmp     short loc_140059202
0x14005924a  mov     rcx, rbx; void *
0x14005924d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140059252  mov     rax, [r14+88h]
0x140059259  movsxd  rcx, ebp
0x14005925c  mov     qword ptr [rax+rcx*8], 0
0x140059264  inc     ebp
0x140059266  jmp     loc_14005910B
0x14005926b  mov     ecx, 3
0x140059270  int     29h; Win8: RtlFailFast(ecx)
0x140059272  movzx   edx, r15w; unsigned __int16
0x140059276  lea     rcx, [rsi+130h]; this
0x14005927d  call    ?RemoveTxEntry@CTxEntryTable@@QEAAHG@Z; CTxEntryTable::RemoveTxEntry(ushort)
0x140059282  mov     ebx, eax
0x140059284  xor     ebp, ebp
0x140059286  jmp     short loc_14005928D
0x140059288  mov     ebx, 103h
0x14005928d  mov     dl, [rdi+8]; NewIrql
0x140059290  mov     rcx, rdi; SpinLock
0x140059293  mov     [rdi+10h], bpl
0x140059297  call    cs:__imp_KeReleaseSpinLock
0x14005929e  nop     dword ptr [rax+rax+00h]
0x1400592a3  mov     r9b, 1; bool
0x1400592a6  mov     r8, r13; struct _NET_BUFFER_LIST *
0x1400592a9  mov     rdx, r12; struct _NET_BUFFER_LIST *
0x1400592ac  mov     rcx, rsi; WorkItemContext
0x1400592af  call    ?CompleteNBLs@CTxMgr@@AEAAXPEAU_NET_BUFFER_LIST@@0_N@Z; CTxMgr::CompleteNBLs(_NET_BUFFER_LIST *,_NET_BUFFER_LIST *,bool)
0x1400592b4  mov     r12d, 1
0x1400592ba  lea     r13, WPP_RECORDER_INITIALIZED
0x1400592c1  lea     rdi, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x1400592c8  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400592cf  jz      short loc_140059301
0x1400592d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400592d8  cmp     byte ptr [rcx+29h], 5
0x1400592dc  jnb     short loc_1400592E4
0x1400592de  cmp     [rcx+48h], bp
0x1400592e2  jz      short loc_140059301
0x1400592e4  mov     rcx, [rcx+40h]
0x1400592e8  mov     r9d, 0AEh
0x1400592ee  mov     dword ptr [rsp+0A8h+var_80], ebx
0x1400592f2  mov     r8d, r12d
0x1400592f5  mov     dl, 5
0x1400592f7  mov     [rsp+0A8h+var_88], rdi
0x1400592fc  call    WPP_RECORDER_SF_D
0x140059301  mov     eax, ebx
0x140059303  add     rsp, 68h
0x140059307  pop     r15
0x140059309  pop     r14
0x14005930b  pop     r13
0x14005930d  pop     r12
0x14005930f  pop     rdi
0x140059310  pop     rsi
0x140059311  pop     rbp
0x140059312  pop     rbx
0x140059313  retn
```
