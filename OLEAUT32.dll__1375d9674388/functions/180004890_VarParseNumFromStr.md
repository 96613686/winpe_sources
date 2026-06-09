# VarParseNumFromStr

- ea: `0x180004890`
- end: `0x18000578a`
- name: `VarParseNumFromStr`
- size: `3834`
- prototype: `HRESULT __stdcall(LPCOLESTR strIn, LCID lcid, ULONG dwFlags, NUMPARSE *pnumprs, BYTE *rgbDig)`
- caller_count: `11`
- callee_count: `13`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180002c80`
- `0x180002e40`
- `0x1800042d0`
- `0x180004690`
- `0x180004730`
- `0x1800070b0`
- `0x1800078c0`
- `0x18002a10c`
- `0x18003f150`
- `0x1800408e0`
- `0x180048dd0`

## callees

- `0x180002bbc`
- `0x1800039b8`
- `0x1800045f8`
- `0x18000463c`
- `0x180004890`
- `0x180005790`
- `0x180005988`
- `0x180005c30`
- `0x18000705c`
- `0x180048bf8`
- `0x18004a8f4`
- `0x18004d924`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180004ad4`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180004bdd`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180004f97`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180005023`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180005535`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180005561`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180004ad4`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180004bdd`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180004f97`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180005023`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180005535`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180005561`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800049f6`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180004a34`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180004a89`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800049f6`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180004a34`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180004a89`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180004c7f`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180004cbe`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180004d22`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180004ff4`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180004c7f`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180004cbe`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180004d22`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180004ff4`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180004e60`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180004ea0`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180004fc3`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180005228`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180004e60`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180004ea0`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180004fc3`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180005228`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180004982`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800049a5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180004b2d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180004fe3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800053c3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180004982`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800049a5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180004b2d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180004fe3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800053c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a04`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180004f5e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005463`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180004f5e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005463`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x180004b75`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x180004b75`

## pseudocode

