# CTxMgr::InitializeTxWfcFrame(_NET_BUFFER_LIST *,ushort,uchar)

- ea: `0x140036ec0`
- end: `0x1400376c0`
- name: `?InitializeTxWfcFrame@CTxMgr@@QEAAHPEAU_NET_BUFFER_LIST@@GE@Z`
- size: `2048`
- prototype: `__int64 __fastcall(CTxMgr *this, struct _NET_BUFFER_LIST *, unsigned __int16, char)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x140036860`
- `0x1400403c0`

## callees

- `0x1400175f8`
- `0x140034e04`
- `0x140034ec4`
- `0x140036ec0`
- `0x1400439cc`
- `0x14007d500`
- `0x1400da4f0`
- `0x1400da740`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140037426`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140037426`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400371c6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400375cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400371c6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400375cd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400370ce`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400370ce`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x140037041`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x140037041`
- `NDIS!NdisGetDataBuffer` at `0x140037067`
- `NDIS!NdisGetDataBuffer` at `0x140037067`
- `NDIS!NdisAllocateNetBufferListContext` at `0x140036f54`
- `NDIS!NdisAllocateNetBufferListContext` at `0x140036f54`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x140037095`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x140037465`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x140037095`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x140037465`
- `NDIS!NdisFreeNetBufferListContext` at `0x14003735f`
- `NDIS!NdisFreeNetBufferListContext` at `0x14003735f`

## pseudocode

