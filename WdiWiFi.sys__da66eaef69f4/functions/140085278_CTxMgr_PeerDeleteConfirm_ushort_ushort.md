# CTxMgr::PeerDeleteConfirm(ushort,ushort)

- ea: `0x140085278`
- end: `0x140085655`
- name: `?PeerDeleteConfirm@CTxMgr@@AEAAHGG@Z`
- size: `989`
- prototype: `__int64 __fastcall(PVOID WorkItemContext, unsigned __int16, unsigned __int16)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1400376d0`
- `0x14003a630`
- `0x14008570c`

## callees

- `0x1400174e8`
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
- `0x140085278`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400853cb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140085570`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400853cb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140085570`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140085367`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140085367`

## pseudocode

```c
__int64 __fastcall CTxMgr::PeerDeleteConfirm(CTxMgr *WorkItemContext, unsigned __int16 a2, unsigned __int16 a3)
{
  int v3; // ebp
  unsigned int v5; // ebx
  int v7; // edx
  CNdisSpinLock *m_TxMgrLock; // rsi
  KIRQL v9; // al
  struct _WFC_TX_ENTRY *TxEntry; // rax
  __int16 v11; // dx
  struct _WFC_TX_ENTRY *v12; // r15
  KIRQL v13; // dl
  struct _NET_BUFFER_LIST *v14; // r13
  struct _NET_BUFFER_LIST *v15; // r14
  struct _WFC_TX_QUEUE *TxQueue; // rbx
  int BacklogCount; // edx
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *v20; // rcx
  struct _NET_BUFFER_LIST *v21; // rcx
  struct _NET_BUFFER_LIST *v22; // rax
  KIRQL OldIrql; // dl
  char v25[8]; // [rsp+28h] [rbp-70h]
  char v26; // [rsp+28h] [rbp-70h]
  struct _NET_BUFFER_LIST *v27; // [rsp+A0h] [rbp+8h]
  unsigned __int16 v28; // [rsp+A8h] [rbp+10h]

  v28 = a2;
  v3 = 0;
  v5 = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        175,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
      a2 = v28;
    }
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v26 = a2;
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        176,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
        v26,
        a3);
    }
  }
  if ( WorkItemContext->m_QueueingMode == PORT_QUEUEING )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return v5;
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      177,
      (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
  }
  else
  {
    m_TxMgrLock = WorkItemContext->m_TxMgrLock;
    v9 = KeAcquireSpinLockRaiseToDpc(&m_TxMgrLock->m_SpinLock.SpinLock);
    m_TxMgrLock->m_IsLocked = 1;
    m_TxMgrLock->m_SpinLock.OldIrql = v9;
    TxEntry = CTxEntryTable::GetTxEntry(&WorkItemContext->m_TxEntryTable, a3);
    v12 = TxEntry;
    if ( TxEntry )
    {
      v14 = 0;
      v27 = 0;
      v15 = 0;
      if ( (TxEntry->TxEntryState & 0x32) == 0x22 )
      {
        while ( WorkItemContext->m_QueueingMode == PORT_QUEUEING
              ? (unsigned __int8)v3 < 2u
              : (unsigned __int8)v3 <= 0x18u )
        {
          TxQueue = CTxMgr::GetTxQueue(WorkItemContext, v12, v3);
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
                179,
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
              if ( (struct _WFC_TX_QUEUE *)Flink->Blink != TxQueue || (v20 = Flink->Flink, Flink->Flink->Blink != Flink) )
                __fastfail(3u);
              TxQueue->BacklogQueue.Flink = v20;
              v20->Blink = &TxQueue->BacklogQueue;
              v21 = (struct _NET_BUFFER_LIST *)Flink[1].Flink;
              BYTE4(Flink[-1].Flink) = 1;
              --TxQueue->BacklogCount;
              --v12->BacklogCount;
              if ( HIDWORD(Flink[-4].Flink) == 1 )
              {
                v22 = v14;
                v14 = v21;
              }
              else
              {
                v22 = v27;
                v27 = v21;
              }
              v21->Link.Alignment = (ULONGLONG)v22;
            }
            operator delete(TxQueue);
            v12->ppTxQueue[v3] = 0;
          }
          ++v3;
        }
        LOBYTE(v3) = 1;
        v15 = v27;
        v5 = CTxEntryTable::RemoveTxEntry(&WorkItemContext->m_TxEntryTable, a3);
      }
      OldIrql = m_TxMgrLock->m_SpinLock.OldIrql;
      m_TxMgrLock->m_IsLocked = 0;
      KeReleaseSpinLock(&m_TxMgrLock->m_SpinLock.SpinLock, OldIrql);
      CTxMgr::CompleteNBLs(WorkItemContext, v14, v15, 1);
      if ( (_BYTE)v3 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v7) = 4;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            (_WORD)v7,
            1,
            180,
            (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
        }
        ((void (__fastcall *)(void *, _QWORD, _QWORD))WorkItemContext->m_pAdapter->m_MiniportDataHandlers.TalTxRxPeerDeleteConfirmHandler)(
          WorkItemContext->m_pAdapter->m_MiniportTalTxRxContext,
          v28,
          a3);
      }
    }
    else
    {
      v5 = -1073741823;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = 2;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          1,
          178,
          (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
      }
      v13 = m_TxMgrLock->m_SpinLock.OldIrql;
      m_TxMgrLock->m_IsLocked = 0;
      KeReleaseSpinLock(&m_TxMgrLock->m_SpinLock.SpinLock, v13);
    }
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    *(_DWORD *)v25 = v5;
    LOBYTE(v7) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      1,
      181,
      (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
      *(_QWORD *)v25);
  }
  return v5;
}

```

