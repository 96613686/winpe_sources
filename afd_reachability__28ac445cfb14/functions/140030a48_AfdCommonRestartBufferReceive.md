# AfdCommonRestartBufferReceive

- ea: `0x140030a48`
- end: `0x140031049`
- name: `AfdCommonRestartBufferReceive`
- size: `1537`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `4`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x1400277f0`
- `0x14002e180`
- `0x140030a10`
- `0x140030a30`

## callees

- `0x14000f450`
- `0x140012610`
- `0x1400137a0`
- `0x140014460`
- `0x14001b0d0`
- `0x14001b800`
- `0x14001c708`
- `0x14001ceb0`
- `0x14001db90`
- `0x140029e10`
- `0x140030a48`
- `0x1400318a0`
- `0x140047c60`
- `0x14004efd0`
- `0x140053f28`
- `0x140093f18`
- `0x140093f78`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140030fcc`
- `ntoskrnl!IofCompleteRequest` at `0x140030fcc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140030ae1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140030c2a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140030def`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140030ee6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140030ae1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140030c2a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140030def`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140030ee6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140030ac8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140030c00`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140030c46`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140030ac8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140030c00`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140030c46`

## pseudocode

```c
__int64 __fastcall AfdCommonRestartBufferReceive(_QWORD *Entry, int a2, int a3)
{
  __int64 v3; // rax
  int v4; // r13d
  _QWORD *v5; // rbx
  __int64 v6; // rdi
  bool v7; // zf
  _DWORD *v8; // r14
  __int64 v9; // r9
  _WORD *v10; // rcx
  _WORD *v11; // r8
  _WORD *v12; // rcx
  __int64 v13; // rdx
  __int16 v14; // ax
  unsigned __int8 v15; // r12
  int v16; // eax
  __int64 v17; // rcx
  unsigned int v18; // eax
  unsigned int v19; // eax
  __int64 v20; // rax
  _QWORD *v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  struct _KLOCK_QUEUE_HANDLE *p_LockHandle; // rdx
  int v25; // ecx
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rsi
  int *v29; // r12
  int *v30; // r14
  __int64 v31; // rdx
  signed __int64 v32; // rcx
  bool v33; // cc
  signed __int64 v34; // rcx
  __int128 v36; // [rsp+60h] [rbp-19h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+70h] [rbp-9h] BYREF
  __int64 v38; // [rsp+E0h] [rbp+67h] BYREF

  *(_QWORD *)&LockHandle.OldIrql = 0;
  v3 = Entry[6];
  v4 = 1073741839;
  if ( a2 != -2147483643 )
    v4 = a2;
  v38 = Entry[6];
  v5 = Entry;
  LockHandle.LockQueue = 0;
  v36 = 0;
  v6 = *(_QWORD *)(v3 + 8);
  if ( v4 < 0 )
  {
    *(_DWORD *)(Entry[7] + 40LL) = *((_DWORD *)Entry + 18);
    AfdReturnBuffer((unsigned __int16 *)Entry, *(PEPROCESS *)(v38 + 32));
    if ( (*(_DWORD *)(v38 + 4) & 0x40000000) != 0 )
    {
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v6 + 56), &LockHandle);
      *(_DWORD *)(v38 + 4) &= ~0x40000000u;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
    AFDETW_TRACEABORT(2, 8021, v6, 14);
    AfdBeginAbort(v38);
    goto LABEL_74;
  }
  v7 = g_AfdEtwTraceEnable == 0;
  v8 = Entry + 8;
  *((_DWORD *)Entry + 16) = a3;
  v9 = 16;
  if ( !v7 )
  {
    v10 = *(_WORD **)(v6 + 240);
    if ( (*(_DWORD *)(v6 + 8) & 0x100) == 0 )
    {
      v14 = v10[3];
      if ( v14 == 2 )
      {
        v12 = v10 + 4;
        v13 = 1;
        v9 = 4;
        v11 = v12 + 1;
      }
      else
      {
        if ( v14 != 23 )
          goto LABEL_21;
        v12 = v10 + 4;
        v13 = 2;
        v11 = v12 + 3;
      }
LABEL_20:
      AfdEtwTraceEvent(AfdEtwTransGuid, v13, v11, v9, v12, 2, v8, 4, &v38, 8, 0, 0);
      goto LABEL_21;
    }
    if ( *v10 == 2 )
    {
      v11 = v10 + 2;
      v9 = 4;
      v12 = v10 + 1;
      v13 = 1;
    }
    else if ( *v10 == 23 )
    {
      v13 = 2;
      v11 = v10 + 4;
      v12 = v10 + 1;
    }
    else
    {
      v11 = 0;
      v12 = 0;
      v13 = 0;
      v9 = 0;
    }
    if ( (_DWORD)v13 )
      goto LABEL_20;
  }