```c
__int64 __fastcall CTxMgr::InitializeTxWfcFrame(
        CTxMgr *this,
        struct _NET_BUFFER_LIST *a2,
        unsigned __int16 a3,
        char a4)
{
  struct _NET_BUFFER_LIST *v5; // rsi
  PNET_BUFFER FirstNetBuffer; // r14
  PMDL CurrentMdl; // rdi
  __int64 CurrentMdlOffset; // rbp
  char *MappedSystemVa; // rdx
  unsigned int NetBufferListContext; // ebx
  __int64 v12; // r15
  char *v13; // rdi
  char *v14; // rbx
  unsigned __int16 PeerId; // cx
  unsigned int v16; // ecx
  __int64 v17; // rdi
  _WORD *DataBuffer; // rax
  int v19; // edx
  int v20; // ecx
  CFrameIdLookupTable *p_m_FrameIdTable; // rbx
  PKSPIN_LOCK p_SpinLock; // rbp
  KIRQL v23; // al
  int v24; // edx
  unsigned int m_NumFrameIdAssigned; // eax
  unsigned int i; // edi
  char *v27; // rdx
  unsigned int v28; // ecx
  unsigned __int16 v29; // di
  _WORD *v30; // r14
  _LIST_ENTRY *v31; // rcx
  struct _LIST_ENTRY *Blink; // rdx
  KIRQL v33; // dl
  int v35; // r8d
  KIRQL v36; // dl
  int AlignOffset; // [rsp+20h] [rbp-98h]
  __int64 Storage; // [rsp+68h] [rbp-50h] BYREF

  v5 = a2;
  Storage = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      103,
      (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
  }
  FirstNetBuffer = v5->FirstNetBuffer;
  CurrentMdl = FirstNetBuffer->CurrentMdl;
  CurrentMdlOffset = FirstNetBuffer->CurrentMdlOffset;
  NetBufferListContext = NdisAllocateNetBufferListContext(v5, this->m_pAdapter->m_WfcFrameSize, 0, 0x54696457u);
  if ( NetBufferListContext )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(MappedSystemVa) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)MappedSystemVa,
        1,
        104,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
    }
    goto LABEL_54;
  }
  v12 = (__int64)&v5->Context->ContextData[v5->Context->Offset];
  memset((void *)v12, 0, this->m_pAdapter->m_WfcFrameSize);
  *(_DWORD *)(v12 + 4) = 2;
  if ( (CurrentMdl->MdlFlags & 5) != 0 )
    MappedSystemVa = (char *)CurrentMdl->MappedSystemVa;
  else
    MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(CurrentMdl, 0, MmCached, 0, 0, 0x40000010u);
  if ( (unsigned int)(CurrentMdl->ByteCount - CurrentMdlOffset) < 0xA )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(MappedSystemVa) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)MappedSystemVa,
        1,
        105,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
    }
    goto LABEL_57;
  }
  v13 = &MappedSystemVa[CurrentMdlOffset];
  v14 = &MappedSystemVa[CurrentMdlOffset + 4];
  PeerId = -1;
  if ( this->m_QueueingMode == PEER_QUEUEING )
  {
    PeerId = CPeerTable::GetPeerId(
               &this->m_pAdapter->m_PeerTable,
               (struct _WDI_MAC_ADDRESS *)&MappedSystemVa[CurrentMdlOffset + 4],
               a3);
    if ( PeerId == 0xFFFF )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(MappedSystemVa) = 2;
        WPP_RECORDER_SF__MAC_(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)MappedSystemVa,
          v35,
          106,
          (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
          (__int64)v14);
      }
      NetBufferListContext = -1073676254;
      goto LABEL_46;
    }
  }
  *(_WORD *)(v12 + 98) = PeerId;
  *(_BYTE *)(v12 + 100) = BYTE2(v5->NetBufferListInfo[4]) & 0xF;
  *(_QWORD *)(v12 + 72) = v12 + 64;
  *(_QWORD *)(v12 + 64) = v12 + 64;
  *(_QWORD *)(v12 + 80) = v5;
  *(_WORD *)(v12 + 96) = a3;
  LODWORD(MappedSystemVa) = *(unsigned __int16 *)v13;
  if ( ((unsigned __int16)MappedSystemVa & 0x300) == 0x300 )
    v16 = 30;
  else
    v16 = 24;
  v17 = v16 + 2;
  if ( (char)MappedSystemVa >= 0 )
    v17 = v16;
  *(_BYTE *)(v12 + 101) = (*v14 & 1) == 0;
  if ( FirstNetBuffer->DataLength < (unsigned __int64)(v17 + 8) )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(MappedSystemVa) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)MappedSystemVa,
        1,
        107,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
      NetBufferListContext = -1073676268;
LABEL_46:
      if ( v12 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(MappedSystemVa) = 2;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)MappedSystemVa,
            1,
            111,
            (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
        }
        NdisFreeNetBufferListContext(v5, this->m_pAdapter->m_WfcFrameSize);
      }
LABEL_54:
      v5->MiniportReserved[0] = 0;
      goto LABEL_35;
    }
LABEL_57:
    NetBufferListContext = -1073676268;
    goto LABEL_46;
  }
  NdisAdvanceNetBufferListDataStart(v5, v17, 0, 0);
  DataBuffer = NdisGetDataBuffer(v5->FirstNetBuffer, 8u, &Storage, 1u, 0);
  if ( !DataBuffer )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v19) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v19,
        1,
        108,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
    }
    NdisRetreatNetBufferListDataStart(v5, v17, 0, 0, 0);
    NetBufferListContext = -1073676267;
    goto LABEL_46;
  }
  *(_WORD *)(v12 + 104) = DataBuffer[3];
  NdisRetreatNetBufferListDataStart(v5, v17, 0, 0, 0);
  v20 = *((unsigned __int16 *)v5->NetBufferListInfo[6] + 2);
  *(_DWORD *)(v12 + 112) = v20;
  if ( v20 == 2 && !a4 )
    *(_DWORD *)(v12 + 112) = 1;
  v5->MiniportReserved[0] = (PVOID)(v12 + 64);
  p_m_FrameIdTable = &this->m_pAdapter->m_FrameIdTable;
  p_SpinLock = &p_m_FrameIdTable->m_FrameIdLock->m_SpinLock.SpinLock;
  v23 = KeAcquireSpinLockRaiseToDpc(&p_m_FrameIdTable->m_FrameIdLock->m_SpinLock.SpinLock);
  *((_BYTE *)p_SpinLock + 16) = 1;
  *((_BYTE *)p_SpinLock + 8) = v23;
  m_NumFrameIdAssigned = p_m_FrameIdTable->m_NumFrameIdAssigned;
  if ( m_NumFrameIdAssigned >= 0xFFFF )
  {
    NetBufferListContext = -1073741670;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v24) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v24,
        1,
        67,
        (__int64)WPP_9437762af08d3eac72fe4950abce8818_Traceguids);
    }
    v36 = *((_BYTE *)p_SpinLock + 8);
    *((_BYTE *)p_SpinLock + 16) = 0;
    KeReleaseSpinLock(p_SpinLock, v36);
    v30 = (_WORD *)(v12 + 88);
    goto LABEL_28;
  }
  p_m_FrameIdTable->m_NumFrameIdAssigned = m_NumFrameIdAssigned + 1;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v24) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v24,
      1,
      74,
      (__int64)WPP_9437762af08d3eac72fe4950abce8818_Traceguids);
  }
  for ( i = p_m_FrameIdTable->m_FreeFrameIdStartIndex; i < 0x800; ++i )
  {
    v27 = (char *)p_m_FrameIdTable + 4 * i;
    if ( *((_DWORD *)v27 + 262) != -1 )
    {
      _BitScanForward(&v28, ~*((_DWORD *)v27 + 262));
      *((_DWORD *)v27 + 262) |= 1 << v28;
      p_m_FrameIdTable->m_FreeFrameIdStartIndex = i;
      v29 = v28 + 32 * i;
      goto LABEL_24;
    }
  }
  v29 = -1;
LABEL_24:
  *(_WORD *)(v12 + 88) = v29;
  v30 = (_WORD *)(v12 + 88);
  v31 = &p_m_FrameIdTable->m_FrameListHeadArray[((unsigned __int64)v29 >> 3) & 0x3F];
  Blink = v31->Blink;
  if ( Blink->Flink != v31 )
    __fastfail(3u);
  *(_QWORD *)(v12 + 16) = v31;
  *(_QWORD *)(v12 + 24) = Blink;
  NetBufferListContext = 0;
  Blink->Flink = (struct _LIST_ENTRY *)(v12 + 16);
  v31->Blink = (struct _LIST_ENTRY *)(v12 + 16);
  v33 = *((_BYTE *)p_SpinLock + 8);
  *((_BYTE *)p_SpinLock + 16) = 0;
  KeReleaseSpinLock(p_SpinLock, v33);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(MappedSystemVa) = 5;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)MappedSystemVa,
        1,
        68,
        (__int64)WPP_9437762af08d3eac72fe4950abce8818_Traceguids,
        v29);
    }
LABEL_28:
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(MappedSystemVa) = 5;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)MappedSystemVa,
        1,
        69,
        (__int64)WPP_9437762af08d3eac72fe4950abce8818_Traceguids,
        NetBufferListContext);
    }
  }
  if ( NetBufferListContext )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(MappedSystemVa) = 2;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)MappedSystemVa,
        1,
        109,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
        NetBufferListContext);
    }
    goto LABEL_46;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_qDDDDdD(
      WPP_GLOBAL_Control->DeviceExtension,
      *(unsigned __int16 *)(v12 + 104),
      *(unsigned __int8 *)(v12 + 100),
      *(unsigned __int16 *)(v12 + 98),
      AlignOffset,
      (char)v5,
      *(_WORD *)(v12 + 96),
      *(_WORD *)(v12 + 98),
      *(_BYTE *)(v12 + 100),
      *(_WORD *)(v12 + 104),
      *(_DWORD *)(v12 + 112),
      *v30);
  }
LABEL_35:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(MappedSystemVa) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)MappedSystemVa,
      1,
      112,
      (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
      NetBufferListContext);
  }
  return NetBufferListContext;
}

```

