# ScCacheWrite

- ea: `0x1800029c8`
- end: `0x180003450`
- name: `ScCacheWrite`
- size: `2696`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, char *, unsigned int, _WORD *, int, void *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x180002584`

## callees

- `0x1800028b0`
- `0x1800028e0`
- `0x1800029c8`
- `0x180004980`
- `0x180005700`
- `0x1800058ec`
- `0x180015074`
- `0x180018488`
- `0x180018514`
- `0x180023276`
- `0x180028b78`
- `0x18002ab90`
- `0x180031294`
- `0x180032696`
- `0x1800326d0`
- `0x180037010`

## import_xrefs

- `msvcrt!time` at `0x180002d94`
- `msvcrt!time` at `0x180002d94`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002b9d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002b9d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800033d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800033d1`

## string_xrefs

- `0x180002b49`: `ScCacheWrite`

## pseudocode

```c
__int64 __fastcall ScCacheWrite(
        LPCRITICAL_SECTION lpCriticalSection,
        char *a2,
        unsigned int a3,
        _WORD *a4,
        int a5,
        void *a6,
        void *a7,
        unsigned int a8)
{
  unsigned int v9; // ebx
  PVOID v12; // rcx
  unsigned int v13; // esi
  __int64 v14; // r14
  __int64 v15; // rax
  __int64 v16; // r8
  unsigned int Item; // eax
  unsigned int i; // ecx
  _QWORD *LockSemaphore; // rdx
  _WORD *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rcx
  _DWORD *v23; // rdi
  __int64 v24; // rcx
  void *v25; // rax
  __int64 v26; // rcx
  _QWORD *v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r8
  void *v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rcx
  _WORD *v34; // rsi
  __int64 v35; // rcx
  _QWORD *v36; // rbx
  void *v37; // rcx
  __int64 v38; // r8
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rsi
  _QWORD *v40; // rax
  __int64 v41; // rdx
  _QWORD *v42; // rbx
  unsigned int v43; // eax
  __int64 v44; // rax
  __int64 v45; // rcx
  ULONG_PTR SpinCount; // rax
  __int64 v47; // rdi
  unsigned int v48; // r8d
  _WORD *v49; // r13
  unsigned int v50; // ecx
  unsigned __int16 *v51; // rdx
  int v52; // eax
  int v53; // r9d
  _QWORD *v54; // rax
  __int64 v55; // rcx
  _QWORD *v56; // r12
  _WORD *v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rbx
  void *v60; // rcx
  unsigned int j; // eax
  _QWORD *v62; // rdx
  _WORD *v63; // rcx
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rcx
  _QWORD *v67; // rcx
  __int64 v68; // rdx
  void *v69; // rdx
  unsigned int k; // ebx
  _QWORD *v71; // rax
  __int64 v72; // rcx
  _WORD *v73; // r12
  __int64 v74; // rcx
  void *v75; // rcx
  int v79; // [rsp+B0h] [rbp-70h] BYREF
  char *v80; // [rsp+B8h] [rbp-68h]
  int v81; // [rsp+C0h] [rbp-60h]
  _WORD *v82; // [rsp+C8h] [rbp-58h]
  void *v83; // [rsp+D0h] [rbp-50h]
  void *Buf2; // [rsp+D8h] [rbp-48h]
  _OWORD v85[2]; // [rsp+E0h] [rbp-40h] BYREF

  v9 = a8;
  v83 = a6;
  Buf2 = a7;
  WppTraceIndent(lpCriticalSection, 0);
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
  }
  v85[0] = 0;
  if ( !a4 || !a2 )
  {
    v13 = -2146435068;
    goto LABEL_135;
  }
  WppTraceIndent(v12, 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_ssDDDDDDDDDDDSDS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
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
      (__int64)a4,
      a3,
      (__int64)v83);
    v9 = a8;
  }
  if ( lpCriticalSection[2].RecursionCount >= v9 )
  {
    v14 = -1;
    v79 = 16;
    v15 = -1;
    v80 = a2;
    do
      ++v15;
    while ( a4[v15] );
    v82 = a4;
    v81 = 2 * v15;
    EnterCriticalSection(lpCriticalSection);
    Item = CacheGetItem(lpCriticalSection[1].DebugInfo, &v79, v16, v85);
    v13 = Item;
    if ( Item )
    {
      if ( Item == 1168 )
      {
        for ( i = v9 + LODWORD(lpCriticalSection[2].DebugInfo);
              lpCriticalSection[2].LockCount < i;
              i = v9 + LODWORD(lpCriticalSection[2].DebugInfo) )
        {
          LockSemaphore = lpCriticalSection[1].LockSemaphore;
          v79 = 16;
          v20 = (_WORD *)LockSemaphore[5];
          v80 = (char *)(LockSemaphore + 3);
          v21 = -1;
          do
            ++v21;
          while ( v20[v21] );
          v82 = v20;
          v81 = 2 * v21;
          I_ServerCacheRemoveItem(lpCriticalSection, LockSemaphore, &v79);
        }
        v23 = (_DWORD *)(*(__int64 (__fastcall **)(__int64))&lpCriticalSection[1].LockCount)(80);
        if ( !v23 )
        {
          WppTraceIndent(v22, 2);
          v13 = 8;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              29,
              &WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
              WPP_pszIndent);
          }
          goto LABEL_133;
        }
        v24 = -1;
        do
          ++v24;
        while ( a4[v24] );
        v25 = (void *)(*(__int64 (__fastcall **)(__int64))&lpCriticalSection[1].LockCount)(2 * v24 + 2);
        *((_QWORD *)v23 + 5) = v25;
        if ( !v25 )
        {
          WppTraceIndent(v26, 2);
          v13 = 8;
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_35;
          }
          v28 = 30;
          goto LABEL_34;
        }
        v29 = -1;
        do
          ++v29;
        while ( a4[v29] );
        memcpy_0(v25, a4, 2 * v29 + 2);
        v23[2] = v9;
        v30 = (void *)(*(__int64 (__fastcall **)(_QWORD))&lpCriticalSection[1].LockCount)(v9);
        *(_QWORD *)v23 = v30;
        if ( !v30 )
        {
          WppTraceIndent(v31, 2);
          v13 = 8;
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_35;
          }
          v28 = 31;
          goto LABEL_34;
        }
        memcpy_0(v30, Buf2, (unsigned int)v23[2]);
        v23[3] = a3;
        time((time_t *const)v23 + 2);
        *(_OWORD *)(v23 + 6) = *(_OWORD *)a2;
        if ( a5 == 1 )
        {
          v32 = (*(__int64 (__fastcall **)(__int64))&lpCriticalSection[1].LockCount)(8);
          *((_QWORD *)v23 + 8) = v32;
          if ( !v32 )
          {
            WppTraceIndent(v33, 2);
            v13 = 8;
            v27 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_35;
            }
            v28 = 32;
            goto LABEL_34;
          }
          v34 = v83;
          v35 = -1;
          do
            ++v35;
          while ( *((_WORD *)v83 + v35) );
          v36 = (_QWORD *)*((_QWORD *)v23 + 8);
          *v36 = (*(__int64 (__fastcall **)(__int64))&lpCriticalSection[1].LockCount)(2 * v35 + 2);
          v37 = (void *)**((_QWORD **)v23 + 8);
          if ( !v37 )
          {
            WppTraceIndent(0, 2);
            v13 = 8;
            v27 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_35;
            }
            v28 = 33;
LABEL_34:
            WPP_SF_s(v27[2], v28, &WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
            goto LABEL_35;
          }
          v38 = -1;
          do
            ++v38;
          while ( v34[v38] );
          memcpy_0(v37, v34, 2 * v38 + 2);
          v23[18] = 1;
        }
        v80 = a2;
        v79 = 16;
        do
          ++v14;
        while ( a4[v14] );
        DebugInfo = lpCriticalSection[1].DebugInfo;
        v81 = 2 * v14;
        v82 = a4;
        v40 = AllocH(0x38u);
        v42 = v40;
        if ( v40 )
        {
          *(_DWORD *)v40 = 80;
          v40[1] = v23;
          v43 = I_CacheHashKeys(&v79, v41, v85);
          if ( v43 )
          {
            v13 = WIN32_FROM_NTSTATUS(v43);
            if ( v13 )
              goto LABEL_35;
          }
          else
          {
            *(_OWORD *)(v42 + 3) = v85[0];
            *(_OWORD *)(v42 + 5) = v85[1];
            v44 = v85[0] & 0xF;
            v45 = *((_QWORD *)&DebugInfo->Type + v44);
            if ( v45 )
              v42[2] = v45;
            *((_QWORD *)&DebugInfo->Type + v44) = v42;
            ++DebugInfo[2].EntryCount;
            v13 = 0;
          }
          SpinCount = lpCriticalSection[1].SpinCount;
          *((_QWORD *)v23 + 6) = SpinCount;
          if ( SpinCount )
            *(_QWORD *)(SpinCount + 56) = v23;
          lpCriticalSection[1].SpinCount = (ULONG_PTR)v23;
          if ( !lpCriticalSection[1].LockSemaphore )
            lpCriticalSection[1].LockSemaphore = v23;
          LODWORD(lpCriticalSection[2].DebugInfo) += v23[2];
          ++HIDWORD(lpCriticalSection[2].DebugInfo);
          goto LABEL_133;
        }
        v13 = 8;
LABEL_35:
        I_ServerCacheFreeItem(lpCriticalSection, v23);
      }
LABEL_133:
      LeaveCriticalSection(lpCriticalSection);
      goto LABEL_135;
    }
    v47 = *((_QWORD *)&v85[0] + 1);
    if ( *(_QWORD *)(*((_QWORD *)&v85[0] + 1) + 8LL) == __PAIR64__(a3, v9)
      && !memcmp_0(**((const void ***)&v85[0] + 1), Buf2, *(unsigned int *)(*((_QWORD *)&v85[0] + 1) + 8LL)) )
    {
      if ( a5 == 1 )
      {
        v48 = *(_DWORD *)(v47 + 72);
        v49 = v83;
        v50 = 0;
        if ( v48 )
        {
          do
          {
            v51 = (unsigned __int16 *)v83;
            do
            {
              v52 = *(unsigned __int16 *)((char *)v51 + *(_QWORD *)(*(_QWORD *)(v47 + 64) + 8LL * v50) - (_QWORD)v83);
              v53 = *v51 - v52;
              if ( v53 )
                break;
              ++v51;
            }
            while ( v52 );
            if ( !v53 )
              goto LABEL_132;
          }
          while ( ++v50 < v48 );
        }
        if ( v50 == v48 )
        {
          v54 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))&lpCriticalSection[1].LockCount)(8LL * (v48 + 1));
          v56 = v54;
          if ( !v54 )
          {
            WppTraceIndent(v55, 2);
            v13 = 8;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                34,
                &WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
                WPP_pszIndent);
            }
            goto LABEL_90;
          }
          memcpy_0(v54, *(const void **)(v47 + 64), 8LL * *(unsigned int *)(v47 + 72));
          v58 = -1;
          do
            ++v58;
          while ( v49[v58] );
          v59 = *(unsigned int *)(v47 + 72);
          v56[v59] = (*(__int64 (__fastcall **)(__int64))&lpCriticalSection[1].LockCount)(2 * v58 + 2);
          v60 = (void *)v56[*(unsigned int *)(v47 + 72)];
          if ( !v60 )
          {
            WppTraceIndent(0, 2);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                35,
                &WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
                WPP_pszIndent);
            }
            ((void (__fastcall *)(_QWORD *))lpCriticalSection[1].OwningThread)(v56);
            v13 = 8;
            goto LABEL_90;
          }
          do
            ++v14;
          while ( v49[v14] );
          memcpy_0(v60, v49, 2 * v14 + 2);
          ((void (__fastcall *)(_QWORD))lpCriticalSection[1].OwningThread)(*(_QWORD *)(v47 + 64));
          ++*(_DWORD *)(v47 + 72);
          *(_QWORD *)(v47 + 64) = v56;
        }
      }
LABEL_132:
      I_ServerCacheSetMRU(lpCriticalSection, v47);
      goto LABEL_133;
    }
    *(_DWORD *)(v47 + 12) = a3;
    I_ServerCacheSetMRU(lpCriticalSection, v47);
    for ( j = LODWORD(lpCriticalSection[2].DebugInfo) + v9 - *(_DWORD *)(v47 + 8);
          lpCriticalSection[2].LockCount < j;
          j = v9 + LODWORD(lpCriticalSection[2].DebugInfo) - *(_DWORD *)(v47 + 8) )
    {
      v62 = lpCriticalSection[1].LockSemaphore;
      v79 = 16;
      v63 = (_WORD *)v62[5];
      v80 = (char *)(v62 + 3);
      v64 = -1;
      do
        ++v64;
      while ( v63[v64] );
      v82 = v63;
      v81 = 2 * v64;
      I_ServerCacheRemoveItem(lpCriticalSection, v62, &v79);
    }
    ((void (__fastcall *)(_QWORD))lpCriticalSection[1].OwningThread)(*(_QWORD *)v47);
    *(_QWORD *)v47 = 0;
    v65 = (*(__int64 (__fastcall **)(_QWORD))&lpCriticalSection[1].LockCount)(v9);
    *(_QWORD *)v47 = v65;
    if ( v65 )
    {
      LODWORD(lpCriticalSection[2].DebugInfo) -= *(_DWORD *)(v47 + 8);
      v69 = Buf2;
      *(_DWORD *)(v47 + 8) = v9;
      LODWORD(lpCriticalSection[2].DebugInfo) += v9;
      memcpy_0(*(void **)v47, v69, *(unsigned int *)(v47 + 8));
      for ( k = 0; k < *(_DWORD *)(v47 + 72); ++k )
        ((void (__fastcall *)(_QWORD))lpCriticalSection[1].OwningThread)(*(_QWORD *)(*(_QWORD *)(v47 + 64) + 8LL * k));
      ((void (__fastcall *)(_QWORD))lpCriticalSection[1].OwningThread)(*(_QWORD *)(v47 + 64));
      *(_QWORD *)(v47 + 64) = 0;
      *(_DWORD *)(v47 + 72) = 0;
      if ( a5 != 1 )
        goto LABEL_132;
      v71 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))&lpCriticalSection[1].LockCount)(8);
      *(_QWORD *)(v47 + 64) = v71;
      if ( v71 )
      {
        v73 = v83;
        v74 = -1;
        do
          ++v74;
        while ( *((_WORD *)v83 + v74) );
        *v71 = (*(__int64 (__fastcall **)(__int64))&lpCriticalSection[1].LockCount)(2 * v74 + 2);
        v75 = **(void ***)(v47 + 64);
        if ( v75 )
        {
          do
            ++v14;
          while ( v73[v14] );
          memcpy_0(v75, v73, 2 * v14 + 2);
          *(_DWORD *)(v47 + 72) = 1;
          goto LABEL_132;
        }
        WppTraceIndent(0, 2);
        v13 = 8;
        v67 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v68 = 38;
          goto LABEL_114;
        }
      }
      else
      {
        WppTraceIndent(v72, 2);
        v13 = 8;
        v67 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v68 = 37;
          goto LABEL_114;
        }
      }
    }
    else
    {
      WppTraceIndent(v66, 2);
      v13 = 8;
      v67 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v68 = 36;
LABEL_114:
        WPP_SF_s(v67[2], v68, &WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
      }
    }
LABEL_90:
    if ( v47 )
    {
      v57 = *(_WORD **)(v47 + 40);
      v80 = (char *)(v47 + 24);
      v79 = 16;
      do
        ++v14;
      while ( v57[v14] );
      v82 = v57;
      v81 = 2 * v14;
      I_ServerCacheRemoveItem(lpCriticalSection, v47, &v79);
    }
    goto LABEL_133;
  }
  v13 = -2146434958;
LABEL_135:
  WppTraceIndent(v12, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      (unsigned int)&WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
      WPP_pszIndent,
      v13);
  }
  return v13;
}

```

