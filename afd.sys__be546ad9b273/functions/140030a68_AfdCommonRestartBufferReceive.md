# AfdCommonRestartBufferReceive

- ea: `0x140030a68`
- end: `0x140031069`
- name: `AfdCommonRestartBufferReceive`
- size: `1537`
- prototype: `__int64 __fastcall(_QWORD *Entry, int, int)`
- caller_count: `4`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x1400277f0`
- `0x14002e180`
- `0x140030a30`
- `0x140030a50`

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
- `0x140030a68`
- `0x1400318c0`
- `0x140047ce0`
- `0x14004f070`
- `0x140053fc8`
- `0x140093f18`
- `0x140093f78`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140030fec`
- `ntoskrnl!IofCompleteRequest` at `0x140030fec`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140030b01`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140030c4a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140030e0f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140030f06`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140030b01`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140030c4a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140030e0f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140030f06`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140030ae8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140030c20`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140030c66`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140030ae8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140030c20`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140030c66`

## pseudocode

```c
__int64 __fastcall AfdCommonRestartBufferReceive(_QWORD *Entry, int a2, int a3)
{
  __int64 v3; // rax
  int v4; // r13d
  _BYTE *v5; // rbx
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
  _DWORD *v29; // r12
  _DWORD *v30; // r14
  __int64 v31; // rdx
  signed __int64 v32; // rcx
  bool v33; // cc
  signed __int64 v34; // rcx
  __int64 v36; // [rsp+48h] [rbp-31h]
  __int128 v37; // [rsp+60h] [rbp-19h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+70h] [rbp-9h] BYREF
  __int64 v39; // [rsp+E0h] [rbp+67h] BYREF

  *(_QWORD *)&LockHandle.OldIrql = 0;
  v3 = Entry[6];
  v4 = 1073741839;
  if ( a2 != -2147483643 )
    v4 = a2;
  v39 = Entry[6];
  v5 = Entry;
  LockHandle.LockQueue = 0;
  v37 = 0;
  v6 = *(_QWORD *)(v3 + 8);
  if ( v4 < 0 )
  {
    *(_DWORD *)(Entry[7] + 40LL) = *((_DWORD *)Entry + 18);
    AfdReturnBuffer(Entry, *(PEPROCESS *)(v39 + 32));
    if ( (*(_DWORD *)(v39 + 4) & 0x40000000) != 0 )
    {
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v6 + 56), &LockHandle);
      *(_DWORD *)(v39 + 4) &= ~0x40000000u;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
    AFDETW_TRACEABORT(2, 8021, v6);
    AfdBeginAbort(v39);
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
      AfdEtwTraceEvent(AfdEtwTransGuid, v13, v11, v9, v12, 2, v8, 4, &v39, 8, 0, 0);
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
  *((_QWORD *)&v37 + 1) = &v37;
  *(_QWORD *)&v37 = &v37;
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v6 + 56), &LockHandle);
  if ( (*(_WORD *)v6 & 0xAFD4) == 0xAFD4 && *(_QWORD *)(v39 + 8) != v6 )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v6 = *(_QWORD *)(v39 + 8);
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v6 + 56), &LockHandle);
  }
  v15 = v5[96] & 1;
  if ( !v15 )
  {
    v16 = *(_DWORD *)(v39 + 4);
    if ( (v16 & 0x40000000) != 0 )
    {
      *(_DWORD *)(v39 + 4) = v16 & 0xBFFFFFFF;
      v17 = v39;
      v18 = *(_DWORD *)(v39 + 100);
      if ( v18 <= *v8 )
      {
        *(_DWORD *)(v39 + 100) = 0;
      }
      else
      {
        *(_DWORD *)(v39 + 100) = v18 - *v8;
        if ( (BYTE9(xmmword_1400875E0) & 0x10) != 0 )
          WPP_SF_qLD(v17, 22);
      }
    }
    ++*(_DWORD *)(v39 + 136);
  }
  if ( *v8 )
  {
    v19 = AfdBFillPendingIrps(
            v39,
            *((_QWORD *)v5 + 7),
            0,
            0,
            *v8,
            v15 | (v4 == 0 ? 2 : 0) | ((unsigned __int8)(~*(_BYTE *)(v6 + 4) & 0xF0) << 27),
            (__int64)&v37);
    AfdAdvanceBuffer(v5, v19);
  }
  if ( !*v8 )
  {
    if ( !*(_DWORD *)(v39 + 100)
      || (*(_DWORD *)(v6 + 8) & 0x100) != 0
      || (v25 = *(_DWORD *)(v39 + 4), (v25 & 0x110) != 0)
      || (*(_DWORD *)(v6 + 8) & 0x20800) != 0
      || (v25 & 0x10000000) != 0 )
    {
      if ( (*(_DWORD *)(v6 + 8) & 0x100) != 0
        && *(_QWORD *)(v39 + 56) != v39 + 56
        && (v5[96] & 1) == 0
        && (*(_DWORD *)(v39 + 4) & 0x10000000) == 0 )
      {
        AfdTLPostPendedReceives(v39, v6, &LockHandle);
      }
    }
    else
    {
      *(_DWORD *)(v39 + 4) = v25 | 0x10000000;
      if ( _InterlockedIncrement64((volatile signed __int64 *)(v39 + 48)) <= 1 )
        __fastfail(0xEu);
      AfdLRListAddItem((PSLIST_ENTRY)(v39 + 192));
    }
    goto LABEL_63;
  }
  v20 = v39 + 72;
  *((_QWORD *)v5 + 2) = 1;
  v21 = *(_QWORD **)(v20 + 8);
  if ( *v21 != v20 )
LABEL_71:
    __fastfail(3u);
  *((_QWORD *)v5 + 1) = v21;
  *(_QWORD *)v5 = v20;
  *v21 = v5;
  *(_QWORD *)(v20 + 8) = v5;
  v22 = *v8;
  if ( v15 )
  {
    *(_DWORD *)(v39 + 92) += v22;
    ++*(_WORD *)(v39 + 98);
  }
  else
  {
    *(_DWORD *)(v39 + 88) += v22;
    ++*(_WORD *)(v39 + 96);
  }
  if ( ((v4 - 1073741839) & 0xFFFFFFFD) != 0 )
    *((_WORD *)v5 + 48) &= ~4u;
  else
    *((_WORD *)v5 + 48) |= 4u;
  v5 = 0;
  if ( *(_WORD *)(v39 + 2) != 3 )
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
    v26 = v37;
    if ( (__int128 *)v37 == &v37 )
      break;
    if ( *(__int128 **)(v37 + 8) != &v37 )
      goto LABEL_71;
    v27 = *(_QWORD *)v37;
    if ( *(_QWORD *)(*(_QWORD *)v37 + 8LL) != (_QWORD)v37 )
      goto LABEL_71;
    *(_QWORD *)&v37 = *(_QWORD *)v37;
    *(_QWORD *)(v27 + 8) = &v37;
    v28 = v26 - 168;
    if ( (BYTE1(xmmword_1400875E0) & 0x10) != 0 )
    {
      v29 = (_DWORD *)(v28 + 56);
      v30 = (_DWORD *)(v28 + 48);
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
      v30 = (_DWORD *)(v26 - 120);
      v29 = (_DWORD *)(v26 - 112);
    }
    LOBYTE(v36) = 1;
    AFDETW_TRACERECV(1, 4121, *(_QWORD *)(v39 + 8), 0, 1, *(_QWORD *)(v28 + 8), *v29, *v30, v28, v36);
    IofCompleteRequest((PIRP)v28, AfdPriorityBoost);
  }
  if ( v5 )
  {
    v31 = v39;
    *((_WORD *)v5 + 48) &= ~1u;
    AfdReturnBuffer(v5, *(PEPROCESS *)(v31 + 32));
  }
LABEL_74:
  v32 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v39 + 48), 0xFFFFFFFFFFFFFFFFuLL);
  v33 = v32 <= 1;
  v34 = v32 - 1;
  if ( v33 )
  {
    if ( v34 )
      __fastfail(0xEu);
    AfdCloseConnection(v39);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x140030a68  push    rbp
0x140030a6a  push    rbx
0x140030a6b  push    rsi
0x140030a6c  push    rdi
0x140030a6d  push    r12
0x140030a6f  push    r13
0x140030a71  push    r14
0x140030a73  push    r15
0x140030a75  lea     rbp, [rsp-1Fh]
0x140030a7a  sub     rsp, 98h
0x140030a81  xor     eax, eax
0x140030a83  xorps   xmm0, xmm0
0x140030a86  cmp     edx, 80000005h
0x140030a8c  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x140030a90  mov     rax, [rcx+30h]
0x140030a94  mov     r13d, 4000000Fh
0x140030a9a  cmovnz  r13d, edx
0x140030a9e  mov     [rbp+57h+arg_0], rax
0x140030aa2  xor     r12d, r12d
0x140030aa5  mov     rbx, rcx
0x140030aa8  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x140030aac  movups  [rbp+57h+var_70], xmm0
0x140030ab0  mov     rdi, [rax+8]
0x140030ab4  test    r13d, r13d
0x140030ab7  jns     short loc_140030B35
0x140030ab9  mov     rcx, [rcx+38h]
0x140030abd  mov     eax, [rbx+48h]
0x140030ac0  mov     [rcx+28h], eax
0x140030ac3  mov     rcx, rbx; Entry
0x140030ac6  mov     rdx, [rbp+57h+arg_0]
0x140030aca  mov     rdx, [rdx+20h]; Process
0x140030ace  call    AfdReturnBuffer
0x140030ad3  mov     rax, [rbp+57h+arg_0]
0x140030ad7  test    dword ptr [rax+4], 40000000h
0x140030ade  jz      short loc_140030B0D
0x140030ae0  lea     rcx, [rdi+38h]; SpinLock
0x140030ae4  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x140030ae8  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140030aef  nop     dword ptr [rax+rax+00h]
0x140030af4  mov     rax, [rbp+57h+arg_0]
0x140030af8  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x140030afc  btr     dword ptr [rax+4], 1Eh
0x140030b01  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140030b08  nop     dword ptr [rax+rax+00h]
0x140030b0d  mov     r15d, 0Eh
0x140030b13  mov     r8, rdi
0x140030b16  mov     r9d, r15d
0x140030b19  mov     edx, 1F55h
0x140030b1e  lea     ecx, [r15-0Ch]
0x140030b22  call    AFDETW_TRACEABORT
0x140030b27  mov     rcx, [rbp+57h+arg_0]
0x140030b2b  call    AfdBeginAbort
0x140030b30  jmp     loc_140031026
0x140030b35  cmp     cs:g_AfdEtwTraceEnable, r12d
0x140030b3c  lea     r14, [rcx+40h]
0x140030b40  mov     esi, 2
0x140030b45  mov     [r14], r8d
0x140030b48  lea     edx, [rsi+15h]
0x140030b4b  lea     r10d, [rsi+2]
0x140030b4f  lea     r9d, [rsi+0Eh]
0x140030b53  jz      loc_140030C08
0x140030b59  mov     eax, [rdi+8]
0x140030b5c  mov     rcx, [rdi+0F0h]
0x140030b63  bt      eax, 8
0x140030b67  jnb     short loc_140030BA2
0x140030b69  movzx   eax, word ptr [rcx]
0x140030b6c  cmp     ax, si
0x140030b6f  jnz     short loc_140030B80
0x140030b71  lea     r8, [rcx+4]
0x140030b75  mov     r9d, r10d
0x140030b78  add     rcx, rsi
0x140030b7b  lea     edx, [rsi-1]
0x140030b7e  jmp     short loc_140030B9C
0x140030b80  cmp     ax, dx
0x140030b83  jnz     short loc_140030B90
0x140030b85  mov     edx, esi
0x140030b87  lea     r8, [rcx+8]
0x140030b8b  add     rcx, rdx
0x140030b8e  jmp     short loc_140030B9C
0x140030b90  mov     r8, r12
0x140030b93  mov     rcx, r12
0x140030b96  mov     edx, r12d
0x140030b99  mov     r9d, r12d
0x140030b9c  test    edx, edx
0x140030b9e  jz      short loc_140030C08
0x140030ba0  jmp     short loc_140030BCC
0x140030ba2  movzx   eax, word ptr [rcx+6]
0x140030ba6  cmp     ax, si
0x140030ba9  jnz     short loc_140030BBD
0x140030bab  add     rcx, 8
0x140030baf  mov     edx, 1
0x140030bb4  mov     r9d, r10d
0x140030bb7  lea     r8, [rcx+2]
0x140030bbb  jmp     short loc_140030BCC
0x140030bbd  cmp     ax, dx
0x140030bc0  jnz     short loc_140030C08
0x140030bc2  add     rcx, 8
0x140030bc6  mov     edx, esi
0x140030bc8  lea     r8, [rcx+6]
0x140030bcc  mov     [rsp+0D0h+var_78], r12
0x140030bd1  lea     rax, [rbp+57h+arg_0]
0x140030bd5  mov     [rsp+0D0h+var_80], r12
0x140030bda  mov     [rsp+0D0h+var_88], 8
0x140030be3  mov     [rsp+0D0h+var_90], rax
0x140030be8  mov     [rsp+0D0h+var_98], r10
0x140030bed  mov     [rsp+0D0h+var_A0], r14
0x140030bf2  mov     [rsp+0D0h+var_A8], rsi
0x140030bf7  mov     [rsp+0D0h+var_B0], rcx
0x140030bfc  lea     rcx, AfdEtwTransGuid
0x140030c03  call    AfdEtwTraceEvent
0x140030c08  lea     rax, [rbp+57h+var_70]
0x140030c0c  mov     qword ptr [rbp+57h+var_70+8], rax
0x140030c10  lea     rcx, [rdi+38h]; SpinLock
0x140030c14  lea     rax, [rbp+57h+var_70]
0x140030c18  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x140030c1c  mov     qword ptr [rbp+57h+var_70], rax
0x140030c20  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140030c27  nop     dword ptr [rax+rax+00h]
0x140030c2c  movzx   eax, word ptr [rdi]
0x140030c2f  mov     ecx, 0AFD4h
0x140030c34  and     ax, cx
0x140030c37  cmp     ax, cx
0x140030c3a  jnz     short loc_140030C72
0x140030c3c  mov     rax, [rbp+57h+arg_0]
0x140030c40  cmp     [rax+8], rdi
0x140030c44  jz      short loc_140030C72
0x140030c46  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x140030c4a  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140030c51  nop     dword ptr [rax+rax+00h]
0x140030c56  mov     rax, [rbp+57h+arg_0]
0x140030c5a  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x140030c5e  mov     rdi, [rax+8]
0x140030c62  lea     rcx, [rdi+38h]; SpinLock
0x140030c66  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140030c6d  nop     dword ptr [rax+rax+00h]
0x140030c72  mov     r12b, [rbx+60h]
0x140030c76  mov     r9d, 1
0x140030c7c  and     r12b, r9b
0x140030c7f  movzx   r15d, r12b
0x140030c83  jnz     short loc_140030CEB
0x140030c85  mov     rcx, [rbp+57h+arg_0]
0x140030c89  mov     eax, [rcx+4]
0x140030c8c  bt      eax, 1Eh
0x140030c90  jnb     short loc_140030CE0
0x140030c92  btr     eax, 1Eh
0x140030c96  mov     [rcx+4], eax
0x140030c99  mov     rcx, [rbp+57h+arg_0]
0x140030c9d  mov     edx, [r14]
0x140030ca0  mov     eax, [rcx+64h]
0x140030ca3  cmp     eax, edx
0x140030ca5  jbe     short loc_140030CD9
0x140030ca7  sub     eax, edx
0x140030ca9  mov     [rcx+64h], eax
0x140030cac  test    byte ptr cs:xmmword_1400875E0+9, 10h
0x140030cb3  jz      short loc_140030CE0
0x140030cb5  lea     edx, [r9+15h]
0x140030cb9  mov     r9, [rbp+57h+arg_0]
0x140030cbd  mov     eax, [r9+64h]
0x140030cc1  mov     dword ptr [rsp+0D0h+var_A8], eax
0x140030cc5  mov     eax, [r14]
0x140030cc8  mov     dword ptr [rsp+0D0h+var_B0], eax
0x140030ccc  call    WPP_SF_qLD
0x140030cd1  mov     r9d, 1
0x140030cd7  jmp     short loc_140030CE0
0x140030cd9  mov     dword ptr [rcx+64h], 0
0x140030ce0  mov     rax, [rbp+57h+arg_0]
0x140030ce4  add     [rax+88h], r9d
0x140030ceb  mov     r8d, [r14]
0x140030cee  test    r8d, r8d
0x140030cf1  jz      short loc_140030D46
0x140030cf3  mov     al, [rdi+4]
0x140030cf6  not     al
0x140030cf8  movzx   edx, al
0x140030cfb  mov     eax, r13d
0x140030cfe  and     edx, 0FFFFFFF0h
0x140030d01  shl     edx, 1Bh
0x140030d04  neg     eax
0x140030d06  lea     rax, [rbp+57h+var_70]
0x140030d0a  sbb     ecx, ecx
0x140030d0c  mov     [rsp+0D0h+var_A0], rax
0x140030d11  not     ecx
0x140030d13  xor     r9d, r9d
0x140030d16  and     ecx, esi
0x140030d18  or      edx, ecx
0x140030d1a  mov     rcx, [rbp+57h+arg_0]
0x140030d1e  or      edx, r15d
0x140030d21  mov     dword ptr [rsp+0D0h+var_A8], edx
0x140030d25  mov     rdx, [rbx+38h]
0x140030d29  mov     dword ptr [rsp+0D0h+var_B0], r8d
0x140030d2e  xor     r8d, r8d
0x140030d31  call    AfdBFillPendingIrps
0x140030d36  mov     edx, eax
0x140030d38  mov     rcx, rbx
0x140030d3b  call    AfdAdvanceBuffer
0x140030d40  mov     r9d, 1
0x140030d46  cmp     dword ptr [r14], 0
0x140030d4a  mov     r15d, 0Eh
0x140030d50  mov     rax, [rbp+57h+arg_0]
0x140030d54  jbe     loc_140030E69
0x140030d5a  add     rax, 48h ; 'H'
0x140030d5e  mov     [rbx+10h], r9
0x140030d62  mov     rcx, [rax+8]
0x140030d66  cmp     [rcx], rax
0x140030d69  jnz     loc_140030FFD
0x140030d6f  mov     [rbx+8], rcx
0x140030d73  mov     [rbx], rax
0x140030d76  mov     [rcx], rbx
0x140030d79  mov     [rax+8], rbx
0x140030d7d  mov     rcx, [rbp+57h+arg_0]
0x140030d81  mov     eax, [r14]
0x140030d84  test    r12b, r12b
0x140030d87  jz      short loc_140030D97
0x140030d89  add     [rcx+5Ch], eax
0x140030d8c  mov     rax, [rbp+57h+arg_0]
0x140030d90  add     [rax+62h], r9w
0x140030d95  jmp     short loc_140030DA3
0x140030d97  add     [rcx+58h], eax
0x140030d9a  mov     rax, [rbp+57h+arg_0]
0x140030d9e  add     [rax+60h], r9w
0x140030da3  lea     eax, [r13-4000000Fh]
0x140030daa  test    eax, 0FFFFFFFDh
0x140030daf  jz      short loc_140030DBC
0x140030db1  mov     eax, 0FFFBh
0x140030db6  and     [rbx+60h], ax
0x140030dba  jmp     short loc_140030DC5
0x140030dbc  mov     eax, 4
0x140030dc1  or      [rbx+60h], ax
0x140030dc5  mov     rax, [rbp+57h+arg_0]
0x140030dc9  xor     ebx, ebx
0x140030dcb  lea     r13d, [rbx+3]
0x140030dcf  cmp     [rax+2], r13w
0x140030dd4  jnz     short loc_140030E0B
0x140030dd6  mov     [rdi+21h], bl
0x140030dd9  test    r12b, r12b
0x140030ddc  jz      short loc_140030E20
0x140030dde  mov     eax, [rdi+8]
0x140030de1  test    al, al
0x140030de3  js      short loc_140030E20
0x140030de5  xor     r8d, r8d
0x140030de8  mov     edx, esi
0x140030dea  mov     rcx, rdi
0x140030ded  call    AfdIndicateEventSelectEvent
0x140030df2  lea     r9, [rbp+57h+LockHandle]
0x140030df6  xor     r8d, r8d
0x140030df9  mov     edx, esi
0x140030dfb  mov     rcx, rdi
0x140030dfe  call    AfdIndicatePollEvent
0x140030e03  test    al, al
0x140030e05  jnz     loc_140030F18
0x140030e0b  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x140030e0f  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140030e16  nop     dword ptr [rax+rax+00h]
0x140030e1b  jmp     loc_140030F18
0x140030e20  xor     r8d, r8d
0x140030e23  mov     edx, r9d
0x140030e26  mov     rcx, rdi
0x140030e29  call    AfdIndicateEventSelectEvent
0x140030e2e  xor     r8d, r8d
0x140030e31  mov     rcx, rdi
0x140030e34  lea     edx, [r8+1]
0x140030e38  call    AfdNotifySockEventsChangedUnderLock
0x140030e3d  xor     r8d, r8d
0x140030e40  lea     r9, [rbp+57h+LockHandle]
0x140030e44  lea     edx, [r8+1]
0x140030e48  call    AfdIndicatePollEvent
0x140030e4d  xor     r8d, r8d
0x140030e50  mov     rcx, rdi
0x140030e53  test    al, al
0x140030e55  jnz     short loc_140030E65
0x140030e57  lea     rdx, [rbp+57h+LockHandle]
0x140030e5b  call    AfdNotifySockIndicateEventsUnlock
0x140030e60  jmp     loc_140030F18
0x140030e65  xor     edx, edx
0x140030e67  jmp     short loc_140030E5B
0x140030e69  cmp     dword ptr [rax+64h], 0
0x140030e6d  mov     r8d, 10000000h
0x140030e73  jbe     short loc_140030ED4
0x140030e75  mov     eax, [rdi+8]
0x140030e78  bt      eax, 8
0x140030e7c  jb      short loc_140030ED4
0x140030e7e  mov     rdx, [rbp+57h+arg_0]
0x140030e82  mov     ecx, [rdx+4]
0x140030e85  test    ecx, 110h
0x140030e8b  jnz     short loc_140030ED4
0x140030e8d  test    dword ptr [rdi+8], 20800h
0x140030e94  jnz     short loc_140030ED4
0x140030e96  test    r8d, ecx
0x140030e99  jnz     short loc_140030ED4
0x140030e9b  or      ecx, r8d
0x140030e9e  mov     [rdx+4], ecx
0x140030ea1  mov     rcx, r9
0x140030ea4  mov     rax, [rbp+57h+arg_0]
0x140030ea8  lock xadd [rax+30h], rcx
0x140030eae  add     rcx, r9
0x140030eb1  cmp     rcx, r9
0x140030eb4  jg      short loc_140030EBB
0x140030eb6  mov     rcx, r15
0x140030eb9  int     29h; Win8: RtlFailFast(ecx)
0x140030ebb  mov     rcx, [rbp+57h+arg_0]
0x140030ebf  lea     rdx, AfdLRRepostReceive
  ... truncated ...
```
