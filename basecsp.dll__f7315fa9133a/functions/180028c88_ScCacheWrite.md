# ScCacheWrite

- ea: `0x180028c88`
- end: `0x1800292ca`
- name: `ScCacheWrite`
- size: `1602`
- prototype: `__int64 __usercall@<rax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, int, int, void *Src, int)`
- caller_count: `3`
- callee_count: `13`
- tags: ``

## callers

- `0x1800215f0`
- `0x180022a88`
- `0x180023504`

## callees

- `0x18000a766`
- `0x180019650`
- `0x1800196ac`
- `0x18001c96c`
- `0x180028130`
- `0x1800281b8`
- `0x180028244`
- `0x180028c88`
- `0x1800292d0`
- `0x1800294c0`
- `0x1800296c0`
- `0x18002cf46`
- `0x18002e010`

## import_xrefs

- `msvcrt!time` at `0x180029017`
- `msvcrt!time` at `0x180029017`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028e2a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028e2a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029257`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029257`

## string_xrefs

- `0x180028dd7`: `ScCacheWrite`

## pseudocode

```c
__int64 __fastcall ScCacheWrite(
        LPCRITICAL_SECTION lpCriticalSection,
        char *a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        int a6,
        void *Src,
        unsigned int a8)
{
  _WORD *v9; // r14
  PVOID v11; // rcx
  unsigned int v12; // ebx
  __int64 v13; // rsi
  __int64 v14; // rax
  __int64 v15; // r8
  unsigned int Item; // eax
  _QWORD *LockSemaphore; // rdx
  _WORD *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  _DWORD *v21; // rdi
  __int64 v22; // rcx
  void *v23; // rax
  __int64 v24; // rcx
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // r8
  void *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // r8
  __int128 v31; // xmm0
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  ULONG_PTR SpinCount; // rax
  bool v34; // zf
  __int64 v35; // rdi
  _QWORD *v36; // rdx
  _WORD *v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rcx
  _WORD *v41; // rcx
  unsigned int i; // esi
  __int128 v44; // [rsp+A8h] [rbp-29h] BYREF
  int v45; // [rsp+B8h] [rbp-19h] BYREF
  char *v46; // [rsp+C0h] [rbp-11h]
  int v47; // [rsp+C8h] [rbp-9h]
  _WORD *v48; // [rsp+D0h] [rbp-1h]

  v9 = (_WORD *)a4;
  WppTraceIndent((__int64)lpCriticalSection, 0);
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
  }
  v44 = 0;
  if ( !v9 || !a2 )
  {
    v12 = -2146435068;
    goto LABEL_73;
  }
  WppTraceIndent((__int64)v11, 2u);
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_ssDDDDDDDDDDDSDS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      (unsigned __int8)a2[14],
      (unsigned __int8)a2[13],
      (__int64)"ScCacheWrite",
      *(_DWORD *)a2,
      *((_WORD *)a2 + 2),
      *((_WORD *)a2 + 3),
      a2[8],
      a2[9],
      a2[10],
      a2[11],
      a2[12],
      a2[13],
      a2[14],
      a2[15],
      a4,
      a3);
    v9 = (_WORD *)a4;
  }
  if ( lpCriticalSection[2].RecursionCount >= a8 )
  {
    v13 = -1;
    v45 = 16;
    v14 = -1;
    v46 = a2;
    do
      ++v14;
    while ( v9[v14] );
    v48 = v9;
    v47 = 2 * v14;
    EnterCriticalSection(lpCriticalSection);
    Item = CacheGetItem(lpCriticalSection[1].DebugInfo, &v45, v15, &v44);
    v12 = Item;
    if ( Item )
    {
      if ( Item == 1168 )
      {
        while ( lpCriticalSection[2].LockCount < a8 + LODWORD(lpCriticalSection[2].DebugInfo) )
        {
          LockSemaphore = lpCriticalSection[1].LockSemaphore;
          v45 = 16;
          v18 = (_WORD *)LockSemaphore[5];
          v46 = (char *)(LockSemaphore + 3);
          v19 = -1;
          do
            ++v19;
          while ( v18[v19] );
          v48 = v18;
          v47 = 2 * v19;
          I_ServerCacheRemoveItem(lpCriticalSection, LockSemaphore, &v45);
        }
        v21 = (_DWORD *)(*(__int64 (__fastcall **)(__int64))&lpCriticalSection[1].LockCount)(80);
        if ( !v21 )
        {
          WppTraceIndent(v20, 2u);
          v12 = 8;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              29,
              WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
              WPP_pszIndent);
          }
          goto LABEL_71;
        }
        v22 = -1;
        do
          ++v22;
        while ( v9[v22] );
        v23 = (void *)(*(__int64 (__fastcall **)(__int64))&lpCriticalSection[1].LockCount)(2 * v22 + 2);
        *((_QWORD *)v21 + 5) = v23;
        if ( v23 )
        {
          v27 = -1;
          do
            ++v27;
          while ( v9[v27] );
          memcpy_0(v23, v9, 2 * v27 + 2);
          v21[2] = a8;
          v28 = (void *)(*(__int64 (__fastcall **)(_QWORD))&lpCriticalSection[1].LockCount)(a8);
          *(_QWORD *)v21 = v28;
          if ( v28 )
          {
            memcpy_0(v28, Src, (unsigned int)v21[2]);
            v21[3] = a3;
            time((time_t *const)v21 + 2);
            v31 = *(_OWORD *)a2;
            *((_QWORD *)&v44 + 1) = v21;
            LODWORD(v44) = 80;
            *(_OWORD *)(v21 + 6) = v31;
            v45 = 16;
            v46 = a2;
            do
              ++v13;
            while ( v9[v13] );
            DebugInfo = lpCriticalSection[1].DebugInfo;
            v47 = 2 * v13;
            v48 = v9;
            v12 = CacheAddItem(DebugInfo, &v45, v30, &v44);
            if ( !v12 )
            {
              SpinCount = lpCriticalSection[1].SpinCount;
              *((_QWORD *)v21 + 6) = SpinCount;
              if ( SpinCount )
                *(_QWORD *)(SpinCount + 56) = v21;
              v34 = lpCriticalSection[1].LockSemaphore == 0;
              lpCriticalSection[1].SpinCount = (ULONG_PTR)v21;
              if ( v34 )
                lpCriticalSection[1].LockSemaphore = v21;
              LODWORD(lpCriticalSection[2].DebugInfo) += v21[2];
              ++HIDWORD(lpCriticalSection[2].DebugInfo);
              goto LABEL_71;
            }
            goto LABEL_50;
          }
          WppTraceIndent(v29, 2u);
          v12 = 8;
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
LABEL_50:
            I_ServerCacheFreeItem(lpCriticalSection);
            goto LABEL_71;
          }
          v26 = 31;
        }
        else
        {
          WppTraceIndent(v24, 2u);
          v12 = 8;
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_50;
          }
          v26 = 30;
        }
        WPP_SF_s(v25[2], v26, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
        goto LABEL_50;
      }
    }
    else
    {
      v35 = *((_QWORD *)&v44 + 1);
      if ( *(_QWORD *)(*((_QWORD *)&v44 + 1) + 8LL) != __PAIR64__(a3, a8)
        || memcmp_0(**((const void ***)&v44 + 1), Src, *(unsigned int *)(*((_QWORD *)&v44 + 1) + 8LL)) )
      {
        *(_DWORD *)(v35 + 12) = a3;
        I_ServerCacheSetMRU(lpCriticalSection, v35);
        while ( lpCriticalSection[2].LockCount < LODWORD(lpCriticalSection[2].DebugInfo) + a8 - *(_DWORD *)(v35 + 8) )
        {
          v36 = lpCriticalSection[1].LockSemaphore;
          v45 = 16;
          v37 = (_WORD *)v36[5];
          v46 = (char *)(v36 + 3);
          v38 = -1;
          do
            ++v38;
          while ( v37[v38] );
          v48 = v37;
          v47 = 2 * v38;
          I_ServerCacheRemoveItem(lpCriticalSection, v36, &v45);
        }
        ((void (__fastcall *)(_QWORD))lpCriticalSection[1].OwningThread)(*(_QWORD *)v35);
        *(_QWORD *)v35 = 0;
        v39 = (*(__int64 (__fastcall **)(_QWORD))&lpCriticalSection[1].LockCount)(a8);
        *(_QWORD *)v35 = v39;
        if ( !v39 )
        {
          WppTraceIndent(v40, 2u);
          v12 = 8;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              36,
              WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
              WPP_pszIndent);
          }
          if ( v35 )
          {
            v41 = *(_WORD **)(v35 + 40);
            v46 = (char *)(v35 + 24);
            v45 = 16;
            do
              ++v13;
            while ( v41[v13] );
            v48 = v41;
            v47 = 2 * v13;
            I_ServerCacheRemoveItem(lpCriticalSection, v35, &v45);
          }
          goto LABEL_71;
        }
        LODWORD(lpCriticalSection[2].DebugInfo) -= *(_DWORD *)(v35 + 8);
        *(_DWORD *)(v35 + 8) = a8;
        LODWORD(lpCriticalSection[2].DebugInfo) += a8;
        memcpy_0(*(void **)v35, Src, *(unsigned int *)(v35 + 8));
        for ( i = 0; i < *(_DWORD *)(v35 + 72); ++i )
          ((void (__fastcall *)(_QWORD))lpCriticalSection[1].OwningThread)(*(_QWORD *)(*(_QWORD *)(v35 + 64) + 8LL * i));
        ((void (__fastcall *)(_QWORD))lpCriticalSection[1].OwningThread)(*(_QWORD *)(v35 + 64));
        *(_QWORD *)(v35 + 64) = 0;
        *(_DWORD *)(v35 + 72) = 0;
      }
      I_ServerCacheSetMRU(lpCriticalSection, v35);
    }
LABEL_71:
    LeaveCriticalSection(lpCriticalSection);
    goto LABEL_73;
  }
  v12 = -2146434958;
LABEL_73:
  WppTraceIndent((__int64)v11, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      (unsigned int)WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
      WPP_pszIndent,
      v12);
  }
  return v12;
}

```

