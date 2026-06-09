# PrepareUnicodePathEx

- ea: `0x18002f238`
- end: `0x18002fb97`
- name: `PrepareUnicodePathEx`
- size: `2399`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `6`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18002dbac`
- `0x18002e2c4`
- `0x18002e4a0`
- `0x18002e578`
- `0x18002eb90`
- `0x18002ef7c`

## callees

- `0x180002ecf`
- `0x180002edb`
- `0x18002d974`
- `0x18002da5c`
- `0x18002eed8`
- `0x18002f08c`
- `0x18002f238`
- `0x180030028`
- `0x1800322ea`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fb55`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fb65`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fb55`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fb65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f2c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f2d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f64c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f6aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f6c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f2c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f2d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f64c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f6aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f6c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f8b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f8e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fb3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f8b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f8e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fb3e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f8c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f8f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fb4c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f8c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f8f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fb4c`
- `ntdll!RtlFreeHeap` at `0x18002f622`
- `ntdll!RtlFreeHeap` at `0x18002f622`
- `ntdll!RtlAllocateHeap` at `0x18002f40c`
- `ntdll!RtlAllocateHeap` at `0x18002f546`
- `ntdll!RtlAllocateHeap` at `0x18002f40c`
- `ntdll!RtlAllocateHeap` at `0x18002f546`

## pseudocode

```c
char *__fastcall PrepareUnicodePathEx(unsigned __int16 *a1, void *a2)
{
  int v2; // r15d
  _QWORD *v3; // r13
  unsigned __int16 *v4; // rbx
  WCHAR *v5; // r12
  signed int v6; // edi
  signed int LastError; // eax
  bool v8; // sf
  signed int v9; // eax
  __int64 v10; // r14
  unsigned __int64 v11; // rax
  char *Heap; // rsi
  int v13; // eax
  const wchar_t *v14; // rbx
  int v15; // r13d
  __int64 v16; // rdi
  __int64 v17; // r15
  bool v18; // zf
  __int64 v19; // rcx
  HRESULT v20; // eax
  unsigned __int16 v21; // di
  HRESULT v22; // eax
  HRESULT v23; // eax
  __int64 v24; // rdi
  __int64 v25; // rbx
  __int64 v26; // rcx
  HRESULT v27; // eax
  HRESULT v28; // eax
  signed int v29; // eax
  bool v30; // sf
  signed int v31; // eax
  signed int v32; // eax
  bool v33; // sf
  signed int v34; // eax
  const wchar_t *i; // r14
  wchar_t *j; // r14
  wchar_t *v37; // rbx
  int v38; // eax
  void *v39; // r15
  HANDLE ProcessHeap; // rax
  HANDLE v41; // rax
  __int16 v42; // cx
  int v43; // eax
  const wchar_t *v44; // rcx
  wchar_t *v45; // rax
  const wchar_t *v46; // rbx
  const wchar_t *k; // rbx
  wchar_t *m; // rbx
  wchar_t v49; // cx
  wchar_t *v50; // rdx
  HANDLE v51; // rax
  DWORD v53; // [rsp+30h] [rbp-D0h]
  DWORD v54; // [rsp+30h] [rbp-D0h]
  DWORD v55; // [rsp+30h] [rbp-D0h]
  size_t pcchRemaining; // [rsp+40h] [rbp-C0h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-B0h]
  size_t cchDest; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v60; // [rsp+60h] [rbp-A0h]
  size_t v61; // [rsp+68h] [rbp-98h]
  wchar_t String2[4]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t pszSrc[8]; // [rsp+78h] [rbp-88h] BYREF
  wchar_t v64[12]; // [rsp+88h] [rbp-78h] BYREF
  wchar_t v65[12]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t v66[12]; // [rsp+B8h] [rbp-48h] BYREF
  wchar_t v67[20]; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t v68[16]; // [rsp+F8h] [rbp-8h] BYREF
  wchar_t v69[16]; // [rsp+118h] [rbp+18h] BYREF
  wchar_t v70[16]; // [rsp+138h] [rbp+38h] BYREF
  wchar_t v71[16]; // [rsp+158h] [rbp+58h] BYREF
  wchar_t v72[24]; // [rsp+178h] [rbp+78h] BYREF

  v2 = 0;
  lpMem = a2;
  v60 = a1;
  wcscpy(String2, L"\\\\?");
  v3 = a2;
  v4 = a1;
  wcscpy(pszSrc, L"\\\\?\\UNC");
  if ( !a1 || !*a1 )
  {
    SetLastError(0x57u);
    return 0;
  }
  v5 = FormFullPathName(a1);
  if ( v5 )
  {
    v6 = 0;
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError < 0;
    if ( LastError > 0 )
      v8 = 1;
    if ( !v8 )
    {
LABEL_139:
      LOWORD(v6) = 16389;
      goto LABEL_140;
    }
    v9 = GetLastError();
    v6 = v9;
    if ( v9 > 0 )
      v6 = (unsigned __int16)v9 | 0x80070000;
    if ( v6 < 0 )
      goto LABEL_140;
  }
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( v5[v11] );
  if ( v11 < 0x104 )
  {
LABEL_68:
    Heap = (char *)StrDupe(v4);
    if ( Heap )
    {
      v6 = 0;
      goto LABEL_76;
    }
    v32 = GetLastError();
    v33 = v32 < 0;
    if ( v32 > 0 )
      v33 = 1;
    if ( v33 )
    {
      v34 = GetLastError();
      v6 = v34;
      if ( v34 > 0 )
        v6 = (unsigned __int16)v34 | 0x80070000;
      if ( v6 < 0 )
        goto LABEL_140;
      goto LABEL_76;
    }
    goto LABEL_139;
  }
  Heap = 0;
  if ( wcsncmp_0(v5, String2, 3u) && wcsnicmp_0(v5, pszSrc, 7u) )
  {
    LODWORD(pcchRemaining) = 0;
    v13 = ParseUncPath(v5);
    LOWORD(v6) = v13;
    if ( v13 < 0 )
    {
LABEL_140:
      Heap = 0;
      goto LABEL_141;
    }
    pszDest = 0;
    v18 = (_DWORD)pcchRemaining == 1;
    pcchRemaining = 0;
    if ( v18 )
    {
      v14 = v5 + 1;
      if ( v5 != (WCHAR *)-2LL )
      {
        v15 = 0;
        v16 = -1;
        do
          ++v16;
        while ( pszSrc[v16] );
        v17 = -1;
        do
          ++v17;
        while ( v14[v17] );
        if ( (_DWORD)v16 )
        {
          if ( pszSrc[(unsigned int)(v16 - 1)] == 92 )
          {
            v18 = *v14 == 92;
            if ( *v14 == 92 )
            {
              LODWORD(v17) = v17 - 1;
              v18 = *v14 == 92;
            }
            if ( !v18 )
              v14 = v5;
            ++v14;
          }
          else if ( *v14 != 92 )
          {
            v15 = 1;
          }
        }
        v19 = (unsigned int)(v16 + v15 + v17 + 1);
        cchDest = (unsigned int)v19;
        Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v19);
        if ( Heap )
        {
          v20 = StringCchCopyNExW(
                  (STRSAFE_LPWSTR)Heap,
                  cchDest,
                  pszSrc,
                  (unsigned int)v16,
                  &pszDest,
                  &pcchRemaining,
                  v53);
          v21 = v20;
          if ( v20 >= 0 )
          {
            if ( !v15
              || (v22 = StringCchCopyNExW(pszDest, pcchRemaining, L"\\", 1u, &pszDest, &pcchRemaining, v54),
                  v21 = v22,
                  v22 >= 0) )
            {
              v23 = StringCchCopyNW(pszDest, pcchRemaining, v14, (unsigned int)v17);
              goto LABEL_55;
            }
          }
          goto LABEL_57;
        }
        goto LABEL_49;
      }
    }
    else if ( v5 )
    {
      cchDest = (size_t)v5;
      v24 = -1;
      do
        ++v24;
      while ( String2[v24] );
      v25 = -1;
      do
        ++v25;
      while ( v5[v25] );
      if ( (_DWORD)v24 )
      {
        if ( String2[(unsigned int)(v24 - 1)] == 92 )
        {
          if ( *v5 == 92 )
          {
            LODWORD(v25) = v25 - 1;
            cchDest = (size_t)(v5 + 1);
          }
        }
        else if ( *v5 != 92 )
        {
          v2 = 1;
        }
      }
      v26 = (unsigned int)(v24 + v2 + v25 + 1);
      v61 = (unsigned int)v26;
      Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v26);
      if ( Heap )
      {
        v27 = StringCchCopyNExW(
                (STRSAFE_LPWSTR)Heap,
                v61,
                String2,
                (unsigned int)v24,
                (STRSAFE_LPWSTR *)&pcchRemaining,
                (size_t *)&pszDest,
                v53);
        v21 = v27;
        if ( v27 >= 0 )
        {
          if ( !v2
            || (v28 = StringCchCopyNExW(
                        (STRSAFE_LPWSTR)pcchRemaining,
                        (size_t)pszDest,
                        L"\\",
                        1u,
                        (STRSAFE_LPWSTR *)&pcchRemaining,
                        (size_t *)&pszDest,
                        v55),
                v21 = v28,
                v28 >= 0) )
          {
            v23 = StringCchCopyNW(
                    (STRSAFE_LPWSTR)pcchRemaining,
                    (size_t)pszDest,
                    (STRSAFE_PCNZWCH)cchDest,
                    (unsigned int)v25);
LABEL_55:
            v21 = v23;
            if ( v23 >= 0 )
            {
              v6 = 0;
              NtCurrentTeb()->LastErrorValue = 0;
LABEL_65:
              v3 = lpMem;
              v4 = v60;
              goto LABEL_66;
            }
          }
        }
LABEL_57:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        NtCurrentTeb()->LastErrorValue = v21;
        goto LABEL_50;
      }
LABEL_49:
      NtCurrentTeb()->LastErrorValue = 8;
LABEL_50:
      Heap = 0;
LABEL_59:
      v29 = GetLastError();
      v30 = v29 < 0;
      if ( v29 > 0 )
        v30 = 1;
      if ( v30 )
      {
        v31 = GetLastError();
        v6 = v31;
        if ( v31 > 0 )
          v6 = (unsigned __int16)v31 | 0x80070000;
      }
      else
      {
        v6 = -2147467259;
      }
      goto LABEL_65;
    }
    NtCurrentTeb()->LastErrorValue = 87;
    goto LABEL_59;
  }
