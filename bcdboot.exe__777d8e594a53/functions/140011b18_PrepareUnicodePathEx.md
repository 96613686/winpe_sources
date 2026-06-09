# PrepareUnicodePathEx

- ea: `0x140011b18`
- end: `0x14001279b`
- name: `PrepareUnicodePathEx`
- size: `3203`
- prototype: `char *__fastcall(STRSAFE_LPCWSTR pszSrc, wchar_t **)`
- caller_count: `7`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1400038d4`
- `0x14000bd28`
- `0x14000d494`
- `0x1400116f4`
- `0x140011978`
- `0x140012810`
- `0x140012cec`

## callees

- `0x140011588`
- `0x140011670`
- `0x1400118d4`
- `0x140011b18`
- `0x140013278`
- `0x14002661e`
- `0x140026650`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x140011c1f`
- `msvcrt!_wcsnicmp` at `0x140011c64`
- `msvcrt!_wcsnicmp` at `0x140011c92`
- `msvcrt!_wcsnicmp` at `0x140012108`
- `msvcrt!_wcsnicmp` at `0x140012120`
- `msvcrt!_wcsnicmp` at `0x140012139`
- `msvcrt!_wcsnicmp` at `0x140012169`
- `msvcrt!_wcsnicmp` at `0x1400121b1`
- `msvcrt!_wcsnicmp` at `0x1400121d5`
- `msvcrt!_wcsnicmp` at `0x140012219`
- `msvcrt!_wcsnicmp` at `0x14001224e`
- `msvcrt!_wcsnicmp` at `0x140012469`
- `msvcrt!_wcsnicmp` at `0x14001249e`
- `msvcrt!_wcsnicmp` at `0x140012627`
- `msvcrt!_wcsnicmp` at `0x140012653`
- `msvcrt!_wcsnicmp` at `0x140012684`
- `msvcrt!_wcsnicmp` at `0x1400126a7`
- `msvcrt!_wcsnicmp` at `0x1400126c7`
- `msvcrt!_wcsnicmp` at `0x1400126fa`
- `msvcrt!_wcsnicmp` at `0x140011c1f`
- `msvcrt!_wcsnicmp` at `0x140011c64`
- `msvcrt!_wcsnicmp` at `0x140011c92`
- `msvcrt!_wcsnicmp` at `0x140012108`
- `msvcrt!_wcsnicmp` at `0x140012120`
- `msvcrt!_wcsnicmp` at `0x140012139`
- `msvcrt!_wcsnicmp` at `0x140012169`
- `msvcrt!_wcsnicmp` at `0x1400121b1`
- `msvcrt!_wcsnicmp` at `0x1400121d5`
- `msvcrt!_wcsnicmp` at `0x140012219`
- `msvcrt!_wcsnicmp` at `0x14001224e`
- `msvcrt!_wcsnicmp` at `0x140012469`
- `msvcrt!_wcsnicmp` at `0x14001249e`
- `msvcrt!_wcsnicmp` at `0x140012627`
- `msvcrt!_wcsnicmp` at `0x140012653`
- `msvcrt!_wcsnicmp` at `0x140012684`
- `msvcrt!_wcsnicmp` at `0x1400126a7`
- `msvcrt!_wcsnicmp` at `0x1400126c7`
- `msvcrt!_wcsnicmp` at `0x1400126fa`
- `msvcrt!wcschr` at `0x140011cba`
- `msvcrt!wcschr` at `0x140011cd3`
- `msvcrt!wcschr` at `0x140012273`
- `msvcrt!wcschr` at `0x14001229e`
- `msvcrt!wcschr` at `0x1400124c3`
- `msvcrt!wcschr` at `0x1400124ee`
- `msvcrt!wcschr` at `0x140012638`
- `msvcrt!wcschr` at `0x140012664`
- `msvcrt!wcschr` at `0x140011cba`
- `msvcrt!wcschr` at `0x140011cd3`
- `msvcrt!wcschr` at `0x140012273`
- `msvcrt!wcschr` at `0x14001229e`
- `msvcrt!wcschr` at `0x1400124c3`
- `msvcrt!wcschr` at `0x1400124ee`
- `msvcrt!wcschr` at `0x140012638`
- `msvcrt!wcschr` at `0x140012664`
- `KERNEL32!SetLastError` at `0x140012759`
- `KERNEL32!SetLastError` at `0x140012769`
- `KERNEL32!SetLastError` at `0x140012759`
- `KERNEL32!SetLastError` at `0x140012769`
- `KERNEL32!GetLastError` at `0x140011ba3`
- `KERNEL32!GetLastError` at `0x140011bba`
- `KERNEL32!GetLastError` at `0x140011e43`
- `KERNEL32!GetLastError` at `0x140011e5d`
- `KERNEL32!GetLastError` at `0x14001201b`
- `KERNEL32!GetLastError` at `0x140012035`
- `KERNEL32!GetLastError` at `0x140011ba3`
- `KERNEL32!GetLastError` at `0x140011bba`
- `KERNEL32!GetLastError` at `0x140011e43`
- `KERNEL32!GetLastError` at `0x140011e5d`
- `KERNEL32!GetLastError` at `0x14001201b`
- `KERNEL32!GetLastError` at `0x140012035`
- `KERNEL32!HeapFree` at `0x140012333`
- `KERNEL32!HeapFree` at `0x14001238e`
- `KERNEL32!HeapFree` at `0x1400123be`
- `KERNEL32!HeapFree` at `0x140012583`
- `KERNEL32!HeapFree` at `0x140012750`
- `KERNEL32!HeapFree` at `0x140012333`
- `KERNEL32!HeapFree` at `0x14001238e`
- `KERNEL32!HeapFree` at `0x1400123be`
- `KERNEL32!HeapFree` at `0x140012583`
- `KERNEL32!HeapFree` at `0x140012750`
- `KERNEL32!GetProcessHeap` at `0x140012325`
- `KERNEL32!GetProcessHeap` at `0x140012380`
- `KERNEL32!GetProcessHeap` at `0x1400123b0`
- `KERNEL32!GetProcessHeap` at `0x140012575`
- `KERNEL32!GetProcessHeap` at `0x140012742`
- `KERNEL32!GetProcessHeap` at `0x140012325`
- `KERNEL32!GetProcessHeap` at `0x140012380`
- `KERNEL32!GetProcessHeap` at `0x1400123b0`
- `KERNEL32!GetProcessHeap` at `0x140012575`
- `KERNEL32!GetProcessHeap` at `0x140012742`
- `ntdll!RtlAllocateHeap` at `0x140011d92`
- `ntdll!RtlAllocateHeap` at `0x140011f1e`
- `ntdll!RtlAllocateHeap` at `0x1400122e6`
- `ntdll!RtlAllocateHeap` at `0x140012536`
- `ntdll!RtlAllocateHeap` at `0x140011d92`
- `ntdll!RtlAllocateHeap` at `0x140011f1e`
- `ntdll!RtlAllocateHeap` at `0x1400122e6`
- `ntdll!RtlAllocateHeap` at `0x140012536`
- `ntdll!RtlFreeHeap` at `0x140011e2b`
- `ntdll!RtlFreeHeap` at `0x140011e2b`