LABEL_21:
  *((_QWORD *)&v36 + 1) = &v36;
  *(_QWORD *)&v36 = &v36;
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v6 + 56), &LockHandle);
  if ( (*(_WORD *)v6 & 0xAFD4) == 0xAFD4 && *(_QWORD *)(v38 + 8) != v6 )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v6 = *(_QWORD *)(v38 + 8);
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v6 + 56), &LockHandle);
  }
  v15 = v5[12] & 1;
  if ( !v15 )
  {
    v16 = *(_DWORD *)(v38 + 4);
    if ( (v16 & 0x40000000) != 0 )
    {
      *(_DWORD *)(v38 + 4) = v16 & 0xBFFFFFFF;
      v17 = v38;
      v18 = *(_DWORD *)(v38 + 100);
      if ( v18 <= *v8 )
      {
        *(_DWORD *)(v38 + 100) = 0;
      }
      else
      {
        *(_DWORD *)(v38 + 100) = v18 - *v8;
        if ( (BYTE9(xmmword_1400875E0) & 0x10) != 0 )
          WPP_SF_qLD(v17, 22);
      }
    }
    ++*(_DWORD *)(v38 + 136);
  }
  if ( *v8 )
  {
    v19 = AfdBFillPendingIrps(
            v38,
            v5[7],
            0,
            0,
            *v8,
            v15 | (v4 == 0 ? 2 : 0) | ((unsigned __int8)(~*(_BYTE *)(v6 + 4) & 0xF0) << 27),
            (__int64)&v36);
    AfdAdvanceBuffer(v5, v19);
  }
  if ( !*v8 )
  {
    if ( !*(_DWORD *)(v38 + 100)
      || (*(_DWORD *)(v6 + 8) & 0x100) != 0
      || (v25 = *(_DWORD *)(v38 + 4), (v25 & 0x110) != 0)
      || (*(_DWORD *)(v6 + 8) & 0x20800) != 0
      || (v25 & 0x10000000) != 0 )
    {
      if ( (*(_DWORD *)(v6 + 8) & 0x100) != 0
        && *(_QWORD *)(v38 + 56) != v38 + 56
        && (v5[12] & 1) == 0
        && (*(_DWORD *)(v38 + 4) & 0x10000000) == 0 )
      {
        AfdTLPostPendedReceives(v38, v6, &LockHandle);
      }
    }
    else
    {
      *(_DWORD *)(v38 + 4) = v25 | 0x10000000;
      if ( _InterlockedIncrement64((volatile signed __int64 *)(v38 + 48)) <= 1 )
        __fastfail(0xEu);
      AfdLRListAddItem((PSLIST_ENTRY)(v38 + 192));
    }
    goto LABEL_63;
  }
  v20 = v38 + 72;
  v5[2] = 1;
  v21 = *(_QWORD **)(v20 + 8);
  if ( *v21 != v20 )