LABEL_66:
  if ( v6 < 0 )
    goto LABEL_102;
  if ( !Heap )
    goto LABEL_68;
LABEL_76:
  if ( !v3 )
    goto LABEL_141;
  wcscpy(v70, L"\\\\?\\GLBALROOT");
  wcscpy(v71, L"\\??\\GLBALROOT");
  wcscpy(v68, L"\\\\arddisk");
  wcscpy(v69, L"\\?arddisk");
  wcscpy(v64, L"Partition");
  wcscpy(v65, L"\\\\?\\Volume{");
  wcscpy(v66, L"\\??\\Volume{");
  if ( wcsnicmp_0((const wchar_t *)Heap, v70, 0xEu) && wcsnicmp_0((const wchar_t *)Heap, v71, 0xEu) )
  {
    if ( !wcsnicmp_0((const wchar_t *)Heap, v68, 0xCu) )
    {
      for ( i = (const wchar_t *)(Heap + 26); (unsigned __int16)(*i - 48) <= 9u; ++i )
        ;
      if ( !wcsnicmp_0(i, v64, 9u) )
      {
        for ( j = (wchar_t *)(i + 10); (unsigned __int16)(*j - 48) <= 9u; ++j )
          ;
        v37 = 0;
        if ( *j == 92 )
          v37 = j;
        goto LABEL_101;
      }
LABEL_90:
      v37 = 0;
      goto LABEL_101;
    }
    if ( !wcsnicmp_0((const wchar_t *)Heap, v65, 0xBu) )
    {
      v37 = (wchar_t *)(Heap + 96);
      goto LABEL_101;
    }
    v37 = 0;
    if ( wcsnicmp_0((const wchar_t *)Heap, pszSrc, 7u) )
    {
      if ( !wcsncmp_0((const wchar_t *)Heap, String2, 3u) )
      {
        v42 = *((_WORD *)Heap + 4);
        if ( ((unsigned __int16)(v42 - 97) <= 0x19u || (unsigned __int16)(v42 - 65) <= 0x19u)
          && *((_WORD *)Heap + 5) == 58 )
        {
          v37 = (wchar_t *)(Heap + 12);
          if ( *((_WORD *)Heap + 6) == 92 )
            goto LABEL_101;
        }
        goto LABEL_90;
      }
      if ( ((unsigned __int16)(*(_WORD *)Heap - 97) <= 0x19u || (unsigned __int16)(*(_WORD *)Heap - 65) <= 0x19u)
        && *((_WORD *)Heap + 1) == 58
        && *((_WORD *)Heap + 2) == 92 )
      {
        v37 = (wchar_t *)(Heap + 4);
        goto LABEL_101;
      }
      LODWORD(pcchRemaining) = 0;
      lpMem = 0;
      v43 = ParseUncPath((STRSAFE_PCNZWCH)Heap);
      v39 = lpMem;
      v6 = v43;
      if ( v43 < 0 )
        goto LABEL_99;
      if ( (_DWORD)pcchRemaining == 1 )
      {
        do
          ++v10;
        while ( *((_WORD *)lpMem + v10) );
        goto LABEL_97;
      }
    }
    else
    {
      LODWORD(pcchRemaining) = 0;
      lpMem = 0;
      v38 = ParseUncPath((STRSAFE_PCNZWCH)Heap);
      v39 = lpMem;
      v6 = v38;
      if ( v38 < 0 )
        goto LABEL_99;
      if ( (_DWORD)pcchRemaining == 1 )
      {
        do
          ++v10;
        while ( *((_WORD *)lpMem + v10) );
LABEL_97:
        v37 = (wchar_t *)&Heap[2 * v10];
        goto LABEL_99;
      }
    }
    v37 = 0;
LABEL_99:
    if ( v39 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v39);
    }
    goto LABEL_101;
  }
  v37 = (wchar_t *)(Heap + 28);
  wcscpy(v72, L"\\Device\\HarddikVolume");
  wcscpy(v67, L"\\Device\\Harddisk");
  if ( !wcsnicmp_0((const wchar_t *)Heap + 14, v72, 0x16u) )
  {
    v44 = (const wchar_t *)(Heap + 74);
    goto LABEL_121;
  }
  if ( !wcsnicmp_0((const wchar_t *)Heap + 14, v67, 0x10u) )
  {
    v45 = wcschr_0((const wchar_t *)Heap + 31, 0x5Cu);
    if ( !v45 )
      goto LABEL_90;
    v46 = v45 + 1;
    if ( wcsnicmp_0(v45 + 1, v64, 9u) )
      goto LABEL_90;
    v44 = v46;
LABEL_121:
    v37 = wcschr_0(v44, 0x5Cu);
    goto LABEL_101;
  }
  if ( !wcsnicmp_0((const wchar_t *)Heap + 14, v66, 0xBu) )
  {
    v37 = (wchar_t *)(Heap + 124);
    goto LABEL_101;
  }
  if ( !wcsnicmp_0((const wchar_t *)Heap + 14, v69, 0xCu) )
  {
    for ( k = (const wchar_t *)(Heap + 54); (unsigned __int16)(*k - 48) <= 9u; ++k )
      ;
    if ( wcsnicmp_0(k, v64, 9u) )
      goto LABEL_90;
    for ( m = (wchar_t *)(k + 10); ; ++m )
    {
      v49 = *m;
      v50 = m;
      if ( (unsigned __int16)(*m - 48) > 9u )
        break;
    }
    v37 = 0;
    if ( v49 == 92 )
      v37 = v50;
  }
