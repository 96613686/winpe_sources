# CTxMgr::CompleteQueuedSuspectFrames(ushort,_NET_BUFFER_LIST * *)

- ea: `0x14009cfa4`
- end: `0x14009d3ad`
- name: `?CompleteQueuedSuspectFrames@CTxMgr@@AEAAXGPEAPEAU_NET_BUFFER_LIST@@@Z`
- size: `1033`
- prototype: `void __fastcall(PVOID WorkItemContext, unsigned __int16, struct _NET_BUFFER_LIST **)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14002b6d8`

## callees

- `0x140034e04`
- `0x140034ec4`
- `0x140038df0`
- `0x14003a200`
- `0x14003a4a0`
- `0x14003b620`
- `0x14003d8f0`
- `0x14004c4f4`
- `0x14004efd4`
- `0x14009cfa4`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14009d0b4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14009d2aa`
- `ntoskrnl!KeReleaseSpinLock` at `0x14009d0b4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14009d2aa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14009d055`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14009d055`

## pseudocode

```c
void __fastcall CTxMgr::CompleteQueuedSuspectFrames(
        CTxMgr *WorkItemContext,
        unsigned __int16 a2,
        struct _NET_BUFFER_LIST **a3)
{
  char v3; // r12
  unsigned int v4; // ebx
  unsigned __int16 v5; // r14
  struct _NET_BUFFER_LIST *v6; // rdi
  struct _NET_BUFFER_LIST *v7; // rbp
  __int64 *v9; // rdx
  int v10; // r13d
  struct _NET_BUFFER_LIST *v11; // r14
  CNdisSpinLock *m_TxMgrLock; // rbx
  int v13; // edx
  int v14; // r8d
  PVOID **v15; // rdi
  int v16; // r9d
  KIRQL OldIrql; // dl
  __int64 v18; // rdx
  struct _WFC_TX_ENTRY *TxEntry; // rax
  int v20; // edx
  struct _WFC_TX_ENTRY *v21; // r15
  int v22; // r9d
  unsigned __int8 v23; // r8
  struct _WFC_TX_QUEUE *TxQueue; // rax
  struct _WFC_TX_QUEUE *v25; // rbp
  PVOID *v26; // rcx
  PVOID *v27; // rax
  bool v28; // r8
  unsigned __int16 PortId; // bp
  unsigned __int16 PeerId; // r15
  ULONGLONG v31; // rax
  KIRQL v32; // dl
  int v33; // edx
  int v34; // edx
  __int64 v35; // [rsp+28h] [rbp-60h]
  __int64 v36; // [rsp+28h] [rbp-60h]
  unsigned __int16 v37; // [rsp+30h] [rbp-58h]
  unsigned int v38; // [rsp+34h] [rbp-54h]
  struct _NET_BUFFER_LIST *v39; // [rsp+38h] [rbp-50h]
  struct _NET_BUFFER_LIST *v40; // [rsp+40h] [rbp-48h]
  struct _NET_BUFFER_LIST **v41; // [rsp+A0h] [rbp+18h]

  v41 = a3;
  v3 = 0;
  v4 = a2;
  v5 = 0;
  v37 = 0;
  v6 = 0;
  v39 = 0;
  v7 = 0;
  v40 = 0;
  v9 = WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v9) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v9,
      1,
      393,
      (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
    a3 = v41;
  }
  v38 = v4;
  v10 = 0;
  if ( v4 )
  {
    while ( 1 )
    {
      v11 = a3[v10];
      if ( v11 )
        break;
LABEL_46:
      if ( ++v10 >= v38 )
      {
        v7 = v40;
        v5 = v37;
        goto LABEL_48;
      }
    }
    m_TxMgrLock = WorkItemContext->m_TxMgrLock;
    m_TxMgrLock->m_SpinLock.OldIrql = KeAcquireSpinLockRaiseToDpc(&m_TxMgrLock->m_SpinLock.SpinLock);
    m_TxMgrLock->m_IsLocked = 1;
    v15 = (PVOID **)v11->MiniportReserved[0];
    if ( !v15 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v16 = 394;
LABEL_10:
        LOBYTE(v13) = 4;
        WPP_RECORDER_SF_q(
          WPP_GLOBAL_Control->DeviceExtension,
          v13,
          v14,
          v16,
          (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
          (char)v11);
      }
LABEL_11:
      OldIrql = m_TxMgrLock->m_SpinLock.OldIrql;
      m_TxMgrLock->m_IsLocked = 0;
      KeReleaseSpinLock(&m_TxMgrLock->m_SpinLock.SpinLock, OldIrql);
      v6 = v39;
LABEL_45:
      a3 = v41;
      goto LABEL_46;
    }
    if ( *((_BYTE *)v15 - 12) == 1 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_11;
      v16 = 395;
      goto LABEL_10;
    }
    v18 = 32;
    if ( WorkItemContext->m_QueueingMode != PORT_QUEUEING )
      v18 = 34;
    TxEntry = CTxEntryTable::GetTxEntry(&WorkItemContext->m_TxEntryTable, *(_WORD *)((char *)v15 + v18));
    v21 = TxEntry;
    if ( TxEntry )
    {
      v23 = *((_BYTE *)v15 + 36);
      if ( WorkItemContext->m_QueueingMode == PORT_QUEUEING )
        v23 = v23 > 0x10u;
      TxQueue = CTxMgr::GetTxQueue(WorkItemContext, TxEntry, v23);
      v25 = TxQueue;
      if ( TxQueue )
      {
        if ( TxQueue->BacklogCount )
        {
          v26 = *v15;
          if ( (*v15)[1] != v15 || (v27 = v15[1], *v27 != v15) )
            __fastfail(3u);
          *v27 = v26;
          v26[1] = v27;
          ++v37;
          *((_BYTE *)v15 - 12) = 1;
          --v25->BacklogCount;
          --v21->BacklogCount;
          if ( v25->GlobalTxQueueListEntry.Flink != &v25->GlobalTxQueueListEntry )
            --WorkItemContext->m_CurActiveBacklog;
          v28 = 0;
          if ( v25->BacklogCount )
          {
            PortId = -1;
            PeerId = -1;
          }
          else
          {
            CGlobalTxQueueList::RemoveTxQueue(&WorkItemContext->m_CGlobalTxQueueList, v25);
            CTxMgr::RemoveTxQueueFromAcEntry(WorkItemContext, v25);
            v28 = 0;
            if ( v21->BacklogCount || !CTxMgr::IsPeerPaused(WorkItemContext, v21) )
            {
              PortId = -1;
              PeerId = -1;
            }
            else
            {
              PortId = v21->PortId;
              v3 = 1;
              PeerId = v21->PeerId;
            }
          }
          if ( *((_DWORD *)v15 - 15) == 1 )
          {
            v31 = (ULONGLONG)v40;
            v6 = v39;
            v40 = v11;
          }
          else
          {
            v31 = (ULONGLONG)v39;
            v6 = v11;
            v39 = v11;
          }
          v11->Link.Alignment = v31;
          v32 = m_TxMgrLock->m_SpinLock.OldIrql;
          m_TxMgrLock->m_IsLocked = v28;
          KeReleaseSpinLock(&m_TxMgrLock->m_SpinLock.SpinLock, v32);
          if ( v3 )
            ((void (__fastcall *)(void *, _QWORD, _QWORD, _QWORD))WorkItemContext->m_pAdapter->m_MiniportDataHandlers.TxPeerBacklogHandler)(
              WorkItemContext->m_pAdapter->m_MiniportTalTxRxContext,
              PortId,
              PeerId,
              0);
          v3 = 0;
          goto LABEL_45;
        }
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_11;
        v22 = 398;
      }
      else
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_11;
        v22 = 397;
      }
    }
    else
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_11;
      v22 = 396;
    }
    LOBYTE(v20) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v20,
      1,
      v22,
      (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
    goto LABEL_11;
  }
LABEL_48:
  CTxMgr::CompleteNBLs(WorkItemContext, v7, v6, 0);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v35) = v5;
    LOBYTE(v33) = 4;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v33,
      1,
      399,
      (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
      v35);
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LODWORD(v36) = 0;
      LOBYTE(v34) = 5;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v34,
        1,
        400,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
        v36);
    }
  }
}

```

