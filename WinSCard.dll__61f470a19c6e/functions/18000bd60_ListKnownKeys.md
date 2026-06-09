# ListKnownKeys

- ea: `0x18000bd60`
- end: `0x18000cad9`
- name: `ListKnownKeys`
- size: `3449`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180009480`
- `0x18000cd90`
- `0x18000ff40`
- `0x18002a8ec`

## callees

- `0x18000bcf0`
- `0x18000bd10`
- `0x18000bd60`
- `0x180013b20`
- `0x18001b9b8`
- `0x18001ba04`
- `0x18001c7a8`
- `0x18002ef20`
- `0x18002ef38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000be12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c4b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000be12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c4b8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000bef8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000bef8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000be42`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000be42`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000c6d8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000c6d8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000c07d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000c07d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_BOOL8 ListKnownKeys(unsigned int a1, __int64 a2, const WCHAR *a3, ...)
{
  unsigned int v3; // edx
  HKEY v4; // rcx
  unsigned int v5; // esi
  unsigned int v6; // r13d
  unsigned int v7; // r15d
  const unsigned __int16 *v8; // r12
  const WCHAR *v9; // r14
  int v10; // ebx
  HKEY v11; // rdi
  LSTATUS v12; // eax
  DWORD v13; // r13d
  unsigned int v14; // ecx
  unsigned __int64 v15; // rdx
  WCHAR *v16; // rdi
  const WCHAR *v17; // r14
  int v18; // edi
  WCHAR *v19; // r8
  LSTATUS v20; // eax
  unsigned int v21; // ebx
  unsigned __int64 v22; // rdx
  const unsigned __int16 *v23; // rdi
  const unsigned __int16 *v24; // r14
  unsigned int v25; // r14d
  int v26; // ebx
  _QWORD *v27; // rsi
  unsigned __int64 v28; // rdx
  const unsigned __int16 *i; // r15
  __int64 v30; // rdi
  unsigned __int64 v31; // rdx
  _QWORD *v32; // r12
  __int64 j; // rax
  unsigned int v34; // r13d
  unsigned int v35; // r15d
  __int64 k; // rdi
  const WCHAR *v37; // rdx
  __int64 v38; // r12
  const WCHAR *v39; // rcx
  int v40; // eax
  unsigned __int64 v41; // rdx
  _QWORD *v42; // r13
  __int64 m; // rax
  unsigned __int64 v44; // rdx
  _QWORD *v45; // r12
  __int64 n; // rax
  int v47; // r8d
  unsigned int ii; // edx
  __int64 v49; // rcx
  __int64 v50; // rax
  unsigned int v51; // ebx
  __int64 v52; // r9
  unsigned int *v53; // rcx
  unsigned __int64 v54; // rdx
  void *v55; // rdi
  void *v56; // rcx
  unsigned int *v57; // rax
  unsigned int *v58; // r15
  unsigned int v59; // r12d
  _WORD *v60; // rbx
  __int64 v61; // rax
  unsigned int v62; // r13d
  unsigned int v63; // eax
  unsigned int v64; // edi
  const WCHAR *v65; // rax
  unsigned __int64 v66; // rdx
  void *v67; // rcx
  unsigned int v68; // edi
  unsigned int v69; // eax
  unsigned __int64 v70; // rdx
  WCHAR *v71; // r14
  LPWSTR v72; // rcx
  WCHAR *v73; // rax
  unsigned __int64 v74; // rdx
  _DWORD *v75; // rbx
  unsigned int *v76; // r14
  unsigned int v77; // edi
  unsigned int v78; // ecx
  unsigned __int64 v79; // rdx
  void *v80; // r15
  void *v81; // rcx
  _DWORD *v82; // rax
  BOOL v83; // edi
  unsigned int v85; // r12d
  unsigned __int64 v86; // rdx
  WCHAR *v87; // r13
  void *v88; // rbx
  void *v89; // rcx
  unsigned __int16 *v90; // rax
  const unsigned __int16 *v91; // rdi
  unsigned __int64 v92; // rdx
  unsigned int v93; // ecx
  int v94; // ebx
  unsigned int v95; // r12d
  __int64 v96; // r8
  void *v97; // rax
  void *v98; // r15
  unsigned __int64 v99; // rdx
  WCHAR *v100; // rax
  int v101; // eax
  unsigned int v102; // edi
  unsigned int v103; // r12d
  unsigned __int64 v104; // rdx
  char *v105; // rsi
  char *v106; // rax
  char *v107; // r13
  unsigned __int64 v108; // rdx
  char *Src; // [rsp+48h] [rbp-51h]
  unsigned int v110; // [rsp+54h] [rbp-45h]
  struct _FILETIME ftLastWriteTime; // [rsp+58h] [rbp-41h] BYREF
  LPCWSTR lpSubKey; // [rsp+60h] [rbp-39h] BYREF
  __int64 v113; // [rsp+68h] [rbp-31h]
  _QWORD *v114; // [rsp+70h] [rbp-29h]
  HKEY hKey; // [rsp+78h] [rbp-21h] BYREF
  int v116; // [rsp+80h] [rbp-19h]
  const int *v117; // [rsp+88h] [rbp-11h]
  LPWSTR lpName; // [rsp+90h] [rbp-9h]
  size_t Size; // [rsp+98h] [rbp-1h]
  int v120; // [rsp+A0h] [rbp+7h]
  const WCHAR *v121; // [rsp+A8h] [rbp+Fh]
  unsigned int *pExceptionObject; // [rsp+110h] [rbp+77h] BYREF
  __int64 cchName; // [rsp+118h] [rbp+7Fh] BYREF
  va_list cchNamea; // [rsp+118h] [rbp+7Fh]
  va_list va1; // [rsp+120h] [rbp+87h] BYREF

  va_start(va1, a3);
  va_start(cchNamea, a3);
  cchName = va_arg(va1, _QWORD);
  v3 = a1;
  v117 = &CBuffer::`vftable';
  lpName = 0;
  Size = 0;
  v4 = 0;
  hKey = 0;
  v120 = 1010;
  Src = 0;
  v5 = 0;
  v110 = 0;
  v6 = 0;
  lpSubKey = a3;
  v113 = 0;
  v7 = 0;
  v8 = &WideCharStr;
LABEL_2:
  if ( v7 < 2 )
  {
    v9 = (&lpSubKey)[v7];
    v121 = v9;
    if ( !v9 )
      goto LABEL_111;
    v10 = 0;
    while ( 1 )
    {
      if ( dword_180038360[4 * v10] < v3 )
        goto LABEL_109;
      v11 = *(HKEY *)&dword_180038360[4 * v10 + 2];
      if ( v4 )
      {
        RegCloseKey(v4);
        hKey = 0;
      }
      v120 = 1010;
      LODWORD(Size) = 0;
      v12 = RegOpenKeyExW(v11, v9, 0, 0x20019u, &hKey);
      v120 = v12;
      v116 = 2;
      if ( v12 )
        goto LABEL_108;
      v13 = 0;
      while ( 2 )
      {
        LODWORD(pExceptionObject) = v13;
        LODWORD(cchName) = 0;
        ftLastWriteTime = 0;
        if ( v12 )
        {
          LODWORD(pExceptionObject) = v12;
          throw (ulong *)&pExceptionObject;
        }
        v14 = HIDWORD(Size);
        if ( HIDWORD(Size) < 0x80 )
        {
          v16 = (WCHAR *)operator new[](0x80u);
          if ( !v16 )
          {
            LODWORD(pExceptionObject) = 14;
            throw (ulong *)&pExceptionObject;
          }
          if ( lpName )
            operator delete(lpName, v15);
          lpName = v16;
          v14 = 128;
          HIDWORD(Size) = 128;
        }
        v17 = 0;
        v18 = 0;
LABEL_17:
        LODWORD(Size) = 0;
        while ( !v18 )
        {
          LODWORD(cchName) = v14 >> 1;
          v19 = (WCHAR *)&WideCharStr;
          if ( v14 )
            v19 = lpName;
          v20 = RegEnumKeyExW(hKey, v13, v19, (LPDWORD)cchNamea, 0, 0, 0, &ftLastWriteTime);
          if ( v20 == 259 )
          {
            v17 = 0;
            v18 = 1;
            v14 = HIDWORD(Size);
          }
          else
          {
            if ( v20 )
            {
              if ( v20 != 234 )
              {
                LODWORD(pExceptionObject) = v20;
                throw (ulong *)&pExceptionObject;
              }
              v85 = 2 * cchName + 2;
              v14 = HIDWORD(Size);
              if ( HIDWORD(Size) < v85 )
              {
                v87 = (WCHAR *)operator new[](v85);
                if ( !v87 )
                {
                  LODWORD(pExceptionObject) = 14;
                  throw (ulong *)&pExceptionObject;
                }
                if ( lpName )
                  operator delete(lpName, v86);
                lpName = v87;
                v14 = v85;
                HIDWORD(Size) = v85;
                v13 = (unsigned int)pExceptionObject;
              }
              v8 = &WideCharStr;
              goto LABEL_17;
            }
            v68 = 2 * cchName + 2;
            v14 = HIDWORD(Size);
            if ( !(_DWORD)Size )
            {
              v69 = HIDWORD(Size);
              if ( HIDWORD(Size) >= v68 )
                goto LABEL_119;
              v71 = (WCHAR *)operator new[](v68);
              if ( !v71 )
              {
                LODWORD(pExceptionObject) = 14;
                throw (ulong *)&pExceptionObject;
              }
              v72 = lpName;
              if ( lpName )
LABEL_117:
                operator delete(v72, v70);
              v14 = v68;
              v69 = v68;
              HIDWORD(Size) = v68;
              lpName = v71;
              goto LABEL_119;
            }
            if ( HIDWORD(Size) < v68 )
            {
              v100 = (WCHAR *)operator new[](v68);
              v71 = v100;
              if ( !v100 )
              {
                LODWORD(pExceptionObject) = 14;
                throw (ulong *)&pExceptionObject;
              }
              memcpy_0(v100, lpName, (unsigned int)Size);
              v72 = lpName;
              goto LABEL_117;
            }
            v69 = HIDWORD(Size);
LABEL_119:
            LODWORD(Size) = v68;
            v17 = &WideCharStr;
            if ( v69 )
              v17 = lpName;
            v18 = 1;
          }
        }
        if ( v17 )
        {
          v101 = lstrlenW(v17);
          v102 = 2 * v101 + 2;
          if ( 2 * v101 != -2 )
          {
            v103 = v102 + v5;
            if ( v5 )
            {
              if ( v110 < v103 )
              {
                v106 = (char *)operator new[](v103);
                v107 = v106;
                if ( !v106 )
                {
                  LODWORD(cchName) = 14;
                  throw (ulong *)cchNamea;
                }
                memcpy_0(v106, Src, v5);
                operator delete(Src, v108);
                Src = v107;
                v110 = v102 + v5;
                v13 = (unsigned int)pExceptionObject;
              }
            }
            else
            {
              if ( v110 < v103 )
              {
                v105 = (char *)operator new[](v103);
                if ( !v105 )
                {
                  LODWORD(cchName) = 14;
                  throw (ulong *)cchNamea;
                }
                if ( Src )
                  operator delete(Src, v104);
                Src = v105;
                v110 = v103;
              }
              v5 = 0;
            }
            memcpy_0(&Src[v5], v17, v102);
            v5 += v102;
            v8 = &WideCharStr;
          }
          ++v13;
          v12 = v120;
          continue;
        }
        break;
      }
      v6 = v110;
      v9 = v121;
LABEL_108:
      v4 = hKey;
      v3 = a1;
LABEL_109:
      if ( (unsigned int)++v10 >= 2 )
      {
        if ( v3 == 2 )
        {
LABEL_111:
          ++v7;
          goto LABEL_2;
        }
        break;
      }
    }
  }
  v21 = v5 + 4;
  if ( v5 )
  {
    if ( v6 >= v21 )
    {
      v24 = (const unsigned __int16 *)Src;
    }
    else
    {
      v90 = (unsigned __int16 *)operator new[](v21);
      v91 = v90;
      if ( !v90 )
      {
        LODWORD(cchName) = 14;
        throw (ulong *)cchNamea;
      }
      memcpy_0(v90, Src, v5);
      operator delete(Src, v92);
      v24 = v91;
      Src = (char *)v91;
      v6 = v5 + 4;
    }
  }
  else
  {
    if ( v6 >= v21 )
    {
      v24 = (const unsigned __int16 *)Src;
    }
    else
    {
      v23 = (const unsigned __int16 *)operator new[](v21);
      if ( !v23 )
      {
        LODWORD(cchName) = 14;
        throw (ulong *)cchNamea;
      }
      if ( Src )
        operator delete(Src, v22);
      v24 = v23;
      Src = (char *)v23;
      v6 = v5 + 4;
    }
    v5 = 0;
  }
  *(_DWORD *)((char *)v24 + v5) = 0;
  if ( v6 )
    v8 = v24;
  lpSubKey = (LPCWSTR)&CDynamicArray<unsigned short const>::`vftable';
  v25 = 0;
  v26 = 0;
  v113 = 0;
  v27 = 0;
  v114 = 0;
  for ( i = FirstString(v8); i; i = NextString(i) )
  {
    v30 = v25;
    if ( v25 >= v26 )
    {
      if ( !v26 )
        v26 = 4;
      for ( ; (int)v25 >= v26; v26 *= 2 )
        ;
      v32 = operator new[](saturated_mul(v26, 8u));
      if ( !v32 )
      {
        LODWORD(cchName) = 14;
        throw (ulong *)cchNamea;
      }
      for ( j = 0; (unsigned int)j < v25; j = (unsigned int)(j + 1) )
      {
        v31 = v27[j];
        v32[j] = v31;
      }
      if ( v27 )
        operator delete(v27, v31);
      v27 = v32;
      v114 = v32;
      LODWORD(v113) = v26;
    }
    ++v25;
    HIDWORD(v113) = v30 + 1;
    v27[v30] = i;
  }
  v34 = v25;
  LODWORD(cchName) = v25;
  if ( v25 )
  {
    v35 = 0;
    do
    {
      for ( k = v34 - 1; v35 < (unsigned int)k; k = (unsigned int)(k - 1) )
      {
        if ( v25 <= (unsigned int)k )
          v37 = 0;
        else
          v37 = (const WCHAR *)v27[(int)k];
        v38 = (unsigned int)(k - 1);
        if ( v25 <= (unsigned int)v38 )
          v39 = 0;
        else
          v39 = (const WCHAR *)v27[(int)v38];
        v40 = lstrcmpiW(v39, v37);
        if ( v40 <= 0 )
        {
          if ( !v40 )
          {
            v93 = k;
            v94 = cchName;
            v34 = cchName - 1;
            if ( (unsigned int)k < (int)cchName - 1 )
            {
              while ( 1 )
              {
                v95 = v93 + 1;
                v96 = v25 <= v93 + 1 ? 0LL : v27[v95];
                CDynamicArray<unsigned short const>::Set(&lpSubKey, v93, v96);
                v93 = v95;
                if ( v95 >= v34 )
                  break;
                v27 = v114;
                v25 = HIDWORD(v113);
              }
            }
            CDynamicArray<unsigned short const>::Set(&lpSubKey, (unsigned int)(v94 - 1), 0);
            LODWORD(cchName) = v34;
            v27 = v114;
            v25 = HIDWORD(v113);
            v26 = v113;
            continue;
          }
        }
        else
        {
          if ( v25 <= (unsigned int)v38 )
            ftLastWriteTime = 0;
          else
            ftLastWriteTime = (struct _FILETIME)v27[(int)v38];
          if ( v25 <= (unsigned int)k )
            pExceptionObject = 0;
          else
            pExceptionObject = (unsigned int *)v27[(int)k];
          if ( (unsigned int)v38 >= v26 )
          {
            if ( !v26 )
              v26 = 4;
            for ( ; (int)v38 >= v26; v26 *= 2 )
              ;
            v42 = operator new[](saturated_mul(v26, 8u));
            if ( !v42 )
            {
              LODWORD(cchName) = 14;
              throw (ulong *)cchNamea;
            }
            for ( m = 0; (unsigned int)m < v25; m = (unsigned int)(m + 1) )
            {
              v41 = 8 * m;
              v42[m] = v27[m];
            }
            if ( v27 )
              operator delete(v27, v41);
            v27 = v42;
            v114 = v42;
            LODWORD(v113) = v26;
          }
          if ( (unsigned int)v38 >= v25 )
          {
            if ( (unsigned int)v38 > v25 )
              memset_0(&v27[v25], 0, 8LL * ((unsigned int)v38 - v25));
            v25 = k;
            HIDWORD(v113) = k;
          }
          v27[v38] = pExceptionObject;
          if ( (unsigned int)k >= v26 )
          {
            if ( !v26 )
              v26 = 4;
            for ( ; (int)k >= v26; v26 *= 2 )
              ;
            v45 = operator new[](saturated_mul(v26, 8u));
            if ( !v45 )
            {
              LODWORD(cchName) = 14;
              throw (ulong *)cchNamea;
            }
            for ( n = 0; (unsigned int)n < v25; n = (unsigned int)(n + 1) )
            {
              v44 = 8 * n;
              v45[n] = v27[n];
            }
            if ( v27 )
              operator delete(v27, v44);
            v27 = v45;
            v114 = v45;
            LODWORD(v113) = v26;
          }
          if ( (unsigned int)k >= v25 )
          {
            if ( (unsigned int)k > v25 )
              memset_0(&v27[v25], 0, 8LL * ((unsigned int)k - v25));
            v25 = k + 1;
            HIDWORD(v113) = k + 1;
          }
          v27[k] = ftLastWriteTime;
        }
        v34 = cchName;
      }
      ++v35;
    }
    while ( v35 < v34 );
    v47 = 0;
    for ( ii = 0; ii < v34; ++ii )
    {
      if ( v25 <= ii )
        v49 = 0;
      else
        v49 = v27[ii];
      v50 = -1;
      do
        ++v50;
      while ( *(_WORD *)(v49 + 2 * v50) );
      v47 += v50 + 1;
    }
    v51 = 2 * v47 + 4;
    v52 = a2;
    v53 = (unsigned int *)(a2 + 20);
    pExceptionObject = (unsigned int *)(a2 + 20);
    if ( *(_DWORD *)(a2 + 20) >= v51 )
    {
      ftLastWriteTime = (struct _FILETIME)(a2 + 20);
    }
    else
    {
      v55 = operator new[](v51);
      if ( !v55 )
      {
        LODWORD(cchName) = 14;
        throw (ulong *)cchNamea;
      }
      v52 = a2;
      v56 = *(void **)(a2 + 8);
      if ( v56 )
      {
        operator delete(v56, v54);
        v52 = a2;
      }
      *(_QWORD *)(v52 + 8) = v55;
      v57 = pExceptionObject;
      *pExceptionObject = v51;
      ftLastWriteTime = (struct _FILETIME)(v52 + 20);
      v53 = v57;
    }
    v58 = (unsigned int *)(v52 + 16);
    *(_DWORD *)(v52 + 16) = 0;
    v59 = 0;
    if ( v34 )
    {
      while ( 1 )
      {
        if ( v25 <= v59 )
          v60 = 0;
        else
          v60 = (_WORD *)v27[v59];
        v61 = -1;
        do
          ++v61;
        while ( v60[v61] );
        v62 = 2 * v61 + 2;
        if ( 2 * (_DWORD)v61 != -2 )
        {
          v63 = *v58;
          v64 = *v58 + v62;
          if ( *v58 )
          {
            if ( *v53 < v64 )
            {
              v73 = (WCHAR *)operator new[](v64);
              v121 = v73;
              if ( !v73 )
              {
                LODWORD(cchName) = 14;
                throw (ulong *)cchNamea;
              }
              memcpy_0(v73, *(const void **)(a2 + 8), *v58);
              operator delete(*(void **)(a2 + 8), v74);
              v52 = a2;
              *(_QWORD *)(a2 + 8) = v121;
              *pExceptionObject = v64;
              v63 = *v58;
            }
          }
          else
          {
            if ( *v53 < v64 )
            {
              v65 = (const WCHAR *)operator new[](v64);
              v121 = v65;
              if ( !v65 )
              {
                LODWORD(cchName) = 14;
                throw (ulong *)cchNamea;
              }
              v52 = a2;
              v67 = *(void **)(a2 + 8);
              if ( v67 )
              {
                operator delete(v67, v66);
                v65 = v121;
                v52 = a2;
              }
              *(_QWORD *)(v52 + 8) = v65;
              *pExceptionObject = v64;
            }
            *v58 = 0;
            v63 = 0;
          }
          memcpy_0((void *)(*(_QWORD *)(v52 + 8) + v63), v60, v62);
          *v58 += v62;
          v52 = a2;
        }
        if ( ++v59 >= (unsigned int)cchName )
          break;
        v53 = pExceptionObject;
      }
      v75 = (_DWORD *)(v52 + 16);
      v76 = (unsigned int *)(v52 + 20);
    }
    else
    {
      v75 = (_DWORD *)(v52 + 16);
      v76 = (unsigned int *)ftLastWriteTime;
    }
    v77 = *v58 + 2;
    v78 = *(_DWORD *)(v52 + 20);
    if ( *v58 )
    {
      if ( v78 < v77 )
      {
        v97 = operator new[](v77);
        v98 = v97;
        if ( !v97 )
        {
          LODWORD(cchName) = 14;
          throw (ulong *)cchNamea;
        }
        memcpy_0(v97, *(const void **)(a2 + 8), (unsigned int)*v75);
        operator delete(*(void **)(a2 + 8), v99);
        v52 = a2;
        *(_QWORD *)(a2 + 8) = v98;
        *v76 = v77;
      }
    }
    else
    {
      if ( v78 >= v77 )
      {
        v82 = v75;
      }
      else
      {
        v80 = operator new[](v77);
        if ( !v80 )
        {
          LODWORD(cchName) = 14;
          throw (ulong *)cchNamea;
        }
        v52 = a2;
        v81 = *(void **)(a2 + 8);
        if ( v81 )
        {
          operator delete(v81, v79);
          v52 = a2;
        }
        *(_QWORD *)(v52 + 8) = v80;
        *v76 = v77;
        v82 = (_DWORD *)(v52 + 16);
      }
      *v75 = 0;
      v75 = v82;
    }
    v28 = (unsigned int)*v75;
    *(_WORD *)(v28 + *(_QWORD *)(v52 + 8)) = 0;
    *v75 += 2;
  }
  else
  {
    if ( *(_DWORD *)(a2 + 20) < 4u )
    {
      v88 = operator new[](4u);
      if ( !v88 )
      {
        LODWORD(cchName) = 14;
        throw (ulong *)cchNamea;
      }
      v89 = *(void **)(a2 + 8);
      if ( v89 )
        operator delete(v89, v28);
      *(_QWORD *)(a2 + 8) = v88;
      *(_DWORD *)(a2 + 20) = 4;
    }
    v75 = (_DWORD *)(a2 + 16);
    **(_DWORD **)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = 4;
  }
  if ( v27 )
    operator delete(v27, v28);
  v83 = *v75 > 4u;
  if ( Src )
    operator delete(Src, v28);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v120 = 1010;
  LODWORD(Size) = 0;
  v117 = &CBuffer::`vftable';
  if ( lpName )
    operator delete(lpName, v28);
  return v83;
}

```

## disassembly

```asm
0x18000bd60  mov     [rsp-8+cchName], r9
0x18000bd65  mov     [rsp-8+arg_8], rdx
0x18000bd6a  mov     [rsp-8+arg_0], ecx
0x18000bd6e  push    rbp
0x18000bd6f  push    rbx
0x18000bd70  push    rsi
0x18000bd71  push    rdi
0x18000bd72  push    r12
0x18000bd74  push    r13
0x18000bd76  push    r14
0x18000bd78  push    r15
0x18000bd7a  lea     rbp, [rsp-1Fh]
0x18000bd7f  sub     rsp, 0B8h
0x18000bd86  mov     edx, ecx
0x18000bd88  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18000bd8f  mov     [rbp+57h+var_68], rax
0x18000bd93  xor     r9d, r9d
0x18000bd96  mov     [rbp+57h+lpName], r9
0x18000bd9a  mov     [rbp+57h+Size], r9
0x18000bd9e  mov     ecx, r9d; hKey
0x18000bda1  mov     [rbp+57h+hKey], rcx
0x18000bda5  mov     [rbp+57h+var_50], 3F2h
0x18000bdac  mov     [rbp+57h+var_B0], rax
0x18000bdb0  mov     [rbp+57h+Src], r9
0x18000bdb4  mov     esi, r9d
0x18000bdb7  mov     [rbp+57h+var_A0], r9
0x18000bdbb  mov     r13d, r9d
0x18000bdbe  mov     [rbp+57h+lpSubKey], r8
0x18000bdc2  mov     [rbp+57h+var_88], r9
0x18000bdc6  mov     r15d, r9d
0x18000bdc9  lea     r8, dword_180038360
0x18000bdd0  lea     r12, WideCharStr
0x18000bdd7  cmp     r15d, 2
0x18000bddb  jnb     loc_18000BF19
0x18000bde1  mov     eax, r15d
0x18000bde4  mov     r14, [rbp+rax*8+57h+lpSubKey]
0x18000bde9  mov     [rbp+57h+var_48], r14
0x18000bded  test    r14, r14
0x18000bdf0  jz      loc_18000C34D
0x18000bdf6  mov     ebx, r9d
0x18000bdf9  mov     eax, ebx
0x18000bdfb  add     rax, rax
0x18000bdfe  cmp     [r8+rax*8], edx
0x18000be02  jb      loc_18000C339
0x18000be08  mov     rdi, [r8+rax*8+8]
0x18000be0d  test    rcx, rcx
0x18000be10  jz      short loc_18000BE1F
0x18000be12  call    cs:__imp_RegCloseKey
0x18000be18  xor     r9d, r9d
0x18000be1b  mov     [rbp+57h+hKey], r9
0x18000be1f  mov     [rbp+57h+var_50], 3F2h
0x18000be26  mov     dword ptr [rbp+57h+Size], r9d
0x18000be2a  lea     rax, [rbp+57h+hKey]
0x18000be2e  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18000be33  mov     r9d, 20019h; samDesired
0x18000be39  xor     r8d, r8d; ulOptions
0x18000be3c  mov     rdx, r14; lpSubKey
0x18000be3f  mov     rcx, rdi; hKey
0x18000be42  call    cs:__imp_RegOpenKeyExW
0x18000be48  mov     [rbp+57h+var_50], eax
0x18000be4b  mov     [rbp+57h+var_70], 2
0x18000be52  xor     r9d, r9d
0x18000be55  test    eax, eax
0x18000be57  jnz     loc_18000C32B
0x18000be5d  mov     r13d, r9d
0x18000be60  mov     dword ptr [rbp+57h+pExceptionObject], r13d
0x18000be64  mov     dword ptr [rbp+57h+cchName], r9d
0x18000be68  mov     qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime], r9
0x18000be6c  test    eax, eax
0x18000be6e  jnz     loc_18000C880
0x18000be74  mov     ecx, dword ptr [rbp+57h+Size+4]
0x18000be77  cmp     ecx, 80h
0x18000be7d  jnb     short loc_18000BEB2
0x18000be7f  mov     ecx, 80h; unsigned __int64
0x18000be84  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000be89  mov     rdi, rax
0x18000be8c  test    rax, rax
0x18000be8f  jz      loc_18000C7DC
0x18000be95  mov     rcx, [rbp+57h+lpName]; void *
0x18000be99  test    rcx, rcx
0x18000be9c  jz      short loc_18000BEA3
0x18000be9e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000bea3  mov     [rbp+57h+lpName], rdi
0x18000bea7  mov     ecx, 80h
0x18000beac  mov     dword ptr [rbp+57h+Size+4], ecx
0x18000beaf  xor     r9d, r9d
0x18000beb2  mov     r14, r9
0x18000beb5  mov     edi, r9d
0x18000beb8  mov     dword ptr [rbp+57h+Size], r9d
0x18000bebc  test    edi, edi
0x18000bebe  jnz     loc_18000C31A
0x18000bec4  mov     eax, ecx
0x18000bec6  shr     eax, 1
0x18000bec8  mov     dword ptr [rbp+57h+cchName], eax
0x18000becb  mov     r8, r12
0x18000bece  test    ecx, ecx
0x18000bed0  cmovnz  r8, [rbp+57h+lpName]; lpName
0x18000bed5  lea     rax, [rbp+57h+ftLastWriteTime]
0x18000bed9  mov     [rsp+0F0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000bede  mov     [rsp+0F0h+lpcchClass], r9; lpcchClass
0x18000bee3  mov     [rsp+0F0h+lpClass], r9; lpClass
0x18000bee8  mov     [rsp+0F0h+phkResult], r9; lpReserved
0x18000beed  lea     r9, [rbp+57h+cchName]; lpcchName
0x18000bef1  mov     edx, r13d; dwIndex
0x18000bef4  mov     rcx, [rbp+57h+hKey]; hKey
0x18000bef8  call    cs:__imp_RegEnumKeyExW
0x18000befe  cmp     eax, 103h
0x18000bf03  jnz     loc_18000C355
0x18000bf09  xor     r9d, r9d
0x18000bf0c  mov     r14d, r9d
0x18000bf0f  mov     edi, 1
0x18000bf14  mov     ecx, dword ptr [rbp+57h+Size+4]
0x18000bf17  jmp     short loc_18000BEBC
0x18000bf19  lea     ebx, [rsi+4]
0x18000bf1c  test    esi, esi
0x18000bf1e  jnz     loc_18000C5A3
0x18000bf24  cmp     r13d, ebx
0x18000bf27  jnb     loc_18000C5EC
0x18000bf2d  mov     ecx, ebx; unsigned __int64
0x18000bf2f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000bf34  mov     rdi, rax
0x18000bf37  test    rax, rax
0x18000bf3a  jz      loc_18000C8AC
0x18000bf40  mov     r14, [rbp+57h+Src]
0x18000bf44  test    r14, r14
0x18000bf47  jz      short loc_18000BF51
0x18000bf49  mov     rcx, r14; void *
0x18000bf4c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000bf51  mov     r14, rdi
0x18000bf54  mov     [rbp+57h+Src], rdi
0x18000bf58  mov     r13d, ebx
0x18000bf5b  mov     dword ptr [rbp+57h+var_A0+4], ebx
0x18000bf5e  xor     r9d, r9d
0x18000bf61  mov     esi, r9d
0x18000bf64  mov     eax, esi
0x18000bf66  mov     [rax+r14], r9d
0x18000bf6a  add     esi, 4
0x18000bf6d  mov     dword ptr [rbp+57h+var_A0], esi
0x18000bf70  test    r13d, r13d
0x18000bf73  cmovnz  r12, r14
0x18000bf77  lea     rax, ??_7?$CDynamicArray@$$CBG@@6B@; const CDynamicArray<ushort const>::`vftable'
0x18000bf7e  mov     [rbp+57h+lpSubKey], rax
0x18000bf82  mov     r14d, r9d
0x18000bf85  mov     dword ptr [rbp+57h+var_88+4], r9d
0x18000bf89  mov     ebx, r9d
0x18000bf8c  mov     dword ptr [rbp+57h+var_88], ebx
0x18000bf8f  mov     rsi, r9
0x18000bf92  mov     [rbp+57h+var_80], r9
0x18000bf96  mov     rcx, r12; unsigned __int16 *
0x18000bf99  call    ?FirstString@@YAPEBGPEBG@Z; FirstString(ushort const *)
0x18000bf9e  mov     r15, rax
0x18000bfa1  mov     r12d, 4
0x18000bfa7  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000bfae  test    rax, rax
0x18000bfb1  jz      short loc_18000C030
0x18000bfb3  mov     edi, r14d
0x18000bfb6  cmp     r14d, ebx
0x18000bfb9  jb      short loc_18000C010
0x18000bfbb  test    ebx, ebx
0x18000bfbd  cmovz   ebx, r12d
0x18000bfc1  cmp     edi, ebx
0x18000bfc3  jge     loc_18000C7B0
0x18000bfc9  movsxd  rcx, ebx
0x18000bfcc  mov     eax, 8
0x18000bfd1  mul     rcx
0x18000bfd4  cmovb   rax, r8
0x18000bfd8  mov     rcx, rax; unsigned __int64
0x18000bfdb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000bfe0  mov     r12, rax
0x18000bfe3  test    rax, rax
0x18000bfe6  jz      loc_18000C8F9
0x18000bfec  xor     eax, eax
0x18000bfee  test    r14d, r14d
0x18000bff1  jnz     loc_18000C8C4
0x18000bff7  test    rsi, rsi
0x18000bffa  jnz     loc_18000C8E0
0x18000c000  mov     rsi, r12
0x18000c003  mov     [rbp+57h+var_80], r12
0x18000c007  mov     dword ptr [rbp+57h+var_88], ebx
0x18000c00a  mov     r12d, 4
0x18000c010  lea     r14d, [rdi+1]
0x18000c014  mov     dword ptr [rbp+57h+var_88+4], r14d
0x18000c018  mov     [rsi+rdi*8], r15
0x18000c01c  mov     rcx, r15; unsigned __int16 *
0x18000c01f  call    ?NextString@@YAPEBGPEBG@Z; NextString(ushort const *)
0x18000c024  mov     r15, rax
0x18000c027  test    rax, rax
0x18000c02a  jnz     loc_18000C8ED
0x18000c030  mov     r13d, r14d
0x18000c033  mov     dword ptr [rbp+57h+cchName], r14d
0x18000c037  test    r14d, r14d
0x18000c03a  jz      loc_18000C559
0x18000c040  xor     r15d, r15d
0x18000c043  test    r14d, r14d
0x18000c046  jz      loc_18000C1AB
0x18000c04c  lea     edi, [r13-1]
0x18000c050  cmp     r15d, edi
0x18000c053  jnb     loc_18000C19F
0x18000c059  cmp     r14d, edi
0x18000c05c  jbe     loc_18000C929
0x18000c062  movsxd  rax, edi
0x18000c065  mov     rdx, [rsi+rax*8]; lpString2
0x18000c069  lea     r12d, [rdi-1]
0x18000c06d  movsxd  r13, r12d
0x18000c070  cmp     r14d, r12d
0x18000c073  jbe     loc_18000C930
0x18000c079  mov     rcx, [rsi+r13*8]; lpString1
0x18000c07d  call    cs:__imp_lstrcmpiW
0x18000c083  test    eax, eax
0x18000c085  jle     loc_18000C619
0x18000c08b  cmp     r14d, r12d
0x18000c08e  jbe     loc_18000C937
0x18000c094  mov     rax, [rsi+r13*8]
0x18000c098  mov     qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime], rax
0x18000c09c  cmp     r14d, edi
0x18000c09f  jbe     loc_18000C944
0x18000c0a5  movsxd  rax, edi
0x18000c0a8  mov     rax, [rsi+rax*8]
0x18000c0ac  mov     [rbp+57h+pExceptionObject], rax
0x18000c0b0  cmp     r12d, ebx
0x18000c0b3  jb      short loc_18000C110
0x18000c0b5  test    ebx, ebx
0x18000c0b7  mov     eax, 4
0x18000c0bc  cmovz   ebx, eax
0x18000c0bf  cmp     r12d, ebx
0x18000c0c2  jge     loc_18000C7C0
0x18000c0c8  movsxd  rcx, ebx
0x18000c0cb  mov     eax, 8
0x18000c0d0  mul     rcx
0x18000c0d3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c0da  cmovb   rax, rcx
0x18000c0de  mov     rcx, rax; unsigned __int64
0x18000c0e1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000c0e6  mov     r13, rax
0x18000c0e9  test    rax, rax
0x18000c0ec  jz      loc_18000CA23
0x18000c0f2  xor     eax, eax
0x18000c0f4  test    r14d, r14d
0x18000c0f7  jnz     loc_18000C951
0x18000c0fd  test    rsi, rsi
0x18000c100  jnz     loc_18000C96D
0x18000c106  mov     rsi, r13
0x18000c109  mov     [rbp+57h+var_80], r13
0x18000c10d  mov     dword ptr [rbp+57h+var_88], ebx
0x18000c110  cmp     r12d, r14d
0x18000c113  jnb     loc_18000C5F5
0x18000c119  mov     rcx, [rbp+57h+pExceptionObject]
0x18000c11d  mov     [rsi+r12*8], rcx
0x18000c121  cmp     edi, ebx
0x18000c123  jb      short loc_18000C17F
0x18000c125  test    ebx, ebx
0x18000c127  mov     eax, 4
0x18000c12c  cmovz   ebx, eax
0x18000c12f  cmp     edi, ebx
0x18000c131  jge     loc_18000C7D0
0x18000c137  movsxd  rcx, ebx
0x18000c13a  mov     eax, 8
0x18000c13f  mul     rcx
0x18000c142  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c149  cmovb   rax, rcx
0x18000c14d  mov     rcx, rax; unsigned __int64
0x18000c150  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000c155  mov     r12, rax
0x18000c158  test    rax, rax
0x18000c15b  jz      loc_18000CA3B
0x18000c161  xor     eax, eax
0x18000c163  test    r14d, r14d
0x18000c166  jnz     loc_18000C997
0x18000c16c  test    rsi, rsi
0x18000c16f  jnz     loc_18000C9B3
0x18000c175  mov     rsi, r12
0x18000c178  mov     [rbp+57h+var_80], r12
0x18000c17c  mov     dword ptr [rbp+57h+var_88], ebx
0x18000c17f  cmp     edi, r14d
0x18000c182  jnb     loc_18000C606
0x18000c188  mov     rcx, qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime]
0x18000c18c  mov     [rsi+rdi*8], rcx
0x18000c190  mov     r13d, dword ptr [rbp+57h+cchName]
0x18000c194  dec     edi
0x18000c196  cmp     r15d, edi
0x18000c199  jb      loc_18000C059
0x18000c19f  inc     r15d
0x18000c1a2  cmp     r15d, r13d
0x18000c1a5  jb      loc_18000C04C
0x18000c1ab  xor     r8d, r8d
0x18000c1ae  xor     edx, edx
0x18000c1b0  test    r13d, r13d
0x18000c1b3  jz      short loc_18000C1E7
0x18000c1b5  cmp     r14d, edx
0x18000c1b8  jbe     loc_18000CA53
0x18000c1be  movsxd  rax, edx
0x18000c1c1  mov     rcx, [rsi+rax*8]
0x18000c1c5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000c1cc  nop     dword ptr [rax+00h]
0x18000c1d0  inc     rax
0x18000c1d3  cmp     word ptr [rcx+rax*2], 0
0x18000c1d8  jnz     short loc_18000C1D0
0x18000c1da  inc     r8d
0x18000c1dd  add     r8d, eax
0x18000c1e0  inc     edx
  ... truncated ...
```
