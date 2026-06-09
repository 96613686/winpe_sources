# PrepareUnicodePathEx

- ea: `0x18001331c`
- end: `0x180013f9f`
- name: `PrepareUnicodePathEx`
- size: `3203`
- prototype: `char *__fastcall(STRSAFE_LPCWSTR pszSrc, wchar_t **)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800128a0`
- `0x180012d7c`
- `0x18001320c`

## callees

- `0x180012eac`
- `0x180013168`
- `0x18001331c`
- `0x18001401c`
- `0x180014104`
- `0x1800142de`
- `0x180014310`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180013423`
- `msvcrt!_wcsnicmp` at `0x180013468`
- `msvcrt!_wcsnicmp` at `0x180013496`
- `msvcrt!_wcsnicmp` at `0x18001390c`
- `msvcrt!_wcsnicmp` at `0x180013924`
- `msvcrt!_wcsnicmp` at `0x18001393d`
- `msvcrt!_wcsnicmp` at `0x18001396d`
- `msvcrt!_wcsnicmp` at `0x1800139b5`
- `msvcrt!_wcsnicmp` at `0x1800139d9`
- `msvcrt!_wcsnicmp` at `0x180013a1d`
- `msvcrt!_wcsnicmp` at `0x180013a52`
- `msvcrt!_wcsnicmp` at `0x180013c6d`
- `msvcrt!_wcsnicmp` at `0x180013ca2`
- `msvcrt!_wcsnicmp` at `0x180013e2b`
- `msvcrt!_wcsnicmp` at `0x180013e57`
- `msvcrt!_wcsnicmp` at `0x180013e88`
- `msvcrt!_wcsnicmp` at `0x180013eab`
- `msvcrt!_wcsnicmp` at `0x180013ecb`
- `msvcrt!_wcsnicmp` at `0x180013efe`
- `msvcrt!_wcsnicmp` at `0x180013423`
- `msvcrt!_wcsnicmp` at `0x180013468`
- `msvcrt!_wcsnicmp` at `0x180013496`
- `msvcrt!_wcsnicmp` at `0x18001390c`
- `msvcrt!_wcsnicmp` at `0x180013924`
- `msvcrt!_wcsnicmp` at `0x18001393d`
- `msvcrt!_wcsnicmp` at `0x18001396d`
- `msvcrt!_wcsnicmp` at `0x1800139b5`
- `msvcrt!_wcsnicmp` at `0x1800139d9`
- `msvcrt!_wcsnicmp` at `0x180013a1d`
- `msvcrt!_wcsnicmp` at `0x180013a52`
- `msvcrt!_wcsnicmp` at `0x180013c6d`
- `msvcrt!_wcsnicmp` at `0x180013ca2`
- `msvcrt!_wcsnicmp` at `0x180013e2b`
- `msvcrt!_wcsnicmp` at `0x180013e57`
- `msvcrt!_wcsnicmp` at `0x180013e88`
- `msvcrt!_wcsnicmp` at `0x180013eab`
- `msvcrt!_wcsnicmp` at `0x180013ecb`
- `msvcrt!_wcsnicmp` at `0x180013efe`
- `msvcrt!wcschr` at `0x1800134be`
- `msvcrt!wcschr` at `0x1800134d7`
- `msvcrt!wcschr` at `0x180013a77`
- `msvcrt!wcschr` at `0x180013aa2`
- `msvcrt!wcschr` at `0x180013cc7`
- `msvcrt!wcschr` at `0x180013cf2`
- `msvcrt!wcschr` at `0x180013e3c`
- `msvcrt!wcschr` at `0x180013e68`
- `msvcrt!wcschr` at `0x1800134be`
- `msvcrt!wcschr` at `0x1800134d7`
- `msvcrt!wcschr` at `0x180013a77`
- `msvcrt!wcschr` at `0x180013aa2`
- `msvcrt!wcschr` at `0x180013cc7`
- `msvcrt!wcschr` at `0x180013cf2`
- `msvcrt!wcschr` at `0x180013e3c`
- `msvcrt!wcschr` at `0x180013e68`
- `KERNEL32!GetLastError` at `0x1800133a7`
- `KERNEL32!GetLastError` at `0x1800133be`
- `KERNEL32!GetLastError` at `0x180013647`
- `KERNEL32!GetLastError` at `0x180013661`
- `KERNEL32!GetLastError` at `0x18001381f`
- `KERNEL32!GetLastError` at `0x180013839`
- `KERNEL32!GetLastError` at `0x1800133a7`
- `KERNEL32!GetLastError` at `0x1800133be`
- `KERNEL32!GetLastError` at `0x180013647`
- `KERNEL32!GetLastError` at `0x180013661`
- `KERNEL32!GetLastError` at `0x18001381f`
- `KERNEL32!GetLastError` at `0x180013839`
- `KERNEL32!GetProcessHeap` at `0x180013b29`
- `KERNEL32!GetProcessHeap` at `0x180013b84`
- `KERNEL32!GetProcessHeap` at `0x180013bb4`
- `KERNEL32!GetProcessHeap` at `0x180013d79`
- `KERNEL32!GetProcessHeap` at `0x180013f46`
- `KERNEL32!GetProcessHeap` at `0x180013b29`
- `KERNEL32!GetProcessHeap` at `0x180013b84`
- `KERNEL32!GetProcessHeap` at `0x180013bb4`
- `KERNEL32!GetProcessHeap` at `0x180013d79`
- `KERNEL32!GetProcessHeap` at `0x180013f46`
- `KERNEL32!HeapFree` at `0x180013b37`
- `KERNEL32!HeapFree` at `0x180013b92`
- `KERNEL32!HeapFree` at `0x180013bc2`
- `KERNEL32!HeapFree` at `0x180013d87`
- `KERNEL32!HeapFree` at `0x180013f54`
- `KERNEL32!HeapFree` at `0x180013b37`
- `KERNEL32!HeapFree` at `0x180013b92`
- `KERNEL32!HeapFree` at `0x180013bc2`
- `KERNEL32!HeapFree` at `0x180013d87`
- `KERNEL32!HeapFree` at `0x180013f54`
- `KERNEL32!SetLastError` at `0x180013f5d`
- `KERNEL32!SetLastError` at `0x180013f6d`
- `KERNEL32!SetLastError` at `0x180013f5d`
- `KERNEL32!SetLastError` at `0x180013f6d`
- `ntdll!RtlFreeHeap` at `0x18001362f`
- `ntdll!RtlFreeHeap` at `0x18001362f`
- `ntdll!RtlAllocateHeap` at `0x180013596`
- `ntdll!RtlAllocateHeap` at `0x180013722`
- `ntdll!RtlAllocateHeap` at `0x180013aea`
- `ntdll!RtlAllocateHeap` at `0x180013d3a`
- `ntdll!RtlAllocateHeap` at `0x180013596`
- `ntdll!RtlAllocateHeap` at `0x180013722`
- `ntdll!RtlAllocateHeap` at `0x180013aea`
- `ntdll!RtlAllocateHeap` at `0x180013d3a`

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
0x18001331c  mov     [rsp-8+arg_10], rbx
0x180013321  push    rbp
0x180013322  push    rsi
0x180013323  push    rdi
0x180013324  push    r12
0x180013326  push    r13
0x180013328  push    r14
0x18001332a  push    r15
0x18001332c  lea     rbp, [rsp-0B0h]
0x180013334  sub     rsp, 1B0h
0x18001333b  mov     rax, cs:__security_cookie
0x180013342  xor     rax, rsp
0x180013345  mov     [rbp+0E0h+var_38], rax
0x18001334c  movups  xmm0, xmmword ptr cs:aUnc; "\\\\?\\UNC"
0x180013353  xor     r12d, r12d
0x180013356  mov     [rsp+1E0h+var_178], rdx
0x18001335b  mov     [rsp+1E0h+var_180], rcx
0x180013360  mov     rax, 3F005C005Ch
0x18001336a  mov     qword ptr [rsp+1E0h+String2], rax
0x18001336f  mov     rsi, rcx
0x180013372  movdqu  xmmword ptr [rsp+1E0h+pszSrc], xmm0
0x180013378  test    rcx, rcx
0x18001337b  jz      loc_180013F68
0x180013381  cmp     r12w, [rcx]
0x180013385  jz      loc_180013F68
0x18001338b  call    FormFullPathName
0x180013390  mov     [rsp+1E0h+var_190], rax
0x180013395  mov     r13, rax
0x180013398  mov     edi, 80070000h
0x18001339d  test    rax, rax
0x1800133a0  jz      short loc_1800133A7
0x1800133a2  mov     ebx, r12d
0x1800133a5  jmp     short loc_1800133D7
0x1800133a7  call    cs:__imp_GetLastError
0x1800133ad  test    eax, eax
0x1800133af  jle     short loc_1800133B8
0x1800133b1  movzx   eax, ax
0x1800133b4  or      eax, edi
0x1800133b6  test    eax, eax
0x1800133b8  jns     loc_180013F39
0x1800133be  call    cs:__imp_GetLastError
0x1800133c4  mov     ebx, eax
0x1800133c6  test    eax, eax
0x1800133c8  jle     short loc_1800133CF
0x1800133ca  movzx   ebx, ax
0x1800133cd  or      ebx, edi
0x1800133cf  test    ebx, ebx
0x1800133d1  js      loc_180013F3E
0x1800133d7  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800133db  mov     rax, r14
0x1800133de  inc     rax
0x1800133e1  cmp     [r13+rax*2+0], r12w
0x1800133e7  jnz     short loc_1800133DE
0x1800133e9  mov     r15d, 5Ch ; '\'
0x1800133ef  cmp     rax, 104h
0x1800133f5  jb      loc_18001380A
0x1800133fb  lea     r8d, [r15-59h]; MaxCount
0x1800133ff  mov     rcx, r13; String1
0x180013402  lea     rdx, [rsp+1E0h+String2]; String2
0x180013407  mov     rdi, r12
0x18001340a  call    wcsncmp_0
0x18001340f  test    eax, eax
0x180013411  jz      loc_1800137FD
0x180013417  lea     r8d, [r15-55h]; MaxCount
0x18001341b  mov     rcx, r13; String1
0x18001341e  lea     rdx, [rsp+1E0h+pszSrc]; String2
0x180013423  call    cs:__imp__wcsnicmp
0x180013429  test    eax, eax
0x18001342b  jz      loc_1800137FD
0x180013431  test    r13, r13
0x180013434  jnz     short loc_180013440
0x180013436  mov     ebx, 80070057h
0x18001343b  jmp     loc_180013F3E
0x180013440  mov     rax, r14
0x180013443  inc     rax
0x180013446  cmp     [r13+rax*2+0], r12w
0x18001344c  jnz     short loc_180013443
0x18001344e  cmp     rax, 2
0x180013452  jb      loc_1800134EB
0x180013458  mov     r8d, 2; MaxCount
0x18001345e  lea     rdx, asc_18001F254; "\\\\"
0x180013465  mov     rcx, r13; String1
0x180013468  call    cs:__imp__wcsnicmp
0x18001346e  test    eax, eax
0x180013470  jnz     short loc_1800134EB
0x180013472  mov     rax, r14
0x180013475  inc     rax
0x180013478  cmp     [r13+rax*2+0], r12w
0x18001347e  jnz     short loc_180013475
0x180013480  cmp     rax, 8
0x180013484  jb      short loc_1800134A6
0x180013486  mov     r8d, 8; MaxCount
0x18001348c  lea     rdx, aUnc_0; "\\\\?\\UNC\\"
0x180013493  mov     rcx, r13; String1
0x180013496  call    cs:__imp__wcsnicmp
0x18001349c  test    eax, eax
0x18001349e  mov     ecx, r12d
0x1800134a1  setz    cl
0x1800134a4  jmp     short loc_1800134A9
0x1800134a6  mov     ecx, r12d
0x1800134a9  neg     ecx
0x1800134ab  mov     edx, r15d; Ch
0x1800134ae  mov     edi, r15d
0x1800134b1  sbb     rcx, rcx
0x1800134b4  and     ecx, 0Ch
0x1800134b7  add     rcx, 4
0x1800134bb  add     rcx, r13; Str
0x1800134be  call    cs:__imp_wcschr
0x1800134c4  test    rax, rax
0x1800134c7  jnz     short loc_1800134D0
0x1800134c9  mov     ebx, 8007000Dh
0x1800134ce  jmp     short loc_1800134F1
0x1800134d0  mov     edx, r15d; Ch
0x1800134d3  lea     rcx, [rax+2]; Str
0x1800134d7  call    cs:__imp_wcschr
0x1800134dd  mov     r8d, 1
0x1800134e3  mov     ebx, r12d
0x1800134e6  mov     eax, r8d
0x1800134e9  jmp     short loc_1800134FA
0x1800134eb  mov     ebx, r12d
0x1800134ee  mov     edi, r15d
0x1800134f1  mov     r8d, 1
0x1800134f7  mov     eax, r12d
0x1800134fa  test    ebx, ebx
0x1800134fc  js      loc_180013F3E
0x180013502  mov     [rsp+1E0h+pszDest], r12
0x180013507  mov     [rsp+1E0h+var_1A0], r12
0x18001350c  cmp     eax, r8d
0x18001350f  jnz     loc_1800136AE
0x180013515  lea     rbx, [r13+2]
0x180013519  test    rbx, rbx
0x18001351c  jz      loc_18001369C
0x180013522  lea     rax, [rsp+1E0h+pszSrc]
0x180013527  mov     rsi, r14
0x18001352a  xor     edx, edx
0x18001352c  inc     rsi
0x18001352f  cmp     [rax+rsi*2], dx
0x180013533  jnz     short loc_18001352C
0x180013535  mov     r15, r14
0x180013538  inc     r15
0x18001353b  cmp     [rbx+r15*2], dx
0x180013540  jnz     short loc_180013538
0x180013542  test    esi, esi
0x180013544  jz      short loc_180013570
0x180013546  lea     eax, [rsi-1]
0x180013549  cmp     di, [rsp+rax*2+1E0h+pszSrc]
0x18001354e  jnz     short loc_180013565
0x180013550  cmp     di, [rbx]
0x180013553  jnz     short loc_18001355B
0x180013555  dec     r15d
0x180013558  cmp     di, [rbx]
0x18001355b  cmovnz  rbx, r13
0x18001355f  add     rbx, 2
0x180013563  jmp     short loc_180013570
0x180013565  test    esi, esi
0x180013567  jz      short loc_180013570
0x180013569  cmp     di, [rbx]
0x18001356c  cmovnz  r12d, r8d
0x180013570  lea     ecx, [r15+1]
0x180013574  mov     edx, 8; Flags
0x180013579  add     ecx, r12d
0x18001357c  add     ecx, esi
0x18001357e  mov     eax, ecx
0x180013580  mov     [rsp+1E0h+cchDest], rax
0x180013585  lea     r8, [rcx+rcx]; Size
0x180013589  mov     rcx, gs:60h
0x180013592  mov     rcx, [rcx+30h]; HeapHandle
0x180013596  call    cs:__imp_RtlAllocateHeap
0x18001359c  mov     rdi, rax
0x18001359f  test    rax, rax
0x1800135a2  jz      loc_180013730
0x1800135a8  mov     rdx, [rsp+1E0h+cchDest]; cchDest
0x1800135ad  lea     rax, [rsp+1E0h+var_1A0]
0x1800135b2  mov     [rsp+1E0h+pcchRemaining], rax; pcchRemaining
0x1800135b7  lea     r8, [rsp+1E0h+pszSrc]; pszSrc
0x1800135bc  lea     rax, [rsp+1E0h+pszDest]
0x1800135c1  mov     r9d, esi; cchToCopy
0x1800135c4  mov     rcx, rdi; pszDest
0x1800135c7  mov     [rsp+1E0h+ppszDestEnd], rax; ppszDestEnd
0x1800135cc  call    StringCchCopyNExW
0x1800135d1  mov     esi, eax
0x1800135d3  test    eax, eax
0x1800135d5  js      loc_180013697
0x1800135db  test    r12d, r12d
0x1800135de  jz      loc_18001367F
0x1800135e4  mov     rdx, [rsp+1E0h+var_1A0]; cchDest
0x1800135e9  lea     rax, [rsp+1E0h+var_1A0]
0x1800135ee  mov     rcx, [rsp+1E0h+pszDest]; pszDest
0x1800135f3  lea     r8, pszSrc; "\\"
0x1800135fa  mov     [rsp+1E0h+pcchRemaining], rax; pcchRemaining
0x1800135ff  mov     r9d, 1; cchToCopy
0x180013605  lea     rax, [rsp+1E0h+pszDest]
0x18001360a  mov     [rsp+1E0h+ppszDestEnd], rax; ppszDestEnd
0x18001360f  call    StringCchCopyNExW
0x180013614  xor     r12d, r12d
0x180013617  mov     esi, eax
0x180013619  test    eax, eax
0x18001361b  jns     short loc_180013682
0x18001361d  mov     rcx, gs:60h
0x180013626  mov     r8, rdi; P
0x180013629  xor     edx, edx; Flags
0x18001362b  mov     rcx, [rcx+30h]; HeapHandle
0x18001362f  call    cs:__imp_RtlFreeHeap
0x180013635  mov     rax, gs:30h
0x18001363e  movzx   ecx, si
0x180013641  mov     [rax+68h], ecx
0x180013644  mov     rdi, r12
0x180013647  call    cs:__imp_GetLastError
0x18001364d  test    eax, eax
0x18001364f  jle     short loc_18001365B
0x180013651  movzx   eax, ax
0x180013654  or      eax, 80070000h
0x180013659  test    eax, eax
0x18001365b  jns     loc_1800137ED
0x180013661  call    cs:__imp_GetLastError
0x180013667  mov     ebx, eax
0x180013669  test    eax, eax
0x18001366b  jle     loc_1800137F2
0x180013671  movzx   ebx, ax
0x180013674  or      ebx, 80070000h
0x18001367a  jmp     loc_1800137F2
0x18001367f  xor     r12d, r12d
0x180013682  mov     rdx, [rsp+1E0h+var_1A0]
0x180013687  mov     r8, rbx
0x18001368a  mov     rcx, [rsp+1E0h+pszDest]
0x18001368f  mov     r9d, r15d
0x180013692  jmp     loc_1800137CC
0x180013697  xor     r12d, r12d
0x18001369a  jmp     short loc_18001361D
0x18001369c  mov     rax, gs:30h
0x1800136a5  mov     dword ptr [rax+68h], 57h ; 'W'
0x1800136ac  jmp     short loc_180013644
0x1800136ae  mov     [rsp+1E0h+cchDest], r13
0x1800136b3  lea     rax, [rsp+1E0h+String2]
0x1800136b8  mov     r15d, r12d
0x1800136bb  mov     rsi, r14
0x1800136be  inc     rsi
0x1800136c1  cmp     [rax+rsi*2], r12w
0x1800136c6  jnz     short loc_1800136BE
0x1800136c8  mov     rbx, r14
0x1800136cb  inc     rbx
0x1800136ce  cmp     [r13+rbx*2+0], r12w
0x1800136d4  jnz     short loc_1800136CB
0x1800136d6  test    esi, esi
0x1800136d8  jz      short loc_180013701
0x1800136da  lea     eax, [rsi-1]
0x1800136dd  cmp     di, [rsp+rax*2+1E0h+String2]
0x1800136e2  jnz     short loc_1800136F8
0x1800136e4  cmp     di, [r13+0]
0x1800136e9  jnz     short loc_180013701
0x1800136eb  lea     rax, [r13+2]
0x1800136ef  dec     ebx
0x1800136f1  mov     [rsp+1E0h+cchDest], rax
0x1800136f6  jmp     short loc_180013701
0x1800136f8  cmp     di, [r13+0]
0x1800136fd  cmovnz  r15d, r8d
0x180013701  lea     ecx, [rbx+1]
0x180013704  mov     edx, 8; Flags
0x180013709  add     ecx, r15d
0x18001370c  add     ecx, esi
0x18001370e  mov     r12d, ecx
0x180013711  lea     r8, [rcx+rcx]; Size
0x180013715  mov     rcx, gs:60h
0x18001371e  mov     rcx, [rcx+30h]; HeapHandle
0x180013722  call    cs:__imp_RtlAllocateHeap
0x180013728  mov     rdi, rax
0x18001372b  test    rax, rax
0x18001372e  jnz     short loc_180013748
0x180013730  mov     rax, gs:30h
0x180013739  xor     r12d, r12d
0x18001373c  mov     dword ptr [rax+68h], 8
0x180013743  jmp     loc_180013644
0x180013748  lea     rax, [rsp+1E0h+pszDest]
0x18001374d  mov     r9d, esi; cchToCopy
0x180013750  mov     [rsp+1E0h+pcchRemaining], rax; pcchRemaining
0x180013755  lea     r8, [rsp+1E0h+String2]; pszSrc
0x18001375a  lea     rax, [rsp+1E0h+var_1A0]
0x18001375f  mov     rdx, r12; cchDest
0x180013762  mov     rcx, rdi; pszDest
0x180013765  mov     [rsp+1E0h+ppszDestEnd], rax; ppszDestEnd
0x18001376a  call    StringCchCopyNExW
0x18001376f  xor     r12d, r12d
0x180013772  mov     esi, eax
0x180013774  test    eax, eax
0x180013776  js      loc_18001361D
0x18001377c  test    r15d, r15d
0x18001377f  jz      short loc_1800137BA
0x180013781  mov     rdx, [rsp+1E0h+pszDest]; cchDest
0x180013786  lea     rax, [rsp+1E0h+pszDest]
0x18001378b  mov     rcx, [rsp+1E0h+var_1A0]; pszDest
0x180013790  lea     r9d, [r12+1]; cchToCopy
0x180013795  mov     [rsp+1E0h+pcchRemaining], rax; pcchRemaining
0x18001379a  lea     r8, pszSrc; "\\"
0x1800137a1  lea     rax, [rsp+1E0h+var_1A0]
0x1800137a6  mov     [rsp+1E0h+ppszDestEnd], rax; ppszDestEnd
0x1800137ab  call    StringCchCopyNExW
0x1800137b0  mov     esi, eax
0x1800137b2  test    eax, eax
0x1800137b4  js      loc_18001361D
0x1800137ba  mov     r8, [rsp+1E0h+cchDest]; pszSrc
  ... truncated ...
```
