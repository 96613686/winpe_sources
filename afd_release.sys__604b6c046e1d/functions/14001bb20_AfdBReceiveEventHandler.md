# AfdBReceiveEventHandler

- ea: `0x14001bb20`
- end: `0x14001c411`
- name: `AfdBReceiveEventHandler`
- size: `2289`
- prototype: `__int64 __fastcall(__int64, __int64, __int16, int, size_t Size, _DWORD *, void *Src, _QWORD *)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140053ab0`

## callees

- `0x140009fb0`
- `0x14000cbe0`
- `0x14000f450`
- `0x1400137a0`
- `0x14001b0d0`
- `0x14001b800`
- `0x14001bb20`
- `0x14001c708`
- `0x14001ceb0`
- `0x14001db90`
- `0x14001dd20`
- `0x1400318a0`
- `0x140036b7c`
- `0x14004efd0`
- `0x140072800`
- `0x14009304c`
- `0x1400931f0`
- `0x140093f78`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001bdff`
- `ntoskrnl!IofCompleteRequest` at `0x14001bea4`
- `ntoskrnl!IofCompleteRequest` at `0x14001bdff`
- `ntoskrnl!IofCompleteRequest` at `0x14001bea4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001bbce`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001bdcd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001bef6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001c11f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001c1f5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001c288`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001c33a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001c39e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001bbce`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001bdcd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001bef6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001c11f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001c1f5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001c288`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001c33a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001c39e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001bba4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001bbea`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001be13`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001bba4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001bbea`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001be13`
- `TDI!TdiCopyBufferToMdl` at `0x14001be46`
- `TDI!TdiCopyBufferToMdl` at `0x14001be46`

## pseudocode