## disassembly

```asm
0x140085278  mov     [rsp+arg_10], rbx
0x14008527d  mov     [rsp+arg_8], dx
0x140085282  push    rbp
0x140085283  push    rsi
0x140085284  push    rdi
0x140085285  push    r12
0x140085287  push    r13
0x140085289  push    r14
0x14008528b  push    r15
0x14008528d  sub     rsp, 60h
0x140085291  xor     ebp, ebp
0x140085293  movzx   r12d, r8w
0x140085297  mov     ebx, ebp
0x140085299  mov     rdi, rcx
0x14008529c  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400852a3  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400852aa  lea     r13, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x1400852b1  jz      short loc_140085322
0x1400852b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400852ba  cmp     byte ptr [rcx+29h], 5
0x1400852be  jnb     short loc_1400852C6
0x1400852c0  cmp     [rcx+48h], bp
0x1400852c4  jz      short loc_1400852EA
0x1400852c6  mov     rcx, [rcx+40h]
0x1400852ca  mov     r9d, 0AFh
0x1400852d0  mov     r8d, 1
0x1400852d6  mov     [rsp+98h+var_78], r13
0x1400852db  mov     dl, 5
0x1400852dd  call    WPP_RECORDER_SF_
0x1400852e2  movzx   edx, [rsp+98h+arg_8]
0x1400852ea  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400852f1  jz      short loc_140085322
0x1400852f3  movzx   ecx, dx
0x1400852f6  mov     r9d, 0B0h
0x1400852fc  mov     [rsp+98h+var_68], r12d
0x140085301  mov     r8d, 1
0x140085307  mov     dword ptr [rsp+98h+var_70], ecx
0x14008530b  mov     dl, 4
0x14008530d  mov     rcx, cs:WPP_GLOBAL_Control
0x140085314  mov     [rsp+98h+var_78], r13
0x140085319  mov     rcx, [rcx+40h]
0x14008531d  call    WPP_RECORDER_SF_DD
0x140085322  cmp     dword ptr [rdi+0F8h], 1
0x140085329  jnz     short loc_140085360
0x14008532b  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140085332  jz      loc_14008563A
0x140085338  mov     rcx, cs:WPP_GLOBAL_Control
0x14008533f  mov     r9d, 0B1h
0x140085345  mov     r8d, 1
0x14008534b  mov     [rsp+98h+var_78], r13
0x140085350  mov     dl, 4
0x140085352  mov     rcx, [rcx+40h]
0x140085356  call    WPP_RECORDER_SF_
0x14008535b  jmp     loc_1400855FE
0x140085360  mov     rsi, [rdi+20h]
0x140085364  mov     rcx, rsi; SpinLock
0x140085367  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14008536e  nop     dword ptr [rax+rax+00h]
0x140085373  lea     rcx, [rdi+130h]; this
0x14008537a  mov     byte ptr [rsi+10h], 1
0x14008537e  movzx   edx, r12w; unsigned __int16
0x140085382  mov     [rsi+8], al
0x140085385  call    ?GetTxEntry@CTxEntryTable@@QEAAPEAU_WFC_TX_ENTRY@@G@Z; CTxEntryTable::GetTxEntry(ushort)
0x14008538a  mov     r15, rax
0x14008538d  test    rax, rax
0x140085390  jnz     short loc_1400853DC
0x140085392  mov     ebx, 0C0000001h
0x140085397  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14008539e  jz      short loc_1400853C1
0x1400853a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400853a7  lea     r8d, [rax+1]
0x1400853ab  mov     r9d, 0B2h
0x1400853b1  mov     [rsp+98h+var_78], r13
0x1400853b6  mov     dl, 2
0x1400853b8  mov     rcx, [rcx+40h]
0x1400853bc  call    WPP_RECORDER_SF_
0x1400853c1  mov     dl, [rsi+8]; NewIrql
0x1400853c4  mov     rcx, rsi; SpinLock
0x1400853c7  mov     [rsi+10h], bpl
0x1400853cb  call    cs:__imp_KeReleaseSpinLock
0x1400853d2  nop     dword ptr [rax+rax+00h]
0x1400853d7  jmp     loc_1400855FE
0x1400853dc  mov     eax, [rax+8]
0x1400853df  mov     r13, rbp
0x1400853e2  and     eax, 32h
0x1400853e5  mov     [rsp+98h+arg_0], rbp
0x1400853ed  mov     r14, rbp
0x1400853f0  cmp     al, 22h ; '"'
0x1400853f2  jnz     loc_140085566
0x1400853f8  cmp     dword ptr [rdi+0F8h], 1
0x1400853ff  jnz     short loc_14008540A
0x140085401  cmp     bpl, 2
0x140085405  setb    al
0x140085408  jmp     short loc_140085411
0x14008540a  cmp     bpl, 18h
0x14008540e  setbe   al
0x140085411  test    al, al
0x140085413  jz      loc_140085549
0x140085419  mov     r8b, bpl; unsigned __int8
0x14008541c  mov     rdx, r15; struct _WFC_TX_ENTRY *
0x14008541f  mov     rcx, rdi; this
0x140085422  call    ?GetTxQueue@CTxMgr@@AEAAPEAU_WFC_TX_QUEUE@@PEAU_WFC_TX_ENTRY@@E@Z; CTxMgr::GetTxQueue(_WFC_TX_ENTRY *,uchar)
0x140085427  mov     rbx, rax
0x14008542a  test    rax, rax
0x14008542d  jz      loc_14008553B
0x140085433  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008543a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140085441  jz      short loc_1400854A3
0x140085443  movzx   eax, word ptr [rbx+34h]
0x140085447  mov     r9d, 0B3h
0x14008544d  movzx   ecx, word ptr [rbx+32h]
0x140085451  movzx   edx, word ptr [rbx+30h]
0x140085455  movzx   r8d, byte ptr [rbx+3Ch]
0x14008545a  movzx   r10d, word ptr [rbx+40h]
0x14008545f  movzx   r11d, word ptr [rbx+3Eh]
0x140085464  mov     [rsp+98h+var_48], eax
0x140085468  lea     rax, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x14008546f  mov     [rsp+98h+var_50], ecx
0x140085473  mov     rcx, cs:WPP_GLOBAL_Control
0x14008547a  mov     [rsp+98h+var_58], edx
0x14008547e  mov     dl, 4
0x140085480  mov     [rsp+98h+var_60], r8d
0x140085485  mov     r8d, 1
0x14008548b  mov     [rsp+98h+var_68], r10d
0x140085490  mov     rcx, [rcx+40h]
0x140085494  mov     dword ptr [rsp+98h+var_70], r11d
0x140085499  mov     [rsp+98h+var_78], rax
0x14008549e  call    WPP_RECORDER_SF_DDDDDD
0x1400854a3  lea     rcx, [rdi+108h]; this
0x1400854aa  mov     rdx, rbx; struct _WFC_TX_QUEUE *
0x1400854ad  call    ?RemoveTxQueue@CGlobalTxQueueList@@QEAAHPEAU_WFC_TX_QUEUE@@@Z; CGlobalTxQueueList::RemoveTxQueue(_WFC_TX_QUEUE *)
0x1400854b2  test    eax, eax
0x1400854b4  jnz     short loc_1400854BD
0x1400854b6  movzx   eax, word ptr [rbx+30h]
0x1400854ba  sub     [rdi+58h], eax
0x1400854bd  mov     rdx, rbx; struct _WFC_TX_QUEUE *
0x1400854c0  mov     rcx, rdi; this
0x1400854c3  call    ?RemoveTxQueueFromAcEntry@CTxMgr@@AEAAHPEAU_WFC_TX_QUEUE@@@Z; CTxMgr::RemoveTxQueueFromAcEntry(_WFC_TX_QUEUE *)
0x1400854c8  mov     r14d, 0FFFFh
0x1400854ce  mov     rax, [rbx]
0x1400854d1  cmp     rax, rbx
0x1400854d4  jz      short loc_140085521
0x1400854d6  cmp     [rax+8], rbx
0x1400854da  jnz     short loc_140085542
0x1400854dc  mov     rcx, [rax]
0x1400854df  cmp     [rcx+8], rax
0x1400854e3  jnz     short loc_140085542
0x1400854e5  mov     [rbx], rcx
0x1400854e8  mov     [rcx+8], rbx
0x1400854ec  mov     rcx, [rax+10h]
0x1400854f0  mov     byte ptr [rax-0Ch], 1
0x1400854f4  add     [rbx+30h], r14w
0x1400854f9  add     [r15+18h], r14w
0x1400854fe  cmp     dword ptr [rax-3Ch], 1
0x140085502  jnz     short loc_14008550C
0x140085504  mov     rax, r13
0x140085507  mov     r13, rcx
0x14008550a  jmp     short loc_14008551C
0x14008550c  mov     rax, [rsp+98h+arg_0]
0x140085514  mov     [rsp+98h+arg_0], rcx
0x14008551c  mov     [rcx], rax
0x14008551f  jmp     short loc_1400854CE
0x140085521  mov     rcx, rbx; void *
0x140085524  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140085529  mov     rax, [r15+88h]
0x140085530  movsxd  rcx, ebp
0x140085533  mov     qword ptr [rax+rcx*8], 0
0x14008553b  inc     ebp
0x14008553d  jmp     loc_1400853F8
0x140085542  mov     ecx, 3
0x140085547  int     29h; Win8: RtlFailFast(ecx)
0x140085549  movzx   edx, r12w; unsigned __int16
0x14008554d  lea     rcx, [rdi+130h]; this
0x140085554  mov     bpl, 1
0x140085557  call    ?RemoveTxEntry@CTxEntryTable@@QEAAHG@Z; CTxEntryTable::RemoveTxEntry(ushort)
0x14008555c  mov     r14, [rsp+98h+arg_0]
0x140085564  mov     ebx, eax
0x140085566  mov     dl, [rsi+8]; NewIrql
0x140085569  mov     rcx, rsi; SpinLock
0x14008556c  mov     byte ptr [rsi+10h], 0
0x140085570  call    cs:__imp_KeReleaseSpinLock
0x140085577  nop     dword ptr [rax+rax+00h]
0x14008557c  mov     r9b, 1; bool
0x14008557f  mov     r8, r14; struct _NET_BUFFER_LIST *
0x140085582  mov     rdx, r13; struct _NET_BUFFER_LIST *
0x140085585  mov     rcx, rdi; WorkItemContext
0x140085588  call    ?CompleteNBLs@CTxMgr@@AEAAXPEAU_NET_BUFFER_LIST@@0_N@Z; CTxMgr::CompleteNBLs(_NET_BUFFER_LIST *,_NET_BUFFER_LIST *,bool)
0x14008558d  test    bpl, bpl
0x140085590  jz      short loc_1400855EE
0x140085592  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140085599  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400855a0  lea     r13, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x1400855a7  jz      short loc_1400855CC
0x1400855a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400855b0  mov     r9d, 0B4h
0x1400855b6  mov     r8d, 1
0x1400855bc  mov     [rsp+98h+var_78], r13
0x1400855c1  mov     dl, 4
0x1400855c3  mov     rcx, [rcx+40h]
0x1400855c7  call    WPP_RECORDER_SF_
0x1400855cc  mov     rcx, [rdi+10h]
0x1400855d0  movzx   r8d, r12w
0x1400855d4  movzx   edx, [rsp+98h+arg_8]
0x1400855dc  mov     rax, [rcx+3EFCh]
0x1400855e3  mov     rcx, [rcx+70h]
0x1400855e7  call    _guard_dispatch_icall
0x1400855ec  jmp     short loc_1400855FC
0x1400855ee  lea     r14, WPP_RECORDER_INITIALIZED
0x1400855f5  lea     r13, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x1400855fc  xor     ebp, ebp
0x1400855fe  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140085605  jz      short loc_14008563A
0x140085607  mov     rcx, cs:WPP_GLOBAL_Control
0x14008560e  cmp     byte ptr [rcx+29h], 5
0x140085612  jnb     short loc_14008561A
0x140085614  cmp     [rcx+48h], bp
0x140085618  jz      short loc_14008563A
0x14008561a  mov     rcx, [rcx+40h]
0x14008561e  mov     r9d, 0B5h
0x140085624  mov     dword ptr [rsp+98h+var_70], ebx
0x140085628  mov     r8d, 1
0x14008562e  mov     dl, 5
0x140085630  mov     [rsp+98h+var_78], r13
0x140085635  call    WPP_RECORDER_SF_D
0x14008563a  mov     eax, ebx
0x14008563c  mov     rbx, [rsp+98h+arg_10]
0x140085644  add     rsp, 60h
0x140085648  pop     r15
0x14008564a  pop     r14
0x14008564c  pop     r13
0x14008564e  pop     r12
0x140085650  pop     rdi
0x140085651  pop     rsi
0x140085652  pop     rbp
0x140085653  retn
```
