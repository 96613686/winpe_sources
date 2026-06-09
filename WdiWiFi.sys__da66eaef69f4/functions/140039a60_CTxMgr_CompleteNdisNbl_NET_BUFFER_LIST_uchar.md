# CTxMgr::CompleteNdisNbl(_NET_BUFFER_LIST *,uchar)

- ea: `0x140039a60`
- end: `0x14003a1eb`
- name: `?CompleteNdisNbl@CTxMgr@@AEAAXPEAU_NET_BUFFER_LIST@@E@Z`
- size: `1931`
- prototype: `void __fastcall(PVOID WorkItemContext, struct _NET_BUFFER_LIST *, unsigned __int8)`
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400376d0`
- `0x14003a200`
- `0x14003a630`

## callees

- `0x14002aa28`
- `0x1400330a0`
- `0x140033590`
- `0x140033730`
- `0x140034e04`
- `0x140034ec4`
- `0x140039a60`
- `0x14003b77c`
- `0x14008640c`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140039b3a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140039b3a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140039af1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140039af1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a105`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a105`
- `ntoskrnl!ExAllocatePool2` at `0x14003a017`
- `ntoskrnl!ExAllocatePool2` at `0x14003a017`
- `NDIS!NdisAllocateIoWorkItem` at `0x14003a04f`
- `NDIS!NdisAllocateIoWorkItem` at `0x14003a04f`
- `NDIS!NdisQueueIoWorkItem` at `0x14003a0b4`
- `NDIS!NdisQueueIoWorkItem` at `0x14003a199`
- `NDIS!NdisQueueIoWorkItem` at `0x14003a0b4`
- `NDIS!NdisQueueIoWorkItem` at `0x14003a199`
- `NDIS!NdisSetEvent` at `0x140039e4b`
- `NDIS!NdisSetEvent` at `0x140039e4b`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x140039c8e`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x140039c8e`

## pseudocode

```c
void __fastcall CTxMgr::CompleteNdisNbl(char *WorkItemContext, struct _NET_BUFFER_LIST *a2, unsigned __int8 a3)
{
  int v3; // r13d
  unsigned __int8 v4; // r15
  struct _NET_BUFFER_LIST *v5; // r14
  __int64 v7; // rbx
  KIRQL v8; // al
  SLIST_HEADER *Alignment; // rax
  KIRQL v10; // dl
  _WORD *v11; // rdx
  int v12; // r8d
  int v13; // r9d
  struct _NET_BUFFER_LIST *v14; // rsi
  CPort *v15; // rbx
  __int16 v16; // r12
  int v17; // edx
  int v18; // r8d
  struct _NET_BUFFER_LIST *v19; // r13
  __int16 v20; // bp
  __int64 i; // rcx
  _QWORD *Pool2; // rax
  void *v23; // rbp
  NDIS_HANDLE IoWorkItem; // rax
  int v25; // r9d
  int v26; // [rsp+20h] [rbp-78h]
  __int64 v27; // [rsp+28h] [rbp-70h]
  __int64 v28; // [rsp+40h] [rbp-58h]
  int v29; // [rsp+A0h] [rbp+8h]
  PVOID P; // [rsp+A8h] [rbp+10h]
  unsigned __int8 v31; // [rsp+B0h] [rbp+18h] BYREF
  _WORD *v32; // [rsp+B8h] [rbp+20h]

  v31 = a3;
  v3 = 0;
  v4 = a3;
  v29 = 0;
  P = 0;
  v5 = a2;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        1,
        354,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
    }
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        1,
        223,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
    }
  }
  v7 = *((_QWORD *)WorkItemContext + 6);
  v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v7);
  *(_BYTE *)(v7 + 16) = 1;
  *(_BYTE *)(v7 + 8) = v8;
  (*(void (__fastcall **)(_QWORD, struct _NET_BUFFER_LIST *))(*((_QWORD *)WorkItemContext + 2) + 15956LL))(
    *(_QWORD *)(*((_QWORD *)WorkItemContext + 2) + 112LL),
    v5);
  Alignment = (SLIST_HEADER *)v5;
  if ( v5 )
  {
    do
    {
      _InterlockedDecrement((volatile signed __int32 *)WorkItemContext + 26);
      Alignment = (SLIST_HEADER *)Alignment->Alignment;
    }
    while ( Alignment );
  }
  v10 = *(_BYTE *)(v7 + 8);
  *(_BYTE *)(v7 + 16) = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)v7, v10);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v11) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v11,
      1,
      224,
      (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
      0);
  }
  if ( !v4 )
    goto LABEL_13;
  Pool2 = (_QWORD *)ExAllocatePool2(64, 24, 1198089303);
  P = Pool2;
  v23 = Pool2;
  if ( !Pool2 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_82;
    v25 = 355;
    goto LABEL_80;
  }
  *Pool2 = *((_QWORD *)WorkItemContext + 2);
  Pool2[1] = WorkItemContext + 112;
  Pool2[2] = v5;
  IoWorkItem = NdisAllocateIoWorkItem(*(NDIS_HANDLE *)(*((_QWORD *)WorkItemContext + 2) + 88LL));
  if ( !IoWorkItem )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
    {
LABEL_82:
      v29 = -1073741670;
LABEL_13:
      v14 = 0;
      v28 = *((_QWORD *)WorkItemContext + 2);
      v15 = 0;
      v16 = -1;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v11) = 5;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v11,
          1,
          161,
          (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
      }
      if ( v5 )
      {
        do
        {
          v11 = v5->MiniportReserved[0];
          v19 = (struct _NET_BUFFER_LIST *)v5->Link.Alignment;
          v5->Link.Alignment = 0;
          v5->Status = 0;
          v20 = v11[16];
          v32 = v11;
          if ( v16 != v20 )
          {
            if ( v14 && v15 )
            {
              CPort::SendCompleteNetBufferLists(v15, v14);
              LODWORD(v11) = (_DWORD)v32;
            }
            v14 = 0;
            for ( i = 0; (unsigned int)i < 5; i = (unsigned int)(i + 1) )
            {
              v12 = v28;
              v15 = *(CPort **)(v28 + 8 * i + 4888);
              if ( v15 && v15->m_WfcPortId == v20 )
                goto LABEL_51;
            }
            if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_Dqq(
                WPP_GLOBAL_Control->DeviceExtension,
                (_DWORD)v11,
                v12,
                v13,
                v26,
                v20,
                (char)v5,
                (char)v11);
            v15 = 0;
          }
LABEL_51:
          v5->Link.Alignment = (ULONGLONG)v14;
          v14 = v5;
          v5 = v19;
          v16 = v20;
        }
        while ( v19 );
        v4 = v31;
        if ( v14 )
        {
          if ( v15 )
          {
            v31 = 0;
            if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
              {
                LOBYTE(v11) = 5;
                WPP_RECORDER_SF_(
                  WPP_GLOBAL_Control->DeviceExtension,
                  (_DWORD)v11,
                  1,
                  102,
                  (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids);
              }
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
                && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
              {
                LOBYTE(v11) = 5;
                WPP_RECORDER_SF_qD(
                  WPP_GLOBAL_Control->DeviceExtension,
                  (_DWORD)v11,
                  v12,
                  103,
                  (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
                  (char)v15,
                  v15->m_WfcPortId);
              }
            }
            CPort::FreeTxWfcFrame(v15, v14, &v31);
            if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
              && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
            {
              LOBYTE(v17) = 5;
              WPP_RECORDER_SF_qDq(
                WPP_GLOBAL_Control->DeviceExtension,
                v17,
                v18,
                104,
                (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
                (char)v15,
                v15->m_WfcPortId,
                (char)v14);
            }
            NdisMSendNetBufferListsComplete(v15->m_pAdapter->m_MiniportAdapterHandle, v14, 0);
            if ( v31 )
              CPort::CompletePendingCancelSendsOrHaltJobs(v15);
            if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
              goto LABEL_37;
            if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
            {
              LODWORD(v27) = 0;
              LOBYTE(v11) = 5;
              WPP_RECORDER_SF_D(
                WPP_GLOBAL_Control->DeviceExtension,
                (_DWORD)v11,
                1,
                105,
                (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
                v27);
            }
          }
        }
      }
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LODWORD(v27) = 0;
        LOBYTE(v11) = 5;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v11,
          1,
          163,
          (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
          v27);
      }
LABEL_37:
      if ( P )
        ExFreePoolWithTag(P, 0x47696457u);
      if ( v4 && _InterlockedExchangeAdd((volatile signed __int32 *)WorkItemContext + 28, 0xFFFFFFFE) == 3 )
        NdisSetEvent((PNDIS_EVENT)WorkItemContext + 5);
      v3 = v29;
      goto LABEL_41;
    }
    v25 = 356;
LABEL_80:
    LOBYTE(v11) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v11,
      1,
      v25,
      (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
    goto LABEL_82;
  }
  NdisQueueIoWorkItem(IoWorkItem, TxMgrDeferSendCompletion, v23);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v11) = 4;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v11,
      1,
      357,
      (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
  }