## disassembly

```asm
0x140036ec0  mov     [rsp+arg_18], rbx
0x140036ec5  push    rbp
0x140036ec6  push    rsi
0x140036ec7  push    rdi
0x140036ec8  push    r12
0x140036eca  push    r13
0x140036ecc  push    r14
0x140036ece  push    r15
0x140036ed0  sub     rsp, 80h
0x140036ed7  mov     rax, cs:__security_cookie
0x140036ede  xor     rax, rsp
0x140036ee1  mov     [rsp+0B8h+var_48], rax
0x140036ee6  mov     [rsp+0B8h+var_58], r9b
0x140036eeb  movzx   r12d, r8w
0x140036eef  mov     rsi, rdx
0x140036ef2  mov     [rsp+0B8h+Storage], 0
0x140036efb  mov     r13, rcx
0x140036efe  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140036f05  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140036f0c  lea     rax, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x140036f13  jz      short loc_140036F31
0x140036f15  mov     rcx, cs:WPP_GLOBAL_Control
0x140036f1c  cmp     byte ptr [rcx+29h], 5
0x140036f20  jnb     loc_14003736D
0x140036f26  cmp     word ptr [rcx+48h], 0
0x140036f2b  jnz     loc_14003736D
0x140036f31  mov     r14, [rsi+8]
0x140036f35  xor     r8d, r8d; ContextBackFill
0x140036f38  mov     rdx, [r13+10h]
0x140036f3c  mov     r9d, 54696457h; PoolTag
0x140036f42  mov     rcx, rsi; NetBufferList
0x140036f45  mov     rdi, [r14+8]
0x140036f49  movzx   edx, word ptr [rdx+15C2h]; ContextSize
0x140036f50  mov     ebp, [r14+10h]
0x140036f54  call    cs:__imp_NdisAllocateNetBufferListContext
0x140036f5b  nop     dword ptr [rax+rax+00h]
0x140036f60  mov     ebx, eax
0x140036f62  test    eax, eax
0x140036f64  jnz     loc_1400373B3
0x140036f6a  mov     rcx, [rsi+10h]
0x140036f6e  xor     edx, edx; Val
0x140036f70  movzx   eax, word ptr [rcx+0Ah]
0x140036f74  lea     r15, [rcx+10h]
0x140036f78  add     r15, rax
0x140036f7b  mov     rax, [r13+10h]
0x140036f7f  mov     rcx, r15; void *
0x140036f82  movzx   r8d, word ptr [rax+15C2h]; Size
0x140036f8a  call    memset
0x140036f8f  mov     dword ptr [r15+4], 2
0x140036f97  test    byte ptr [rdi+0Ah], 5
0x140036f9b  jz      loc_140037408
0x140036fa1  mov     rdx, [rdi+18h]
0x140036fa5  mov     ecx, [rdi+28h]
0x140036fa8  sub     ecx, ebp
0x140036faa  cmp     ecx, 0Ah
0x140036fad  jb      loc_1400374BA
0x140036fb3  cmp     dword ptr [r13+0F8h], 0
0x140036fbb  lea     rdi, [rdx+rbp]
0x140036fbf  lea     rbx, [rdi+4]
0x140036fc3  mov     ecx, 0FFFFh
0x140036fc8  jz      loc_1400372D4
0x140036fce  mov     [r15+62h], cx
0x140036fd3  lea     rbp, [r15+40h]
0x140036fd7  movzx   eax, byte ptr [rsi+0B2h]
0x140036fde  mov     ecx, 300h
0x140036fe3  and     al, 0Fh
0x140036fe5  mov     [r15+64h], al
0x140036fe9  mov     [rbp+8], rbp
0x140036fed  mov     [rbp+0], rbp
0x140036ff1  mov     [r15+50h], rsi
0x140036ff5  mov     [r15+60h], r12w
0x140036ffa  movzx   edx, word ptr [rdi]
0x140036ffd  movzx   eax, dx
0x140037000  and     ax, cx
0x140037003  cmp     ax, cx
0x140037006  jz      loc_140037524
0x14003700c  mov     ecx, 18h
0x140037011  movzx   eax, byte ptr [rbx]
0x140037014  lea     edi, [rcx+2]
0x140037017  test    dl, 80h
0x14003701a  not     al
0x14003701c  cmovz   edi, ecx
0x14003701f  and     al, 1
0x140037021  mov     [r15+65h], al
0x140037025  mov     ecx, [r14+18h]
0x140037029  lea     rax, [rdi+8]
0x14003702d  cmp     rcx, rax
0x140037030  jb      loc_1400373E3
0x140037036  xor     r9d, r9d; FreeMdlMdlHandler
0x140037039  xor     r8d, r8d; FreeMdl
0x14003703c  mov     edx, edi; DataOffsetDelta
0x14003703e  mov     rcx, rsi; NetBufferList
0x140037041  call    cs:__imp_NdisAdvanceNetBufferListDataStart
0x140037048  nop     dword ptr [rax+rax+00h]
0x14003704d  mov     rcx, [rsi+8]; NetBuffer
0x140037051  lea     r8, [rsp+0B8h+Storage]; Storage
0x140037056  xor     ebx, ebx
0x140037058  mov     r9d, 1; AlignMultiple
0x14003705e  mov     edx, 8; BytesNeeded
0x140037063  mov     [rsp+0B8h+AlignOffset], ebx; AlignOffset
0x140037067  call    cs:__imp_NdisGetDataBuffer
0x14003706e  nop     dword ptr [rax+rax+00h]
0x140037073  test    rax, rax
0x140037076  jz      loc_14003743A
0x14003707c  movzx   eax, word ptr [rax+6]
0x140037080  xor     r9d, r9d; AllocateMdlHandler
0x140037083  xor     r8d, r8d; DataBackFill
0x140037086  mov     [r15+68h], ax
0x14003708b  mov     edx, edi; DataOffsetDelta
0x14003708d  mov     qword ptr [rsp+0B8h+AlignOffset], rbx; FreeMdlHandler
0x140037092  mov     rcx, rsi; NetBufferList
0x140037095  call    cs:__imp_NdisRetreatNetBufferListDataStart
0x14003709c  nop     dword ptr [rax+rax+00h]
0x1400370a1  mov     rax, [rsi+0C0h]
0x1400370a8  movzx   ecx, word ptr [rax+4]
0x1400370ac  mov     [r15+70h], ecx
0x1400370b0  cmp     ecx, 2
0x1400370b3  jz      loc_14003747B
0x1400370b9  mov     [rsi+60h], rbp
0x1400370bd  mov     rbx, [r13+10h]
0x1400370c1  add     rbx, 15E0h
0x1400370c8  mov     rbp, [rbx]
0x1400370cb  mov     rcx, rbp; SpinLock
0x1400370ce  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400370d5  nop     dword ptr [rax+rax+00h]
0x1400370da  mov     byte ptr [rbp+10h], 1
0x1400370de  mov     ecx, 0FFFFh
0x1400370e3  mov     [rbp+8], al
0x1400370e6  mov     eax, [rbx+10h]
0x1400370e9  cmp     eax, ecx
0x1400370eb  jnb     loc_140037583
0x1400370f1  inc     eax
0x1400370f3  mov     [rbx+10h], eax
0x1400370f6  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400370fd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140037104  lea     r12, WPP_9437762af08d3eac72fe4950abce8818_Traceguids
0x14003710b  jz      short loc_14003712E
0x14003710d  mov     rcx, cs:WPP_GLOBAL_Control
0x140037114  cmp     byte ptr [rcx+29h], 5
0x140037118  jnb     loc_1400372A5
0x14003711e  cmp     word ptr [rcx+48h], 0
0x140037123  jnz     loc_1400372A5
0x140037129  mov     ecx, 0FFFFh
0x14003712e  mov     edi, [rbx+0Ch]
0x140037131  mov     [rsp+0B8h+var_54], 20h ; ' '
0x140037139  cmp     edi, 800h
0x14003713f  jnb     loc_1400373DB
0x140037145  mov     eax, edi
0x140037147  lea     rdx, [rbx+rax*4]
0x14003714b  mov     r8d, [rdx+418h]
0x140037152  mov     eax, r8d
0x140037155  not     eax
0x140037157  test    eax, eax
0x140037159  jz      loc_1400372CD
0x14003715f  bsf     ecx, eax
0x140037162  mov     eax, 1
0x140037167  shl     eax, cl
0x140037169  or      eax, r8d
0x14003716c  mov     [rdx+418h], eax
0x140037172  mov     [rbx+0Ch], edi
0x140037175  shl     di, 5
0x140037179  add     di, cx
0x14003717c  mov     [r15+58h], di
0x140037181  lea     r14, [r15+58h]
0x140037185  movzx   ecx, di
0x140037188  shr     rcx, 3
0x14003718c  and     ecx, 3Fh
0x14003718f  shl     rcx, 4
0x140037193  add     rcx, 18h
0x140037197  add     rcx, rbx
0x14003719a  mov     rdx, [rcx+8]
0x14003719e  cmp     [rdx], rcx
0x1400371a1  jnz     loc_1400372C6
0x1400371a7  mov     [r15+10h], rcx
0x1400371ab  lea     rax, [r15+10h]
0x1400371af  mov     [rax+8], rdx
0x1400371b3  xor     ebx, ebx
0x1400371b5  mov     [rdx], rax
0x1400371b8  mov     [rcx+8], rax
0x1400371bc  mov     rcx, rbp; SpinLock
0x1400371bf  movzx   edx, byte ptr [rbp+8]; NewIrql
0x1400371c3  mov     [rbp+10h], bl
0x1400371c6  call    cs:__imp_KeReleaseSpinLock
0x1400371cd  nop     dword ptr [rax+rax+00h]
0x1400371d2  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400371d9  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400371e0  jz      short loc_140037222
0x1400371e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400371e9  cmp     byte ptr [rcx+29h], 5
0x1400371ed  jnb     loc_1400375E9
0x1400371f3  cmp     [rcx+48h], bx
0x1400371f7  jnz     loc_1400375E9
0x1400371fd  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140037204  jz      short loc_140037222
0x140037206  mov     rcx, cs:WPP_GLOBAL_Control
0x14003720d  cmp     byte ptr [rcx+29h], 5
0x140037211  jnb     loc_140037611
0x140037217  cmp     word ptr [rcx+48h], 0
0x14003721c  jnz     loc_140037611
0x140037222  test    ebx, ebx
0x140037224  jnz     loc_140037636
0x14003722a  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140037231  jz      short loc_14003724E
0x140037233  mov     rcx, cs:WPP_GLOBAL_Control
0x14003723a  cmp     byte ptr [rcx+29h], 5
0x14003723e  jnb     loc_140037676
0x140037244  cmp     [rcx+48h], bx
0x140037248  jnz     loc_140037676
0x14003724e  lea     r14, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x140037255  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003725c  jz      short loc_14003727A
0x14003725e  mov     rcx, cs:WPP_GLOBAL_Control
0x140037265  cmp     byte ptr [rcx+29h], 5
0x140037269  jnb     loc_14003738E
0x14003726f  cmp     word ptr [rcx+48h], 0
0x140037274  jnz     loc_14003738E
0x14003727a  mov     eax, ebx
0x14003727c  mov     rcx, [rsp+0B8h+var_48]
0x140037281  xor     rcx, rsp; StackCookie
0x140037284  call    __security_check_cookie
0x140037289  mov     rbx, [rsp+0B8h+arg_18]
0x140037291  add     rsp, 80h
0x140037298  pop     r15
0x14003729a  pop     r14
0x14003729c  pop     r13
0x14003729e  pop     r12
0x1400372a0  pop     rdi
0x1400372a1  pop     rsi
0x1400372a2  pop     rbp
0x1400372a3  retn
0x1400372a5  mov     rcx, [rcx+40h]
0x1400372a9  mov     r9d, 4Ah ; 'J'
0x1400372af  mov     r8d, 1
0x1400372b5  mov     qword ptr [rsp+0B8h+AlignOffset], r12
0x1400372ba  mov     dl, 5
0x1400372bc  call    WPP_RECORDER_SF_
0x1400372c1  jmp     loc_140037129
0x1400372c6  mov     ecx, 3
0x1400372cb  int     29h; Win8: RtlFailFast(ecx)
0x1400372cd  inc     edi
0x1400372cf  jmp     loc_140037139
0x1400372d4  mov     rcx, [r13+10h]
0x1400372d8  movzx   r8d, r12w; unsigned __int16
0x1400372dc  add     rcx, 39F8h; this
0x1400372e3  mov     rdx, rbx; struct _WDI_MAC_ADDRESS *
0x1400372e6  call    ?GetPeerId@CPeerTable@@QEAAGPEAU_WDI_MAC_ADDRESS@@G@Z; CPeerTable::GetPeerId(_WDI_MAC_ADDRESS *,ushort)
0x1400372eb  movzx   ecx, ax
0x1400372ee  mov     eax, 0FFFFh
0x1400372f3  cmp     cx, ax
0x1400372f6  jnz     loc_140036FCE
0x1400372fc  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140037303  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14003730a  lea     r14, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x140037311  jnz     loc_1400374FD
0x140037317  mov     ebx, 0C0010022h
0x14003731c  test    r15, r15
0x14003731f  jz      loc_1400373C7
0x140037325  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003732c  jz      short loc_140037351
0x14003732e  mov     rcx, cs:WPP_GLOBAL_Control
0x140037335  mov     r9d, 6Fh ; 'o'
0x14003733b  mov     r8d, 1
0x140037341  mov     qword ptr [rsp+0B8h+AlignOffset], r14
0x140037346  mov     dl, 2
0x140037348  mov     rcx, [rcx+40h]
0x14003734c  call    WPP_RECORDER_SF_
0x140037351  mov     rdx, [r13+10h]
0x140037355  mov     rcx, rsi; NetBufferList
0x140037358  movzx   edx, word ptr [rdx+15C2h]; ContextSize
0x14003735f  call    cs:__imp_NdisFreeNetBufferListContext
0x140037366  nop     dword ptr [rax+rax+00h]
0x14003736b  jmp     short loc_1400373C7
0x14003736d  mov     rcx, [rcx+40h]
0x140037371  mov     r9d, 67h ; 'g'
0x140037377  mov     r8d, 1
0x14003737d  mov     qword ptr [rsp+0B8h+AlignOffset], rax
0x140037382  mov     dl, 5
0x140037384  call    WPP_RECORDER_SF_
0x140037389  jmp     loc_140036F31
0x14003738e  mov     rcx, [rcx+40h]
0x140037392  mov     r9d, 70h ; 'p'
0x140037398  mov     [rsp+0B8h+Priority], ebx
0x14003739c  mov     r8d, 1
0x1400373a2  mov     dl, 5
0x1400373a4  mov     qword ptr [rsp+0B8h+AlignOffset], r14
0x1400373a9  call    WPP_RECORDER_SF_D
0x1400373ae  jmp     loc_14003727A
0x1400373b3  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400373ba  lea     r14, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x1400373c1  jnz     loc_140037492
0x1400373c7  mov     qword ptr [rsi+60h], 0
0x1400373cf  lea     rbp, WPP_RECORDER_INITIALIZED
0x1400373d6  jmp     loc_140037255
0x1400373db  movzx   edi, cx
0x1400373de  jmp     loc_14003717C
0x1400373e3  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400373ea  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400373f1  lea     r14, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x1400373f8  jnz     loc_14003752E
0x1400373fe  mov     ebx, 0C0010014h
  ... truncated ...
```
