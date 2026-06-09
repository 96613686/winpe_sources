# UlReceiveHttpRequest

- ea: `0x14003f190`
- end: `0x14003fa5e`
- name: `UlReceiveHttpRequest`
- size: `2254`
- prototype: `__int64 __fastcall(unsigned __int64, __int64, ULONG_PTR, IRP *)`
- caller_count: `2`
- callee_count: `19`
- tags: ``

## callers

- `0x14003a850`
- `0x140081da0`

## callees

- `0x14000a350`
- `0x14000bfb0`
- `0x14001a6d0`
- `0x14001a750`
- `0x14003c124`
- `0x14003ec20`
- `0x14003f190`
- `0x140041320`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401c4e4c`
- `0x1401c4eb4`
- `0x1401c5068`
- `0x1401c53b0`
- `0x1401c5480`
- `0x1401cfa20`
- `0x1401da310`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14003f1fe`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14003f1fe`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14003f247`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14003f629`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14003f247`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14003f629`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f253`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f3fc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f5f3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f618`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f635`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f806`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f82b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f253`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f3fc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f5f3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f618`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f635`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f806`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f82b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003f3f0`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003f5e7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003f60c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003f7fa`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003f81f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003f3f0`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003f5e7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003f60c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003f7fa`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003f81f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003f394`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003f4bd`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003f4e6`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003f394`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003f4bd`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003f4e6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003f1e9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003f37f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003f4a4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003f4c9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003f1e9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003f37f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003f4a4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003f4c9`

## pseudocode

```c
__int64 __fastcall UlReceiveHttpRequest(unsigned __int64 a1, __int64 a2, ULONG_PTR a3, IRP *a4)
{
  int v6; // esi
  unsigned __int64 v7; // rdi
  __int64 v8; // rsi
  __int64 v9; // r15
  unsigned int v10; // eax
  unsigned int v11; // edi
  __int64 v13; // rsi
  __int64 v14; // r9
  unsigned __int64 v15; // r8
  unsigned __int8 v16; // r15
  __int64 v17; // r15
  __int64 v18; // r12
  __int64 v19; // r15
  ULONG_PTR v20; // rdx
  int v21; // r12d
  int v22; // r8d
  __int64 v23; // rdi
  __int64 v24; // rdx
  int v25; // r8d
  __int64 v26; // rdx
  __int64 v27; // rcx
  _QWORD *v28; // r8
  int v29; // eax
  unsigned __int8 v30; // di
  ULONG_PTR v31; // rdx
  int v32; // r13d
  ULONG_PTR v33; // rdx
  int v34; // r12d
  int v35; // eax
  __int64 v36; // rax
  ULONG_PTR v37; // rdx
  int v38; // eax
  int v39; // [rsp+20h] [rbp-40h]
  ULONG_PTR v40; // [rsp+28h] [rbp-38h]
  IRP *v41; // [rsp+30h] [rbp-30h]
  unsigned int v42; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v43; // [rsp+54h] [rbp-Ch] BYREF
  __int64 v44; // [rsp+58h] [rbp-8h] BYREF
  __int64 v45; // [rsp+A0h] [rbp+40h] BYREF

  v44 = 0;
  v6 = a2;
  v7 = a1;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    v41 = a4;
    v40 = a3;
    v39 = a2;
    WPP_SF_iLqq(a1, a2, a3, a1);
  }
  if ( *(_DWORD *)(a3 + 40) == 4 && v6 )
  {
    v11 = -1073741811;
    goto LABEL_8;
  }
  if ( v7 )
  {
    if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_qq(1033, 10, WPP_3bf590e843a03617467a72dc4e459b29_Traceguids, v7, a3);
    v13 = 0;
    LODWORD(v45) = 0;
    v43 = 0;
    v42 = 0;
    if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_iLLqqq(a1, a2, a3, v7, v39, v40, (_DWORD)v41);
    v14 = (unsigned int)v7 >> 28;
    if ( (_DWORD)v14 != 4 )
    {
      if ( (BYTE1(xmmword_1401A2C90) & 2) != 0 )
        WPP_SF_d(521, 14, WPP_02f89a7cef4b3153cc79135fcb4f2711_Traceguids, v14);
      goto LABEL_32;
    }
    if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_iqqq(a1, a2, a3, v7, &v43, &v45, &v42);
    LODWORD(v45) = 0;
    v15 = HIDWORD(v7);
    v42 = 0;
    v43 = WORD2(v7) & 0xFFF;
    if ( v43 >= UxMaximumNumberOfProcessors )
    {
      if ( (BYTE1(xmmword_1401A2C90) & 2) != 0 )
        WPP_SF_(521, 11, WPP_6218f2abddb13899518e42ce65335ae2_Traceguids);
    }
    else
    {
      a2 = (HIDWORD(v7) >> 12) & 0xFFF;
      a1 = (unsigned __int64)(WORD2(v7) & 0xFFF) << 6;
      LODWORD(v45) = a2;
      if ( (unsigned int)a2 < *(_DWORD *)((char *)UxOpaqueIdTable + a1 + 40) )
      {
        v15 = HIBYTE(HIDWORD(v7));
        v16 = 1;
        v42 = HIBYTE(HIDWORD(v7));
LABEL_23:
        if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
        {
          LODWORD(v41) = v42;
          LODWORD(v40) = v45;
          WPP_SF_lLLL(a1, a2, v15, v16, v43, v40, v41);
        }
        if ( v16 )
        {
          v17 = 48LL * v42
              + *(_QWORD *)(*((_QWORD *)UxOpaqueIdTable + 8 * (unsigned __int64)v43 + 2) + 8LL * (unsigned int)v45);
          KeEnterCriticalRegion();
          v18 = v17 + 32;
          ExAcquirePushLockExclusiveEx(v17 + 32, 0);
          if ( (*(_DWORD *)(v17 + 40) & 0xF0000000) == 0x30000000 )
          {
            v19 = *(_QWORD *)v17;
            if ( (*(_DWORD *)(v19 + 32) & 0xF0000000) == 0x40000000
              && (((unsigned int)v7 ^ *(_DWORD *)(v19 + 32)) & 0xFFFFFFF) == 0
              && (unsigned __int8)UlValidateHttpRequestFromId(*(_QWORD *)(v19 + 24), a3) )
            {
              v13 = *(_QWORD *)(v19 + 24);
              UlReferenceHttpRequestFromId(v13);
            }
          }
          ExReleasePushLockExclusiveEx(v18, 0);
          KeLeaveCriticalRegion();
        }
LABEL_32:
        if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
        {
          WPP_SF_q(1033, 15, WPP_02f89a7cef4b3153cc79135fcb4f2711_Traceguids, v13);
          if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
          {
            if ( v13 )
              v36 = *(_QWORD *)(v13 + 64);
            else
              v36 = 0;
            WPP_SF_qq(1033, 11, WPP_3bf590e843a03617467a72dc4e459b29_Traceguids, v13, v36);
          }
        }
        v44 = v13;
        if ( v13 )
        {
          UlStopRequestQueueTimer(v13);
          a4->Tail.Overlay.CurrentStackLocation->Control |= 1u;
          UlCopyRequestToIrp(v44, a4, 0);
          v20 = v44 + 48;
          v21 = _InterlockedDecrement((volatile signed __int32 *)(v44 + 48));
          if ( UxDebugCheckRefcount && v21 <= -1 )
            UlBugCheckEx(3u, v20, 0xBu, v21);
          if ( !v21 )
            UlpQueueFreeHttpRequest(v44);
          v44 = 0;
          v11 = 259;
        }
        else
        {
          v11 = -1073741254;
        }
        goto LABEL_8;
      }
      if ( (BYTE1(xmmword_1401A2C90) & 2) != 0 )
      {
        WPP_SF_(521, 12, WPP_6218f2abddb13899518e42ce65335ae2_Traceguids);
        v16 = 0;
        goto LABEL_23;
      }
    }
    v16 = 0;
    goto LABEL_23;
  }
  v8 = *(_QWORD *)(a3 + 8);
  KeEnterCriticalRegion();
  v9 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v8 + 280), 0);
  if ( *(_BYTE *)(a3 + 4) )
  {
    v11 = -1073741816;
  }
  else
  {
    while ( 1 )
    {
      v10 = UlpRetrieveRequest(v8, a3, a4, &v44);
      v11 = v10;
      if ( v10 == 259 )
        break;
      if ( v10 == -1073741738 )
      {
        v11 = 259;
        break;
      }
      if ( v10 == -1073741536 )
        break;
      if ( v10 )
      {
        v11 = -1073741823;
        break;
      }
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v44 + 1704, 0);
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(*(_QWORD *)(v44 + 1712) + 72LL, 0);
      v23 = v44;
      v24 = *(_QWORD *)(v44 + 1712);
      v45 = v24;
      if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      {
        LODWORD(v41) = 1;
        WPP_SF_qqqL(1032, 183, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v44, *(_QWORD *)(v44 + 64), a3, v41);
        v24 = v45;
      }
      if ( *(_BYTE *)(v24 + 80) && (BYTE10(xmmword_1401A2C90) & 0x40) != 0 )
      {
        WPP_SF_qLLqqZq(
          *(_QWORD *)(a3 + 8),
          v24,
          v22,
          v23,
          *(_DWORD *)(v23 + 1736),
          *(_DWORD *)(v23 + 1740),
          a3,
          *(_QWORD *)(a3 + 8),
          *(_QWORD *)(a3 + 8) + 160LL,
          v24);
        LODWORD(v24) = v45;
      }
      v25 = *(_DWORD *)(v23 + 1736);
      if ( v25 == 1 )
      {
        UlStopRequestQueueTimer(v23);
        v26 = v45;
        v27 = v45 + 96;
        *(_DWORD *)(v23 + 1736) = 2;
        v28 = *(_QWORD **)(v27 + 8);
        if ( *v28 != v27 )
          __fastfail(3u);
        *(_QWORD *)(v23 + 1720) = v27;
        *(_QWORD *)(v23 + 1728) = v28;
        *v28 = v23 + 1720;
        *(_QWORD *)(v27 + 8) = v23 + 1720;
        if ( *(_DWORD *)(a3 + 40) == 1 && !*(_QWORD *)(v26 + 88) )
        {
          *(_QWORD *)(v26 + 88) = a3;
          v35 = _InterlockedIncrement((volatile signed __int32 *)a3);
          if ( UxDebugCheckRefcount )
          {
            if ( v35 <= -1 )
              UlBugCheckEx(3u, a3, 0xEu, v35);
          }
        }
        if ( *(_DWORD *)(a3 + 40) == 4 )
          *(_BYTE *)(v23 + 1853) = 1;
        *(_QWORD *)(v23 + 1744) = a3;
        v29 = _InterlockedIncrement((volatile signed __int32 *)a3);
        if ( UxDebugCheckRefcount && v29 <= -1 )
          UlBugCheckEx(3u, a3, 9u, v29);
        v30 = 1;
      }
      else
      {
        LOBYTE(v45) = 0;
        if ( (BYTE10(xmmword_1401A2C90) & 0x40) != 0 )
        {
          WPP_SF_qqqZqL(
            *(_QWORD *)(a3 + 8),
            v24,
            v25,
            v23,
            a3,
            *(_QWORD *)(a3 + 8),
            *(_QWORD *)(a3 + 8) + 160LL,
            v24,
            v25);
          v30 = v45;
        }
        else
        {
          v30 = 0;
        }
      }
      if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
        WPP_SF_d(1032, 186, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v30);
      if ( v30 )
      {
        v31 = v44 + 48;
        v32 = _InterlockedIncrement((volatile signed __int32 *)(v44 + 48));
        if ( UxDebugCheckRefcount && v32 <= -1 )
          UlBugCheckEx(3u, v31, 0x27u, v32);
        ExReleasePushLockExclusiveEx(*(_QWORD *)(v44 + 1712) + 72LL, 0);
        KeLeaveCriticalRegion();
        ExReleasePushLockExclusiveEx(v44 + 1704, 0);
        KeLeaveCriticalRegion();
        ExReleaseCacheAwarePushLockSharedEx(v9, 0);
        KeLeaveCriticalRegion();
        a4->Tail.Overlay.CurrentStackLocation->Control |= 1u;
        UlCopyRequestToIrp(v44, a4, 0);
        v33 = v44 + 48;
        v34 = _InterlockedDecrement((volatile signed __int32 *)(v44 + 48));
        if ( UxDebugCheckRefcount && v34 <= -1 )
          UlBugCheckEx(3u, v33, 0x27u, v34);
        v11 = 259;
        if ( !v34 )
          UlpQueueFreeHttpRequest(v44);
        goto LABEL_8;
      }
      ExReleasePushLockExclusiveEx(*(_QWORD *)(v44 + 1712) + 72LL, 0);
      KeLeaveCriticalRegion();
      ExReleasePushLockExclusiveEx(v44 + 1704, 0);
      KeLeaveCriticalRegion();
      v37 = v44 + 48;
      v38 = _InterlockedDecrement((volatile signed __int32 *)(v44 + 48));
      if ( UxDebugCheckRefcount && v38 <= -1 )
        UlBugCheckEx(3u, v37, 0xCu, v38);
      if ( !v38 )
        UlpQueueFreeHttpRequest(v44);
    }
  }
  ExReleaseCacheAwarePushLockSharedEx(v9, 0);
  KeLeaveCriticalRegion();