```c
HRESULT __stdcall VarParseNumFromStr(LPCOLESTR strIn, LCID lcid, ULONG dwFlags, NUMPARSE *pnumprs, BYTE *rgbDig)
{
  const WCHAR *v5; // r12
  NUMPARSE *v6; // rax
  ULONG v7; // ebx
  LCID v8; // edi
  ULONG dwInFlags; // r13d
  __int64 cDig; // rsi
  LCID UserDefaultLCID; // ecx
  __int64 v12; // rdx
  __int16 v13; // cx
  const WCHAR *v14; // rbx
  WCHAR v15; // ax
  __int64 v16; // rdi
  unsigned __int64 v18; // rbx
  _QWORD *Value; // rax
  WCHAR *lpDestStr; // r15
  HRESULT inited; // ecx
  unsigned __int64 v22; // rbx
  BYTE *v24; // r15
  unsigned __int16 v25; // si
  unsigned __int16 *v26; // r12
  __int64 v27; // rdx
  char *v28; // r14
  struct CNumInfo *v29; // r13
  unsigned int v30; // r12d
  signed int v31; // ebx
  unsigned __int64 v32; // rdx
  LPVOID v33; // r15
  char **v34; // rdi
  int v35; // ebx
  HRESULT v36; // ebx
  int v37; // r15d
  int v38; // edi
  int v39; // r12d
  LCID v40; // eax
  LCID SystemDefaultLCID; // eax
  unsigned __int16 *v42; // rcx
  unsigned __int16 *v43; // rcx
  unsigned __int64 v44; // r14
  int v45; // eax
  LCID v46; // eax
  __int64 v47; // rdx
  int v48; // r8d
  __int64 v49; // r9
  unsigned __int16 *v50; // rdx
  unsigned __int64 v51; // rax
  CNumInfo *v52; // rcx
  __int16 v53; // di
  int v54; // r14d
  unsigned __int16 *v55; // r12
  BYTE *v56; // rdi
  BYTE *v57; // r13
  int v58; // edi
  unsigned __int64 v59; // rcx
  unsigned __int16 *v60; // r14
  unsigned __int16 v61; // di
  unsigned __int16 *v62; // rsi
  int j; // edi
  char v64; // si
  int v65; // eax
  __int64 v66; // r9
  unsigned __int16 *v67; // rdi
  int v68; // edi
  unsigned __int16 i; // r14
  int v70; // eax
  __int64 v71; // rdx
  int v72; // r14d
  __int64 v73; // rdx
  ULONG v74; // [rsp+38h] [rbp-41h]
  __int128 v75; // [rsp+40h] [rbp-39h]
  __int64 v76; // [rsp+50h] [rbp-29h]
  BYTE *v77; // [rsp+58h] [rbp-21h]
  LPWSTR v78; // [rsp+60h] [rbp-19h] BYREF
  char *v79; // [rsp+68h] [rbp-11h] BYREF
  struct CNumInfo *v80; // [rsp+70h] [rbp-9h] BYREF
  BYTE *v81; // [rsp+78h] [rbp-1h]
  unsigned __int16 *v82; // [rsp+80h] [rbp+7h]
  unsigned __int16 *v83; // [rsp+D8h] [rbp+5Fh]
  unsigned int v86; // [rsp+E8h] [rbp+6Fh]

  v5 = strIn;
  v77 = rgbDig;
  v78 = 0;
  v6 = pnumprs;
  v7 = dwFlags;
  v8 = lcid;
  if ( !rgbDig || !pnumprs )
    return -2147024809;
  dwInFlags = pnumprs->dwInFlags;
  v74 = dwInFlags;
  DWORD1(v75) = dwInFlags;
  LODWORD(v75) = 0;
  *((_QWORD *)&v75 + 1) = 0;
  v76 = 0;
  if ( !strIn )
  {
    v36 = -2147352571;
    goto LABEL_61;
  }
  cDig = pnumprs->cDig;
  if ( (lcid & 0xFFFFFBFF) != 0 )
    UserDefaultLCID = lcid;
  else
    UserDefaultLCID = GetUserDefaultLCID();
  if ( UserDefaultLCID == 2048 )
    LOWORD(UserDefaultLCID) = GetSystemDefaultLCID();
  v12 = 256;
  v13 = UserDefaultLCID & 0x3FF;
  if ( (unsigned __int16)(v13 - 17) > 1u && v13 != 4 )
    goto LABEL_27;
  v14 = v5;
  do
  {
    v15 = *v14;
    if ( !*v14 )
      goto LABEL_26;
    ++v14;
  }
  while ( v15 < 0x100u );
  v16 = -1;
  while ( v14[++v16] != 0 )
    ;
  if ( !TlsGetValue(g_itlsAppData) )
  {
    inited = InitAppData();
    if ( inited < 0 )
      return inited;
    TlsGetValue(g_itlsAppData);
  }
  v18 = (unsigned __int64)v14 + 2 * v16 + 2 - (_QWORD)v5;
  Value = TlsGetValue(g_itlsAppData);
  lpDestStr = (WCHAR *)(*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(*(_QWORD *)*Value + 24LL))(*Value, v18);
  v78 = lpDestStr;
  inited = -2147024882;
  if ( !lpDestStr )
    return inited;
  v8 = lcid;
  if ( !LCMapStringW(lcid, 0x400000u, v5, -1, lpDestStr, v18 >> 1) )
  {
    if ( GetLastError() != 122 )
      goto LABEL_21;
    v22 = 2LL * LCMapStringW(lcid, 0x400000u, v5, -1, 0, 0);
    if ( !v22 )
      goto LABEL_21;
    DispFree(lpDestStr);
    v78 = 0;
    inited = DispAlloc(v22, &v78);
    if ( inited > -1 )
    {
      lpDestStr = v78;
      if ( !LCMapStringW(lcid, 0x400000u, v5, -1, v78, v22 >> 1) )
      {
LABEL_21:
        DispFree(lpDestStr);
        return -2147352571;
      }
      goto LABEL_24;
    }
    return inited;
  }
LABEL_24:
  if ( lpDestStr )
    v5 = lpDestStr;
LABEL_26:
  v7 = dwFlags;
LABEL_27:
  v24 = &rgbDig[cDig];
  v25 = *v5;
  v26 = (unsigned __int16 *)(v5 + 1);
  v81 = v24;
  v83 = v26;
  v82 = v26;
  if ( (unsigned int)_o_iswspace(v25, v12) && (dwInFlags & 1) != 0 )
  {
    DWORD2(v75) = 1;
    do
      v25 = *v26++;
    while ( (unsigned int)_o_iswspace(v25, v27) );
    v83 = v26;
  }
  if ( v25 == 38 && (dwInFlags & 0x40) != 0 )
  {
    v25 = *v26;
    v36 = 0;
    v55 = v26 + 1;
    if ( ((v25 - 72) & 0xFFDF) != 0 )
    {
      LODWORD(v76) = 3;
      v68 = 7;
      if ( v25 != 111 && v25 != 79 )
      {
LABEL_218:
        for ( i = v25; v25 == 48; ++v55 )
          v25 = *v55;
        while ( 1 )
        {
          v70 = GETOADIGIT(lcid, v25);
          if ( v70 < 0 )
          {
            if ( (unsigned __int16)(v25 - 97) > 5u )
            {
              if ( (unsigned __int16)(v25 - 65) > 5u )
                goto LABEL_225;
              v70 = v25 - 55;
            }
            else
            {
              v70 = v25 - 87;
            }
          }
          if ( v70 > v68 )
            goto LABEL_225;
          if ( v77 >= v24 )
            break;
          *v77 = v70;
          v25 = *v55++;
          ++v77;
        }
        v36 = -2147352566;
LABEL_225:
        LODWORD(v56) = (_DWORD)rgbDig;
        LODWORD(v57) = (_DWORD)v77;
        if ( v77 == rgbDig )
        {
          if ( i != 48 )
            goto LABEL_57;
          *v77 = 0;
          LODWORD(v57) = (_DWORD)v77 + 1;
        }
        v72 = DWORD2(v75) | 0x40;
        DWORD2(v75) |= 0x40u;
        if ( (unsigned int)_o_iswspace(v25, v71) && (v74 & 2) != 0 )
        {
          DWORD2(v75) = v72 | 2;
          do
            v25 = *v55++;
          while ( (unsigned int)_o_iswspace(v25, v73) );
        }
        goto LABEL_147;
      }
    }
    else
    {
      LODWORD(v76) = 4;
      v68 = 15;
    }
    v25 = *v55++;
    goto LABEL_218;
  }
  v28 = 0;
  v29 = 0;
  v30 = v8;
  v79 = 0;
  if ( g_bPerUserNlsCache )
  {
    if ( v7 == 0x80000000 && v8 == 1033 )
      goto LABEL_32;
    GetUserInfo(&v79);
    v28 = v79;
  }
  if ( v8 == 1024 )
  {
    SystemDefaultLCID = GetUserDefaultLCID();
  }
  else
  {
    if ( v8 != 2048 )
      goto LABEL_32;
    SystemDefaultLCID = GetSystemDefaultLCID();
  }
  v30 = SystemDefaultLCID;
LABEL_32:
  v31 = g_dwProcessNlsFlags | v7;
  v86 = v31;
  v33 = TlsGetValue(g_itlsAppData);
  if ( !v33 )
  {
    v36 = InitAppData();
    if ( v36 < 0 )
      goto LABEL_100;
    v31 = v86;
    v33 = TlsGetValue(g_itlsAppData);
  }
  v34 = (char **)*((_QWORD *)v33 + 51);
  v80 = (struct CNumInfo *)v34;
  if ( !v34
    || *((_DWORD *)v34 + 4) != v30
    || *((_DWORD *)v34 + 5) != v31
    || v28 && !(unsigned int)IsSameUser(v28, v34[1])
    || v31 >= 0 && (v35 = *(_DWORD *)v34, v35 != (unsigned int)NlsGetCacheUpdateCount()) )
  {
    v36 = CNumInfo::Create(v30, v86, &v80, &v79);
    if ( v36 >= 0 )
    {
      v52 = (CNumInfo *)*((_QWORD *)v33 + 51);
      if ( v52 )
        CNumInfo::Release(v52);
      v29 = v80;
      *((_QWORD *)v33 + 51) = v80;
    }
    v28 = v79;
LABEL_100:
    if ( v28 )
      operator delete(v28, v32);
    if ( v36 < 0 )
      goto LABEL_58;
    goto LABEL_42;
  }
  if ( v28 )
    operator delete(v28, v32);
  v29 = (struct CNumInfo *)v34;
  v36 = 0;
LABEL_42:
  v37 = 0;
  v38 = 0;
  v39 = 1;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          if ( (unsigned __int16)(v25 - 48) <= 9u )
            goto LABEL_77;
          if ( (lcid & 0xFFFFFBFF) != 0 )
            v40 = lcid;
          else
            v40 = GetUserDefaultLCID();
          if ( v40 == 2048 )
            LOWORD(v40) = GetSystemDefaultLCID();
          if ( (v40 & 0x3FF) == 0x1E && (unsigned __int16)(v25 - 3664) <= 9u )
            goto LABEL_77;
          if ( (unsigned int)_o_iswspace(v25, v32) )
          {
            if ( (v74 & 1) == 0 )
              goto LABEL_57;
            DWORD2(v75) |= 1u;
            goto LABEL_65;
          }
          if ( v25 != 43 )
            break;
          if ( (v74 & 4) == 0 || (BYTE8(v75) & 0xBC) != 0 )
            goto LABEL_57;
          DWORD2(v75) |= 4u;
          v25 = *v83++;
        }
        if ( v25 != 45 )
          break;
        if ( (v74 & 0x10) == 0 || (BYTE8(v75) & 0xBC) != 0 )
          goto LABEL_57;
        DWORD2(v75) |= 0x10010u;
        v25 = *v83++;
      }
      if ( v25 != 40 )
        break;
      if ( (v74 & 0x80u) == 0 || (BYTE8(v75) & 0xBC) != 0 )
        goto LABEL_57;
      v37 = 1;
      DWORD2(v75) |= 0x10080u;
      v25 = *v83++;
    }
    if ( v25 == *((_WORD *)v29 + 26) )
      break;
    v32 = v74;
    if ( v25 == *((_WORD *)v29 + 31) )
    {
      if ( (v74 & 0x400) == 0 )
        goto LABEL_57;
      if ( v25 == *((_WORD *)v29 + 27) )
        goto LABEL_56;
      if ( v25 != *((_WORD *)v29 + 28) )
      {
        if ( (v74 & 0x100) != 0 )
        {
          v25 = *v83;
          if ( (unsigned __int16)(*v83 - 48) <= 9u )
          {
            v43 = v83 + 1;
            DWORD2(v75) |= 0x500u;
            goto LABEL_239;
          }
        }
LABEL_57:
        v36 = -2147352571;
        goto LABEL_58;
      }
    }
    if ( (v74 & 0x400) == 0 )
      goto LABEL_57;
LABEL_56:
    if ( (WORD4(v75) & 0x400) != 0 )
      goto LABEL_57;
    if ( *((_DWORD *)v29 + 7) )
    {
      if ( v25 != *((_WORD *)v29 + 16) )
        goto LABEL_57;
      DWORD2(v75) |= 0x400u;
      v25 = *v83++;
    }
    else
    {
      v49 = *((int *)v29 + 6);
      v50 = v83 - 1;
      v51 = (unsigned __int64)&v83[v49 - 1];
      while ( 1 )
      {
        v83 = v50;
        if ( (unsigned __int64)v50 >= v51 )
          break;
        if ( !*v50 )
          goto LABEL_57;
        ++v50;
      }
      if ( CompareStringW(lcid, 0x20001u, &v50[-v49], v49, (PCNZWCH)v29 + 16, v49) != 2 )
        goto LABEL_57;
      DWORD2(v75) |= 0x400u;
LABEL_65:
      v25 = *v83++;
    }
  }
  if ( (v74 & 0x100) == 0 )
    goto LABEL_57;
  v42 = v83;
  v25 = *v83;
  if ( (unsigned __int16)(*v83 - 48) > 9u )
  {
    if ( !(unsigned int)IsThai(lcid) || (unsigned __int16)(v25 - 3664) > 9u )
      goto LABEL_57;
    v42 = v83;
  }
  v43 = v42 + 1;
  DWORD2(v75) |= 0x100u;
LABEL_239:
  v83 = v43;
  v38 = -1;
LABEL_77:
  v44 = (unsigned __int64)v81;
  while ( 2 )
  {
    while ( 2 )
    {
      while ( 2 )
      {
        if ( (unsigned __int16)(v25 - 48) <= 9u )
        {
          v45 = v25 - 48;
          goto LABEL_80;
        }
        if ( (unsigned int)IsThai(lcid) && (unsigned __int16)(v25 - 3664) <= 9u )
        {
          v45 = v25 - 3664;
LABEL_80:
          if ( !v45 )
          {
            HIDWORD(v76) += v38;
LABEL_155:
            v25 = *v83++;
            continue;
          }
        }
        break;
      }
      if ( v25 == *((_WORD *)v29 + 27) || v25 == *((_WORD *)v29 + 28) )
      {
        if ( !v25 || (v74 & 0x200) == 0 )
        {
LABEL_153:
          v55 = v83;
          goto LABEL_139;
        }
        DWORD2(v75) |= 0x200u;
        goto LABEL_155;
      }
      if ( v25 == *((_WORD *)v29 + 32) && v25 != *((_WORD *)v29 + 26) && (v74 & 0x400) != 0 )
      {
        if ( !v25 || (v74 & 0x200) == 0 )
          goto LABEL_153;
        DWORD2(v75) |= 0x600u;
        v25 = *v83++;
        continue;
      }
      break;
    }
    while ( 1 )
    {
      while ( 1 )
      {
LABEL_84:
        while ( 1 )
        {
          if ( (unsigned __int16)(v25 - 48) > 9u )
          {
            v46 = lcid;
            if ( (lcid & 0xFFFFFBFF) == 0 )
              v46 = GetUserDefaultLCID();
            if ( v46 == 2048 )
              LOWORD(v46) = GetSystemDefaultLCID();
            if ( (v46 & 0x3FF) != 0x1E || (unsigned __int16)(v25 - 3664) > 9u )
              break;
          }
          if ( (unsigned __int64)v77 >= v44 )
          {
            if ( v25 != 48 )
              DWORD2(v75) |= 0x20000u;
            HIDWORD(v76) += v38 + 1;
          }
          else
          {
            if ( (unsigned __int16)(v25 - 48) > 9u )
            {
              if ( (unsigned int)IsThai(lcid) && (unsigned __int16)(v25 - 3664) <= 9u )
                v64 = v25 - 80;
              else
                v64 = -1;
            }
            else
            {
              v64 = v25 - 48;
            }
            *v77 = v64;
            HIDWORD(v76) += v38;
            ++v77;
          }
          v25 = *v83++;
        }
        if ( v25 != *((_WORD *)v29 + 27) && v25 != *((_WORD *)v29 + 28) )
          break;
        if ( !v25 || (v74 & 0x200) == 0 )
          goto LABEL_153;
        DWORD2(v75) |= 0x200u;
        v25 = *v83++;
      }
      v47 = v74;
      if ( v25 != *((_WORD *)v29 + 32) )
        break;
      if ( v25 == *((_WORD *)v29 + 26) )
        goto LABEL_190;
      if ( (v74 & 0x400) == 0 )
        break;
      if ( !v25 || (v74 & 0x200) == 0 )
        goto LABEL_153;
      DWORD2(v75) |= 0x600u;
      v25 = *v83++;
    }
    if ( v25 == *((_WORD *)v29 + 26) )
    {
LABEL_190:
      if ( (v74 & 0x100) == 0 || (WORD4(v75) & 0x100) != 0 )
        goto LABEL_153;
      v48 = DWORD2(v75) | 0x100;
      goto LABEL_193;
    }
    if ( v25 == *((_WORD *)v29 + 31) )
    {
      if ( (v74 & 0x500) == 0 || (WORD4(v75) & 0x100) != 0 )
        goto LABEL_153;
      v48 = DWORD2(v75) | 0x500;
LABEL_193:
      v38 = -1;
      DWORD2(v75) = v48;
      v25 = *v83++;
      if ( v77 == rgbDig )
        continue;
      goto LABEL_84;
    }
    break;
  }
  v53 = v74;
  if ( ((v25 - 68) & 0xFFDE) != 0 || (v74 & 0x800) == 0 )
  {
    v54 = DWORD2(v75);
    goto LABEL_132;
  }
  v60 = v83;
  v61 = *v83;
  v62 = ++v83;
  if ( v61 == 45 || (v39 = 0, v61 == 43) )
  {
    v61 = *v62++;
    v83 = v62;
  }
  if ( (unsigned int)ISOADIGIT(lcid, v61) )
  {
    for ( j = GETOADIGIT(lcid, v61); ; j = v65 + 10 * j )
    {
      v25 = *v62;
      ++v83;
      if ( !(unsigned int)ISOADIGIT(lcid, v25) )
        break;
      if ( j >= 107374182 )
      {
        v55 = v60;
        v36 = -2147352566;
        goto LABEL_139;
      }
      v65 = GETOADIGIT(lcid, v25);
      v62 = v83;
    }
    if ( v39 )
      j = -j;
    HIDWORD(v76) += j;
    v53 = v74;
    v54 = DWORD2(v75) | 0x800;
    DWORD2(v75) |= 0x800u;
LABEL_132:
    v55 = v83;
    goto LABEL_133;
  }
  v25 = *(v60 - 1);
  v55 = v60;
  v54 = DWORD2(v75);
  v53 = v74;
LABEL_133:
  while ( 2 )
  {
    while ( 2 )
    {
      if ( !v25 )
        goto LABEL_139;
      if ( (unsigned int)_o_iswspace(v25, v47) )
      {
        if ( (v53 & 2) == 0 )
          goto LABEL_139;
        v54 |= 2u;
LABEL_179:
        v25 = *v55++;
        v53 = v74;
        DWORD2(v75) = v54;
        continue;
      }
      break;
    }
    switch ( v25 )
    {
      case ')':
        if ( !v37 )
          break;
        v25 = *v55;
        v37 = 0;
        v53 = v74;
        ++v55;
        continue;
      case '+':
        if ( (v53 & 8) == 0 || (v54 & 0xBC) != 0 )
          goto LABEL_139;
        v54 |= 8u;
        goto LABEL_179;
      case '-':
        if ( (v53 & 0x20) == 0 || (v54 & 0xBC) != 0 )
          goto LABEL_139;
        v54 |= 0x10020u;
        goto LABEL_179;
    }
    break;
  }
  if ( (v53 & 0x400) == 0 )
    goto LABEL_139;
  if ( *((_DWORD *)v29 + 7) )
  {
    if ( v25 != *((_WORD *)v29 + 16) )
      goto LABEL_139;
LABEL_241:
    v54 |= 0x400u;
    goto LABEL_179;
  }
  v66 = *((int *)v29 + 6);
  --v55;
  v67 = &v55[v66];
  while ( v55 < v67 )
  {
    if ( !*v55 )
      goto LABEL_243;
    ++v55;
  }
  if ( CompareStringW(lcid, 0x20001u, &v55[-v66], v66, (PCNZWCH)v29 + 16, *((_DWORD *)v29 + 6)) == 2 )
    goto LABEL_241;
LABEL_243:
  v55 = &v67[-*((int *)v29 + 6) + 1];
LABEL_139:
  v56 = rgbDig;
  v57 = v77;
  if ( v77 > rgbDig + 1 )
  {
    v58 = HIDWORD(v76);
    do
    {
      v59 = (unsigned __int64)(v57 - 1);
      if ( *(v57 - 1) )
        break;
      ++v58;
      --v57;
      HIDWORD(v76) = v58;
    }
    while ( v59 > (unsigned __int64)(rgbDig + 1) );
    v56 = rgbDig;
  }
  if ( v57 == v56 )
  {
    *v57 = 0;
    LODWORD(v57) = (_DWORD)v57 + 1;
  }
  if ( v37 )
    v36 = -2147352571;
LABEL_147:
  LODWORD(v75) = (_DWORD)v57 - (_DWORD)v56;
  HIDWORD(v75) = v55 - v82;
  if ( v25 && (v74 & 0x1000) != 0 )
    v36 = -2147352571;
LABEL_58:
  if ( v78 )
    DispFree(v78);
  v6 = pnumprs;
LABEL_61:
  *(_OWORD *)&v6->cDig = v75;
  *(_QWORD *)&v6->nBaseShift = v76;
  return v36;
}

```