## disassembly

```asm
0x1800029c8  mov     [rsp-8+arg_8], rbx
0x1800029cd  push    rbp
0x1800029ce  push    rsi
0x1800029cf  push    rdi
0x1800029d0  push    r12
0x1800029d2  push    r13
0x1800029d4  push    r14
0x1800029d6  push    r15
0x1800029d8  lea     rbp, [rsp+10h]
0x1800029dd  sub     rsp, 110h
0x1800029e4  mov     rax, cs:__security_cookie
0x1800029eb  xor     rax, rsp
0x1800029ee  mov     [rbp+20h+var_40], rax
0x1800029f2  mov     rax, [rbp+20h+arg_28]
0x1800029f6  mov     r12, rdx
0x1800029f9  mov     ebx, [rbp+20h+arg_38]
0x1800029fc  xor     edx, edx
0x1800029fe  mov     [rbp+20h+var_70], rax
0x180002a02  mov     rdi, r9
0x180002a05  mov     rax, [rbp+20h+arg_30]
0x180002a09  mov     r15, rcx
0x180002a0c  mov     [rbp+20h+Buf2], rax
0x180002a10  mov     [rbp+20h+Src], r9
0x180002a14  mov     dword ptr [rbp+20h+var_94], r8d
0x180002a18  mov     [rbp+20h+var_98], ebx
0x180002a1b  call    WppTraceIndent
0x180002a20  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a27  lea     r14, WPP_GLOBAL_Control
0x180002a2e  cmp     rcx, r14
0x180002a31  jz      short loc_180002A5B
0x180002a33  test    byte ptr [rcx+1Ch], 2
0x180002a37  jz      short loc_180002A5B
0x180002a39  cmp     byte ptr [rcx+19h], 5
0x180002a3d  jb      short loc_180002A5B
0x180002a3f  mov     r9, cs:WPP_pszIndent
0x180002a46  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180002a4d  mov     rcx, [rcx+10h]
0x180002a51  mov     edx, 1Bh
0x180002a56  call    WPP_SF_s
0x180002a5b  xor     esi, esi
0x180002a5d  xorps   xmm0, xmm0
0x180002a60  movups  [rbp+20h+var_60], xmm0
0x180002a64  test    rdi, rdi
0x180002a67  jz      loc_1800033D9
0x180002a6d  test    r12, r12
0x180002a70  jz      loc_1800033D9
0x180002a76  lea     edx, [rsi+2]
0x180002a79  call    WppTraceIndent
0x180002a7e  mov     r13, cs:WPP_GLOBAL_Control
0x180002a85  cmp     r13, r14
0x180002a88  jz      loc_180002B5F
0x180002a8e  test    byte ptr [r13+1Ch], 4
0x180002a93  jz      loc_180002B5F
0x180002a99  cmp     byte ptr [r13+19h], 4
0x180002a9e  jb      loc_180002B5F
0x180002aa4  movzx   eax, byte ptr [r12+0Fh]
0x180002aaa  mov     edx, 1Ch
0x180002aaf  mov     r13, [rbp+20h+var_70]
0x180002ab3  movzx   ecx, byte ptr [r12+0Eh]
0x180002ab9  movzx   r8d, byte ptr [r12+0Dh]
0x180002abf  movzx   r9d, byte ptr [r12+0Ch]
0x180002ac5  movzx   r10d, byte ptr [r12+0Bh]
0x180002acb  movzx   r11d, byte ptr [r12+0Ah]
0x180002ad1  movzx   ebx, byte ptr [r12+9]
0x180002ad7  movzx   edi, byte ptr [r12+8]
0x180002add  movzx   esi, word ptr [r12+6]
0x180002ae3  movzx   r14d, word ptr [r12+4]
0x180002ae9  mov     [rsp+140h+var_B0], r13; __int64
0x180002af1  mov     r13d, dword ptr [rbp+20h+var_94]
0x180002af5  mov     dword ptr [rsp+140h+var_B8], r13d; char
0x180002afd  mov     r13, [rbp+20h+Src]
0x180002b01  mov     [rsp+140h+var_C0], r13; __int64
0x180002b09  mov     r13, cs:WPP_GLOBAL_Control
0x180002b10  mov     dword ptr [rsp+140h+var_C8], eax; char
0x180002b14  mov     eax, [r12]
0x180002b18  mov     dword ptr [rsp+140h+var_D0], ecx; char
0x180002b1c  mov     rcx, [r13+10h]; LoggerHandle
0x180002b20  mov     dword ptr [rsp+140h+var_D8], r8d; char
0x180002b25  mov     dword ptr [rsp+140h+var_E0], r9d; char
0x180002b2a  mov     dword ptr [rsp+140h+var_E8], r10d; char
0x180002b2f  mov     dword ptr [rsp+140h+var_F0], r11d; char
0x180002b34  mov     dword ptr [rsp+140h+var_F8], ebx; char
0x180002b38  mov     dword ptr [rsp+140h+var_100], edi; char
0x180002b3c  mov     dword ptr [rsp+140h+var_108], esi; char
0x180002b40  mov     dword ptr [rsp+140h+var_110], r14d; char
0x180002b45  mov     dword ptr [rsp+140h+var_118], eax; char
0x180002b49  lea     rax, aSccachewrite; "ScCacheWrite"
0x180002b50  mov     [rsp+140h+var_120], rax; __int64
0x180002b55  call    WPP_SF_ssDDDDDDDDDDDSDS
0x180002b5a  mov     ebx, [rbp+20h+var_98]
0x180002b5d  xor     esi, esi
0x180002b5f  cmp     [r15+5Ch], ebx
0x180002b63  jnb     short loc_180002B6F
0x180002b65  mov     esi, 80100072h
0x180002b6a  jmp     loc_1800033DE
0x180002b6f  mov     r13, [rbp+20h+Src]
0x180002b73  mov     edi, 10h
0x180002b78  or      r14, 0FFFFFFFFFFFFFFFFh
0x180002b7c  mov     [rbp+20h+var_90], edi
0x180002b7f  mov     rax, r14
0x180002b82  mov     [rbp+20h+var_88], r12
0x180002b86  inc     rax
0x180002b89  cmp     [r13+rax*2+0], si
0x180002b8f  jnz     short loc_180002B86
0x180002b91  add     eax, eax
0x180002b93  mov     [rbp+20h+var_78], r13
0x180002b97  mov     rcx, r15; lpCriticalSection
0x180002b9a  mov     [rbp+20h+var_80], eax
0x180002b9d  call    cs:__imp_EnterCriticalSection
0x180002ba3  mov     rcx, [r15+28h]
0x180002ba7  lea     r9, [rbp+20h+var_60]
0x180002bab  lea     rdx, [rbp+20h+var_90]
0x180002baf  mov     dword ptr [rbp+20h+Src], 1
0x180002bb6  call    CacheGetItem
0x180002bbb  mov     esi, eax
0x180002bbd  test    eax, eax
0x180002bbf  jz      loc_180002F71
0x180002bc5  cmp     eax, 490h
0x180002bca  jnz     loc_1800033CE
0x180002bd0  mov     ecx, [r15+50h]
0x180002bd4  add     ecx, ebx
0x180002bd6  xor     esi, esi
0x180002bd8  cmp     [r15+58h], ecx
0x180002bdc  jnb     short loc_180002C1A
0x180002bde  mov     rdx, [r15+40h]
0x180002be2  mov     [rbp+20h+var_90], edi
0x180002be5  mov     rcx, [rdx+28h]
0x180002be9  lea     rax, [rdx+18h]
0x180002bed  mov     [rbp+20h+var_88], rax
0x180002bf1  mov     rax, r14
0x180002bf4  inc     rax
0x180002bf7  cmp     [rcx+rax*2], si
0x180002bfb  jnz     short loc_180002BF4
0x180002bfd  add     eax, eax
0x180002bff  mov     [rbp+20h+var_78], rcx
0x180002c03  mov     rcx, r15
0x180002c06  mov     [rbp+20h+var_80], eax
0x180002c09  lea     r8, [rbp+20h+var_90]
0x180002c0d  call    I_ServerCacheRemoveItem
0x180002c12  mov     ecx, [r15+50h]
0x180002c16  add     ecx, ebx
0x180002c18  jmp     short loc_180002BD8
0x180002c1a  mov     rax, [r15+30h]
0x180002c1e  mov     ecx, 50h ; 'P'
0x180002c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c28  mov     rdi, rax
0x180002c2b  test    rax, rax
0x180002c2e  jnz     short loc_180002C85
0x180002c30  lea     edx, [rax+2]
0x180002c33  call    WppTraceIndent
0x180002c38  lea     esi, [rdi+8]
0x180002c3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c42  lea     rax, WPP_GLOBAL_Control
0x180002c49  cmp     rcx, rax
0x180002c4c  jz      loc_1800033CE
0x180002c52  test    byte ptr [rcx+1Ch], 1
0x180002c56  jz      loc_1800033CE
0x180002c5c  cmp     byte ptr [rcx+19h], 2
0x180002c60  jb      loc_1800033CE
0x180002c66  mov     r9, cs:WPP_pszIndent
0x180002c6d  lea     edx, [rdi+1Dh]
0x180002c70  mov     rcx, [rcx+10h]
0x180002c74  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180002c7b  call    WPP_SF_s
0x180002c80  jmp     loc_1800033CE
0x180002c85  mov     rcx, r14
0x180002c88  inc     rcx
0x180002c8b  cmp     [r13+rcx*2+0], si
0x180002c91  jnz     short loc_180002C88
0x180002c93  mov     rax, [r15+30h]
0x180002c97  lea     rcx, ds:2[rcx*2]
0x180002c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ca4  mov     [rdi+28h], rax
0x180002ca8  test    rax, rax
0x180002cab  jnz     short loc_180002D0F
0x180002cad  lea     edx, [rax+2]
0x180002cb0  call    WppTraceIndent
0x180002cb5  mov     esi, 8
0x180002cba  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cc1  lea     rax, WPP_GLOBAL_Control
0x180002cc8  cmp     rcx, rax
0x180002ccb  jz      short loc_180002CF3
0x180002ccd  test    byte ptr [rcx+1Ch], 1
0x180002cd1  jz      short loc_180002CF3
0x180002cd3  cmp     byte ptr [rcx+19h], 2
0x180002cd7  jb      short loc_180002CF3
0x180002cd9  lea     edx, [rsi+16h]
0x180002cdc  mov     r9, cs:WPP_pszIndent
0x180002ce3  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180002cea  mov     rcx, [rcx+10h]
0x180002cee  call    WPP_SF_s
0x180002cf3  mov     ebx, dword ptr [rbp+20h+Src]
0x180002cf6  mov     rdx, rdi
0x180002cf9  mov     rcx, r15
0x180002cfc  call    I_ServerCacheFreeItem
0x180002d01  cmp     ebx, 1
0x180002d04  jz      loc_1800033CE
0x180002d0a  jmp     loc_1800033DE
0x180002d0f  mov     r8, r14
0x180002d12  inc     r8
0x180002d15  cmp     [r13+r8*2+0], si
0x180002d1b  jnz     short loc_180002D12
0x180002d1d  lea     r8, ds:2[r8*2]; Size
0x180002d25  mov     rdx, r13; Src
0x180002d28  mov     rcx, rax; void *
0x180002d2b  call    memcpy_0
0x180002d30  mov     [rdi+8], ebx
0x180002d33  mov     rax, [r15+30h]
0x180002d37  mov     ecx, ebx
0x180002d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d3e  mov     [rdi], rax
0x180002d41  test    rax, rax
0x180002d44  jnz     short loc_180002D7A
0x180002d46  lea     edx, [rax+2]
0x180002d49  call    WppTraceIndent
0x180002d4e  mov     esi, 8
0x180002d53  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d5a  lea     rax, WPP_GLOBAL_Control
0x180002d61  cmp     rcx, rax
0x180002d64  jz      short loc_180002CF3
0x180002d66  test    byte ptr [rcx+1Ch], 1
0x180002d6a  jz      short loc_180002CF3
0x180002d6c  cmp     byte ptr [rcx+19h], 2
0x180002d70  jb      short loc_180002CF3
0x180002d72  lea     edx, [rsi+17h]
0x180002d75  jmp     loc_180002CDC
0x180002d7a  mov     r8d, [rdi+8]; Size
0x180002d7e  mov     rcx, rax; void *
0x180002d81  mov     rdx, [rbp+20h+Buf2]; Src
0x180002d85  call    memcpy_0
0x180002d8a  mov     eax, dword ptr [rbp+20h+var_94]
0x180002d8d  lea     rcx, [rdi+10h]; Time
0x180002d91  mov     [rdi+0Ch], eax
0x180002d94  call    cs:__imp_time
0x180002d9a  cmp     [rbp+20h+arg_20], 1
0x180002d9e  movups  xmm0, xmmword ptr [r12]
0x180002da3  movdqu  xmmword ptr [rdi+18h], xmm0
0x180002da8  jnz     loc_180002EA1
0x180002dae  mov     rax, [r15+30h]
0x180002db2  mov     ecx, 8
0x180002db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dbc  mov     [rdi+40h], rax
0x180002dc0  test    rax, rax
0x180002dc3  jnz     short loc_180002E05
0x180002dc5  lea     edx, [rax+2]
0x180002dc8  call    WppTraceIndent
0x180002dcd  mov     esi, 8
0x180002dd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180002dd9  lea     rax, WPP_GLOBAL_Control
0x180002de0  cmp     rcx, rax
0x180002de3  jz      loc_180002CF3
0x180002de9  test    byte ptr [rcx+1Ch], 1
0x180002ded  jz      loc_180002CF3
0x180002df3  cmp     byte ptr [rcx+19h], 2
0x180002df7  jb      loc_180002CF3
0x180002dfd  lea     edx, [rsi+18h]
0x180002e00  jmp     loc_180002CDC
0x180002e05  mov     rsi, [rbp+20h+var_70]
0x180002e09  mov     rcx, r14
0x180002e0c  xor     eax, eax
0x180002e0e  inc     rcx
0x180002e11  cmp     [rsi+rcx*2], ax
0x180002e15  jnz     short loc_180002E0E
0x180002e17  mov     rax, [r15+30h]
0x180002e1b  lea     rcx, ds:2[rcx*2]
0x180002e23  mov     rbx, [rdi+40h]
0x180002e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e2c  mov     [rbx], rax
0x180002e2f  mov     rax, [rdi+40h]
0x180002e33  mov     rcx, [rax]; void *
0x180002e36  xor     eax, eax
0x180002e38  test    rcx, rcx
0x180002e3b  jnz     short loc_180002E7D
0x180002e3d  lea     edx, [rax+2]
0x180002e40  call    WppTraceIndent
0x180002e45  mov     esi, 8
0x180002e4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e51  lea     rax, WPP_GLOBAL_Control
0x180002e58  cmp     rcx, rax
0x180002e5b  jz      loc_180002CF3
0x180002e61  test    byte ptr [rcx+1Ch], 1
0x180002e65  jz      loc_180002CF3
0x180002e6b  cmp     byte ptr [rcx+19h], 2
0x180002e6f  jb      loc_180002CF3
0x180002e75  lea     edx, [rsi+19h]
0x180002e78  jmp     loc_180002CDC
0x180002e7d  mov     r8, r14
0x180002e80  inc     r8
0x180002e83  cmp     [rsi+r8*2], ax
0x180002e88  jnz     short loc_180002E80
0x180002e8a  lea     r8, ds:2[r8*2]; Size
0x180002e92  mov     rdx, rsi; Src
0x180002e95  call    memcpy_0
0x180002e9a  mov     dword ptr [rdi+48h], 1
0x180002ea1  mov     [rbp+20h+var_88], r12
0x180002ea5  xor     r12d, r12d
0x180002ea8  mov     [rbp+20h+var_90], 10h
0x180002eaf  inc     r14
0x180002eb2  cmp     [r13+r14*2+0], r12w
0x180002eb8  jnz     short loc_180002EAF
  ... truncated ...
```