```c
__int64 __fastcall AfdBReceiveEventHandler(
        __int64 a1,
        __int64 a2,
        __int16 a3,
        int a4,
        size_t Size,
        _DWORD *a6,
        void *Src,
        _QWORD *a8)
{
  __int64 v9; // rbx
  signed __int64 v10; // rax
  signed __int64 v11; // rax
  bool v12; // zf
  _DWORD *v13; // r15
  __int64 v14; // r8
  int v15; // r14d
  int v16; // ebx
  size_t v17; // rdi
  __int64 v18; // rcx
  _QWORD *v19; // rax
  _QWORD *v20; // rdx
  __int64 v21; // rcx
  _QWORD *v22; // rsi
  _DWORD *v23; // r14
  ULONG v24; // ecx
  int v25; // r15d
  int v26; // r15d
  int v27; // ecx
  _QWORD *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rsi
  _BYTE *v32; // rcx
  char *v33; // rdx
  struct _MDL *v34; // rcx
  int v35; // eax
  CCHAR v36; // dl
  ULONG v37; // edx
  signed __int64 v38; // rcx
  signed __int64 v39; // rcx
  int v41; // edx
  __int64 v42; // rcx
  __int64 v43; // rdx
  _QWORD *v44; // rax
  _BYTE *v45; // r8
  char v46; // al
  __int64 v47; // rdx
  __int16 v48; // cx
  __int64 v49; // rdx
  unsigned int v50; // r10d
  unsigned int v51; // ecx
  __int64 v52; // r11
  __int64 v53; // rax
  __int64 *v54; // rcx
  __int64 v55; // rcx
  char v56; // al
  struct _KLOCK_QUEUE_HANDLE *p_LockHandle; // rdx
  signed __int64 v58; // rcx
  bool v59; // of
  char v60; // cc
  __int64 v61; // rcx
  unsigned int v62; // r10d
  __int64 Buffer; // rsi
  int v64; // eax
  signed __int64 v65; // rcx
  signed __int64 v66; // rcx
  int v67; // edi
  __int64 v68; // r8
  __int64 v69; // rax
  __int64 v70; // rdx
  _QWORD *v71; // rax
  int v72; // edi
  signed __int64 v73; // rcx
  __int64 v74; // [rsp+68h] [rbp-21h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+70h] [rbp-19h] BYREF
  ULONG BytesCopied; // [rsp+D8h] [rbp+4Fh] BYREF
  int v77; // [rsp+E8h] [rbp+5Fh]

  v77 = a4;
  v74 = a2;
  BytesCopied = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( !(unsigned __int8)AfdCheckAndReferenceConnection(a2) )
    return 3221226011LL;
  v9 = *(_QWORD *)(v74 + 8);
  if ( !v9 )
  {
    v10 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v74 + 48), 0xFFFFFFFFFFFFFFFFuLL);
    v60 = v10 <= 1;
    v11 = v10 - 1;
    if ( v60 )
    {
      v12 = v11 == 0;
LABEL_92:
      if ( !v12 )
        __fastfail(0xEu);
      AfdCloseConnection(v74);
    }
    return 3221226011LL;
  }
  v13 = a6;
  *a6 = 0;
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v9 + 56), &LockHandle);
  v14 = v74;
  if ( (*(_WORD *)v9 & 0xAFD4) == 0xAFD4 && *(_QWORD *)(v74 + 8) != v9 )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v9 = *(_QWORD *)(v74 + 8);
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v9 + 56), &LockHandle);
    v14 = v74;
  }
  if ( (*(_DWORD *)(v9 + 8) & 0x20800) != 0 )
  {
    v72 = Size;
    if ( (BYTE9(xmmword_1400875E0) & 0x10) != 0 )
      WPP_SF_Dq(1292, 17, WPP_94063a909a5b3f5b0152c31595e93fc7_Traceguids, (unsigned int)Size, v9);
    *v13 = v72;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    AFDETW_TRACEABORT(2, 8019, v9, (*(_DWORD *)(v9 + 8) & 0x20000) != 0 ? 11 : 13);
    AfdBeginAbort(v74);
    goto LABEL_104;
  }
  v15 = a3 & 0x40;
  if ( (a3 & 0x40) != 0 )
  {
    v67 = Size;
    BytesCopied = Size;
    if ( *(_WORD *)(v14 + 98) != 16 )
    {
      Buffer = AfdGetBuffer((unsigned int)Size, 0, *(struct _KPROCESS **)(v14 + 32), 0);
      if ( Buffer )
      {
LABEL_99:
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        v68 = *(_QWORD *)(Buffer + 104);
        *(_QWORD *)(Buffer + 48) = v74;
        *(_WORD *)(Buffer + 96) = ((a3 & 0x400) == 0 ? 4 : 0) | *(_WORD *)(Buffer + 96) & 0xFFFA | (v15 != 0);
        v69 = *(_QWORD *)(v68 + 184);
        *(_QWORD *)(v69 - 16) = &AfdRestartBufferReceive;
        *(_QWORD *)(v69 - 8) = Buffer;
        *(_BYTE *)(v69 - 69) = -32;
        v70 = *(_QWORD *)(v68 + 184);
        *(_WORD *)(v70 - 72) = 2063;
        *(_QWORD *)(v70 - 32) = *(_QWORD *)(v74 + 24);
        *(_QWORD *)(v70 - 24) = *(_QWORD *)(v74 + 16);
        *(_DWORD *)(v70 - 60) = a3 & 0x60;
        *(_DWORD *)(v70 - 64) = BytesCopied;
        --*(_BYTE *)(v68 + 67);
        v71 = a8;
        *(_QWORD *)(v68 + 184) -= 72LL;
        *v71 = v68;
        return 3221225494LL;
      }
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    AFDETW_TRACEABORT(2, 8020, v9, 10);
    AfdBeginAbort(v74);
    *v13 = v67;
LABEL_104:
    v73 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v74 + 48), 0xFFFFFFFFFFFFFFFFuLL);
    v60 = v73 <= 1;
    v61 = v73 - 1;
    goto LABEL_105;
  }
  if ( (*(_DWORD *)(v14 + 4) & 0x40000000) != 0 )
  {
    v16 = Size;
    if ( ((unsigned __int8)(v15 + 16) & BYTE9(xmmword_1400875E0)) != 0 )
    {
      WPP_SF_qD(1292, (unsigned int)(v15 + 18), WPP_94063a909a5b3f5b0152c31595e93fc7_Traceguids, v14, Size);
      v14 = v74;
    }
    *(_DWORD *)(v14 + 100) = v16;
LABEL_90:
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v65 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v74 + 48), 0xFFFFFFFFFFFFFFFFuLL);
    v60 = v65 <= 1;
    v66 = v65 - 1;
    if ( !v60 )
      return 3221226011LL;
    v12 = v66 == 0;
    goto LABEL_92;
  }
  v17 = (unsigned int)Size;
  *(_DWORD *)(v14 + 100) = 0;
  while ( 1 )
  {
    v18 = v74;
    v19 = (_QWORD *)(v74 + 56);
    v20 = *(_QWORD **)(v74 + 56);
    if ( v20 == (_QWORD *)(v74 + 56) )
      goto LABEL_23;
    if ( (_QWORD *)v20[1] != v19 )
      goto LABEL_71;
    v21 = *v20;
    if ( *(_QWORD **)(*v20 + 8LL) != v20 )
      goto LABEL_71;
    *v19 = v21;
    v22 = v20 - 21;
    *(_QWORD *)(v21 + 8) = v19;
    v23 = (_DWORD *)v20[2];
    v24 = v23[2] - v23[4];
    v25 = v23[6];
    BytesCopied = v24;
    v26 = v25 & 0x4000;
    if ( v26 )
    {
      if ( v24 != (_DWORD)v17 )
        break;
      v27 = v77;
      if ( v77 != (_DWORD)v17 )
        break;
      goto LABEL_34;
    }
    if ( v24 < (unsigned int)v17 || (v23[6] & 0xA0) != 0x20 )
      break;
    v27 = v77;
LABEL_34:
    if ( _InterlockedExchange64(v22 + 13, 0) )
    {
      if ( (a3 & 0x400) == 0 || v27 != (_DWORD)v17 || v26 && BytesCopied != (_DWORD)v17 )
      {
        --*(_DWORD *)(v74 + 136);
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        if ( (AfdIgnorePushBitOnReceives || (*(_DWORD *)(v9 + 16) & 0x2000) != 0) && !v26 )
          BytesCopied = v17;
        v41 = v23[4];
        if ( v41 )
        {
          v22[1] = AfdAdvanceMdlChain((PMDL)v22[1], v41 - v23[8]);
          *((_QWORD *)v23 + 4) = (unsigned int)v23[4];
        }
        v42 = v22[23];
        *(_QWORD *)(v42 - 8) = v74;
        *(_QWORD *)(v42 - 16) = AfdRestartBufferReceiveWithUserIrp;
        *(_BYTE *)(v42 - 69) = -32;
        v43 = v22[23];
        *(_WORD *)(v43 - 72) = 2063;
        *(_QWORD *)(v43 - 32) = *(_QWORD *)(v74 + 24);
        *(_QWORD *)(v43 - 24) = *(_QWORD *)(v74 + 16);
        *(_DWORD *)(v43 - 60) = a3 & 0x60 | v23[6] & 0x4000;
        *(_DWORD *)(v43 - 64) = BytesCopied;
        _InterlockedAdd((volatile signed __int32 *)(v9 + 248), 1u);
        --*((_BYTE *)v22 + 67);
        v44 = a8;
        v22[23] -= 72LL;
        *v44 = v22;
        return 3221225494LL;
      }
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v34 = (struct _MDL *)v22[1];
      if ( !v34 )
      {
        v37 = v23[4];
        goto LABEL_45;
      }
      v35 = AfdMapMdlChain(v34);
      if ( v35 >= 0 )
      {
        TdiCopyBufferToMdl(Src, 0, v17, (PMDL)v22[1], v23[4] - v23[8], &BytesCopied);
        v37 = v23[4] + BytesCopied;
LABEL_45:
        v22[7] = v37;
        if ( (BYTE1(xmmword_1400875E0) & 0x10) != 0 )
          WPP_SF_qqLP(1036, 19, WPP_94063a909a5b3f5b0152c31595e93fc7_Traceguids, v9, v22, *((_DWORD *)v22 + 12), v37);
        IofCompleteRequest((PIRP)v22, AfdPriorityBoost);
        v38 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v74 + 48), 0xFFFFFFFFFFFFFFFFuLL);
        v60 = v38 <= 1;
        v39 = v38 - 1;
        if ( v60 )
        {
          if ( v39 )
            __fastfail(0xEu);
          AfdCloseConnection(v74);
        }
        *a6 = v17;
        return 0;
      }
      v36 = AfdPriorityBoost;
      *((_DWORD *)v22 + 12) = v35;
      v22[7] = 0;
      IofCompleteRequest((PIRP)v22, v36);
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v9 + 56), &LockHandle);
    }
    else
    {
      *v20 = 0;
    }
  }
  v28 = (_QWORD *)(v74 + 56);
  v29 = *(_QWORD *)(v74 + 56);
  if ( *(_QWORD *)(v29 + 8) != v74 + 56 )
    goto LABEL_71;
  *v20 = v29;
  v20[1] = v28;
  *(_QWORD *)(v29 + 8) = v20;
  *v28 = v20;
  v18 = v74;
LABEL_23:
  if ( *(_DWORD *)(v18 + 88) >= *(_DWORD *)(v18 + 144) || *(_WORD *)(v18 + 96) == 0xFFFF )
  {
    *(_DWORD *)(v18 + 100) += v17;
    goto LABEL_90;
  }
  if ( (a3 & 0x400) == 0 || v77 != (_DWORD)v17 || *(_QWORD *)(v18 + 56) != v18 + 56 )
  {
    v62 = AfdLargeBufferSize;
    if ( (unsigned int)AfdLargeBufferSize < (unsigned int)v17
      || AfdIgnorePushBitOnReceives
      || (*(_DWORD *)(v9 + 16) & 0x2000) != 0 )
    {
      v62 = v17;
      BytesCopied = v17;
    }
    else
    {
      BytesCopied = AfdLargeBufferSize;
    }
    Buffer = AfdGetBuffer(v62, 0, *(struct _KPROCESS **)(v18 + 32), 0);
    if ( Buffer )
    {
      v15 = a3 & 0x40;
      --*(_DWORD *)(v74 + 136);
      goto LABEL_99;
    }
    goto LABEL_85;
  }
  v30 = AfdGetBuffer((unsigned int)v17, 0, *(struct _KPROCESS **)(v18 + 32), 0);
  v31 = v30;
  if ( !v30 )
  {
LABEL_85:
    *(_DWORD *)(v74 + 100) += v17;
    if ( !*(_DWORD *)(v74 + 88) )
    {
      v64 = *(_DWORD *)(v74 + 4);
      if ( (v64 & 0x10000000) == 0 )
      {
        *(_DWORD *)(v74 + 4) = v64 | 0x10000000;
        if ( _InterlockedIncrement64((volatile signed __int64 *)(v74 + 48)) <= 1 )
          __fastfail(0xEu);
        AfdLRListAddItem((PSLIST_ENTRY)(v74 + 192));
      }
    }
    goto LABEL_90;
  }
  v32 = *(_BYTE **)(v30 + 112);
  v33 = (char *)Src;
  if ( (a3 & 0x200) != 0 )
  {
    memmove(v32, Src, v17);
  }
  else
  {
    v45 = &v32[v17];
    while ( v32 < v45 )
    {
      v46 = *v33++;
      *v32++ = v46;
    }
  }
  *(_QWORD *)(v31 + 16) = 1;
  *(_WORD *)(v31 + 96) &= ~4u;
  v12 = g_AfdEtwTraceEnable == 0;
  *(_DWORD *)(v31 + 64) = v17;
  if ( !v12 )
  {
    v47 = *(_QWORD *)(v9 + 240);
    v48 = *(_WORD *)(v47 + 6);
    if ( v48 == 2 )
    {
      v49 = v47 + 8;
      v50 = 1;
      v51 = 4;
      v52 = v49 + 2;
      goto LABEL_69;
    }
    if ( v48 == 23 )
    {
      v49 = v47 + 8;
      v50 = 2;
      v51 = 16;
      v52 = v49 + 6;
LABEL_69:
      AfdEtwTraceEvent(AfdEtwTransGuid, v50, v52, v51, v49, 2, v31 + 64, 4, &v74, 8, 0, 0);
    }
  }
  v53 = v74 + 72;
  v54 = *(__int64 **)(v74 + 80);
  if ( *v54 != v74 + 72 )
LABEL_71:
    __fastfail(3u);
  *(_QWORD *)v31 = v53;
  *(_QWORD *)(v31 + 8) = v54;
  *v54 = v31;
  *(_QWORD *)(v53 + 8) = v31;
  *(_DWORD *)(v74 + 88) += v17;
  ++*(_WORD *)(v74 + 96);
  *a6 = v17;
  *(_BYTE *)(v9 + 33) = 0;
  if ( *(_WORD *)(v74 + 2) == 3 )
  {
    AfdIndicateEventSelectEvent(v9, 1, 0);
    AfdNotifySockEventsChangedUnderLock(v9, 1, 0);
    v56 = AfdIndicatePollEvent(v55, 1u, 0, &LockHandle);
    p_LockHandle = &LockHandle;
    if ( v56 )
      p_LockHandle = 0;
    AfdNotifySockIndicateEventsUnlock((struct _EX_RUNDOWN_REF *)v9, p_LockHandle, 0);
  }
  else
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  v58 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v74 + 48), 0xFFFFFFFFFFFFFFFFuLL);
  v59 = __OFSUB__(v58, 1);
  v61 = v58 - 1;
  v60 = (v61 < 0) ^ v59 | (v61 == 0);
LABEL_105:
  if ( v60 )
  {
    if ( v61 )
      __fastfail(0xEu);
    AfdCloseConnection(v74);
  }
  return 0;
}

```