## disassembly

```asm
0x180028c88  mov     rax, rsp
0x180028c8b  mov     [rax+8], rbx
0x180028c8f  mov     [rax+20h], r9
0x180028c93  mov     [rax+18h], r8d
0x180028c97  push    rbp
0x180028c98  push    rsi
0x180028c99  push    rdi
0x180028c9a  push    r12
0x180028c9c  push    r13
0x180028c9e  push    r14
0x180028ca0  push    r15
0x180028ca2  lea     rbp, [rax-3Fh]
0x180028ca6  sub     rsp, 0D0h
0x180028cad  mov     r12, rdx
0x180028cb0  mov     r14, r9
0x180028cb3  xor     edx, edx
0x180028cb5  mov     r13, rcx
0x180028cb8  call    WppTraceIndent
0x180028cbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180028cc4  lea     rbx, WPP_GLOBAL_Control
0x180028ccb  cmp     rcx, rbx
0x180028cce  jz      short loc_180028CF8
0x180028cd0  test    byte ptr [rcx+1Ch], 2
0x180028cd4  jz      short loc_180028CF8
0x180028cd6  cmp     byte ptr [rcx+19h], 5
0x180028cda  jb      short loc_180028CF8
0x180028cdc  mov     r9, cs:WPP_pszIndent
0x180028ce3  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180028cea  mov     rcx, [rcx+10h]
0x180028cee  mov     edx, 1Bh
0x180028cf3  call    WPP_SF_s
0x180028cf8  xor     edi, edi
0x180028cfa  xorps   xmm0, xmm0
0x180028cfd  movups  [rbp+37h+var_60], xmm0
0x180028d01  test    r14, r14
0x180028d04  jz      loc_18002925F
0x180028d0a  test    r12, r12
0x180028d0d  jz      loc_18002925F
0x180028d13  lea     edx, [rdi+2]
0x180028d16  call    WppTraceIndent
0x180028d1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028d22  cmp     rcx, rbx
0x180028d25  jz      loc_180028DEE
0x180028d2b  test    byte ptr [rcx+1Ch], 4
0x180028d2f  jz      loc_180028DEE
0x180028d35  cmp     byte ptr [rcx+19h], 4
0x180028d39  jb      loc_180028DEE
0x180028d3f  movzx   eax, byte ptr [r12+0Fh]
0x180028d45  mov     edx, 1Ch
0x180028d4a  mov     ecx, [rbp+37h+arg_10]
0x180028d4d  movzx   r8d, byte ptr [r12+0Eh]
0x180028d53  movzx   r9d, byte ptr [r12+0Dh]
0x180028d59  movzx   r10d, byte ptr [r12+0Ch]
0x180028d5f  movzx   r11d, byte ptr [r12+0Bh]
0x180028d65  movzx   ebx, byte ptr [r12+0Ah]
0x180028d6b  movzx   edi, byte ptr [r12+9]
0x180028d71  movzx   esi, byte ptr [r12+8]
0x180028d77  movzx   r14d, word ptr [r12+6]
0x180028d7d  movzx   r15d, word ptr [r12+4]
0x180028d83  mov     [rsp+88h], ecx
0x180028d8a  mov     rcx, [rbp+37h+arg_18]
0x180028d8e  mov     qword ptr [rsp+100h+var_80], rcx
0x180028d96  mov     rcx, cs:WPP_GLOBAL_Control
0x180028d9d  mov     dword ptr [rsp+100h+var_88], eax
0x180028da1  mov     eax, [r12]
0x180028da5  mov     [rsp+100h+var_90], r8d
0x180028daa  mov     rcx, [rcx+10h]
0x180028dae  mov     [rsp+100h+var_98], r9d
0x180028db3  mov     [rsp+100h+var_A0], r10d
0x180028db8  mov     [rsp+100h+var_A8], r11d
0x180028dbd  mov     [rsp+100h+var_B0], ebx
0x180028dc1  mov     [rsp+100h+var_B8], edi
0x180028dc5  mov     [rsp+100h+var_C0], esi
0x180028dc9  mov     [rsp+100h+var_C8], r14d
0x180028dce  mov     [rsp+100h+var_D0], r15d
0x180028dd3  mov     [rsp+100h+var_D8], eax
0x180028dd7  lea     rax, aSccachewrite; "ScCacheWrite"
0x180028dde  mov     qword ptr [rsp+100h+var_E0], rax
0x180028de3  call    WPP_SF_ssDDDDDDDDDDDSDS
0x180028de8  mov     r14, [rbp+37h+arg_18]
0x180028dec  xor     edi, edi
0x180028dee  mov     r15d, [rbp+37h+arg_38]
0x180028df2  cmp     [r13+5Ch], r15d
0x180028df6  jnb     short loc_180028E02
0x180028df8  mov     ebx, 80100072h
0x180028dfd  jmp     loc_180029264
0x180028e02  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180028e06  mov     [rbp+37h+var_50], 10h
0x180028e0d  mov     rax, rsi
0x180028e10  mov     [rbp+37h+var_48], r12
0x180028e14  inc     rax
0x180028e17  cmp     [r14+rax*2], di
0x180028e1c  jnz     short loc_180028E14
0x180028e1e  add     eax, eax
0x180028e20  mov     [rbp+37h+var_38], r14
0x180028e24  mov     rcx, r13; lpCriticalSection
0x180028e27  mov     [rbp+37h+var_40], eax
0x180028e2a  call    cs:__imp_EnterCriticalSection
0x180028e30  mov     rcx, [r13+28h]
0x180028e34  lea     r9, [rbp+37h+var_60]
0x180028e38  lea     rdx, [rbp+37h+var_50]
0x180028e3c  call    CacheGetItem
0x180028e41  mov     ebx, eax
0x180028e43  test    eax, eax
0x180028e45  jz      loc_1800290AF
0x180028e4b  cmp     eax, 490h
0x180028e50  jnz     loc_18002924D
0x180028e56  jmp     short loc_180028E90
0x180028e58  mov     rdx, [r13+40h]
0x180028e5c  mov     [rbp+37h+var_50], 10h
0x180028e63  mov     rcx, [rdx+28h]
0x180028e67  lea     rax, [rdx+18h]
0x180028e6b  mov     [rbp+37h+var_48], rax
0x180028e6f  mov     rax, rsi
0x180028e72  inc     rax
0x180028e75  cmp     [rcx+rax*2], di
0x180028e79  jnz     short loc_180028E72
0x180028e7b  add     eax, eax
0x180028e7d  mov     [rbp+37h+var_38], rcx
0x180028e81  mov     rcx, r13
0x180028e84  mov     [rbp+37h+var_40], eax
0x180028e87  lea     r8, [rbp+37h+var_50]
0x180028e8b  call    I_ServerCacheRemoveItem
0x180028e90  mov     ecx, [r13+50h]
0x180028e94  add     ecx, r15d
0x180028e97  cmp     [r13+58h], ecx
0x180028e9b  jb      short loc_180028E58
0x180028e9d  mov     rax, [r13+30h]
0x180028ea1  mov     ecx, 50h ; 'P'
0x180028ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028eab  xor     ebx, ebx
0x180028ead  mov     rdi, rax
0x180028eb0  test    rax, rax
0x180028eb3  jnz     short loc_180028F0A
0x180028eb5  lea     edx, [rax+2]
0x180028eb8  call    WppTraceIndent
0x180028ebd  lea     ebx, [rdi+8]
0x180028ec0  mov     rcx, cs:WPP_GLOBAL_Control
0x180028ec7  lea     r14, WPP_GLOBAL_Control
0x180028ece  cmp     rcx, r14
0x180028ed1  jz      loc_180029254
0x180028ed7  test    byte ptr [rcx+1Ch], 1
0x180028edb  jz      loc_180029254
0x180028ee1  cmp     byte ptr [rcx+19h], 2
0x180028ee5  jb      loc_180029254
0x180028eeb  mov     r9, cs:WPP_pszIndent
0x180028ef2  lea     edx, [rdi+1Dh]
0x180028ef5  mov     rcx, [rcx+10h]
0x180028ef9  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180028f00  call    WPP_SF_s
0x180028f05  jmp     loc_180029254
0x180028f0a  mov     rcx, rsi
0x180028f0d  inc     rcx
0x180028f10  cmp     [r14+rcx*2], bx
0x180028f15  jnz     short loc_180028F0D
0x180028f17  mov     rax, [r13+30h]
0x180028f1b  lea     rcx, ds:2[rcx*2]
0x180028f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f28  mov     [rdi+28h], rax
0x180028f2c  test    rax, rax
0x180028f2f  jnz     short loc_180028F6E
0x180028f31  lea     edx, [rax+2]
0x180028f34  call    WppTraceIndent
0x180028f39  mov     ebx, 8
0x180028f3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f45  lea     r14, WPP_GLOBAL_Control
0x180028f4c  cmp     rcx, r14
0x180028f4f  jz      loc_18002909F
0x180028f55  test    byte ptr [rcx+1Ch], 1
0x180028f59  jz      loc_18002909F
0x180028f5f  cmp     byte ptr [rcx+19h], 2
0x180028f63  jb      loc_18002909F
0x180028f69  lea     edx, [rbx+16h]
0x180028f6c  jmp     short loc_180028FE1
0x180028f6e  mov     r8, rsi
0x180028f71  inc     r8
0x180028f74  cmp     [r14+r8*2], bx
0x180028f79  jnz     short loc_180028F71
0x180028f7b  lea     r8, ds:2[r8*2]; Size
0x180028f83  mov     rdx, r14; Src
0x180028f86  mov     rcx, rax; void *
0x180028f89  call    memcpy_0
0x180028f8e  mov     [rdi+8], r15d
0x180028f92  mov     rcx, r15
0x180028f95  mov     rax, [r13+30h]
0x180028f99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f9e  mov     [rdi], rax
0x180028fa1  test    rax, rax
0x180028fa4  jnz     short loc_180028FFD
0x180028fa6  lea     edx, [rax+2]
0x180028fa9  call    WppTraceIndent
0x180028fae  mov     ebx, 8
0x180028fb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180028fba  lea     r14, WPP_GLOBAL_Control
0x180028fc1  cmp     rcx, r14
0x180028fc4  jz      loc_18002909F
0x180028fca  test    byte ptr [rcx+1Ch], 1
0x180028fce  jz      loc_18002909F
0x180028fd4  cmp     byte ptr [rcx+19h], 2
0x180028fd8  jb      loc_18002909F
0x180028fde  lea     edx, [rbx+17h]
0x180028fe1  mov     r9, cs:WPP_pszIndent
0x180028fe8  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180028fef  mov     rcx, [rcx+10h]
0x180028ff3  call    WPP_SF_s
0x180028ff8  jmp     loc_18002909F
0x180028ffd  mov     r8d, [rdi+8]; Size
0x180029001  mov     rcx, rax; void *
0x180029004  mov     rdx, [rbp+37h+Src]; Src
0x180029008  call    memcpy_0
0x18002900d  mov     eax, [rbp+37h+arg_10]
0x180029010  lea     rcx, [rdi+10h]; Time
0x180029014  mov     [rdi+0Ch], eax
0x180029017  call    cs:__imp_time
0x18002901d  movups  xmm0, xmmword ptr [r12]
0x180029022  mov     qword ptr [rbp+37h+var_60+8], rdi
0x180029026  mov     dword ptr [rbp+37h+var_60], 50h ; 'P'
0x18002902d  movdqu  xmmword ptr [rdi+18h], xmm0
0x180029032  mov     [rbp+37h+var_50], 10h
0x180029039  mov     [rbp+37h+var_48], r12
0x18002903d  inc     rsi
0x180029040  cmp     [r14+rsi*2], bx
0x180029045  jnz     short loc_18002903D
0x180029047  mov     rcx, [r13+28h]
0x18002904b  lea     eax, [rsi+rsi]
0x18002904e  lea     r9, [rbp+37h+var_60]
0x180029052  mov     [rbp+37h+var_40], eax
0x180029055  lea     rdx, [rbp+37h+var_50]
0x180029059  mov     [rbp+37h+var_38], r14
0x18002905d  call    CacheAddItem
0x180029062  mov     ebx, eax
0x180029064  test    eax, eax
0x180029066  jnz     short loc_180029098
0x180029068  mov     rax, [r13+48h]
0x18002906c  mov     [rdi+30h], rax
0x180029070  test    rax, rax
0x180029073  jz      short loc_180029079
0x180029075  mov     [rax+38h], rdi
0x180029079  cmp     qword ptr [r13+40h], 0
0x18002907e  mov     [r13+48h], rdi
0x180029082  jnz     short loc_180029088
0x180029084  mov     [r13+40h], rdi
0x180029088  mov     eax, [rdi+8]
0x18002908b  add     [r13+50h], eax
0x18002908f  inc     dword ptr [r13+54h]
0x180029093  jmp     loc_18002924D
0x180029098  lea     r14, WPP_GLOBAL_Control
0x18002909f  mov     rdx, rdi
0x1800290a2  mov     rcx, r13
0x1800290a5  call    I_ServerCacheFreeItem
0x1800290aa  jmp     loc_180029254
0x1800290af  mov     rdi, qword ptr [rbp+37h+var_60+8]
0x1800290b3  mov     r14d, [rbp+37h+arg_10]
0x1800290b7  cmp     [rdi+0Ch], r14d
0x1800290bb  jnz     short loc_1800290E0
0x1800290bd  cmp     [rdi+8], r15d
0x1800290c1  jnz     short loc_1800290E0
0x1800290c3  mov     r8d, [rdi+8]; Size
0x1800290c7  mov     rdx, [rbp+37h+Src]; Buf2
0x1800290cb  mov     rcx, [rdi]; Buf1
0x1800290ce  call    memcmp_0
0x1800290d3  xor     r12d, r12d
0x1800290d6  test    eax, eax
0x1800290d8  jz      loc_180029242
0x1800290de  jmp     short loc_1800290E3
0x1800290e0  xor     r12d, r12d
0x1800290e3  mov     rdx, rdi
0x1800290e6  mov     [rdi+0Ch], r14d
0x1800290ea  mov     rcx, r13
0x1800290ed  call    I_ServerCacheSetMRU
0x1800290f2  jmp     short loc_18002912D
0x1800290f4  mov     rdx, [r13+40h]
0x1800290f8  mov     [rbp+37h+var_50], 10h
0x1800290ff  mov     rcx, [rdx+28h]
0x180029103  lea     rax, [rdx+18h]
0x180029107  mov     [rbp+37h+var_48], rax
0x18002910b  mov     rax, rsi
0x18002910e  inc     rax
0x180029111  cmp     [rcx+rax*2], r12w
0x180029116  jnz     short loc_18002910E
0x180029118  add     eax, eax
0x18002911a  mov     [rbp+37h+var_38], rcx
0x18002911e  mov     rcx, r13
0x180029121  mov     [rbp+37h+var_40], eax
0x180029124  lea     r8, [rbp+37h+var_50]
0x180029128  call    I_ServerCacheRemoveItem
0x18002912d  mov     eax, r15d
0x180029130  sub     eax, [rdi+8]
0x180029133  add     eax, [r13+50h]
0x180029137  cmp     [r13+58h], eax
0x18002913b  jb      short loc_1800290F4
0x18002913d  mov     rcx, [rdi]
0x180029140  mov     rax, [r13+38h]
0x180029144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029149  mov     [rdi], r12
0x18002914c  mov     rcx, r15
0x18002914f  mov     rax, [r13+30h]
0x180029153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029158  mov     [rdi], rax
0x18002915b  test    rax, rax
  ... truncated ...
```