## pseudocode

```c
char *__fastcall PrepareUnicodePathEx(STRSAFE_LPCWSTR pszSrc, wchar_t **a2)
{
  wchar_t *v2; // r12
  const wchar_t *v3; // rsi
  WCHAR *v4; // r13
  int v5; // ebx
  signed int LastError; // eax
  bool v7; // sf
  signed int v8; // eax
  __int64 v9; // r14
  unsigned __int64 v10; // rax
  char *Heap; // rdi
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rax
  BOOL v14; // ecx
  wchar_t *v15; // rax
  int v16; // eax
  const wchar_t *v17; // rbx
  __int64 v18; // rsi
  __int64 v19; // r15
  bool v20; // zf
  __int64 v21; // rcx
  HRESULT v22; // eax
  unsigned __int16 v23; // si
  HRESULT v24; // eax
  signed int v25; // eax
  bool v26; // sf
  signed int v27; // eax
  size_t v28; // rdx
  const wchar_t *v29; // r8
  wchar_t *v30; // rcx
  size_t v31; // r9
  int v32; // r15d
  __int64 v33; // rsi
  __int64 v34; // rbx
  __int64 v35; // rcx
  size_t v36; // r12
  HRESULT v37; // eax
  HRESULT v38; // eax
  HRESULT v39; // eax
  signed int v40; // eax
  bool v41; // sf
  signed int v42; // eax
  const wchar_t *i; // r14
  wchar_t *j; // r14
  wchar_t *v45; // rsi
  unsigned __int64 v46; // rax
  int v47; // r15d
  unsigned __int64 v48; // rax
  BOOL v49; // ecx
  wchar_t *v50; // rax
  size_t v51; // r15
  wchar_t *v52; // rax
  unsigned __int64 v53; // rax
  wchar_t *v54; // r13
  HANDLE ProcessHeap; // rax
  HANDLE v56; // rax
  HANDLE v57; // rax
  __int16 v58; // cx
  unsigned __int64 v59; // rax
  int v60; // r15d
  unsigned __int64 v61; // rax
  BOOL v62; // ecx
  wchar_t *v63; // rax
  size_t v64; // r15
  wchar_t *v65; // rax
  unsigned __int64 v66; // rax
  wchar_t *v67; // r13
  HANDLE v68; // rax
  const wchar_t *v69; // rcx
  wchar_t *v70; // rax
  const wchar_t *v71; // rsi
  const wchar_t *k; // rsi
  wchar_t *m; // rsi
  wchar_t v74; // cx
  wchar_t *v75; // rdx
  HANDLE v76; // rax
  DWORD v78; // [rsp+30h] [rbp-D0h]
  DWORD v79; // [rsp+30h] [rbp-D0h]
  DWORD v80; // [rsp+30h] [rbp-D0h]
  size_t pcchRemaining; // [rsp+40h] [rbp-C0h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR *v83; // [rsp+50h] [rbp-B0h]
  size_t cchDest; // [rsp+58h] [rbp-A8h]
  STRSAFE_LPCWSTR v85; // [rsp+60h] [rbp-A0h]
  wchar_t **v86; // [rsp+68h] [rbp-98h]
  wchar_t String2[4]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t pszSrca[8]; // [rsp+78h] [rbp-88h] BYREF
  wchar_t v89[12]; // [rsp+88h] [rbp-78h] BYREF
  wchar_t v90[12]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t v91[12]; // [rsp+B8h] [rbp-48h] BYREF
  wchar_t v92[20]; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t v93[16]; // [rsp+F8h] [rbp-8h] BYREF
  wchar_t v94[16]; // [rsp+118h] [rbp+18h] BYREF
  wchar_t v95[16]; // [rsp+138h] [rbp+38h] BYREF
  wchar_t v96[16]; // [rsp+158h] [rbp+58h] BYREF
  wchar_t v97[24]; // [rsp+178h] [rbp+78h] BYREF

  v2 = 0;
  v86 = a2;
  v85 = pszSrc;
  wcscpy(String2, L"\\\\?");
  v3 = pszSrc;
  wcscpy(pszSrca, L"\\\\?\\UNC");
  if ( !pszSrc || !*pszSrc )
  {
    SetLastError(0x57u);
    return 0;
  }
  v83 = FormFullPathName(pszSrc);
  v4 = v83;
  if ( v83 )
  {
    v5 = 0;
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError < 0;
    if ( LastError > 0 )
      v7 = 1;
    if ( !v7 )
      goto LABEL_212;
    v8 = GetLastError();
    v5 = v8;
    if ( v8 > 0 )
      v5 = (unsigned __int16)v8 | 0x80070000;
    if ( v5 < 0 )
      goto LABEL_213;
  }
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( v83[v10] );
  if ( v10 < 0x104 )
  {
LABEL_84:
    Heap = (char *)StrDupe(v3);
    if ( Heap )
    {
      v5 = 0;
      goto LABEL_92;
    }
    v40 = GetLastError();
    v41 = v40 < 0;
    if ( v40 > 0 )
      v41 = 1;
    if ( v41 )
    {
      v42 = GetLastError();
      v5 = v42;
      if ( v42 > 0 )
        v5 = (unsigned __int16)v42 | 0x80070000;
      if ( v5 < 0 )
        goto LABEL_213;
      goto LABEL_92;
    }
LABEL_212:
    LOWORD(v5) = 16389;
    goto LABEL_213;
  }
  Heap = 0;
  if ( wcsncmp_0(v83, String2, 3u) && _wcsnicmp(v83, pszSrca, 7u) )
  {
    if ( !v83 )
    {
      LOWORD(v5) = 87;
LABEL_213:
      Heap = 0;
      goto LABEL_214;
    }
    v12 = -1;
    do
      ++v12;
    while ( v83[v12] );
    if ( v12 < 2 || _wcsnicmp(v83, L"\\\\", 2u) )
    {
      v5 = 0;
    }
    else
    {
      v13 = -1;
      do
        ++v13;
      while ( v83[v13] );
      v14 = v13 >= 8 && _wcsnicmp(v83, L"\\\\?\\UNC\\", 8u) == 0;
      v15 = wcschr((WCHAR *)((char *)v83 + (v14 ? 16LL : 4LL)), 0x5Cu);
      if ( v15 )
      {
        wcschr(v15 + 1, 0x5Cu);
        v5 = 0;
        v16 = 1;
        goto LABEL_32;
      }
      v5 = -2147024883;
    }
    v16 = 0;
LABEL_32:
    if ( v5 < 0 )
      goto LABEL_213;
    pszDest = 0;
    pcchRemaining = 0;
    if ( v16 == 1 )
    {
      v17 = v83 + 1;
      if ( v83 == (WCHAR *)-2LL )
      {
        NtCurrentTeb()->LastErrorValue = 87;
        goto LABEL_53;
      }
      v18 = -1;
      do
        ++v18;
      while ( pszSrca[v18] );
      v19 = -1;
      do
        ++v19;
      while ( v17[v19] );
      if ( (_DWORD)v18 )
      {
        if ( pszSrca[(unsigned int)(v18 - 1)] == 92 )
        {
          v20 = *v17 == 92;
          if ( *v17 == 92 )
          {
            LODWORD(v19) = v19 - 1;
            v20 = *v17 == 92;
          }
          if ( !v20 )
            v17 = v83;
          ++v17;
        }
        else if ( *v17 != 92 )
        {
          LODWORD(v2) = 1;
        }
      }
      v21 = (unsigned int)(v18 + (_DWORD)v2 + v19 + 1);
      cchDest = (unsigned int)v21;
      Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v21);
      if ( Heap )
      {
        v22 = StringCchCopyNExW(
                (STRSAFE_LPWSTR)Heap,
                cchDest,
                pszSrca,
                (unsigned int)v18,
                &pszDest,
                &pcchRemaining,
                v78);
        v23 = v22;
        if ( v22 < 0 )
        {
          v2 = 0;
          goto LABEL_52;
        }
        if ( (_DWORD)v2 )
        {
          v24 = StringCchCopyNExW(pszDest, pcchRemaining, L"\\", 1u, &pszDest, &pcchRemaining, v79);
          v2 = 0;
          v23 = v24;
          if ( v24 < 0 )
          {
LABEL_52:
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
            NtCurrentTeb()->LastErrorValue = v23;
LABEL_53:
            Heap = 0;
            v25 = GetLastError();
            v26 = v25 < 0;
            if ( v25 > 0 )
              v26 = 1;
            if ( v26 )
            {
              v27 = GetLastError();
              v5 = v27;
              if ( v27 > 0 )
                v5 = (unsigned __int16)v27 | 0x80070000;
            }
            else
            {
              v5 = -2147467259;
            }
            goto LABEL_81;
          }
        }
        else
        {
          v2 = 0;
        }
        v28 = pcchRemaining;
        v29 = v17;
        v30 = pszDest;
        v31 = (unsigned int)v19;
LABEL_78:
        v39 = StringCchCopyNW(v30, v28, v29, v31);
        v23 = v39;
        if ( v39 >= 0 )
        {
          v5 = 0;
          NtCurrentTeb()->LastErrorValue = 0;
LABEL_81:
          v3 = v85;
          goto LABEL_82;
        }
        goto LABEL_52;
      }
    }
    else
    {
      cchDest = (size_t)v83;
      v32 = 0;
      v33 = -1;
      do
        ++v33;
      while ( String2[v33] );
      v34 = -1;
      do
        ++v34;
      while ( v83[v34] );
      if ( (_DWORD)v33 )
      {
        if ( String2[(unsigned int)(v33 - 1)] == 92 )
        {
          if ( *v83 == 92 )
          {
            LODWORD(v34) = v34 - 1;
            cchDest = (size_t)(v83 + 1);
          }
        }
        else if ( *v83 != 92 )
        {
          v32 = 1;
        }
      }
      v35 = (unsigned int)(v33 + v32 + v34 + 1);
      v36 = (unsigned int)v35;
      Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v35);
      if ( Heap )
      {
        v37 = StringCchCopyNExW(
                (STRSAFE_LPWSTR)Heap,
                v36,
                String2,
                (unsigned int)v33,
                (STRSAFE_LPWSTR *)&pcchRemaining,
                (size_t *)&pszDest,
                v78);
        v2 = 0;
        v23 = v37;
        if ( v37 < 0 )
          goto LABEL_52;
        if ( v32 )
        {
          v38 = StringCchCopyNExW(
                  (STRSAFE_LPWSTR)pcchRemaining,
                  (size_t)pszDest,
                  L"\\",
                  1u,
                  (STRSAFE_LPWSTR *)&pcchRemaining,
                  (size_t *)&pszDest,
                  v80);
          v23 = v38;
          if ( v38 < 0 )
            goto LABEL_52;
        }
        v29 = (const wchar_t *)cchDest;
        v28 = (size_t)pszDest;
        v30 = (wchar_t *)pcchRemaining;
        v31 = (unsigned int)v34;
        goto LABEL_78;
      }
    }
    v2 = 0;
    NtCurrentTeb()->LastErrorValue = 8;
    goto LABEL_53;
  }
LABEL_82:
  if ( v5 < 0 )
    goto LABEL_147;
  if ( !Heap )
    goto LABEL_84;
LABEL_92:
  if ( !v86 )
    goto LABEL_214;
  wcscpy(v95, L"\\\\?\\GLBALROOT");
  wcscpy(v96, L"\\??\\GLBALROOT");
  wcscpy(v93, L"\\\\arddisk");
  wcscpy(v94, L"\\?arddisk");
  wcscpy(v89, L"Partition");
  wcscpy(v90, L"\\\\?\\Volume{");
  wcscpy(v91, L"\\??\\Volume{");
  if ( _wcsnicmp((const wchar_t *)Heap, v95, 0xEu) && _wcsnicmp((const wchar_t *)Heap, v96, 0xEu) )
  {
    if ( !_wcsnicmp((const wchar_t *)Heap, v93, 0xCu) )
    {
      for ( i = (const wchar_t *)(Heap + 26); (unsigned __int16)(*i - 48) <= 9u; ++i )
        ;
      if ( !_wcsnicmp(i, v89, 9u) )
      {
        for ( j = (wchar_t *)(i + 10); (unsigned __int16)(*j - 48) <= 9u; ++j )
          ;
        v45 = 0;
        if ( *j == 92 )
          v45 = j;
        goto LABEL_146;
      }
LABEL_154:
      v45 = 0;
      goto LABEL_146;
    }
    if ( !_wcsnicmp((const wchar_t *)Heap, v90, 0xBu) )
    {
      v45 = (wchar_t *)(Heap + 96);
      goto LABEL_146;
    }
    v45 = 0;
    if ( !_wcsnicmp((const wchar_t *)Heap, pszSrca, 7u) )
    {
      if ( !Heap )
      {
        v5 = -2147024809;
        goto LABEL_146;
      }
      v46 = -1;
      do
        ++v46;
      while ( *(_WORD *)&Heap[2 * v46] );
      if ( v46 < 2 || _wcsnicmp((const wchar_t *)Heap, L"\\\\", 2u) )
      {
        v5 = 0;
        v47 = 0;
      }
      else
      {
        v47 = 0;
        v48 = -1;
        do
          ++v48;
        while ( *(_WORD *)&Heap[2 * v48] );
        v49 = v48 >= 8 && _wcsnicmp((const wchar_t *)Heap, L"\\\\?\\UNC\\", 8u) == 0;
        v50 = wcschr((const wchar_t *)&Heap[v49 ? 16LL : 4LL], 0x5Cu);
        if ( !v50 )
        {
          v5 = -2147024883;
          goto LABEL_139;
        }
        v51 = -1;
        do
          ++v51;
        while ( *(_WORD *)&Heap[2 * v51] );
        v52 = wcschr(v50 + 1, 0x5Cu);
        if ( v52 )
          v51 = ((char *)v52 - Heap) >> 1;
        v53 = -1;
        do
          ++v53;
        while ( *(_WORD *)&Heap[2 * v53] );
        if ( v51 > v53 )
        {
          v5 = -2147024809;
          goto LABEL_135;
        }
        v5 = -2147024882;
        v54 = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v51 + 2);
        if ( v54 )
          v5 = StringCchCopyNW(v54, v51 + 1, (STRSAFE_PCNZWCH)Heap, v51);
        if ( v5 >= 0 )
        {
          v2 = v54;
          v47 = 1;
          v4 = v83;
          goto LABEL_139;
        }
        if ( v54 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v54);
          v4 = v83;
LABEL_135:
          v47 = 0;
          goto LABEL_139;
        }
        v4 = v83;
        v47 = 0;
      }
LABEL_139:
      if ( v5 < 0 )
        goto LABEL_144;
      if ( v47 == 1 )
      {
        do
          ++v9;
        while ( v2[v9] );
LABEL_142:
        v45 = (wchar_t *)&Heap[2 * v9];
        goto LABEL_144;
      }
      goto LABEL_143;
    }
    if ( !wcsncmp_0((const wchar_t *)Heap, String2, 3u) )
    {
      v58 = *((_WORD *)Heap + 4);
      if ( ((unsigned __int16)(v58 - 97) <= 0x19u || (unsigned __int16)(v58 - 65) <= 0x19u)
        && *((_WORD *)Heap + 5) == 58 )
      {
        v45 = (wchar_t *)(Heap + 12);
        if ( *((_WORD *)Heap + 6) == 92 )
          goto LABEL_146;
      }
      goto LABEL_154;
    }
    if ( ((unsigned __int16)(*(_WORD *)Heap - 97) <= 0x19u || (unsigned __int16)(*(_WORD *)Heap - 65) <= 0x19u)
      && *((_WORD *)Heap + 1) == 58
      && *((_WORD *)Heap + 2) == 92 )
    {
      v45 = (wchar_t *)(Heap + 4);
      goto LABEL_146;
    }
    v59 = -1;
    do
      ++v59;
    while ( *(_WORD *)&Heap[2 * v59] );
    if ( v59 < 2 || _wcsnicmp((const wchar_t *)Heap, L"\\\\", 2u) )
    {
      v5 = 0;
      goto LABEL_143;
    }
    v60 = 0;
    v61 = -1;
    do
      ++v61;
    while ( *(_WORD *)&Heap[2 * v61] );
    v62 = v61 >= 8 && _wcsnicmp((const wchar_t *)Heap, L"\\\\?\\UNC\\", 8u) == 0;
    v63 = wcschr((const wchar_t *)&Heap[v62 ? 16LL : 4LL], 0x5Cu);
    if ( !v63 )
    {
      v5 = -2147024883;
LABEL_187:
      if ( v5 < 0 )
      {
LABEL_144:
        if ( v2 )
        {
          v56 = GetProcessHeap();
          HeapFree(v56, 0, v2);
        }
        goto LABEL_146;
      }
      if ( v60 == 1 )
      {
        do
          ++v9;
        while ( v2[v9] );
        goto LABEL_142;
      }
LABEL_143:
      v45 = 0;
      goto LABEL_144;
    }
    v64 = -1;
    do
      ++v64;
    while ( *(_WORD *)&Heap[2 * v64] );
    v65 = wcschr(v63 + 1, 0x5Cu);
    if ( v65 )
      v64 = ((char *)v65 - Heap) >> 1;
    v66 = -1;
    do
      ++v66;
    while ( *(_WORD *)&Heap[2 * v66] );
    if ( v64 > v66 )
    {
      v5 = -2147024809;
    }
    else
    {
      v5 = -2147024882;
      v67 = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v64 + 2);
      if ( v67 )
        v5 = StringCchCopyNW(v67, v64 + 1, (STRSAFE_PCNZWCH)Heap, v64);
      if ( v5 >= 0 )
      {
        v2 = v67;
        v60 = 1;
        v4 = v83;
        goto LABEL_187;
      }
      if ( !v67 )
      {
        v4 = v83;
        v60 = 0;
        goto LABEL_187;
      }
      v68 = GetProcessHeap();
      HeapFree(v68, 0, v67);
      v4 = v83;
    }
    v60 = 0;
    goto LABEL_187;
  }
  v45 = (wchar_t *)(Heap + 28);
  wcscpy(v97, L"\\Device\\HarddikVolume");
  wcscpy(v92, L"\\Device\\Harddisk");
  if ( !_wcsnicmp((const wchar_t *)Heap + 14, v97, 0x16u) )
  {
    v69 = (const wchar_t *)(Heap + 74);
    goto LABEL_194;
  }
  if ( !_wcsnicmp((const wchar_t *)Heap + 14, v92, 0x10u) )
  {
    v70 = wcschr((const wchar_t *)Heap + 31, 0x5Cu);
    if ( !v70 )
      goto LABEL_154;
    v71 = v70 + 1;
    if ( _wcsnicmp(v70 + 1, v89, 9u) )
      goto LABEL_154;
    v69 = v71;
LABEL_194:
    v45 = wcschr(v69, 0x5Cu);
    goto LABEL_146;
  }
  if ( !_wcsnicmp((const wchar_t *)Heap + 14, v91, 0xBu) )
  {
    v45 = (wchar_t *)(Heap + 124);
    goto LABEL_146;
  }
  if ( !_wcsnicmp((const wchar_t *)Heap + 14, v94, 0xCu) )
  {
    for ( k = (const wchar_t *)(Heap + 54); (unsigned __int16)(*k - 48) <= 9u; ++k )
      ;
    if ( _wcsnicmp(k, v89, 9u) )
      goto LABEL_154;
    for ( m = (wchar_t *)(k + 10); ; ++m )
    {
      v74 = *m;
      v75 = m;
      if ( (unsigned __int16)(*m - 48) > 9u )
        break;
    }
    v45 = 0;
    if ( v74 == 92 )
      v45 = v75;
  }
LABEL_146:
  *v86 = v45;
  if ( v5 < 0 )
  {
LABEL_147:
    if ( Heap )
    {
      v57 = GetProcessHeap();
      HeapFree(v57, 0, Heap);
    }
    goto LABEL_213;
  }
LABEL_214:
  if ( v4 )
  {
    v76 = GetProcessHeap();
    HeapFree(v76, 0, v4);
  }
  SetLastError((unsigned __int16)v5);
  return Heap;
}

```