## disassembly

```asm
0x14001bb20  mov     [rsp-8+arg_0], rbx
0x14001bb25  mov     [rsp-8+arg_18], r9d
0x14001bb2a  push    rbp
0x14001bb2b  push    rsi
0x14001bb2c  push    rdi
0x14001bb2d  push    r12
0x14001bb2f  push    r13
0x14001bb31  push    r14
0x14001bb33  push    r15
0x14001bb35  lea     rbp, [rsp-7]
0x14001bb3a  sub     rsp, 90h
0x14001bb41  xor     eax, eax
0x14001bb43  mov     [rbp+37h+var_58], rdx
0x14001bb47  xorps   xmm0, xmm0
0x14001bb4a  mov     qword ptr [rbp+37h+LockHandle.OldIrql], rax
0x14001bb4e  mov     rcx, rdx
0x14001bb51  mov     [rbp+37h+arg_8], eax
0x14001bb54  movups  xmmword ptr [rbp+37h+LockHandle.LockQueue.Next], xmm0
0x14001bb58  mov     r13d, r8d
0x14001bb5b  call    AfdCheckAndReferenceConnection
0x14001bb60  test    al, al
0x14001bb62  jz      loc_14001C223
0x14001bb68  mov     rcx, [rbp+37h+var_58]
0x14001bb6c  mov     rbx, [rcx+8]
0x14001bb70  test    rbx, rbx
0x14001bb73  jnz     short loc_14001BB91
0x14001bb75  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001bb79  lock xadd [rcx+30h], rax
0x14001bb7f  sub     rax, 1
0x14001bb83  jg      loc_14001C223
0x14001bb89  test    rax, rax
0x14001bb8c  jmp     loc_14001C218
0x14001bb91  mov     r15, [rbp+37h+arg_28]
0x14001bb95  lea     rcx, [rbx+38h]; SpinLock
0x14001bb99  lea     rdx, [rbp+37h+LockHandle]; LockHandle
0x14001bb9d  mov     dword ptr [r15], 0
0x14001bba4  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14001bbab  nop     dword ptr [rax+rax+00h]
0x14001bbb0  movzx   eax, word ptr [rbx]
0x14001bbb3  mov     ecx, 0AFD4h
0x14001bbb8  mov     r8, [rbp+37h+var_58]
0x14001bbbc  and     ax, cx
0x14001bbbf  cmp     ax, cx
0x14001bbc2  jnz     short loc_14001BBFA
0x14001bbc4  cmp     [r8+8], rbx
0x14001bbc8  jz      short loc_14001BBFA
0x14001bbca  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x14001bbce  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001bbd5  nop     dword ptr [rax+rax+00h]
0x14001bbda  mov     rax, [rbp+37h+var_58]
0x14001bbde  lea     rdx, [rbp+37h+LockHandle]; LockHandle
0x14001bbe2  mov     rbx, [rax+8]
0x14001bbe6  lea     rcx, [rbx+38h]; SpinLock
0x14001bbea  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14001bbf1  nop     dword ptr [rax+rax+00h]
0x14001bbf6  mov     r8, [rbp+37h+var_58]
0x14001bbfa  test    dword ptr [rbx+8], 20800h
0x14001bc01  jnz     loc_14001C36B
0x14001bc07  mov     r14d, r13d
0x14001bc0a  mov     r12d, r13d
0x14001bc0d  and     r14d, 40h
0x14001bc11  and     r12d, 400h
0x14001bc18  mov     [rbp+37h+var_60], r14d
0x14001bc1c  test    r14d, r14d
0x14001bc1f  jnz     loc_14001C252
0x14001bc25  test    dword ptr [r8+4], 40000000h
0x14001bc2d  jz      short loc_14001BC66
0x14001bc2f  mov     ebx, dword ptr [rbp+37h+Size]
0x14001bc32  lea     ecx, [r14+10h]
0x14001bc36  test    byte ptr cs:xmmword_1400875E0+9, cl
0x14001bc3c  jz      short loc_14001BC5D
0x14001bc3e  lea     edx, [rcx+2]
0x14001bc41  mov     [rsp+0C0h+DestinationOffset], ebx
0x14001bc45  mov     r9, r8
0x14001bc48  mov     ecx, 50Ch
0x14001bc4d  lea     r8, WPP_94063a909a5b3f5b0152c31595e93fc7_Traceguids
0x14001bc54  call    WPP_SF_qD
0x14001bc59  mov     r8, [rbp+37h+var_58]
0x14001bc5d  mov     [r8+64h], ebx
0x14001bc61  jmp     loc_14001C1F1
0x14001bc66  mov     edi, dword ptr [rbp+37h+Size]
0x14001bc69  mov     dword ptr [r8+64h], 0
0x14001bc71  mov     rcx, [rbp+37h+var_58]
0x14001bc75  lea     rax, [rcx+38h]
0x14001bc79  mov     rdx, [rax]
0x14001bc7c  cmp     rdx, rax
0x14001bc7f  jz      short loc_14001BCFF
0x14001bc81  cmp     [rdx+8], rax
0x14001bc85  jnz     loc_14001C099
0x14001bc8b  mov     rcx, [rdx]
0x14001bc8e  cmp     [rcx+8], rdx
0x14001bc92  jnz     loc_14001C099
0x14001bc98  mov     [rax], rcx
0x14001bc9b  lea     rsi, [rdx-0A8h]
0x14001bca2  mov     [rcx+8], rax
0x14001bca6  mov     r14, [rsi+0B8h]
0x14001bcad  mov     ecx, [r14+8]
0x14001bcb1  sub     ecx, [r14+10h]
0x14001bcb5  mov     r15d, [r14+18h]
0x14001bcb9  mov     [rbp+37h+arg_8], ecx
0x14001bcbc  and     r15d, 4000h
0x14001bcc3  jz      loc_14001BD7E
0x14001bcc9  cmp     ecx, edi
0x14001bccb  jnz     short loc_14001BCD8
0x14001bccd  mov     ecx, [rbp+37h+arg_18]
0x14001bcd0  cmp     ecx, edi
0x14001bcd2  jz      loc_14001BD97
0x14001bcd8  mov     rax, [rbp+37h+var_58]
0x14001bcdc  add     rax, 38h ; '8'
0x14001bce0  mov     rcx, [rax]
0x14001bce3  cmp     [rcx+8], rax
0x14001bce7  jnz     loc_14001C099
0x14001bced  mov     [rdx], rcx
0x14001bcf0  mov     [rdx+8], rax
0x14001bcf4  mov     [rcx+8], rdx
0x14001bcf8  mov     [rax], rdx
0x14001bcfb  mov     rcx, [rbp+37h+var_58]
0x14001bcff  mov     eax, [rcx+90h]
0x14001bd05  cmp     [rcx+58h], eax
0x14001bd08  jnb     loc_14001C244
0x14001bd0e  mov     eax, 0FFFFh
0x14001bd13  cmp     [rcx+60h], ax
0x14001bd17  jz      loc_14001C244
0x14001bd1d  test    r12d, r12d
0x14001bd20  jz      loc_14001C141
0x14001bd26  cmp     [rbp+37h+arg_18], edi
0x14001bd29  jnz     loc_14001C141
0x14001bd2f  lea     rax, [rcx+38h]
0x14001bd33  cmp     [rax], rax
0x14001bd36  jnz     loc_14001C141
0x14001bd3c  mov     r8, [rcx+20h]
0x14001bd40  xor     r9d, r9d
0x14001bd43  mov     ecx, edi; Length
0x14001bd45  xor     edx, edx
0x14001bd47  call    AfdGetBuffer
0x14001bd4c  mov     rsi, rax
0x14001bd4f  test    rax, rax
0x14001bd52  jz      loc_14001C197
0x14001bd58  mov     rcx, [rax+70h]; void *
0x14001bd5c  mov     r14d, 1
0x14001bd62  mov     rdx, [rbp+37h+Src]; Src
0x14001bd66  bt      r13d, 9
0x14001bd6b  jnb     loc_14001BFC6
0x14001bd71  mov     r8, rdi; Size
0x14001bd74  call    memmove
0x14001bd79  jmp     loc_14001BFDB
0x14001bd7e  cmp     ecx, edi
0x14001bd80  jb      loc_14001BCD8
0x14001bd86  mov     eax, [r14+18h]
0x14001bd8a  and     al, 0A0h
0x14001bd8c  cmp     al, 20h ; ' '
0x14001bd8e  jnz     loc_14001BCD8
0x14001bd94  mov     ecx, [rbp+37h+arg_18]
0x14001bd97  xor     eax, eax
0x14001bd99  xchg    rax, [rsi+68h]
0x14001bd9d  test    rax, rax
0x14001bda0  jnz     short loc_14001BDAA
0x14001bda2  mov     [rdx], rax
0x14001bda5  jmp     loc_14001BC71
0x14001bdaa  test    r12d, r12d
0x14001bdad  jz      loc_14001BEE8
0x14001bdb3  cmp     ecx, edi
0x14001bdb5  jnz     loc_14001BEE8
0x14001bdbb  test    r15d, r15d
0x14001bdbe  jz      short loc_14001BDC9
0x14001bdc0  cmp     [rbp+37h+arg_8], edi
0x14001bdc3  jnz     loc_14001BEE8
0x14001bdc9  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x14001bdcd  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001bdd4  nop     dword ptr [rax+rax+00h]
0x14001bdd9  mov     rcx, [rsi+8]; MemoryDescriptorList
0x14001bddd  test    rcx, rcx
0x14001bde0  jz      short loc_14001BE5B
0x14001bde2  call    AfdMapMdlChain
0x14001bde7  test    eax, eax
0x14001bde9  jns     short loc_14001BE24
0x14001bdeb  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14001bdf1  mov     rcx, rsi; Irp
0x14001bdf4  mov     [rsi+30h], eax
0x14001bdf7  mov     qword ptr [rsi+38h], 0
0x14001bdff  call    cs:__imp_IofCompleteRequest
0x14001be06  nop     dword ptr [rax+rax+00h]
0x14001be0b  lea     rcx, [rbx+38h]; SpinLock
0x14001be0f  lea     rdx, [rbp+37h+LockHandle]; LockHandle
0x14001be13  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14001be1a  nop     dword ptr [rax+rax+00h]
0x14001be1f  jmp     loc_14001BC71
0x14001be24  mov     ecx, [r14+10h]
0x14001be28  lea     rax, [rbp+37h+arg_8]
0x14001be2c  sub     ecx, [r14+20h]
0x14001be30  mov     r8d, edi; SourceBytesToCopy
0x14001be33  mov     r9, [rsi+8]; DestinationMdlChain
0x14001be37  xor     edx, edx; SourceOffset
0x14001be39  mov     [rsp+0C0h+BytesCopied], rax; BytesCopied
0x14001be3e  mov     [rsp+0C0h+DestinationOffset], ecx; DestinationOffset
0x14001be42  mov     rcx, [rbp+37h+Src]; SourceBuffer
0x14001be46  call    cs:__imp_TdiCopyBufferToMdl
0x14001be4d  nop     dword ptr [rax+rax+00h]
0x14001be52  mov     edx, [rbp+37h+arg_8]
0x14001be55  add     edx, [r14+10h]
0x14001be59  jmp     short loc_14001BE5F
0x14001be5b  mov     edx, [r14+10h]
0x14001be5f  mov     r8d, edx
0x14001be62  mov     ecx, 10h
0x14001be67  mov     [rsi+38h], r8
0x14001be6b  test    byte ptr cs:xmmword_1400875E0+1, cl
0x14001be71  jz      short loc_14001BE9B
0x14001be73  mov     eax, [rsi+30h]
0x14001be76  lea     edx, [rcx+3]
0x14001be79  mov     [rsp+0C0h+var_90], r8
0x14001be7e  mov     ecx, 40Ch
0x14001be83  mov     dword ptr [rsp+0C0h+BytesCopied], eax
0x14001be87  lea     r8, WPP_94063a909a5b3f5b0152c31595e93fc7_Traceguids
0x14001be8e  mov     r9, rbx
0x14001be91  mov     qword ptr [rsp+0C0h+DestinationOffset], rsi
0x14001be96  call    WPP_SF_qqLP
0x14001be9b  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14001bea1  mov     rcx, rsi; Irp
0x14001bea4  call    cs:__imp_IofCompleteRequest
0x14001beab  nop     dword ptr [rax+rax+00h]
0x14001beb0  mov     rax, [rbp+37h+var_58]
0x14001beb4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14001beb8  lock xadd [rax+30h], rcx
0x14001bebe  sub     rcx, 1
0x14001bec2  jg      short loc_14001BEDB
0x14001bec4  test    rcx, rcx
0x14001bec7  jnz     short loc_14001BED4
0x14001bec9  mov     rcx, [rbp+37h+var_58]
0x14001becd  call    AfdCloseConnection
0x14001bed2  jmp     short loc_14001BEDB
0x14001bed4  mov     ecx, 0Eh
0x14001bed9  int     29h; Win8: RtlFailFast(ecx)
0x14001bedb  mov     rax, [rbp+37h+arg_28]
0x14001bedf  mov     [rax], edi
0x14001bee1  xor     eax, eax
0x14001bee3  jmp     loc_14001C228
0x14001bee8  mov     rax, [rbp+37h+var_58]
0x14001beec  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x14001bef0  dec     dword ptr [rax+88h]
0x14001bef6  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001befd  nop     dword ptr [rax+rax+00h]
0x14001bf02  cmp     cs:AfdIgnorePushBitOnReceives, 0
0x14001bf09  jnz     short loc_14001BF14
0x14001bf0b  test    dword ptr [rbx+10h], 2000h
0x14001bf12  jz      short loc_14001BF1C
0x14001bf14  test    r15d, r15d
0x14001bf17  jnz     short loc_14001BF1C
0x14001bf19  mov     [rbp+37h+arg_8], edi
0x14001bf1c  mov     edx, [r14+10h]
0x14001bf20  test    edx, edx
0x14001bf22  jz      short loc_14001BF40
0x14001bf24  sub     edx, [r14+20h]; NumberOfBytes
0x14001bf28  xor     r8d, r8d
0x14001bf2b  mov     rcx, [rsi+8]; Mdl
0x14001bf2f  call    AfdAdvanceMdlChain
0x14001bf34  mov     [rsi+8], rax
0x14001bf38  mov     eax, [r14+10h]
0x14001bf3c  mov     [r14+20h], rax
0x14001bf40  mov     rcx, [rsi+0B8h]
0x14001bf47  lea     rdx, AfdRestartBufferReceiveWithUserIrp
0x14001bf4e  mov     rax, [rbp+37h+var_58]
0x14001bf52  and     r13d, 60h
0x14001bf56  mov     [rcx-8], rax
0x14001bf5a  mov     [rcx-10h], rdx
0x14001bf5e  mov     byte ptr [rcx-45h], 0E0h
0x14001bf62  mov     rdx, [rsi+0B8h]
0x14001bf69  mov     word ptr [rdx-48h], 80Fh
0x14001bf6f  mov     rax, [rbp+37h+var_58]
0x14001bf73  mov     rcx, [rax+18h]
0x14001bf77  mov     [rdx-20h], rcx
0x14001bf7b  mov     rax, [rbp+37h+var_58]
0x14001bf7f  mov     rcx, [rax+10h]
0x14001bf83  mov     [rdx-18h], rcx
0x14001bf87  mov     eax, [r14+18h]
0x14001bf8b  mov     r14d, 1
0x14001bf91  and     eax, 4000h
0x14001bf96  or      eax, r13d
0x14001bf99  mov     [rdx-3Ch], eax
0x14001bf9c  mov     eax, [rbp+37h+arg_8]
0x14001bf9f  mov     [rdx-40h], eax
0x14001bfa2  lock add [rbx+0F8h], r14d
0x14001bfaa  dec     byte ptr [rsi+43h]
0x14001bfad  mov     rax, [rbp+37h+arg_38]
0x14001bfb1  sub     qword ptr [rsi+0B8h], 48h ; 'H'
0x14001bfb9  mov     [rax], rsi
0x14001bfbc  mov     eax, 0C0000016h
0x14001bfc1  jmp     loc_14001C228
0x14001bfc6  lea     r8, [rcx+rdi]
0x14001bfca  jmp     short loc_14001BFD6
0x14001bfcc  mov     al, [rdx]
0x14001bfce  add     rdx, r14
0x14001bfd1  mov     [rcx], al
0x14001bfd3  add     rcx, r14
0x14001bfd6  cmp     rcx, r8
0x14001bfd9  jb      short loc_14001BFCC
0x14001bfdb  mov     eax, 0FFFBh
0x14001bfe0  mov     [rsi+10h], r14
0x14001bfe4  and     [rsi+60h], ax
0x14001bfe8  lea     r8, [rsi+40h]
0x14001bfec  cmp     cs:g_AfdEtwTraceEnable, 0
  ... truncated ...
```