## disassembly

```asm
0x180004890  mov     r11, rsp
0x180004893  mov     [r11+20h], r9
0x180004897  mov     [r11+18h], r8d
0x18000489b  mov     [rsp-8+Locale], edx
0x18000489f  push    rbp
0x1800048a0  push    rbx
0x1800048a1  push    rdi
0x1800048a2  push    r12
0x1800048a4  push    r14
0x1800048a6  push    r15
0x1800048a8  lea     rbp, [r11-57h]
0x1800048ac  sub     rsp, 98h
0x1800048b3  mov     r14, [rbp+4Fh+rgbDig]
0x1800048b7  mov     r12, rcx
0x1800048ba  xor     ecx, ecx
0x1800048bc  mov     [rbp+4Fh+var_70], r14
0x1800048c0  mov     [rbp+4Fh+var_68], rcx
0x1800048c4  mov     rax, r9
0x1800048c7  mov     qword ptr [rbp+4Fh+var_88+4], rcx
0x1800048cb  mov     ebx, r8d
0x1800048ce  mov     [rbp+4Fh+var_74], ecx
0x1800048d1  mov     edi, edx
0x1800048d3  mov     r15d, ecx
0x1800048d6  test    r14, r14
0x1800048d9  jz      loc_180004CA8
0x1800048df  test    rax, rax
0x1800048e2  jz      loc_180004CA8
0x1800048e8  mov     [r11-40h], r13
0x1800048ec  mov     r13d, [r9+4]
0x1800048f0  mov     [rbp+4Fh+var_90], r13d
0x1800048f4  mov     dword ptr [rbp+4Fh+var_88+4], r13d
0x1800048f8  mov     [r11-38h], rsi
0x1800048fc  mov     dword ptr [rbp+4Fh+var_88], ecx
0x1800048ff  mov     qword ptr [rbp+4Fh+var_88+8], rcx
0x180004903  mov     [rbp-29h], rcx
0x180004907  test    r12, r12
0x18000490a  jz      loc_180004FAA
0x180004910  movsxd  rsi, dword ptr [r9]
0x180004913  test    edx, 0FFFFFBFFh
0x180004919  jz      loc_180004D22
0x18000491f  mov     ecx, edx
0x180004921  cmp     ecx, 800h
0x180004927  jz      loc_180004E60
0x18000492d  mov     eax, 3FFh
0x180004932  mov     edx, 100h
0x180004937  and     cx, ax
0x18000493a  lea     eax, [rcx-11h]
0x18000493d  cmp     ax, 1
0x180004941  ja      loc_180004FB4
0x180004947  mov     rbx, r12
0x18000494a  nop     word ptr [rax+rax+00h]
0x180004950  movzx   eax, word ptr [rbx]
0x180004953  test    ax, ax
0x180004956  jz      loc_180004AB5
0x18000495c  add     rbx, 2
0x180004960  cmp     ax, dx
0x180004963  jb      short loc_180004950
0x180004965  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000496c  nop     dword ptr [rax+00h]
0x180004970  cmp     [rbx+rdi*2+2], r15w
0x180004976  lea     rdi, [rdi+1]
0x18000497a  jnz     short loc_180004970
0x18000497c  mov     ecx, cs:?g_itlsAppData@@3KA; dwTlsIndex
0x180004982  call    cs:__imp_TlsGetValue
0x180004988  test    rax, rax
0x18000498b  jz      loc_1800053AE
0x180004991  mov     ecx, cs:?g_itlsAppData@@3KA; dwTlsIndex
0x180004997  lea     rax, ds:2[rdi*2]
0x18000499f  sub     rax, r12
0x1800049a2  add     rbx, rax
0x1800049a5  call    cs:__imp_TlsGetValue
0x1800049ab  mov     rdx, rbx
0x1800049ae  mov     rcx, [rax]
0x1800049b1  mov     rax, [rcx]
0x1800049b4  mov     rax, [rax+18h]
0x1800049b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049bd  mov     r15, rax
0x1800049c0  mov     [rbp+4Fh+var_68], rax
0x1800049c4  xor     eax, eax
0x1800049c6  mov     ecx, 8007000Eh
0x1800049cb  test    r15, r15
0x1800049ce  cmovnz  ecx, eax
0x1800049d1  jz      loc_180004AA7
0x1800049d7  mov     edi, [rbp+4Fh+Locale]
0x1800049da  mov     r9d, 0FFFFFFFFh; cchSrc
0x1800049e0  shr     rbx, 1
0x1800049e3  mov     r8, r12; lpSrcStr
0x1800049e6  mov     [rsp+28h], ebx; cchDest
0x1800049ea  mov     edx, 400000h; dwMapFlags
0x1800049ef  mov     ecx, edi; Locale
0x1800049f1  mov     [rsp+0C0h+lpDestStr], r15; lpDestStr
0x1800049f6  call    cs:__imp_LCMapStringW
0x1800049fc  test    eax, eax
0x1800049fe  jnz     loc_180004AAE
0x180004a04  call    cs:__imp_GetLastError
0x180004a0a  cmp     eax, 7Ah ; 'z'
0x180004a0d  jnz     loc_180004A93
0x180004a13  mov     dword ptr [rsp+28h], 0; cchDest
0x180004a1b  mov     r9d, 0FFFFFFFFh; cchSrc
0x180004a21  mov     r8, r12; lpSrcStr
0x180004a24  mov     [rsp+0C0h+lpDestStr], 0; lpDestStr
0x180004a2d  mov     edx, 400000h; dwMapFlags
0x180004a32  mov     ecx, edi; Locale
0x180004a34  call    cs:__imp_LCMapStringW
0x180004a3a  movsxd  rbx, eax
0x180004a3d  add     rbx, rbx
0x180004a40  jz      short loc_180004A93
0x180004a42  mov     rcx, r15
0x180004a45  call    DispFree
0x180004a4a  lea     rdx, [rbp+4Fh+var_68]
0x180004a4e  mov     [rbp+4Fh+var_68], 0
0x180004a56  mov     rcx, rbx
0x180004a59  call    DispAlloc
0x180004a5e  mov     ecx, eax
0x180004a60  cmp     eax, 0FFFFFFFFh
0x180004a63  jle     short loc_180004AA0
0x180004a65  mov     r15, [rbp+4Fh+var_68]
0x180004a69  mov     r9d, 0FFFFFFFFh; cchSrc
0x180004a6f  shr     rbx, 1
0x180004a72  mov     r8, r12; lpSrcStr
0x180004a75  mov     [rsp+28h], ebx; cchDest
0x180004a79  mov     edx, 400000h; dwMapFlags
0x180004a7e  mov     ecx, edi; Locale
0x180004a80  mov     [rsp+0C0h+lpDestStr], r15; lpDestStr
0x180004a85  mov     [rbp+4Fh+var_68], r15
0x180004a89  call    cs:__imp_LCMapStringW
0x180004a8f  test    eax, eax
0x180004a91  jnz     short loc_180004AAE
0x180004a93  mov     rcx, r15
0x180004a96  call    DispFree
0x180004a9b  mov     ecx, 80020005h
0x180004aa0  mov     eax, ecx
0x180004aa2  jmp     loc_180004C5E
0x180004aa7  test    ecx, ecx
0x180004aa9  js      short loc_180004AA0
0x180004aab  mov     edi, [rbp+4Fh+Locale]
0x180004aae  test    r15, r15
0x180004ab1  cmovnz  r12, r15
0x180004ab5  mov     ebx, [rbp+4Fh+arg_10]
0x180004ab8  lea     r15, [r14+rsi]
0x180004abc  movzx   esi, word ptr [r12]
0x180004ac1  add     r12, 2
0x180004ac5  mov     [rbp+4Fh+var_50], r15
0x180004ac9  movzx   ecx, si
0x180004acc  mov     [rbp+4Fh+arg_0], r12
0x180004ad0  mov     [rbp+4Fh+var_48], r12
0x180004ad4  call    cs:__imp__o_iswspace
0x180004ada  test    eax, eax
0x180004adc  jnz     loc_180004F79
0x180004ae2  cmp     si, 26h ; '&'
0x180004ae6  jz      loc_180005477
0x180004aec  xor     r14d, r14d
0x180004aef  xor     r13d, r13d
0x180004af2  cmp     cs:?g_bPerUserNlsCache@@3KA, r13d; ulong g_bPerUserNlsCache
0x180004af9  mov     r12d, edi
0x180004afc  mov     [rbp+4Fh+var_60], r14
0x180004b00  jnz     loc_18000567D
0x180004b06  cmp     edi, 400h
0x180004b0c  jz      loc_180004CBE
0x180004b12  cmp     edi, 800h
0x180004b18  jz      loc_180004FC3
0x180004b1e  or      ebx, cs:?g_dwProcessNlsFlags@@3KA; ulong g_dwProcessNlsFlags
0x180004b24  mov     ecx, cs:?g_itlsAppData@@3KA; dwTlsIndex
0x180004b2a  mov     [rbp+4Fh+arg_10], ebx
0x180004b2d  call    cs:__imp_TlsGetValue
0x180004b33  mov     r15, rax
0x180004b36  test    rax, rax
0x180004b39  jz      loc_180004FCE
0x180004b3f  mov     rdi, [r15+198h]
0x180004b46  mov     [rbp+4Fh+var_58], rdi
0x180004b4a  test    rdi, rdi
0x180004b4d  jz      loc_180004E29
0x180004b53  cmp     [rdi+10h], r12d
0x180004b57  jnz     loc_180004E29
0x180004b5d  cmp     [rdi+14h], ebx
0x180004b60  jnz     loc_180004E29
0x180004b66  test    r14, r14
0x180004b69  jnz     loc_180005664
0x180004b6f  test    ebx, ebx
0x180004b71  js      short loc_180004B83
0x180004b73  mov     ebx, [rdi]
0x180004b75  call    cs:__imp_NlsGetCacheUpdateCount
0x180004b7b  cmp     ebx, eax
0x180004b7d  jnz     loc_180004E29
0x180004b83  test    r14, r14
0x180004b86  jnz     loc_180005774
0x180004b8c  mov     r13, rdi
0x180004b8f  xor     ebx, ebx
0x180004b91  mov     r14d, [rbp+4Fh+Locale]
0x180004b95  xor     r15d, r15d
0x180004b98  xor     edi, edi
0x180004b9a  mov     r12d, 1
0x180004ba0  lea     eax, [rsi-30h]
0x180004ba3  cmp     ax, 9
0x180004ba7  jbe     loc_180004D44
0x180004bad  test    r14d, 0FFFFFBFFh
0x180004bb4  jz      loc_180004C7F
0x180004bba  mov     eax, r14d
0x180004bbd  cmp     eax, 800h
0x180004bc2  jz      loc_180004EA0
0x180004bc8  mov     ecx, 3FFh
0x180004bcd  and     ax, cx
0x180004bd0  cmp     ax, 1Eh
0x180004bd4  jz      loc_180004D2F
0x180004bda  movzx   ecx, si
0x180004bdd  call    cs:__imp__o_iswspace
0x180004be3  test    eax, eax
0x180004be5  jnz     loc_180004C8A
0x180004beb  cmp     si, 2Bh ; '+'
0x180004bef  jz      loc_1800056B7
0x180004bf5  cmp     si, 2Dh ; '-'
0x180004bf9  jz      loc_180004E6D
0x180004bff  cmp     si, 28h ; '('
0x180004c03  jz      loc_180004EB5
0x180004c09  cmp     si, [r13+34h]
0x180004c0e  jz      loc_180004CCC
0x180004c14  mov     edx, [rbp+4Fh+var_90]
0x180004c17  cmp     si, [r13+3Eh]
0x180004c1c  jz      loc_18000557D
0x180004c22  bt      edx, 0Ah
0x180004c26  jnb     short loc_180004C35
0x180004c28  mov     ecx, dword ptr [rbp+4Fh+var_88+8]
0x180004c2b  bt      ecx, 0Ah
0x180004c2f  jnb     loc_180004EEB
0x180004c35  mov     ebx, 80020005h
0x180004c3a  mov     rcx, [rbp+4Fh+var_68]
0x180004c3e  test    rcx, rcx
0x180004c41  jnz     loc_180004EAB
0x180004c47  mov     rax, [rbp+4Fh+arg_18]
0x180004c4b  movups  xmm0, [rbp+4Fh+var_88]
0x180004c4f  movsd   xmm1, qword ptr [rbp-29h]
0x180004c54  movups  xmmword ptr [rax], xmm0
0x180004c57  movsd   qword ptr [rax+10h], xmm1
0x180004c5c  mov     eax, ebx
0x180004c5e  mov     rsi, [rsp+90h]
0x180004c66  mov     r13, [rsp+0C0h+var_38]
0x180004c6e  add     rsp, 98h
0x180004c75  pop     r15
0x180004c77  pop     r14
0x180004c79  pop     r12
0x180004c7b  pop     rdi
0x180004c7c  pop     rbx
0x180004c7d  pop     rbp
0x180004c7e  retn
0x180004c7f  call    cs:__imp_GetUserDefaultLCID
0x180004c85  jmp     loc_180004BBD
0x180004c8a  test    byte ptr [rbp+4Fh+var_90], r12b
0x180004c8e  jz      short loc_180004C35
0x180004c90  or      dword ptr [rbp+4Fh+var_88+8], r12d
0x180004c94  mov     rax, [rbp+4Fh+arg_0]
0x180004c98  movzx   esi, word ptr [rax]
0x180004c9b  add     rax, 2
0x180004c9f  mov     [rbp+4Fh+arg_0], rax
0x180004ca3  jmp     loc_180004BA0
0x180004ca8  mov     eax, 80070057h
0x180004cad  add     rsp, 98h
0x180004cb4  pop     r15
0x180004cb6  pop     r14
0x180004cb8  pop     r12
0x180004cba  pop     rdi
0x180004cbb  pop     rbx
0x180004cbc  pop     rbp
0x180004cbd  retn
0x180004cbe  call    cs:__imp_GetUserDefaultLCID
0x180004cc4  mov     r12d, eax
0x180004cc7  jmp     loc_180004B1E
0x180004ccc  test    [rbp+4Fh+var_90], 100h
0x180004cd3  jz      loc_180004C35
0x180004cd9  mov     rcx, [rbp+4Fh+arg_0]
0x180004cdd  movzx   esi, word ptr [rcx]
0x180004ce0  lea     eax, [rsi-30h]
0x180004ce3  cmp     ax, 9
0x180004ce7  jbe     short loc_180004D12
0x180004ce9  mov     ecx, r14d
0x180004cec  call    IsThai
0x180004cf1  test    eax, eax
0x180004cf3  jz      loc_180004C35
0x180004cf9  movzx   eax, si
0x180004cfc  mov     ecx, 0E50h
0x180004d01  sub     ax, cx
0x180004d04  cmp     ax, 9
0x180004d08  ja      loc_180004C35
0x180004d0e  mov     rcx, [rbp+4Fh+arg_0]
0x180004d12  add     rcx, 2
0x180004d16  or      dword ptr [rbp+4Fh+var_88+8], 100h
0x180004d1d  jmp     loc_1800055C6
0x180004d22  call    cs:__imp_GetUserDefaultLCID
0x180004d28  mov     ecx, eax
0x180004d2a  jmp     loc_180004921
0x180004d2f  movzx   eax, si
0x180004d32  mov     ecx, 0E50h
0x180004d37  sub     ax, cx
0x180004d3a  cmp     ax, 9
0x180004d3e  ja      loc_180004BDA
0x180004d44  mov     r14, [rbp+4Fh+var_50]
0x180004d48  lea     eax, [rsi-30h]
0x180004d4b  cmp     ax, 9
0x180004d4f  ja      loc_1800052D4
0x180004d55  movzx   eax, si
0x180004d58  add     eax, 0FFFFFFD0h
  ... truncated ...
```