## disassembly

```asm
0x14009cfa4  mov     [rsp+arg_0], rbx
0x14009cfa9  mov     [rsp+arg_10], r8
0x14009cfae  push    rbp
0x14009cfaf  push    rsi
0x14009cfb0  push    rdi
0x14009cfb1  push    r12
0x14009cfb3  push    r13
0x14009cfb5  push    r14
0x14009cfb7  push    r15
0x14009cfb9  sub     rsp, 50h
0x14009cfbd  xor     r12d, r12d
0x14009cfc0  movzx   ebx, dx
0x14009cfc3  mov     r14d, r12d
0x14009cfc6  mov     [rsp+88h+var_58], r12d
0x14009cfcb  mov     edi, r12d
0x14009cfce  mov     [rsp+88h+var_50], r12
0x14009cfd3  mov     ebp, r12d
0x14009cfd6  mov     [rsp+88h+var_48], r12
0x14009cfdb  mov     rsi, rcx
0x14009cfde  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14009cfe5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14009cfec  lea     rdx, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x14009cff3  lea     r15d, [r12+1]
0x14009cff8  jz      short loc_14009D02F
0x14009cffa  mov     rcx, cs:WPP_GLOBAL_Control
0x14009d001  cmp     byte ptr [rcx+29h], 5
0x14009d005  jnb     short loc_14009D00E
0x14009d007  cmp     [rcx+48h], r12w
0x14009d00c  jz      short loc_14009D02F
0x14009d00e  mov     rcx, [rcx+40h]
0x14009d012  mov     r9d, 189h
0x14009d018  mov     [rsp+88h+var_68], rdx
0x14009d01d  mov     r8d, r15d
0x14009d020  mov     dl, 5
0x14009d022  call    WPP_RECORDER_SF_
0x14009d027  mov     r8, [rsp+88h+arg_10]
0x14009d02f  mov     [rsp+88h+var_54], ebx
0x14009d033  mov     r13d, r12d
0x14009d036  test    ebx, ebx
0x14009d038  jz      loc_14009D302
0x14009d03e  mov     eax, r13d
0x14009d041  mov     r14, [r8+rax*8]
0x14009d045  test    r14, r14
0x14009d048  jz      loc_14009D2EA
0x14009d04e  mov     rbx, [rsi+20h]
0x14009d052  mov     rcx, rbx; SpinLock
0x14009d055  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14009d05c  nop     dword ptr [rax+rax+00h]
0x14009d061  mov     [rbx+8], al
0x14009d064  mov     [rbx+10h], r15b
0x14009d068  mov     rdi, [r14+60h]
0x14009d06c  test    rdi, rdi
0x14009d06f  jnz     short loc_14009D0CA
0x14009d071  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14009d078  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14009d07f  jz      short loc_14009D0AA
0x14009d081  mov     r9d, 18Ah
0x14009d087  mov     rcx, cs:WPP_GLOBAL_Control
0x14009d08e  lea     rax, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x14009d095  mov     [rsp+88h+var_60], r14
0x14009d09a  mov     dl, 4
0x14009d09c  mov     [rsp+88h+var_68], rax
0x14009d0a1  mov     rcx, [rcx+40h]
0x14009d0a5  call    WPP_RECORDER_SF_q
0x14009d0aa  mov     dl, [rbx+8]; NewIrql
0x14009d0ad  mov     rcx, rbx; SpinLock
0x14009d0b0  mov     [rbx+10h], r12b
0x14009d0b4  call    cs:__imp_KeReleaseSpinLock
0x14009d0bb  nop     dword ptr [rax+rax+00h]
0x14009d0c0  mov     rdi, [rsp+88h+var_50]
0x14009d0c5  jmp     loc_14009D2E2
0x14009d0ca  cmp     [rdi-0Ch], r15b
0x14009d0ce  jnz     short loc_14009D0E8
0x14009d0d0  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14009d0d7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14009d0de  jz      short loc_14009D0AA
0x14009d0e0  mov     r9d, 18Bh
0x14009d0e6  jmp     short loc_14009D087
0x14009d0e8  cmp     [rsi+0F8h], r15d
0x14009d0ef  lea     rcx, [rsi+130h]; this
0x14009d0f6  mov     edx, 20h ; ' '
0x14009d0fb  lea     eax, [rdx+2]
0x14009d0fe  cmovnz  edx, eax
0x14009d101  movzx   edx, word ptr [rdx+rdi]; unsigned __int16
0x14009d105  call    ?GetTxEntry@CTxEntryTable@@QEAAPEAU_WFC_TX_ENTRY@@G@Z; CTxEntryTable::GetTxEntry(ushort)
0x14009d10a  mov     r15, rax
0x14009d10d  test    rax, rax
0x14009d110  jnz     short loc_14009D154
0x14009d112  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14009d119  mov     r15d, 1
0x14009d11f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14009d126  jz      short loc_14009D0AA
0x14009d128  mov     r9d, 18Ch
0x14009d12e  mov     rcx, cs:WPP_GLOBAL_Control
0x14009d135  lea     rax, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x14009d13c  mov     r8d, r15d
0x14009d13f  mov     [rsp+88h+var_68], rax
0x14009d144  mov     dl, 2
0x14009d146  mov     rcx, [rcx+40h]
0x14009d14a  call    WPP_RECORDER_SF_
0x14009d14f  jmp     loc_14009D0AA
0x14009d154  cmp     dword ptr [rsi+0F8h], 1
0x14009d15b  mov     r8b, [rdi+24h]
0x14009d15f  jnz     short loc_14009D169
0x14009d161  cmp     r8b, 10h
0x14009d165  setnbe  r8b; unsigned __int8
0x14009d169  mov     rdx, r15; struct _WFC_TX_ENTRY *
0x14009d16c  mov     rcx, rsi; this
0x14009d16f  call    ?GetTxQueue@CTxMgr@@AEAAPEAU_WFC_TX_QUEUE@@PEAU_WFC_TX_ENTRY@@E@Z; CTxMgr::GetTxQueue(_WFC_TX_ENTRY *,uchar)
0x14009d174  mov     rbp, rax
0x14009d177  test    rax, rax
0x14009d17a  jnz     short loc_14009D19C
0x14009d17c  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14009d183  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14009d18a  lea     r15d, [rbp+1]
0x14009d18e  jz      loc_14009D0AA
0x14009d194  mov     r9d, 18Dh
0x14009d19a  jmp     short loc_14009D12E
0x14009d19c  cmp     [rax+30h], r12w
0x14009d1a1  jnz     short loc_14009D1C8
0x14009d1a3  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14009d1aa  mov     r15d, 1
0x14009d1b0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14009d1b7  jz      loc_14009D0AA
0x14009d1bd  mov     r9d, 18Eh
0x14009d1c3  jmp     loc_14009D12E
0x14009d1c8  mov     rcx, [rdi]
0x14009d1cb  cmp     [rcx+8], rdi
0x14009d1cf  jnz     loc_14009D3A6
0x14009d1d5  mov     rax, [rdi+8]
0x14009d1d9  cmp     [rax], rdi
0x14009d1dc  jnz     loc_14009D3A6
0x14009d1e2  mov     [rax], rcx
0x14009d1e5  mov     edx, 0FFFFh
0x14009d1ea  mov     [rcx+8], rax
0x14009d1ee  mov     eax, 1
0x14009d1f3  add     word ptr [rsp+88h+var_58], ax
0x14009d1f8  mov     [rdi-0Ch], al
0x14009d1fb  lea     rax, [rbp+10h]
0x14009d1ff  add     [rbp+30h], dx
0x14009d203  add     [r15+18h], dx
0x14009d208  mov     [rsp+88h+arg_8], dx
0x14009d210  cmp     [rax], rax
0x14009d213  jz      short loc_14009D218
0x14009d215  dec     dword ptr [rsi+58h]
0x14009d218  xor     r8d, r8d
0x14009d21b  cmp     [rbp+30h], r8w
0x14009d220  jnz     short loc_14009D264
0x14009d222  lea     rcx, [rsi+108h]; this
0x14009d229  mov     rdx, rbp; struct _WFC_TX_QUEUE *
0x14009d22c  call    ?RemoveTxQueue@CGlobalTxQueueList@@QEAAHPEAU_WFC_TX_QUEUE@@@Z; CGlobalTxQueueList::RemoveTxQueue(_WFC_TX_QUEUE *)
0x14009d231  mov     rdx, rbp; struct _WFC_TX_QUEUE *
0x14009d234  mov     rcx, rsi; this
0x14009d237  call    ?RemoveTxQueueFromAcEntry@CTxMgr@@AEAAHPEAU_WFC_TX_QUEUE@@@Z; CTxMgr::RemoveTxQueueFromAcEntry(_WFC_TX_QUEUE *)
0x14009d23c  xor     r8d, r8d
0x14009d23f  cmp     [r15+18h], r8w
0x14009d244  jnz     short loc_14009D26D
0x14009d246  mov     rdx, r15; struct _WFC_TX_ENTRY *
0x14009d249  mov     rcx, rsi; this
0x14009d24c  call    ?IsPeerPaused@CTxMgr@@AEAAEPEAU_WFC_TX_ENTRY@@@Z; CTxMgr::IsPeerPaused(_WFC_TX_ENTRY *)
0x14009d251  test    al, al
0x14009d253  jz      short loc_14009D26D
0x14009d255  movzx   ebp, word ptr [r15+4]
0x14009d25a  mov     r12b, 1
0x14009d25d  movzx   r15d, word ptr [r15+6]
0x14009d262  jmp     short loc_14009D279
0x14009d264  movzx   ebp, dx
0x14009d267  movzx   r15d, dx
0x14009d26b  jmp     short loc_14009D279
0x14009d26d  movzx   ebp, [rsp+88h+arg_8]
0x14009d275  movzx   r15d, bp
0x14009d279  cmp     dword ptr [rdi-3Ch], 1
0x14009d27d  jnz     short loc_14009D290
0x14009d27f  mov     rax, [rsp+88h+var_48]
0x14009d284  mov     rdi, [rsp+88h+var_50]
0x14009d289  mov     [rsp+88h+var_48], r14
0x14009d28e  jmp     short loc_14009D29D
0x14009d290  mov     rax, [rsp+88h+var_50]
0x14009d295  mov     rdi, r14
0x14009d298  mov     [rsp+88h+var_50], r14
0x14009d29d  mov     [r14], rax
0x14009d2a0  mov     rcx, rbx; SpinLock
0x14009d2a3  mov     dl, [rbx+8]; NewIrql
0x14009d2a6  mov     [rbx+10h], r8b
0x14009d2aa  call    cs:__imp_KeReleaseSpinLock
0x14009d2b1  nop     dword ptr [rax+rax+00h]
0x14009d2b6  test    r12b, r12b
0x14009d2b9  jz      short loc_14009D2D9
0x14009d2bb  mov     rcx, [rsi+10h]
0x14009d2bf  xor     r9d, r9d
0x14009d2c2  movzx   r8d, r15w
0x14009d2c6  movzx   edx, bp
0x14009d2c9  mov     rax, [rcx+3E7Ch]
0x14009d2d0  mov     rcx, [rcx+70h]
0x14009d2d4  call    _guard_dispatch_icall
0x14009d2d9  mov     r15d, 1
0x14009d2df  xor     r12d, r12d
0x14009d2e2  mov     r8, [rsp+88h+arg_10]
0x14009d2ea  add     r13d, r15d
0x14009d2ed  cmp     r13d, [rsp+88h+var_54]
0x14009d2f2  jb      loc_14009D03E
0x14009d2f8  mov     rbp, [rsp+88h+var_48]
0x14009d2fd  mov     r14d, [rsp+88h+var_58]
0x14009d302  xor     r9d, r9d; bool
0x14009d305  mov     r8, rdi; struct _NET_BUFFER_LIST *
0x14009d308  mov     rdx, rbp; struct _NET_BUFFER_LIST *
0x14009d30b  mov     rcx, rsi; WorkItemContext
0x14009d30e  call    ?CompleteNBLs@CTxMgr@@AEAAXPEAU_NET_BUFFER_LIST@@0_N@Z; CTxMgr::CompleteNBLs(_NET_BUFFER_LIST *,_NET_BUFFER_LIST *,bool)
0x14009d313  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14009d31a  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14009d321  jz      short loc_14009D38D
0x14009d323  mov     rcx, cs:WPP_GLOBAL_Control
0x14009d32a  lea     rdi, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x14009d331  movzx   eax, r14w
0x14009d335  mov     r9d, 18Fh
0x14009d33b  mov     dword ptr [rsp+88h+var_60], eax
0x14009d33f  mov     r8d, r15d
0x14009d342  mov     dl, 4
0x14009d344  mov     [rsp+88h+var_68], rdi
0x14009d349  mov     rcx, [rcx+40h]
0x14009d34d  call    WPP_RECORDER_SF_D
0x14009d352  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x14009d359  jz      short loc_14009D38D
0x14009d35b  mov     rcx, cs:WPP_GLOBAL_Control
0x14009d362  cmp     byte ptr [rcx+29h], 5
0x14009d366  jnb     short loc_14009D36F
0x14009d368  cmp     [rcx+48h], r12w
0x14009d36d  jz      short loc_14009D38D
0x14009d36f  mov     rcx, [rcx+40h]
0x14009d373  mov     r9d, 190h
0x14009d379  mov     dword ptr [rsp+88h+var_60], r12d
0x14009d37e  mov     r8d, r15d
0x14009d381  mov     dl, 5
0x14009d383  mov     [rsp+88h+var_68], rdi
0x14009d388  call    WPP_RECORDER_SF_D
0x14009d38d  mov     rbx, [rsp+88h+arg_0]
0x14009d395  add     rsp, 50h
0x14009d399  pop     r15
0x14009d39b  pop     r14
0x14009d39d  pop     r13
0x14009d39f  pop     r12
0x14009d3a1  pop     rdi
0x14009d3a2  pop     rsi
0x14009d3a3  pop     rbp
0x14009d3a4  retn
0x14009d3a6  mov     ecx, 3
0x14009d3ab  int     29h; Win8: RtlFailFast(ecx)
```