LABEL_101:
  *v3 = v37;
  if ( v6 < 0 )
  {
LABEL_102:
    if ( Heap )
    {
      v41 = GetProcessHeap();
      HeapFree(v41, 0, Heap);
    }
    goto LABEL_140;
  }
LABEL_141:
  if ( v5 )
  {
    v51 = GetProcessHeap();
    HeapFree(v51, 0, v5);
  }
  SetLastError((unsigned __int16)v6);
  return Heap;
}

```

## disassembly

```asm
0x18002f238  mov     [rsp-8+arg_10], rbx
0x18002f23d  push    rbp
0x18002f23e  push    rsi
0x18002f23f  push    rdi
0x18002f240  push    r12
0x18002f242  push    r13
0x18002f244  push    r14
0x18002f246  push    r15
0x18002f248  lea     rbp, [rsp-0B0h]
0x18002f250  sub     rsp, 1B0h
0x18002f257  mov     rax, cs:__security_cookie
0x18002f25e  xor     rax, rsp
0x18002f261  mov     [rbp+0E0h+var_38], rax
0x18002f268  movups  xmm0, xmmword ptr cs:aUnc; "\\\\?\\UNC"
0x18002f26f  xor     r15d, r15d
0x18002f272  mov     [rsp+1E0h+lpMem], rdx
0x18002f277  mov     [rsp+1E0h+var_180], rcx
0x18002f27c  mov     rax, 3F005C005Ch
0x18002f286  mov     qword ptr [rsp+1E0h+String2], rax
0x18002f28b  mov     r13, rdx
0x18002f28e  mov     rbx, rcx
0x18002f291  movdqu  xmmword ptr [rsp+1E0h+pszSrc], xmm0
0x18002f297  test    rcx, rcx
0x18002f29a  jz      loc_18002FB60
0x18002f2a0  cmp     r15w, [rcx]
0x18002f2a4  jz      loc_18002FB60
0x18002f2aa  call    FormFullPathName
0x18002f2af  mov     r12, rax
0x18002f2b2  mov     esi, 80070000h
0x18002f2b7  test    rax, rax
0x18002f2ba  jz      short loc_18002F2C1
0x18002f2bc  mov     edi, r15d
0x18002f2bf  jmp     short loc_18002F2F1
0x18002f2c1  call    cs:__imp_GetLastError
0x18002f2c7  test    eax, eax
0x18002f2c9  jle     short loc_18002F2D2
0x18002f2cb  movzx   eax, ax
0x18002f2ce  or      eax, esi
0x18002f2d0  test    eax, eax
0x18002f2d2  jns     loc_18002FB31
0x18002f2d8  call    cs:__imp_GetLastError
0x18002f2de  mov     edi, eax
0x18002f2e0  test    eax, eax
0x18002f2e2  jle     short loc_18002F2E9
0x18002f2e4  movzx   edi, ax
0x18002f2e7  or      edi, esi
0x18002f2e9  test    edi, edi
0x18002f2eb  js      loc_18002FB36
0x18002f2f1  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002f2f5  mov     rax, r14
0x18002f2f8  inc     rax
0x18002f2fb  cmp     [r12+rax*2], r15w
0x18002f300  jnz     short loc_18002F2F8
0x18002f302  cmp     rax, 104h
0x18002f308  jb      loc_18002F695
0x18002f30e  mov     r8d, 3; MaxCount
0x18002f314  lea     rdx, [rsp+1E0h+String2]; String2
0x18002f319  mov     rcx, r12; String1
0x18002f31c  mov     rsi, r15
0x18002f31f  call    wcsncmp_0
0x18002f324  test    eax, eax
0x18002f326  jz      loc_18002F688
0x18002f32c  mov     r8d, 7; MaxCount
0x18002f332  lea     rdx, [rsp+1E0h+pszSrc]; String2
0x18002f337  mov     rcx, r12; String1
0x18002f33a  call    _wcsnicmp_0
0x18002f33f  test    eax, eax
0x18002f341  jz      loc_18002F688
0x18002f347  xor     r8d, r8d
0x18002f34a  mov     dword ptr [rsp+1E0h+var_1A0], r15d
0x18002f34f  lea     rdx, [rsp+1E0h+var_1A0]
0x18002f354  mov     rcx, r12; pszSrc
0x18002f357  call    ParseUncPath
0x18002f35c  mov     edi, eax
0x18002f35e  test    eax, eax
0x18002f360  js      loc_18002FB36
0x18002f366  mov     r8d, 1
0x18002f36c  mov     [rsp+1E0h+pszDest], r15
0x18002f371  cmp     dword ptr [rsp+1E0h+var_1A0], r8d
0x18002f376  mov     [rsp+1E0h+var_1A0], r15
0x18002f37b  jnz     loc_18002F4BE
0x18002f381  lea     rbx, [r12+2]
0x18002f386  test    rbx, rbx
0x18002f389  jz      loc_18002F63C
0x18002f38f  mov     r13d, r15d
0x18002f392  lea     rax, [rsp+1E0h+pszSrc]
0x18002f397  mov     rdi, r14
0x18002f39a  inc     rdi
0x18002f39d  cmp     [rax+rdi*2], r15w
0x18002f3a2  jnz     short loc_18002F39A
0x18002f3a4  mov     r15, r14
0x18002f3a7  xor     edx, edx
0x18002f3a9  inc     r15
0x18002f3ac  cmp     [rbx+r15*2], dx
0x18002f3b1  jnz     short loc_18002F3A9
0x18002f3b3  mov     eax, 5Ch ; '\'
0x18002f3b8  test    edi, edi
0x18002f3ba  jz      short loc_18002F3E6
0x18002f3bc  lea     ecx, [rdi-1]
0x18002f3bf  cmp     ax, [rsp+rcx*2+1E0h+pszSrc]
0x18002f3c4  jnz     short loc_18002F3DB
0x18002f3c6  cmp     ax, [rbx]
0x18002f3c9  jnz     short loc_18002F3D1
0x18002f3cb  dec     r15d
0x18002f3ce  cmp     ax, [rbx]
0x18002f3d1  cmovnz  rbx, r12
0x18002f3d5  add     rbx, 2
0x18002f3d9  jmp     short loc_18002F3E6
0x18002f3db  test    edi, edi
0x18002f3dd  jz      short loc_18002F3E6
0x18002f3df  cmp     ax, [rbx]
0x18002f3e2  cmovnz  r13d, r8d
0x18002f3e6  lea     ecx, [r15+1]
0x18002f3ea  mov     edx, 8; Flags
0x18002f3ef  add     ecx, r13d
0x18002f3f2  add     ecx, edi
0x18002f3f4  mov     eax, ecx
0x18002f3f6  mov     [rsp+1E0h+cchDest], rax
0x18002f3fb  lea     r8, [rcx+rcx]; Size
0x18002f3ff  mov     rcx, gs:60h
0x18002f408  mov     rcx, [rcx+30h]; HeapHandle
0x18002f40c  call    cs:__imp_RtlAllocateHeap
0x18002f412  mov     rsi, rax
0x18002f415  test    rax, rax
0x18002f418  jnz     short loc_18002F42F
0x18002f41a  mov     rax, gs:30h
0x18002f423  mov     dword ptr [rax+68h], 8
0x18002f42a  jmp     loc_18002F561
0x18002f42f  mov     rdx, [rsp+1E0h+cchDest]; cchDest
0x18002f434  lea     rax, [rsp+1E0h+var_1A0]
0x18002f439  mov     [rsp+1E0h+pcchRemaining], rax; pcchRemaining
0x18002f43e  lea     r8, [rsp+1E0h+pszSrc]; pszSrc
0x18002f443  lea     rax, [rsp+1E0h+pszDest]
0x18002f448  mov     r9d, edi; cchToCopy
0x18002f44b  mov     rcx, rsi; pszDest
0x18002f44e  mov     [rsp+1E0h+ppszDestEnd], rax; ppszDestEnd
0x18002f453  call    StringCchCopyNExW
0x18002f458  mov     edi, eax
0x18002f45a  test    eax, eax
0x18002f45c  js      loc_18002F60D
0x18002f462  test    r13d, r13d
0x18002f465  jz      short loc_18002F4A1
0x18002f467  mov     rdx, [rsp+1E0h+var_1A0]; cchDest
0x18002f46c  lea     rax, [rsp+1E0h+var_1A0]
0x18002f471  mov     rcx, [rsp+1E0h+pszDest]; pszDest
0x18002f476  lea     r8, pszSrc; "\\"
0x18002f47d  mov     [rsp+1E0h+pcchRemaining], rax; pcchRemaining
0x18002f482  mov     r9d, 1; cchToCopy
0x18002f488  lea     rax, [rsp+1E0h+pszDest]
0x18002f48d  mov     [rsp+1E0h+ppszDestEnd], rax; ppszDestEnd
0x18002f492  call    StringCchCopyNExW
0x18002f497  mov     edi, eax
0x18002f499  test    eax, eax
0x18002f49b  js      loc_18002F60D
0x18002f4a1  mov     rdx, [rsp+1E0h+var_1A0]; cchDest
0x18002f4a6  mov     r8, rbx; pszSrc
0x18002f4a9  mov     rcx, [rsp+1E0h+pszDest]; pszDest
0x18002f4ae  mov     r9d, r15d; cchToCopy
0x18002f4b1  call    StringCchCopyNW
0x18002f4b6  xor     r15d, r15d
0x18002f4b9  jmp     loc_18002F5F5
0x18002f4be  test    r12, r12
0x18002f4c1  jz      loc_18002F63C
0x18002f4c7  mov     [rsp+1E0h+cchDest], r12
0x18002f4cc  lea     rcx, [rsp+1E0h+String2]
0x18002f4d1  mov     rdi, r14
0x18002f4d4  xor     eax, eax
0x18002f4d6  inc     rdi
0x18002f4d9  cmp     [rcx+rdi*2], ax
0x18002f4dd  jnz     short loc_18002F4D6
0x18002f4df  mov     rbx, r14
0x18002f4e2  inc     rbx
0x18002f4e5  cmp     [r12+rbx*2], ax
0x18002f4ea  jnz     short loc_18002F4E2
0x18002f4ec  test    edi, edi
0x18002f4ee  jz      short loc_18002F51D
0x18002f4f0  lea     ecx, [rdi-1]
0x18002f4f3  mov     eax, 5Ch ; '\'
0x18002f4f8  cmp     ax, [rsp+rcx*2+1E0h+String2]
0x18002f4fd  jnz     short loc_18002F514
0x18002f4ff  cmp     ax, [r12]
0x18002f504  jnz     short loc_18002F51D
0x18002f506  lea     rax, [r12+2]
0x18002f50b  dec     ebx
0x18002f50d  mov     [rsp+1E0h+cchDest], rax
0x18002f512  jmp     short loc_18002F51D
0x18002f514  cmp     ax, [r12]
0x18002f519  cmovnz  r15d, r8d
0x18002f51d  lea     ecx, [rbx+1]
0x18002f520  mov     r13d, 8
0x18002f526  add     ecx, r15d
0x18002f529  mov     edx, r13d; Flags
0x18002f52c  add     ecx, edi
0x18002f52e  mov     eax, ecx
0x18002f530  mov     [rsp+1E0h+var_178], rax
0x18002f535  lea     r8, [rcx+rcx]; Size
0x18002f539  mov     rcx, gs:60h
0x18002f542  mov     rcx, [rcx+30h]; HeapHandle
0x18002f546  call    cs:__imp_RtlAllocateHeap
0x18002f54c  mov     rsi, rax
0x18002f54f  test    rax, rax
0x18002f552  jnz     short loc_18002F56C
0x18002f554  mov     rax, gs:30h
0x18002f55d  mov     [rax+68h], r13d
0x18002f561  xor     r15d, r15d
0x18002f564  mov     rsi, r15
0x18002f567  jmp     loc_18002F64C
0x18002f56c  mov     rdx, [rsp+1E0h+var_178]; cchDest
0x18002f571  lea     rax, [rsp+1E0h+pszDest]
0x18002f576  mov     [rsp+1E0h+pcchRemaining], rax; pcchRemaining
0x18002f57b  lea     r8, [rsp+1E0h+String2]; pszSrc
0x18002f580  lea     rax, [rsp+1E0h+var_1A0]
0x18002f585  mov     r9d, edi; cchToCopy
0x18002f588  mov     rcx, rsi; pszDest
0x18002f58b  mov     [rsp+1E0h+ppszDestEnd], rax; ppszDestEnd
0x18002f590  call    StringCchCopyNExW
0x18002f595  mov     edi, eax
0x18002f597  test    eax, eax
0x18002f599  js      short loc_18002F60D
0x18002f59b  test    r15d, r15d
0x18002f59e  jz      short loc_18002F5DB
0x18002f5a0  mov     rdx, [rsp+1E0h+pszDest]; cchDest
0x18002f5a5  lea     rax, [rsp+1E0h+pszDest]
0x18002f5aa  mov     rcx, [rsp+1E0h+var_1A0]; pszDest
0x18002f5af  lea     r8, pszSrc; "\\"
0x18002f5b6  mov     [rsp+1E0h+pcchRemaining], rax; pcchRemaining
0x18002f5bb  mov     r9d, 1; cchToCopy
0x18002f5c1  lea     rax, [rsp+1E0h+var_1A0]
0x18002f5c6  mov     [rsp+1E0h+ppszDestEnd], rax; ppszDestEnd
0x18002f5cb  call    StringCchCopyNExW
0x18002f5d0  xor     r15d, r15d
0x18002f5d3  mov     edi, eax
0x18002f5d5  test    eax, eax
0x18002f5d7  jns     short loc_18002F5DE
0x18002f5d9  jmp     short loc_18002F610
0x18002f5db  xor     r15d, r15d
0x18002f5de  mov     r8, [rsp+1E0h+cchDest]; pszSrc
0x18002f5e3  mov     rdx, [rsp+1E0h+pszDest]; cchDest
0x18002f5e8  mov     rcx, [rsp+1E0h+var_1A0]; pszDest
0x18002f5ed  mov     r9d, ebx; cchToCopy
0x18002f5f0  call    StringCchCopyNW
0x18002f5f5  mov     edi, eax
0x18002f5f7  test    eax, eax
0x18002f5f9  js      short loc_18002F610
0x18002f5fb  mov     rax, gs:30h
0x18002f604  mov     edi, r15d
0x18002f607  mov     [rax+68h], r15d
0x18002f60b  jmp     short loc_18002F67E
0x18002f60d  xor     r15d, r15d
0x18002f610  mov     rcx, gs:60h
0x18002f619  mov     r8, rsi; P
0x18002f61c  xor     edx, edx; Flags
0x18002f61e  mov     rcx, [rcx+30h]; HeapHandle
0x18002f622  call    cs:__imp_RtlFreeHeap
0x18002f628  mov     rax, gs:30h
0x18002f631  movzx   ecx, di
0x18002f634  mov     [rax+68h], ecx
0x18002f637  jmp     loc_18002F564
0x18002f63c  mov     rax, gs:30h
0x18002f645  mov     dword ptr [rax+68h], 57h ; 'W'
0x18002f64c  call    cs:__imp_GetLastError
0x18002f652  test    eax, eax
0x18002f654  jle     short loc_18002F660
0x18002f656  movzx   eax, ax
0x18002f659  or      eax, 80070000h
0x18002f65e  test    eax, eax
0x18002f660  jns     short loc_18002F679
0x18002f662  call    cs:__imp_GetLastError
0x18002f668  mov     edi, eax
0x18002f66a  test    eax, eax
0x18002f66c  jle     short loc_18002F67E
0x18002f66e  movzx   edi, ax
0x18002f671  or      edi, 80070000h
0x18002f677  jmp     short loc_18002F67E
0x18002f679  mov     edi, 80004005h
0x18002f67e  mov     r13, [rsp+1E0h+lpMem]
0x18002f683  mov     rbx, [rsp+1E0h+var_180]
0x18002f688  test    edi, edi
0x18002f68a  js      loc_18002F8DB
0x18002f690  test    rsi, rsi
0x18002f693  jnz     short loc_18002F6E1
0x18002f695  mov     rcx, rbx; unsigned __int16 *
0x18002f698  call    StrDupe
0x18002f69d  mov     rsi, rax
0x18002f6a0  test    rax, rax
0x18002f6a3  jz      short loc_18002F6AA
0x18002f6a5  mov     edi, r15d
0x18002f6a8  jmp     short loc_18002F6E1
0x18002f6aa  call    cs:__imp_GetLastError
0x18002f6b0  test    eax, eax
0x18002f6b2  jle     short loc_18002F6BE
0x18002f6b4  movzx   eax, ax
0x18002f6b7  or      eax, 80070000h
0x18002f6bc  test    eax, eax
0x18002f6be  jns     loc_18002FB31
0x18002f6c4  call    cs:__imp_GetLastError
0x18002f6ca  mov     edi, eax
0x18002f6cc  test    eax, eax
0x18002f6ce  jle     short loc_18002F6D9
0x18002f6d0  movzx   edi, ax
  ... truncated ...
```