LABEL_71:
    __fastfail(3u);
  v5[1] = v21;
  *v5 = v20;
  *v21 = v5;
  *(_QWORD *)(v20 + 8) = v5;
  v22 = *v8;
  if ( v15 )
  {
    *(_DWORD *)(v38 + 92) += v22;
    ++*(_WORD *)(v38 + 98);
  }
  else
  {
    *(_DWORD *)(v38 + 88) += v22;
    ++*(_WORD *)(v38 + 96);
  }
  if ( ((v4 - 1073741839) & 0xFFFFFFFD) != 0 )
    *((_WORD *)v5 + 48) &= ~4u;
  else
    *((_WORD *)v5 + 48) |= 4u;
  v5 = 0;
  if ( *(_WORD *)(v38 + 2) != 3 )
  {
LABEL_63:
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    goto LABEL_64;
  }
  *(_BYTE *)(v6 + 33) = 0;
  if ( v15 && (*(_DWORD *)(v6 + 8) & 0x80u) == 0 )
  {
    AfdIndicateEventSelectEvent(v6, 2, 0);
    if ( (unsigned __int8)AfdIndicatePollEvent(v6, 2, 0, &LockHandle) )
      goto LABEL_64;
    goto LABEL_63;
  }
  AfdIndicateEventSelectEvent(v6, 1, 0);
  AfdNotifySockEventsChangedUnderLock(v6, 1, 0);
  if ( (unsigned __int8)AfdIndicatePollEvent(v23, 1, 0, &LockHandle) )
    p_LockHandle = 0;
  else
    p_LockHandle = &LockHandle;
  AfdNotifySockIndicateEventsUnlock(v6, p_LockHandle, 0);
LABEL_64:
  while ( 1 )
  {
    v26 = v36;
    if ( (__int128 *)v36 == &v36 )
      break;
    if ( *(__int128 **)(v36 + 8) != &v36 )
      goto LABEL_71;
    v27 = *(_QWORD *)v36;
    if ( *(_QWORD *)(*(_QWORD *)v36 + 8LL) != (_QWORD)v36 )
      goto LABEL_71;
    *(_QWORD *)&v36 = *(_QWORD *)v36;
    *(_QWORD *)(v27 + 8) = &v36;
    v28 = v26 - 168;
    if ( (BYTE1(xmmword_1400875E0) & 0x10) != 0 )
    {
      v29 = (int *)(v28 + 56);
      v30 = (int *)(v28 + 48);
      WPP_SF_qqLP(
        1036,
        23,
        WPP_94063a909a5b3f5b0152c31595e93fc7_Traceguids,
        v6,
        v28,
        *(_DWORD *)(v28 + 48),
        *(_QWORD *)(v28 + 56));
    }
    else
    {
      v30 = (int *)(v26 - 120);
      v29 = (int *)(v26 - 112);
    }
    AFDETW_TRACERECV(1, 4121, *(_QWORD *)(v38 + 8), 0, 1, *(_QWORD *)(v28 + 8), *v29, *v30, v28, 1);
    IofCompleteRequest((PIRP)v28, AfdPriorityBoost);
  }
  if ( v5 )
  {
    v31 = v38;
    *((_WORD *)v5 + 48) &= ~1u;
    AfdReturnBuffer((unsigned __int16 *)v5, *(PEPROCESS *)(v31 + 32));
  }