LABEL_41:
  if ( *((int *)WorkItemContext + 2) <= 0 )
  {
LABEL_42:
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LODWORD(v27) = v3;
      LOBYTE(v11) = 5;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v11,
        1,
        358,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
        v27);
    }
    return;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v11) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v11,
      1,
      362,
      (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
  }
  if ( _InterlockedIncrement((volatile signed __int32 *)WorkItemContext + 92) == 1 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v11) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v11,
        1,
        363,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
    }
    NdisQueueIoWorkItem(*((NDIS_HANDLE *)WorkItemContext + 47), TxMgrProcessPendingFrames, WorkItemContext);
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LODWORD(v27) = 0;
      LOBYTE(v11) = 5;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v11,
        1,
        364,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
        v27);
    }
    goto LABEL_42;
  }
}

```

## disassembly

```asm
0x140039a60  mov     [rsp+arg_10], r8b
0x140039a65  push    rbx
0x140039a66  push    rbp
0x140039a67  push    rsi
0x140039a68  push    rdi
0x140039a69  push    r12
0x140039a6b  push    r13
0x140039a6d  push    r14
0x140039a6f  push    r15
0x140039a71  sub     rsp, 58h
0x140039a75  xor     r13d, r13d
0x140039a78  movzx   r15d, r8b
0x140039a7c  xor     ebp, ebp
0x140039a7e  mov     [rsp+98h+arg_0], r13d
0x140039a86  mov     [rsp+98h+P], rbp
0x140039a8e  mov     r14, rdx
0x140039a91  mov     rdi, rcx
0x140039a94  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140039a9b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140039aa2  lea     rsi, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x140039aa9  jz      short loc_140039AEA
0x140039aab  mov     rcx, cs:WPP_GLOBAL_Control
0x140039ab2  cmp     byte ptr [rcx+29h], 5
0x140039ab6  jnb     loc_140039EEC
0x140039abc  cmp     [rcx+48h], bp
0x140039ac0  jnz     loc_140039EEC
0x140039ac6  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140039acd  jz      short loc_140039AEA
0x140039acf  mov     rcx, cs:WPP_GLOBAL_Control
0x140039ad6  cmp     byte ptr [rcx+29h], 5
0x140039ada  jnb     loc_140039E81
0x140039ae0  cmp     [rcx+48h], bp
0x140039ae4  jnz     loc_140039E81
0x140039aea  mov     rbx, [rdi+30h]
0x140039aee  mov     rcx, rbx; SpinLock
0x140039af1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140039af8  nop     dword ptr [rax+rax+00h]
0x140039afd  mov     byte ptr [rbx+10h], 1
0x140039b01  mov     rdx, r14
0x140039b04  mov     [rbx+8], al
0x140039b07  mov     rcx, [rdi+10h]
0x140039b0b  mov     rax, [rcx+3E54h]
0x140039b12  mov     rcx, [rcx+70h]
0x140039b16  call    _guard_dispatch_icall
0x140039b1b  mov     rax, r14
0x140039b1e  test    r14, r14
0x140039b21  jz      short loc_140039B2F
0x140039b23  lock dec dword ptr [rdi+68h]
0x140039b27  mov     rax, [rax]
0x140039b2a  test    rax, rax
0x140039b2d  jnz     short loc_140039B23
0x140039b2f  movzx   edx, byte ptr [rbx+8]; NewIrql
0x140039b33  mov     rcx, rbx; SpinLock
0x140039b36  mov     [rbx+10h], bpl
0x140039b3a  call    cs:__imp_KeReleaseSpinLock
0x140039b41  nop     dword ptr [rax+rax+00h]
0x140039b46  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140039b4d  jz      short loc_140039B6A
0x140039b4f  mov     rcx, cs:WPP_GLOBAL_Control
0x140039b56  cmp     byte ptr [rcx+29h], 5
0x140039b5a  jnb     loc_140039E5C
0x140039b60  cmp     [rcx+48h], bp
0x140039b64  jnz     loc_140039E5C
0x140039b6a  test    r15b, r15b
0x140039b6d  jnz     loc_14003A007
0x140039b73  mov     rax, [rdi+10h]
0x140039b77  xor     esi, esi
0x140039b79  mov     [rsp+98h+var_58], rax
0x140039b7e  xor     ebx, ebx
0x140039b80  mov     r12d, 0FFFFh
0x140039b86  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140039b8d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140039b94  lea     rbp, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x140039b9b  jz      short loc_140039BB8
0x140039b9d  mov     rcx, cs:WPP_GLOBAL_Control
0x140039ba4  cmp     byte ptr [rcx+29h], 5
0x140039ba8  jnb     loc_140039EA2
0x140039bae  cmp     [rcx+48h], bx
0x140039bb2  jnz     loc_140039EA2
0x140039bb8  test    r14, r14
0x140039bbb  jnz     loc_140039DB1
0x140039bc1  lea     r12, WPP_RECORDER_INITIALIZED
0x140039bc8  jmp     loc_140039CD8
0x140039bcd  movzx   r15d, [rsp+98h+arg_10]
0x140039bd6  test    rsi, rsi
0x140039bd9  jz      loc_140039F0D
0x140039bdf  test    rbx, rbx
0x140039be2  jz      loc_140039F0D
0x140039be8  mov     [rsp+98h+arg_10], 0
0x140039bf0  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140039bf7  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140039bfe  lea     rbp, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x140039c05  jz      short loc_140039C48
0x140039c07  mov     rcx, cs:WPP_GLOBAL_Control
0x140039c0e  cmp     byte ptr [rcx+29h], 5
0x140039c12  jnb     loc_140039F19
0x140039c18  cmp     word ptr [rcx+48h], 0
0x140039c1d  jnz     loc_140039F19
0x140039c23  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140039c2a  jz      short loc_140039C48
0x140039c2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140039c33  cmp     byte ptr [rcx+29h], 5
0x140039c37  jnb     loc_140039F63
0x140039c3d  cmp     word ptr [rcx+48h], 0
0x140039c42  jnz     loc_140039F63
0x140039c48  lea     r8, [rsp+98h+arg_10]; unsigned __int8 *
0x140039c50  mov     rdx, rsi; struct _NET_BUFFER_LIST *
0x140039c53  mov     rcx, rbx; this
0x140039c56  call    ?FreeTxWfcFrame@CPort@@AEAAHPEAU_NET_BUFFER_LIST@@PEAE@Z; CPort::FreeTxWfcFrame(_NET_BUFFER_LIST *,uchar *)
0x140039c5b  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140039c62  jz      short loc_140039C80
0x140039c64  mov     rcx, cs:WPP_GLOBAL_Control
0x140039c6b  cmp     byte ptr [rcx+29h], 5
0x140039c6f  jnb     loc_140039F8B
0x140039c75  cmp     word ptr [rcx+48h], 0
0x140039c7a  jnz     loc_140039F8B
0x140039c80  mov     rcx, [rbx+58h]
0x140039c84  xor     r8d, r8d; SendCompleteFlags
0x140039c87  mov     rdx, rsi; NetBufferList
0x140039c8a  mov     rcx, [rcx+58h]; MiniportAdapterHandle
0x140039c8e  call    cs:__imp_NdisMSendNetBufferListsComplete
0x140039c95  nop     dword ptr [rax+rax+00h]
0x140039c9a  cmp     [rsp+98h+arg_10], 0
0x140039ca2  jz      short loc_140039CAC
0x140039ca4  mov     rcx, rbx; this
0x140039ca7  call    ?CompletePendingCancelSendsOrHaltJobs@CPort@@AEAAXXZ; CPort::CompletePendingCancelSendsOrHaltJobs(void)
0x140039cac  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140039cb3  jz      short loc_140039CFD
0x140039cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x140039cbc  cmp     byte ptr [rcx+29h], 5
0x140039cc0  jnb     loc_140039F3A
0x140039cc6  cmp     word ptr [rcx+48h], 0
0x140039ccb  jnz     loc_140039F3A
0x140039cd1  lea     rbp, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x140039cd8  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140039cdf  jz      short loc_140039CFD
0x140039ce1  mov     rcx, cs:WPP_GLOBAL_Control
0x140039ce8  cmp     byte ptr [rcx+29h], 5
0x140039cec  jnb     loc_140039EC3
0x140039cf2  cmp     word ptr [rcx+48h], 0
0x140039cf7  jnz     loc_140039EC3
0x140039cfd  mov     rcx, [rsp+98h+P]; P
0x140039d05  test    rcx, rcx
0x140039d08  jnz     loc_14003A100
0x140039d0e  test    r15b, r15b
0x140039d11  jnz     loc_140039E34
0x140039d17  mov     r13d, [rsp+98h+arg_0]
0x140039d1f  lea     rsi, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x140039d26  mov     eax, [rdi+8]
0x140039d29  test    eax, eax
0x140039d2b  jg      short loc_140039D6D
0x140039d2d  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140039d34  jz      short loc_140039D9F
0x140039d36  mov     rcx, cs:WPP_GLOBAL_Control
0x140039d3d  cmp     byte ptr [rcx+29h], 5
0x140039d41  jnb     short loc_140039D4A
0x140039d43  cmp     word ptr [rcx+48h], 0
0x140039d48  jz      short loc_140039D9F
0x140039d4a  mov     rcx, [rcx+40h]
0x140039d4e  mov     r9d, 166h
0x140039d54  mov     dword ptr [rsp+98h+var_70], r13d
0x140039d59  mov     r8d, 1
0x140039d5f  mov     dl, 5
0x140039d61  mov     [rsp+98h+var_78], rsi
0x140039d66  call    WPP_RECORDER_SF_D
0x140039d6b  jmp     short loc_140039D9F
0x140039d6d  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140039d74  jnz     loc_14003A116
0x140039d7a  mov     eax, 1
0x140039d7f  lock xadd [rdi+170h], eax
0x140039d87  inc     eax
0x140039d89  cmp     eax, 1
0x140039d8c  jz      loc_14003A14F
0x140039d92  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140039d99  jnz     loc_14003A1AA
0x140039d9f  add     rsp, 58h
0x140039da3  pop     r15
0x140039da5  pop     r14
0x140039da7  pop     r13
0x140039da9  pop     r12
0x140039dab  pop     rdi
0x140039dac  pop     rsi
0x140039dad  pop     rbp
0x140039dae  pop     rbx
0x140039daf  retn
0x140039db1  lea     r15, WPP_RECORDER_INITIALIZED
0x140039db8  nop     dword ptr [rax+rax+00000000h]
0x140039dc0  mov     rdx, [r14+60h]
0x140039dc4  mov     r13, [r14]
0x140039dc7  mov     qword ptr [r14], 0
0x140039dce  mov     dword ptr [r14+8Ch], 0
0x140039dd9  movzx   ebp, word ptr [rdx+20h]
0x140039ddd  mov     [rsp+98h+arg_18], rdx
0x140039de5  cmp     r12w, bp
0x140039de9  jnz     short loc_140039E02
0x140039deb  mov     [r14], rsi
0x140039dee  mov     rsi, r14
0x140039df1  mov     r14, r13
0x140039df4  movzx   r12d, bp
0x140039df8  test    r13, r13
0x140039dfb  jnz     short loc_140039DC0
0x140039dfd  jmp     loc_140039BCD
0x140039e02  test    rsi, rsi
0x140039e05  jnz     loc_140039FB8
0x140039e0b  xor     esi, esi
0x140039e0d  xor     ecx, ecx
0x140039e0f  cmp     ecx, 5
0x140039e12  jnb     loc_140039FD9
0x140039e18  mov     r8, [rsp+98h+var_58]
0x140039e1d  mov     rbx, [r8+rcx*8+1318h]
0x140039e25  test    rbx, rbx
0x140039e28  jz      short loc_140039E30
0x140039e2a  cmp     [rbx+64h], bp
0x140039e2e  jz      short loc_140039DEB
0x140039e30  inc     ecx
0x140039e32  jmp     short loc_140039E0F
0x140039e34  mov     eax, 0FFFFFFFEh
0x140039e39  lock xadd [rdi+70h], eax
0x140039e3e  cmp     eax, 3
0x140039e41  jnz     loc_140039D17
0x140039e47  lea     rcx, [rdi+78h]; Event
0x140039e4b  call    cs:__imp_NdisSetEvent
0x140039e52  nop     dword ptr [rax+rax+00h]
0x140039e57  jmp     loc_140039D17
0x140039e5c  mov     rcx, [rcx+40h]
0x140039e60  mov     r9d, 0E0h
0x140039e66  mov     dword ptr [rsp+98h+var_70], ebp
0x140039e6a  mov     r8d, 1
0x140039e70  mov     dl, 5
0x140039e72  mov     [rsp+98h+var_78], rsi
0x140039e77  call    WPP_RECORDER_SF_D
0x140039e7c  jmp     loc_140039B6A
0x140039e81  mov     rcx, [rcx+40h]
0x140039e85  mov     r9d, 0DFh
0x140039e8b  mov     r8d, 1
0x140039e91  mov     [rsp+98h+var_78], rsi
0x140039e96  mov     dl, 5
0x140039e98  call    WPP_RECORDER_SF_
0x140039e9d  jmp     loc_140039AEA
0x140039ea2  mov     rcx, [rcx+40h]
0x140039ea6  mov     r9d, 0A1h
0x140039eac  mov     r8d, 1
0x140039eb2  mov     [rsp+98h+var_78], rbp
0x140039eb7  mov     dl, 5
0x140039eb9  call    WPP_RECORDER_SF_
0x140039ebe  jmp     loc_140039BB8
0x140039ec3  mov     rcx, [rcx+40h]
0x140039ec7  mov     r9d, 0A3h
0x140039ecd  mov     dword ptr [rsp+98h+var_70], 0
0x140039ed5  mov     r8d, 1
0x140039edb  mov     dl, 5
0x140039edd  mov     [rsp+98h+var_78], rbp
0x140039ee2  call    WPP_RECORDER_SF_D
0x140039ee7  jmp     loc_140039CFD
0x140039eec  mov     rcx, [rcx+40h]
0x140039ef0  mov     r9d, 162h
0x140039ef6  mov     r8d, 1
0x140039efc  mov     [rsp+98h+var_78], rsi
0x140039f01  mov     dl, 5
0x140039f03  call    WPP_RECORDER_SF_
0x140039f08  jmp     loc_140039AC6
0x140039f0d  lea     r12, WPP_RECORDER_INITIALIZED
0x140039f14  jmp     loc_140039CD1
0x140039f19  mov     rcx, [rcx+40h]
0x140039f1d  mov     r9d, 66h ; 'f'
0x140039f23  mov     r8d, 1
0x140039f29  mov     [rsp+98h+var_78], rbp
0x140039f2e  mov     dl, 5
0x140039f30  call    WPP_RECORDER_SF_
0x140039f35  jmp     loc_140039C23
0x140039f3a  mov     rcx, [rcx+40h]
0x140039f3e  mov     r9d, 69h ; 'i'
0x140039f44  mov     dword ptr [rsp+98h+var_70], 0
0x140039f4c  mov     r8d, 1
0x140039f52  mov     dl, 5
0x140039f54  mov     [rsp+98h+var_78], rbp
0x140039f59  call    WPP_RECORDER_SF_D
0x140039f5e  jmp     loc_140039CD1
0x140039f63  movzx   eax, word ptr [rbx+64h]
0x140039f67  mov     r9d, 67h ; 'g'
0x140039f6d  mov     rcx, [rcx+40h]
0x140039f71  mov     dl, 5
0x140039f73  mov     dword ptr [rsp+98h+var_68], eax
0x140039f77  mov     [rsp+98h+var_70], rbx
0x140039f7c  mov     [rsp+98h+var_78], rbp
0x140039f81  call    WPP_RECORDER_SF_qD
0x140039f86  jmp     loc_140039C48
0x140039f8b  movzx   eax, word ptr [rbx+64h]
0x140039f8f  mov     r9d, 68h ; 'h'
0x140039f95  mov     rcx, [rcx+40h]
0x140039f99  mov     dl, 5
0x140039f9b  mov     [rsp+98h+var_60], rsi
0x140039fa0  mov     dword ptr [rsp+98h+var_68], eax
0x140039fa4  mov     [rsp+98h+var_70], rbx
0x140039fa9  mov     [rsp+98h+var_78], rbp
0x140039fae  call    WPP_RECORDER_SF_qDq
0x140039fb3  jmp     loc_140039C80
0x140039fb8  test    rbx, rbx
0x140039fbb  jz      loc_140039E0B
0x140039fc1  mov     rdx, rsi; struct _NET_BUFFER_LIST *
  ... truncated ...
```