## disassembly

```asm
0x140011b18  mov     [rsp-8+arg_10], rbx
0x140011b1d  push    rbp
0x140011b1e  push    rsi
0x140011b1f  push    rdi
0x140011b20  push    r12
0x140011b22  push    r13
0x140011b24  push    r14
0x140011b26  push    r15
0x140011b28  lea     rbp, [rsp-0B0h]
0x140011b30  sub     rsp, 1B0h
0x140011b37  mov     rax, cs:__security_cookie
0x140011b3e  xor     rax, rsp
0x140011b41  mov     [rbp+0E0h+var_38], rax
0x140011b48  movups  xmm0, xmmword ptr cs:aUnc; "\\\\?\\UNC"
0x140011b4f  xor     r12d, r12d
0x140011b52  mov     [rsp+1E0h+var_178], rdx
0x140011b57  mov     [rsp+1E0h+var_180], rcx
0x140011b5c  mov     rax, 3F005C005Ch
0x140011b66  mov     qword ptr [rsp+1E0h+String2], rax
0x140011b6b  mov     rsi, rcx
0x140011b6e  movdqu  xmmword ptr [rsp+1E0h+pszSrc], xmm0
0x140011b74  test    rcx, rcx
0x140011b77  jz      loc_140012764
0x140011b7d  cmp     r12w, [rcx]
0x140011b81  jz      loc_140012764
0x140011b87  call    FormFullPathName
0x140011b8c  mov     [rsp+1E0h+var_190], rax
0x140011b91  mov     r13, rax
0x140011b94  mov     edi, 80070000h
0x140011b99  test    rax, rax
0x140011b9c  jz      short loc_140011BA3
0x140011b9e  mov     ebx, r12d
0x140011ba1  jmp     short loc_140011BD3
0x140011ba3  call    cs:__imp_GetLastError
0x140011ba9  test    eax, eax
0x140011bab  jle     short loc_140011BB4
0x140011bad  movzx   eax, ax
0x140011bb0  or      eax, edi
0x140011bb2  test    eax, eax
0x140011bb4  jns     loc_140012735
0x140011bba  call    cs:__imp_GetLastError
0x140011bc0  mov     ebx, eax
0x140011bc2  test    eax, eax
0x140011bc4  jle     short loc_140011BCB
0x140011bc6  movzx   ebx, ax
0x140011bc9  or      ebx, edi
0x140011bcb  test    ebx, ebx
0x140011bcd  js      loc_14001273A
0x140011bd3  or      r14, 0FFFFFFFFFFFFFFFFh
0x140011bd7  mov     rax, r14
0x140011bda  inc     rax
0x140011bdd  cmp     [r13+rax*2+0], r12w
0x140011be3  jnz     short loc_140011BDA
0x140011be5  mov     r15d, 5Ch ; '\'
0x140011beb  cmp     rax, 104h
0x140011bf1  jb      loc_140012006
0x140011bf7  lea     r8d, [r15-59h]; MaxCount
0x140011bfb  mov     rcx, r13; String1
0x140011bfe  lea     rdx, [rsp+1E0h+String2]; String2
0x140011c03  mov     rdi, r12
0x140011c06  call    wcsncmp_0
0x140011c0b  test    eax, eax
0x140011c0d  jz      loc_140011FF9
0x140011c13  lea     r8d, [r15-55h]; MaxCount
0x140011c17  mov     rcx, r13; String1
0x140011c1a  lea     rdx, [rsp+1E0h+pszSrc]; String2
0x140011c1f  call    cs:__imp__wcsnicmp
0x140011c25  test    eax, eax
0x140011c27  jz      loc_140011FF9
0x140011c2d  test    r13, r13
0x140011c30  jnz     short loc_140011C3C
0x140011c32  mov     ebx, 80070057h
0x140011c37  jmp     loc_14001273A
0x140011c3c  mov     rax, r14
0x140011c3f  inc     rax
0x140011c42  cmp     [r13+rax*2+0], r12w
0x140011c48  jnz     short loc_140011C3F
0x140011c4a  cmp     rax, 2
0x140011c4e  jb      loc_140011CE7
0x140011c54  mov     r8d, 2; MaxCount
0x140011c5a  lea     rdx, asc_1400338AC; "\\\\"
0x140011c61  mov     rcx, r13; String1
0x140011c64  call    cs:__imp__wcsnicmp
0x140011c6a  test    eax, eax
0x140011c6c  jnz     short loc_140011CE7
0x140011c6e  mov     rax, r14
0x140011c71  inc     rax
0x140011c74  cmp     [r13+rax*2+0], r12w
0x140011c7a  jnz     short loc_140011C71
0x140011c7c  cmp     rax, 8
0x140011c80  jb      short loc_140011CA2
0x140011c82  mov     r8d, 8; MaxCount
0x140011c88  lea     rdx, aUnc_0; "\\\\?\\UNC\\"
0x140011c8f  mov     rcx, r13; String1
0x140011c92  call    cs:__imp__wcsnicmp
0x140011c98  test    eax, eax
0x140011c9a  mov     ecx, r12d
0x140011c9d  setz    cl
0x140011ca0  jmp     short loc_140011CA5
0x140011ca2  mov     ecx, r12d
0x140011ca5  neg     ecx
0x140011ca7  mov     edx, r15d; Ch
0x140011caa  mov     edi, r15d
0x140011cad  sbb     rcx, rcx
0x140011cb0  and     ecx, 0Ch
0x140011cb3  add     rcx, 4
0x140011cb7  add     rcx, r13; Str
0x140011cba  call    cs:__imp_wcschr
0x140011cc0  test    rax, rax
0x140011cc3  jnz     short loc_140011CCC
0x140011cc5  mov     ebx, 8007000Dh
0x140011cca  jmp     short loc_140011CED
0x140011ccc  mov     edx, r15d; Ch
0x140011ccf  lea     rcx, [rax+2]; Str
0x140011cd3  call    cs:__imp_wcschr
0x140011cd9  mov     r8d, 1
0x140011cdf  mov     ebx, r12d
0x140011ce2  mov     eax, r8d
0x140011ce5  jmp     short loc_140011CF6
0x140011ce7  mov     ebx, r12d
0x140011cea  mov     edi, r15d
0x140011ced  mov     r8d, 1
0x140011cf3  mov     eax, r12d
0x140011cf6  test    ebx, ebx
0x140011cf8  js      loc_14001273A
0x140011cfe  mov     [rsp+1E0h+pszDest], r12
0x140011d03  mov     [rsp+1E0h+var_1A0], r12
0x140011d08  cmp     eax, r8d
0x140011d0b  jnz     loc_140011EAA
0x140011d11  lea     rbx, [r13+2]
0x140011d15  test    rbx, rbx
0x140011d18  jz      loc_140011E98
0x140011d1e  lea     rax, [rsp+1E0h+pszSrc]
0x140011d23  mov     rsi, r14
0x140011d26  xor     edx, edx
0x140011d28  inc     rsi
0x140011d2b  cmp     [rax+rsi*2], dx
0x140011d2f  jnz     short loc_140011D28
0x140011d31  mov     r15, r14
0x140011d34  inc     r15
0x140011d37  cmp     [rbx+r15*2], dx
0x140011d3c  jnz     short loc_140011D34
0x140011d3e  test    esi, esi
0x140011d40  jz      short loc_140011D6C
0x140011d42  lea     eax, [rsi-1]
0x140011d45  cmp     di, [rsp+rax*2+1E0h+pszSrc]
0x140011d4a  jnz     short loc_140011D61
0x140011d4c  cmp     di, [rbx]
0x140011d4f  jnz     short loc_140011D57
0x140011d51  dec     r15d
0x140011d54  cmp     di, [rbx]
0x140011d57  cmovnz  rbx, r13
0x140011d5b  add     rbx, 2
0x140011d5f  jmp     short loc_140011D6C
0x140011d61  test    esi, esi
0x140011d63  jz      short loc_140011D6C
0x140011d65  cmp     di, [rbx]
0x140011d68  cmovnz  r12d, r8d
0x140011d6c  lea     ecx, [r15+1]
0x140011d70  mov     edx, 8; Flags
0x140011d75  add     ecx, r12d
0x140011d78  add     ecx, esi
0x140011d7a  mov     eax, ecx
0x140011d7c  mov     [rsp+1E0h+cchDest], rax
0x140011d81  lea     r8, [rcx+rcx]; Size
0x140011d85  mov     rcx, gs:60h
0x140011d8e  mov     rcx, [rcx+30h]; HeapHandle
0x140011d92  call    cs:__imp_RtlAllocateHeap
0x140011d98  mov     rdi, rax
0x140011d9b  test    rax, rax
0x140011d9e  jz      loc_140011F2C
0x140011da4  mov     rdx, [rsp+1E0h+cchDest]; cchDest
0x140011da9  lea     rax, [rsp+1E0h+var_1A0]
0x140011dae  mov     [rsp+1E0h+pcchRemaining], rax; pcchRemaining
0x140011db3  lea     r8, [rsp+1E0h+pszSrc]; pszSrc
0x140011db8  lea     rax, [rsp+1E0h+pszDest]
0x140011dbd  mov     r9d, esi; cchToCopy
0x140011dc0  mov     rcx, rdi; pszDest
0x140011dc3  mov     [rsp+1E0h+ppszDestEnd], rax; ppszDestEnd
0x140011dc8  call    StringCchCopyNExW
0x140011dcd  mov     esi, eax
0x140011dcf  test    eax, eax
0x140011dd1  js      loc_140011E93
0x140011dd7  test    r12d, r12d
0x140011dda  jz      loc_140011E7B
0x140011de0  mov     rdx, [rsp+1E0h+var_1A0]; cchDest
0x140011de5  lea     rax, [rsp+1E0h+var_1A0]
0x140011dea  mov     rcx, [rsp+1E0h+pszDest]; pszDest
0x140011def  lea     r8, pszSrc; "\\"
0x140011df6  mov     [rsp+1E0h+pcchRemaining], rax; pcchRemaining
0x140011dfb  mov     r9d, 1; cchToCopy
0x140011e01  lea     rax, [rsp+1E0h+pszDest]
0x140011e06  mov     [rsp+1E0h+ppszDestEnd], rax; ppszDestEnd
0x140011e0b  call    StringCchCopyNExW
0x140011e10  xor     r12d, r12d
0x140011e13  mov     esi, eax
0x140011e15  test    eax, eax
0x140011e17  jns     short loc_140011E7E
0x140011e19  mov     rcx, gs:60h
0x140011e22  mov     r8, rdi; P
0x140011e25  xor     edx, edx; Flags
0x140011e27  mov     rcx, [rcx+30h]; HeapHandle
0x140011e2b  call    cs:__imp_RtlFreeHeap
0x140011e31  mov     rax, gs:30h
0x140011e3a  movzx   ecx, si
0x140011e3d  mov     [rax+68h], ecx
0x140011e40  mov     rdi, r12
0x140011e43  call    cs:__imp_GetLastError
0x140011e49  test    eax, eax
0x140011e4b  jle     short loc_140011E57
0x140011e4d  movzx   eax, ax
0x140011e50  or      eax, 80070000h
0x140011e55  test    eax, eax
0x140011e57  jns     loc_140011FE9
0x140011e5d  call    cs:__imp_GetLastError
0x140011e63  mov     ebx, eax
0x140011e65  test    eax, eax
0x140011e67  jle     loc_140011FEE
0x140011e6d  movzx   ebx, ax
0x140011e70  or      ebx, 80070000h
0x140011e76  jmp     loc_140011FEE
0x140011e7b  xor     r12d, r12d
0x140011e7e  mov     rdx, [rsp+1E0h+var_1A0]
0x140011e83  mov     r8, rbx
0x140011e86  mov     rcx, [rsp+1E0h+pszDest]
0x140011e8b  mov     r9d, r15d
0x140011e8e  jmp     loc_140011FC8
0x140011e93  xor     r12d, r12d
0x140011e96  jmp     short loc_140011E19
0x140011e98  mov     rax, gs:30h
0x140011ea1  mov     dword ptr [rax+68h], 57h ; 'W'
0x140011ea8  jmp     short loc_140011E40
0x140011eaa  mov     [rsp+1E0h+cchDest], r13
0x140011eaf  lea     rax, [rsp+1E0h+String2]
0x140011eb4  mov     r15d, r12d
0x140011eb7  mov     rsi, r14
0x140011eba  inc     rsi
0x140011ebd  cmp     [rax+rsi*2], r12w
0x140011ec2  jnz     short loc_140011EBA
0x140011ec4  mov     rbx, r14
0x140011ec7  inc     rbx
0x140011eca  cmp     [r13+rbx*2+0], r12w
0x140011ed0  jnz     short loc_140011EC7
0x140011ed2  test    esi, esi
0x140011ed4  jz      short loc_140011EFD
0x140011ed6  lea     eax, [rsi-1]
0x140011ed9  cmp     di, [rsp+rax*2+1E0h+String2]
0x140011ede  jnz     short loc_140011EF4
0x140011ee0  cmp     di, [r13+0]
0x140011ee5  jnz     short loc_140011EFD
0x140011ee7  lea     rax, [r13+2]
0x140011eeb  dec     ebx
0x140011eed  mov     [rsp+1E0h+cchDest], rax
0x140011ef2  jmp     short loc_140011EFD
0x140011ef4  cmp     di, [r13+0]
0x140011ef9  cmovnz  r15d, r8d
0x140011efd  lea     ecx, [rbx+1]
0x140011f00  mov     edx, 8; Flags
0x140011f05  add     ecx, r15d
0x140011f08  add     ecx, esi
0x140011f0a  mov     r12d, ecx
0x140011f0d  lea     r8, [rcx+rcx]; Size
0x140011f11  mov     rcx, gs:60h
0x140011f1a  mov     rcx, [rcx+30h]; HeapHandle
0x140011f1e  call    cs:__imp_RtlAllocateHeap
0x140011f24  mov     rdi, rax
0x140011f27  test    rax, rax
0x140011f2a  jnz     short loc_140011F44
0x140011f2c  mov     rax, gs:30h
0x140011f35  xor     r12d, r12d
0x140011f38  mov     dword ptr [rax+68h], 8
0x140011f3f  jmp     loc_140011E40
0x140011f44  lea     rax, [rsp+1E0h+pszDest]
0x140011f49  mov     r9d, esi; cchToCopy
0x140011f4c  mov     [rsp+1E0h+pcchRemaining], rax; pcchRemaining
0x140011f51  lea     r8, [rsp+1E0h+String2]; pszSrc
0x140011f56  lea     rax, [rsp+1E0h+var_1A0]
0x140011f5b  mov     rdx, r12; cchDest
0x140011f5e  mov     rcx, rdi; pszDest
0x140011f61  mov     [rsp+1E0h+ppszDestEnd], rax; ppszDestEnd
0x140011f66  call    StringCchCopyNExW
0x140011f6b  xor     r12d, r12d
0x140011f6e  mov     esi, eax
0x140011f70  test    eax, eax
0x140011f72  js      loc_140011E19
0x140011f78  test    r15d, r15d
0x140011f7b  jz      short loc_140011FB6
0x140011f7d  mov     rdx, [rsp+1E0h+pszDest]; cchDest
0x140011f82  lea     rax, [rsp+1E0h+pszDest]
0x140011f87  mov     rcx, [rsp+1E0h+var_1A0]; pszDest
0x140011f8c  lea     r9d, [r12+1]; cchToCopy
0x140011f91  mov     [rsp+1E0h+pcchRemaining], rax; pcchRemaining
0x140011f96  lea     r8, pszSrc; "\\"
0x140011f9d  lea     rax, [rsp+1E0h+var_1A0]
0x140011fa2  mov     [rsp+1E0h+ppszDestEnd], rax; ppszDestEnd
0x140011fa7  call    StringCchCopyNExW
0x140011fac  mov     esi, eax
0x140011fae  test    eax, eax
0x140011fb0  js      loc_140011E19
0x140011fb6  mov     r8, [rsp+1E0h+cchDest]; pszSrc
  ... truncated ...
```