LABEL_74:
  v32 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v38 + 48), 0xFFFFFFFFFFFFFFFFuLL);
  v33 = v32 <= 1;
  v34 = v32 - 1;
  if ( v33 )
  {
    if ( v34 )
      __fastfail(0xEu);
    AfdCloseConnection(v38);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x140030a48  push    rbp
0x140030a4a  push    rbx
0x140030a4b  push    rsi
0x140030a4c  push    rdi
0x140030a4d  push    r12
0x140030a4f  push    r13
0x140030a51  push    r14
0x140030a53  push    r15
0x140030a55  lea     rbp, [rsp-1Fh]
0x140030a5a  sub     rsp, 98h
0x140030a61  xor     eax, eax
0x140030a63  xorps   xmm0, xmm0
0x140030a66  cmp     edx, 80000005h
0x140030a6c  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x140030a70  mov     rax, [rcx+30h]
0x140030a74  mov     r13d, 4000000Fh
0x140030a7a  cmovnz  r13d, edx
0x140030a7e  mov     [rbp+57h+arg_0], rax
0x140030a82  xor     r12d, r12d
0x140030a85  mov     rbx, rcx
0x140030a88  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x140030a8c  movups  [rbp+57h+var_70], xmm0
0x140030a90  mov     rdi, [rax+8]
0x140030a94  test    r13d, r13d
0x140030a97  jns     short loc_140030B15
0x140030a99  mov     rcx, [rcx+38h]
0x140030a9d  mov     eax, [rbx+48h]
0x140030aa0  mov     [rcx+28h], eax
0x140030aa3  mov     rcx, rbx; Entry
0x140030aa6  mov     rdx, [rbp+57h+arg_0]
0x140030aaa  mov     rdx, [rdx+20h]; Process
0x140030aae  call    AfdReturnBuffer
0x140030ab3  mov     rax, [rbp+57h+arg_0]
0x140030ab7  test    dword ptr [rax+4], 40000000h
0x140030abe  jz      short loc_140030AED
0x140030ac0  lea     rcx, [rdi+38h]; SpinLock
0x140030ac4  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x140030ac8  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140030acf  nop     dword ptr [rax+rax+00h]
0x140030ad4  mov     rax, [rbp+57h+arg_0]
0x140030ad8  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x140030adc  btr     dword ptr [rax+4], 1Eh
0x140030ae1  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140030ae8  nop     dword ptr [rax+rax+00h]
0x140030aed  mov     r15d, 0Eh
0x140030af3  mov     r8, rdi
0x140030af6  mov     r9d, r15d
0x140030af9  mov     edx, 1F55h
0x140030afe  lea     ecx, [r15-0Ch]
0x140030b02  call    AFDETW_TRACEABORT
0x140030b07  mov     rcx, [rbp+57h+arg_0]
0x140030b0b  call    AfdBeginAbort
0x140030b10  jmp     loc_140031006
0x140030b15  cmp     cs:g_AfdEtwTraceEnable, r12d
0x140030b1c  lea     r14, [rcx+40h]
0x140030b20  mov     esi, 2
0x140030b25  mov     [r14], r8d
0x140030b28  lea     edx, [rsi+15h]
0x140030b2b  lea     r10d, [rsi+2]
0x140030b2f  lea     r9d, [rsi+0Eh]
0x140030b33  jz      loc_140030BE8
0x140030b39  mov     eax, [rdi+8]
0x140030b3c  mov     rcx, [rdi+0F0h]
0x140030b43  bt      eax, 8
0x140030b47  jnb     short loc_140030B82
0x140030b49  movzx   eax, word ptr [rcx]
0x140030b4c  cmp     ax, si
0x140030b4f  jnz     short loc_140030B60
0x140030b51  lea     r8, [rcx+4]
0x140030b55  mov     r9d, r10d
0x140030b58  add     rcx, rsi
0x140030b5b  lea     edx, [rsi-1]
0x140030b5e  jmp     short loc_140030B7C
0x140030b60  cmp     ax, dx
0x140030b63  jnz     short loc_140030B70
0x140030b65  mov     edx, esi
0x140030b67  lea     r8, [rcx+8]
0x140030b6b  add     rcx, rdx
0x140030b6e  jmp     short loc_140030B7C
0x140030b70  mov     r8, r12
0x140030b73  mov     rcx, r12
0x140030b76  mov     edx, r12d
0x140030b79  mov     r9d, r12d
0x140030b7c  test    edx, edx
0x140030b7e  jz      short loc_140030BE8
0x140030b80  jmp     short loc_140030BAC
0x140030b82  movzx   eax, word ptr [rcx+6]
0x140030b86  cmp     ax, si
0x140030b89  jnz     short loc_140030B9D
0x140030b8b  add     rcx, 8
0x140030b8f  mov     edx, 1
0x140030b94  mov     r9d, r10d
0x140030b97  lea     r8, [rcx+2]
0x140030b9b  jmp     short loc_140030BAC
0x140030b9d  cmp     ax, dx
0x140030ba0  jnz     short loc_140030BE8
0x140030ba2  add     rcx, 8
0x140030ba6  mov     edx, esi
0x140030ba8  lea     r8, [rcx+6]
0x140030bac  mov     [rsp+0D0h+var_78], r12
0x140030bb1  lea     rax, [rbp+57h+arg_0]
0x140030bb5  mov     [rsp+0D0h+var_80], r12
0x140030bba  mov     [rsp+0D0h+var_88], 8
0x140030bc3  mov     [rsp+0D0h+var_90], rax
0x140030bc8  mov     [rsp+0D0h+var_98], r10
0x140030bcd  mov     [rsp+0D0h+var_A0], r14
0x140030bd2  mov     [rsp+0D0h+var_A8], rsi
0x140030bd7  mov     [rsp+0D0h+var_B0], rcx
0x140030bdc  lea     rcx, AfdEtwTransGuid
0x140030be3  call    AfdEtwTraceEvent
0x140030be8  lea     rax, [rbp+57h+var_70]
0x140030bec  mov     qword ptr [rbp+57h+var_70+8], rax
0x140030bf0  lea     rcx, [rdi+38h]; SpinLock
0x140030bf4  lea     rax, [rbp+57h+var_70]
0x140030bf8  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x140030bfc  mov     qword ptr [rbp+57h+var_70], rax
0x140030c00  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140030c07  nop     dword ptr [rax+rax+00h]
0x140030c0c  movzx   eax, word ptr [rdi]
0x140030c0f  mov     ecx, 0AFD4h
0x140030c14  and     ax, cx
0x140030c17  cmp     ax, cx
0x140030c1a  jnz     short loc_140030C52
0x140030c1c  mov     rax, [rbp+57h+arg_0]
0x140030c20  cmp     [rax+8], rdi
0x140030c24  jz      short loc_140030C52
0x140030c26  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x140030c2a  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140030c31  nop     dword ptr [rax+rax+00h]
0x140030c36  mov     rax, [rbp+57h+arg_0]
0x140030c3a  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x140030c3e  mov     rdi, [rax+8]
0x140030c42  lea     rcx, [rdi+38h]; SpinLock
0x140030c46  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140030c4d  nop     dword ptr [rax+rax+00h]
0x140030c52  mov     r12b, [rbx+60h]
0x140030c56  mov     r9d, 1
0x140030c5c  and     r12b, r9b
0x140030c5f  movzx   r15d, r12b
0x140030c63  jnz     short loc_140030CCB
0x140030c65  mov     rcx, [rbp+57h+arg_0]
0x140030c69  mov     eax, [rcx+4]
0x140030c6c  bt      eax, 1Eh
0x140030c70  jnb     short loc_140030CC0
0x140030c72  btr     eax, 1Eh
0x140030c76  mov     [rcx+4], eax
0x140030c79  mov     rcx, [rbp+57h+arg_0]
0x140030c7d  mov     edx, [r14]
0x140030c80  mov     eax, [rcx+64h]
0x140030c83  cmp     eax, edx
0x140030c85  jbe     short loc_140030CB9
0x140030c87  sub     eax, edx
0x140030c89  mov     [rcx+64h], eax
0x140030c8c  test    byte ptr cs:xmmword_1400875E0+9, 10h
0x140030c93  jz      short loc_140030CC0
0x140030c95  lea     edx, [r9+15h]
0x140030c99  mov     r9, [rbp+57h+arg_0]
0x140030c9d  mov     eax, [r9+64h]
0x140030ca1  mov     dword ptr [rsp+0D0h+var_A8], eax
0x140030ca5  mov     eax, [r14]
0x140030ca8  mov     dword ptr [rsp+0D0h+var_B0], eax
0x140030cac  call    WPP_SF_qLD
0x140030cb1  mov     r9d, 1
0x140030cb7  jmp     short loc_140030CC0
0x140030cb9  mov     dword ptr [rcx+64h], 0
0x140030cc0  mov     rax, [rbp+57h+arg_0]
0x140030cc4  add     [rax+88h], r9d
0x140030ccb  mov     r8d, [r14]
0x140030cce  test    r8d, r8d
0x140030cd1  jz      short loc_140030D26
0x140030cd3  mov     al, [rdi+4]
0x140030cd6  not     al
0x140030cd8  movzx   edx, al
0x140030cdb  mov     eax, r13d
0x140030cde  and     edx, 0FFFFFFF0h
0x140030ce1  shl     edx, 1Bh
0x140030ce4  neg     eax
0x140030ce6  lea     rax, [rbp+57h+var_70]
0x140030cea  sbb     ecx, ecx
0x140030cec  mov     [rsp+0D0h+var_A0], rax
0x140030cf1  not     ecx
0x140030cf3  xor     r9d, r9d
0x140030cf6  and     ecx, esi
0x140030cf8  or      edx, ecx
0x140030cfa  mov     rcx, [rbp+57h+arg_0]
0x140030cfe  or      edx, r15d
0x140030d01  mov     dword ptr [rsp+0D0h+var_A8], edx
0x140030d05  mov     rdx, [rbx+38h]
0x140030d09  mov     dword ptr [rsp+0D0h+var_B0], r8d
0x140030d0e  xor     r8d, r8d
0x140030d11  call    AfdBFillPendingIrps
0x140030d16  mov     edx, eax
0x140030d18  mov     rcx, rbx
0x140030d1b  call    AfdAdvanceBuffer
0x140030d20  mov     r9d, 1
0x140030d26  cmp     dword ptr [r14], 0
0x140030d2a  mov     r15d, 0Eh
0x140030d30  mov     rax, [rbp+57h+arg_0]
0x140030d34  jbe     loc_140030E49
0x140030d3a  add     rax, 48h ; 'H'
0x140030d3e  mov     [rbx+10h], r9
0x140030d42  mov     rcx, [rax+8]
0x140030d46  cmp     [rcx], rax
0x140030d49  jnz     loc_140030FDD
0x140030d4f  mov     [rbx+8], rcx
0x140030d53  mov     [rbx], rax
0x140030d56  mov     [rcx], rbx
0x140030d59  mov     [rax+8], rbx
0x140030d5d  mov     rcx, [rbp+57h+arg_0]
0x140030d61  mov     eax, [r14]
0x140030d64  test    r12b, r12b
0x140030d67  jz      short loc_140030D77
0x140030d69  add     [rcx+5Ch], eax
0x140030d6c  mov     rax, [rbp+57h+arg_0]
0x140030d70  add     [rax+62h], r9w
0x140030d75  jmp     short loc_140030D83
0x140030d77  add     [rcx+58h], eax
0x140030d7a  mov     rax, [rbp+57h+arg_0]
0x140030d7e  add     [rax+60h], r9w
0x140030d83  lea     eax, [r13-4000000Fh]
0x140030d8a  test    eax, 0FFFFFFFDh
0x140030d8f  jz      short loc_140030D9C
0x140030d91  mov     eax, 0FFFBh
0x140030d96  and     [rbx+60h], ax
0x140030d9a  jmp     short loc_140030DA5
0x140030d9c  mov     eax, 4
0x140030da1  or      [rbx+60h], ax
0x140030da5  mov     rax, [rbp+57h+arg_0]
0x140030da9  xor     ebx, ebx
0x140030dab  lea     r13d, [rbx+3]
0x140030daf  cmp     [rax+2], r13w
0x140030db4  jnz     short loc_140030DEB
0x140030db6  mov     [rdi+21h], bl
0x140030db9  test    r12b, r12b
0x140030dbc  jz      short loc_140030E00
0x140030dbe  mov     eax, [rdi+8]
0x140030dc1  test    al, al
0x140030dc3  js      short loc_140030E00
0x140030dc5  xor     r8d, r8d
0x140030dc8  mov     edx, esi
0x140030dca  mov     rcx, rdi
0x140030dcd  call    AfdIndicateEventSelectEvent
0x140030dd2  lea     r9, [rbp+57h+LockHandle]
0x140030dd6  xor     r8d, r8d
0x140030dd9  mov     edx, esi
0x140030ddb  mov     rcx, rdi
0x140030dde  call    AfdIndicatePollEvent
0x140030de3  test    al, al
0x140030de5  jnz     loc_140030EF8
0x140030deb  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x140030def  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140030df6  nop     dword ptr [rax+rax+00h]
0x140030dfb  jmp     loc_140030EF8
0x140030e00  xor     r8d, r8d
0x140030e03  mov     edx, r9d
0x140030e06  mov     rcx, rdi
0x140030e09  call    AfdIndicateEventSelectEvent
0x140030e0e  xor     r8d, r8d
0x140030e11  mov     rcx, rdi
0x140030e14  lea     edx, [r8+1]
0x140030e18  call    AfdNotifySockEventsChangedUnderLock
0x140030e1d  xor     r8d, r8d
0x140030e20  lea     r9, [rbp+57h+LockHandle]
0x140030e24  lea     edx, [r8+1]
0x140030e28  call    AfdIndicatePollEvent
0x140030e2d  xor     r8d, r8d
0x140030e30  mov     rcx, rdi
0x140030e33  test    al, al
0x140030e35  jnz     short loc_140030E45
0x140030e37  lea     rdx, [rbp+57h+LockHandle]
0x140030e3b  call    AfdNotifySockIndicateEventsUnlock
0x140030e40  jmp     loc_140030EF8
0x140030e45  xor     edx, edx
0x140030e47  jmp     short loc_140030E3B
0x140030e49  cmp     dword ptr [rax+64h], 0
0x140030e4d  mov     r8d, 10000000h
0x140030e53  jbe     short loc_140030EB4
0x140030e55  mov     eax, [rdi+8]
0x140030e58  bt      eax, 8
0x140030e5c  jb      short loc_140030EB4
0x140030e5e  mov     rdx, [rbp+57h+arg_0]
0x140030e62  mov     ecx, [rdx+4]
0x140030e65  test    ecx, 110h
0x140030e6b  jnz     short loc_140030EB4
0x140030e6d  test    dword ptr [rdi+8], 20800h
0x140030e74  jnz     short loc_140030EB4
0x140030e76  test    r8d, ecx
0x140030e79  jnz     short loc_140030EB4
0x140030e7b  or      ecx, r8d
0x140030e7e  mov     [rdx+4], ecx
0x140030e81  mov     rcx, r9
0x140030e84  mov     rax, [rbp+57h+arg_0]
0x140030e88  lock xadd [rax+30h], rcx
0x140030e8e  add     rcx, r9
0x140030e91  cmp     rcx, r9
0x140030e94  jg      short loc_140030E9B
0x140030e96  mov     rcx, r15
0x140030e99  int     29h; Win8: RtlFailFast(ecx)
0x140030e9b  mov     rcx, [rbp+57h+arg_0]
0x140030e9f  lea     rdx, AfdLRRepostReceive
  ... truncated ...
```