LABEL_8:
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_d(1032, 196, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x14003f190  mov     [rsp-28h+arg_18], rbx
0x14003f195  push    rbp
0x14003f196  push    rsi
0x14003f197  push    rdi
0x14003f198  push    r13
0x14003f19a  push    r14
0x14003f19c  mov     rbp, rsp
0x14003f19f  sub     rsp, 60h
0x14003f1a3  xor     r13d, r13d
0x14003f1a6  mov     r14, r9
0x14003f1a9  mov     [rbp+var_8], r13
0x14003f1ad  mov     rbx, r8
0x14003f1b0  mov     esi, edx
0x14003f1b2  mov     rdi, rcx
0x14003f1b5  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003f1bc  jnz     loc_14003F880
0x14003f1c2  cmp     dword ptr [rbx+28h], 4
0x14003f1c6  mov     [rsp+60h+arg_0], r12
0x14003f1ce  mov     [rsp+60h+arg_8], r15
0x14003f1d6  jz      loc_14003F293
0x14003f1dc  test    rdi, rdi
0x14003f1df  jnz     loc_14003F2A2
0x14003f1e5  mov     rsi, [rbx+8]
0x14003f1e9  call    cs:__imp_KeEnterCriticalRegion
0x14003f1f0  nop     dword ptr [rax+rax+00h]
0x14003f1f5  mov     rcx, [rsi+118h]
0x14003f1fc  xor     edx, edx
0x14003f1fe  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x14003f205  nop     dword ptr [rax+rax+00h]
0x14003f20a  mov     r15, rax
0x14003f20d  cmp     [rbx+4], r13b
0x14003f211  jnz     loc_14003F764
0x14003f217  mov     r12d, 0FFFFFFFFh
0x14003f21d  mov     r13d, 1
0x14003f223  lea     r9, [rbp+var_8]
0x14003f227  mov     r8, r14
0x14003f22a  mov     rdx, rbx
0x14003f22d  mov     rcx, rsi
0x14003f230  call    UlpRetrieveRequest
0x14003f235  mov     edi, eax
0x14003f237  cmp     eax, 103h
0x14003f23c  jnz     loc_14003F486
0x14003f242  xor     edx, edx
0x14003f244  mov     rcx, r15
0x14003f247  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x14003f24e  nop     dword ptr [rax+rax+00h]
0x14003f253  call    cs:__imp_KeLeaveCriticalRegion
0x14003f25a  nop     dword ptr [rax+rax+00h]
0x14003f25f  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003f266  jnz     loc_14003FA40
0x14003f26c  mov     r15, [rsp+60h+arg_8]
0x14003f274  mov     eax, edi
0x14003f276  mov     r12, [rsp+60h+arg_0]
0x14003f27e  mov     rbx, [rsp+60h+arg_18]
0x14003f286  add     rsp, 60h
0x14003f28a  pop     r14
0x14003f28c  pop     r13
0x14003f28e  pop     rdi
0x14003f28f  pop     rsi
0x14003f290  pop     rbp
0x14003f291  retn
0x14003f293  test    esi, esi
0x14003f295  jz      loc_14003F1DC
0x14003f29b  mov     edi, 0C000000Dh
0x14003f2a0  jmp     short loc_14003F25F
0x14003f2a2  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14003f2a9  jnz     loc_14003F89B
0x14003f2af  mov     rsi, r13
0x14003f2b2  mov     dword ptr [rbp+arg_10], r13d
0x14003f2b6  mov     [rbp+var_C], r13d
0x14003f2ba  mov     [rbp+var_10], r13d
0x14003f2be  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14003f2c5  jnz     loc_14003F8BE
0x14003f2cb  mov     r9d, edi
0x14003f2ce  shr     r9d, 1Ch
0x14003f2d2  cmp     r9d, 4
0x14003f2d6  jnz     loc_14003F8D0
0x14003f2dc  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14003f2e3  jnz     loc_14003F8F8
0x14003f2e9  mov     r8, rdi
0x14003f2ec  mov     dword ptr [rbp+arg_10], r13d
0x14003f2f0  shr     r8, 20h
0x14003f2f4  mov     eax, r8d
0x14003f2f7  mov     [rbp+var_10], r13d
0x14003f2fb  and     eax, 0FFFh
0x14003f300  cmp     eax, cs:UxMaximumNumberOfProcessors
0x14003f306  mov     [rbp+var_C], eax
0x14003f309  jnb     loc_14003F76E
0x14003f30f  mov     ecx, eax
0x14003f311  mov     edx, r8d
0x14003f314  mov     rax, cs:UxOpaqueIdTable
0x14003f31b  shr     edx, 0Ch
0x14003f31e  and     edx, 0FFFh
0x14003f324  shl     rcx, 6
0x14003f328  mov     dword ptr [rbp+arg_10], edx
0x14003f32b  cmp     edx, [rcx+rax+28h]
0x14003f32f  jnb     loc_14003F93B
0x14003f335  shr     r8d, 18h
0x14003f339  mov     r15b, 1
0x14003f33c  mov     [rbp+var_10], r8d
0x14003f340  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14003f347  jnz     loc_14003F966
0x14003f34d  test    r15b, r15b
0x14003f350  jz      loc_14003F408
0x14003f356  mov     rax, cs:UxOpaqueIdTable
0x14003f35d  mov     ecx, [rbp+var_C]
0x14003f360  mov     r8d, dword ptr [rbp+arg_10]
0x14003f364  shl     rcx, 6
0x14003f368  mov     rdx, [rcx+rax+10h]
0x14003f36d  mov     eax, [rbp+var_10]
0x14003f370  mov     r15, [rdx+r8*8]
0x14003f374  lea     rcx, [rax+rax*2]
0x14003f378  shl     rcx, 4
0x14003f37c  add     r15, rcx
0x14003f37f  call    cs:__imp_KeEnterCriticalRegion
0x14003f386  nop     dword ptr [rax+rax+00h]
0x14003f38b  lea     r12, [r15+20h]
0x14003f38f  xor     edx, edx
0x14003f391  mov     rcx, r12
0x14003f394  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14003f39b  nop     dword ptr [rax+rax+00h]
0x14003f3a0  mov     eax, [r15+28h]
0x14003f3a4  and     eax, 0F0000000h
0x14003f3a9  cmp     eax, 30000000h
0x14003f3ae  jnz     short loc_14003F3EB
0x14003f3b0  mov     r15, [r15]
0x14003f3b3  mov     ecx, [r15+20h]
0x14003f3b7  mov     eax, ecx
0x14003f3b9  and     eax, 0F0000000h
0x14003f3be  cmp     eax, 40000000h
0x14003f3c3  jnz     short loc_14003F3EB
0x14003f3c5  xor     ecx, edi
0x14003f3c7  test    ecx, 0FFFFFFFh
0x14003f3cd  jnz     short loc_14003F3EB
0x14003f3cf  mov     rcx, [r15+18h]
0x14003f3d3  mov     rdx, rbx
0x14003f3d6  call    UlValidateHttpRequestFromId
0x14003f3db  test    al, al
0x14003f3dd  jz      short loc_14003F3EB
0x14003f3df  mov     rsi, [r15+18h]
0x14003f3e3  mov     rcx, rsi
0x14003f3e6  call    UlReferenceHttpRequestFromId
0x14003f3eb  xor     edx, edx
0x14003f3ed  mov     rcx, r12
0x14003f3f0  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14003f3f7  nop     dword ptr [rax+rax+00h]
0x14003f3fc  call    cs:__imp_KeLeaveCriticalRegion
0x14003f403  nop     dword ptr [rax+rax+00h]
0x14003f408  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14003f40f  jnz     loc_14003F989
0x14003f415  mov     [rbp+var_8], rsi
0x14003f419  test    rsi, rsi
0x14003f41c  jz      loc_14003F9B4
0x14003f422  mov     rcx, rsi
0x14003f425  call    UlStopRequestQueueTimer
0x14003f42a  mov     rax, [r14+0B8h]
0x14003f431  xor     r9d, r9d
0x14003f434  mov     r8, rbx
0x14003f437  mov     byte ptr [rsp+60h+var_40], r13b
0x14003f43c  mov     rdx, r14
0x14003f43f  or      byte ptr [rax+3], 1
0x14003f443  mov     rcx, [rbp+var_8]
0x14003f447  call    UlCopyRequestToIrp
0x14003f44c  mov     rdx, [rbp+var_8]
0x14003f450  mov     r12d, 0FFFFFFFFh
0x14003f456  add     rdx, 30h ; '0'; BugCheckParameter2
0x14003f45a  lock xadd [rdx], r12d
0x14003f45f  dec     r12d
0x14003f462  cmp     cs:UxDebugCheckRefcount, r13b
0x14003f469  jnz     loc_14003F713
0x14003f46f  test    r12d, r12d
0x14003f472  jz      loc_14003F9BE
0x14003f478  mov     [rbp+var_8], r13
0x14003f47c  mov     edi, 103h
0x14003f481  jmp     loc_14003F25F
0x14003f486  cmp     eax, 0C0000056h
0x14003f48b  jz      loc_14003FA36
0x14003f491  cmp     eax, 0C0000120h
0x14003f496  jz      loc_14003F242
0x14003f49c  test    eax, eax
0x14003f49e  jnz     loc_14003FA2C
0x14003f4a4  call    cs:__imp_KeEnterCriticalRegion
0x14003f4ab  nop     dword ptr [rax+rax+00h]
0x14003f4b0  mov     rcx, [rbp+var_8]
0x14003f4b4  xor     edx, edx
0x14003f4b6  add     rcx, 6A8h
0x14003f4bd  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14003f4c4  nop     dword ptr [rax+rax+00h]
0x14003f4c9  call    cs:__imp_KeEnterCriticalRegion
0x14003f4d0  nop     dword ptr [rax+rax+00h]
0x14003f4d5  mov     rax, [rbp+var_8]
0x14003f4d9  xor     edx, edx
0x14003f4db  mov     rcx, [rax+6B0h]
0x14003f4e2  add     rcx, 48h ; 'H'
0x14003f4e6  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14003f4ed  nop     dword ptr [rax+rax+00h]
0x14003f4f2  mov     rdi, [rbp+var_8]
0x14003f4f6  mov     rdx, [rdi+6B0h]
0x14003f4fd  mov     [rbp+arg_10], rdx
0x14003f501  test    byte ptr cs:xmmword_1401A2CA0+1, r13b
0x14003f508  jnz     loc_14003F9CC
0x14003f50e  cmp     byte ptr [rdx+50h], 0
0x14003f512  jnz     loc_140175B18
0x14003f518  mov     r8d, [rdi+6C8h]
0x14003f51f  cmp     r8d, r13d
0x14003f522  jnz     loc_14003F74F
0x14003f528  mov     rcx, rdi
0x14003f52b  call    UlStopRequestQueueTimer
0x14003f530  mov     rdx, [rbp+arg_10]
0x14003f534  lea     rcx, [rdx+60h]
0x14003f538  mov     dword ptr [rdi+6C8h], 2
0x14003f542  mov     r8, [rcx+8]
0x14003f546  cmp     [r8], rcx
0x14003f549  jz      short loc_14003F552
0x14003f54b  mov     ecx, 3
0x14003f550  int     29h; Win8: RtlFailFast(ecx)
0x14003f552  lea     rax, [rdi+6B8h]
0x14003f559  mov     [rax], rcx
0x14003f55c  mov     [rax+8], r8
0x14003f560  mov     [r8], rax
0x14003f563  mov     [rcx+8], rax
0x14003f567  cmp     [rbx+28h], r13d
0x14003f56b  jnz     short loc_14003F578
0x14003f56d  cmp     qword ptr [rdx+58h], 0
0x14003f572  jz      loc_14003F6D9
0x14003f578  cmp     dword ptr [rbx+28h], 4
0x14003f57c  jz      loc_14003FA01
0x14003f582  mov     [rdi+6D0h], rbx
0x14003f589  mov     eax, r13d
0x14003f58c  lock xadd [rbx], eax
0x14003f590  inc     eax
0x14003f592  cmp     cs:UxDebugCheckRefcount, 0
0x14003f599  jnz     loc_14003F6B9
0x14003f59f  movzx   edi, r13b
0x14003f5a3  test    byte ptr cs:xmmword_1401A2CA0+1, r13b
0x14003f5aa  jnz     loc_14003FA0D
0x14003f5b0  test    dil, dil
0x14003f5b3  jz      loc_14003F7E9
0x14003f5b9  mov     rdx, [rbp+var_8]
0x14003f5bd  add     rdx, 30h ; '0'; BugCheckParameter2
0x14003f5c1  lock xadd [rdx], r13d
0x14003f5c6  inc     r13d
0x14003f5c9  cmp     cs:UxDebugCheckRefcount, 0
0x14003f5d0  jnz     loc_14003F69C
0x14003f5d6  mov     rax, [rbp+var_8]
0x14003f5da  xor     edx, edx
0x14003f5dc  mov     rcx, [rax+6B0h]
0x14003f5e3  add     rcx, 48h ; 'H'
0x14003f5e7  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14003f5ee  nop     dword ptr [rax+rax+00h]
0x14003f5f3  call    cs:__imp_KeLeaveCriticalRegion
0x14003f5fa  nop     dword ptr [rax+rax+00h]
0x14003f5ff  mov     rcx, [rbp+var_8]
0x14003f603  xor     edx, edx
0x14003f605  add     rcx, 6A8h
0x14003f60c  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14003f613  nop     dword ptr [rax+rax+00h]
0x14003f618  call    cs:__imp_KeLeaveCriticalRegion
0x14003f61f  nop     dword ptr [rax+rax+00h]
0x14003f624  xor     edx, edx
0x14003f626  mov     rcx, r15
0x14003f629  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x14003f630  nop     dword ptr [rax+rax+00h]
0x14003f635  call    cs:__imp_KeLeaveCriticalRegion
0x14003f63c  nop     dword ptr [rax+rax+00h]
0x14003f641  mov     rax, [r14+0B8h]
0x14003f648  xor     r9d, r9d
0x14003f64b  mov     r8, rbx
0x14003f64e  mov     byte ptr [rsp+60h+var_40], 0
0x14003f653  mov     rdx, r14
0x14003f656  or      byte ptr [rax+3], 1
0x14003f65a  mov     rcx, [rbp+var_8]
0x14003f65e  call    UlCopyRequestToIrp
0x14003f663  mov     rdx, [rbp+var_8]
0x14003f667  add     rdx, 30h ; '0'; BugCheckParameter2
0x14003f66b  lock xadd [rdx], r12d
0x14003f670  dec     r12d
0x14003f673  cmp     cs:UxDebugCheckRefcount, 0
0x14003f67a  jnz     loc_14003F731
0x14003f680  mov     edi, 103h
0x14003f685  test    r12d, r12d
0x14003f688  jnz     loc_14003F25F
0x14003f68e  mov     rcx, [rbp+var_8]
0x14003f692  call    UlpQueueFreeHttpRequest
0x14003f697  jmp     loc_14003F25F
0x14003f69c  cmp     r13d, r12d
0x14003f69f  jg      loc_14003F5D6
0x14003f6a5  movsxd  r9, r13d; BugCheckParameter4
0x14003f6a8  mov     ecx, 3; BugCheckParameter1
0x14003f6ad  mov     r8d, 27h ; '''; BugCheckParameter3
0x14003f6b3  call    UlBugCheckEx
0x14003f6b9  cmp     eax, r12d
0x14003f6bc  jg      loc_14003F59F
0x14003f6c2  movsxd  r9, eax; BugCheckParameter4
0x14003f6c5  mov     r8d, 9; BugCheckParameter3
0x14003f6cb  mov     rdx, rbx; BugCheckParameter2
0x14003f6ce  mov     ecx, 3; BugCheckParameter1
0x14003f6d3  call    UlBugCheckEx
0x14003f6d9  mov     [rdx+58h], rbx
0x14003f6dd  mov     eax, r13d
  ... truncated ...
```
