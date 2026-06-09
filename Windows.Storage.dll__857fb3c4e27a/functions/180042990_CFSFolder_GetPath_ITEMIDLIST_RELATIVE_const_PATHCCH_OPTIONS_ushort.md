# CFSFolder::GetPath(_ITEMIDLIST_RELATIVE const *,PATHCCH_OPTIONS,ushort * *)

- ea: `0x180042990`
- end: `0x1800432ea`
- name: `?GetPath@CFSFolder@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@W4PATHCCH_OPTIONS@@PEAPEAG@Z`
- size: `2394`
- prototype: `int(CFSFolder *__hidden this, const struct _ITEMIDLIST_RELATIVE *, enum PATHCCH_OPTIONS, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path, service_task, installer_update, broker_com_uri`

## callees

- `0x1800412a0`
- `0x180042990`
- `0x1800432f0`
- `0x180043320`
- `0x180091870`
- `0x180148460`
- `0x180333018`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18004312b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800431fa`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18004312b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800431fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042ac9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004323d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042ac9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004323d`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180042b3b`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180042b3b`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x180042bce`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x180042bce`
- `OLEAUT32!__imp_SysAllocString` at `0x18004325b`
- `OLEAUT32!__imp_SysAllocString` at `0x18004325b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180042a2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180042a2f`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180042a58`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180042a58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042ada`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042c42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042c52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042c62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042c88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042dbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042fab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042fbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042fcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800430ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004324e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042ada`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042c42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042c52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042c62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042c88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042dbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042fab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042fbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042fcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800430ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004324e`
- `SHCORE!__imp_ualstrcpynW` at `0x180042e6b`
- `SHCORE!__imp_ualstrcpynW` at `0x18004300c`
- `SHCORE!__imp_ualstrcpynW` at `0x180042e6b`
- `SHCORE!__imp_ualstrcpynW` at `0x18004300c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CFSFolder::GetPath(
        CFSFolder *this,
        const struct _ITEMIDLIST_RELATIVE *a2,
        ULONG a3,
        unsigned __int16 **a4)
{
  void *v6; // r14
  const WCHAR *v7; // rdi
  __int64 v8; // rax
  unsigned __int64 v9; // r15
  const struct _ITEMIDLIST_RELATIVE *i; // rbx
  __int64 v11; // rcx
  void *v12; // rbx
  size_t v13; // rsi
  int v14; // esi
  const struct _ITEMIDLIST_RELATIVE *v16; // rsi
  HRESULT v17; // eax
  unsigned int v18; // edi
  WCHAR *v19; // rdx
  WCHAR *v20; // r8
  HRESULT v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  char IsEnabled; // al
  unsigned __int16 v26; // r8
  unsigned __int16 *v27; // rdx
  __int64 v28; // r9
  unsigned int v29; // ecx
  unsigned __int64 v30; // rcx
  _BYTE *v31; // rcx
  unsigned __int64 v32; // rdx
  int v33; // ecx
  unsigned __int16 *v34; // r9
  _WORD *v35; // rax
  unsigned __int16 *v36; // r8
  WCHAR *v37; // rdx
  WCHAR *v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  const KNOWNFOLDERID *v43; // rcx
  __int64 v44; // rax
  HRESULT v45; // eax
  unsigned int v46; // ebx
  __int64 v47; // rdx
  const ITEMIDLIST *v48; // rcx
  unsigned __int64 v49; // r11
  unsigned __int16 *v50; // r9
  unsigned int v51; // edx
  __int64 v52; // rcx
  const ITEMIDLIST *v53; // rcx
  int lpWideCharStr; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  LPMALLOC ppMalloc; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v59[2]; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v60; // [rsp+70h] [rbp-90h]
  LPVOID v61; // [rsp+78h] [rbp-88h]
  LPVOID v62; // [rsp+90h] [rbp-70h]
  __int64 v63; // [rsp+98h] [rbp-68h]
  __int64 v64; // [rsp+A0h] [rbp-60h]
  __int64 v65; // [rsp+A8h] [rbp-58h]
  __int64 v66; // [rsp+B0h] [rbp-50h]
  __int64 v67; // [rsp+B8h] [rbp-48h]
  WCHAR *v68; // [rsp+C8h] [rbp-38h]
  int v69; // [rsp+E0h] [rbp-20h]
  WCHAR pszMore[278]; // [rsp+E4h] [rbp-1Ch] BYREF
  void **v71; // [rsp+310h] [rbp+210h] BYREF
  LPVOID v72; // [rsp+320h] [rbp+220h]
  LPVOID v73; // [rsp+328h] [rbp+228h]
  LPVOID v74; // [rsp+340h] [rbp+240h]
  __int64 v75; // [rsp+348h] [rbp+248h]
  __int64 v76; // [rsp+350h] [rbp+250h]
  __int64 v77; // [rsp+358h] [rbp+258h]
  __int64 v78; // [rsp+360h] [rbp+260h]
  __int64 v79; // [rsp+368h] [rbp+268h]
  WCHAR *v80; // [rsp+378h] [rbp+278h]
  int v81; // [rsp+390h] [rbp+290h]
  WCHAR WideCharStr[278]; // [rsp+394h] [rbp+294h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+618h] [rbp+518h]

  v6 = 0;
  *a4 = 0;
  pv = 0;
  v7 = (const WCHAR *)*((_QWORD *)this + 17);
  if ( v7 )
    goto LABEL_2;
  pv = 0;
  v43 = (const KNOWNFOLDERID *)((char *)this + 184);
  v44 = *(_QWORD *)&v43->Data1 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *(_QWORD *)&v43->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
    v44 = *(_QWORD *)v43->Data4 - *(_QWORD *)GUID_NULL.Data4;
  if ( v44 )
  {
    v45 = SHGetKnownFolderPath(v43, 0x4000u, 0, (PWSTR *)&pv);
    v46 = v45;
    if ( v45 < 0 )
    {
      v47 = 1163;
LABEL_125:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v47,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
        (const char *)(unsigned int)v45,
        lpWideCharStr);
LABEL_130:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F5,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
        (const char *)v46,
        lpWideCharStr);
      if ( pv )
        CoTaskMemFree(pv);
      return v46;
    }
  }
  else
  {
    v48 = (const ITEMIDLIST *)*((_QWORD *)this + 16);
    if ( v48 )
    {
      v45 = SHGetNameFromIDList(v48, SIGDN_DESKTOPABSOLUTEPARSING, (PWSTR *)&pv);
      v46 = v45;
      if ( v45 < 0 )
      {
        v47 = 1177;
        goto LABEL_125;
      }
    }
    else
    {
      v53 = (const ITEMIDLIST *)*((_QWORD *)this + 15);
      if ( v53 )
      {
        v45 = SHGetNameFromIDList(v53, SIGDN_DESKTOPABSOLUTEPARSING, (PWSTR *)&pv);
        v46 = v45;
        if ( v45 < 0 )
        {
          v47 = 1181;
          goto LABEL_125;
        }
      }
    }
    if ( !pv )
    {
      v46 = -2147024893;
      goto LABEL_130;
    }
    *((_QWORD *)this + 17) = SysAllocString((const OLECHAR *)pv);
  }
  v7 = (const WCHAR *)pv;
LABEL_2:
  v8 = -1;
  do
    ++v8;
  while ( v7[v8] );
  v9 = v8 + 7;
  for ( i = a2; i; i = (const struct _ITEMIDLIST_RELATIVE *)((char *)i + *(unsigned __int16 *)i) )
  {
    v11 = *(unsigned __int16 *)i;
    if ( !(_WORD)v11 )
      break;
    if ( (unsigned int)v11 <= 0xB )
      goto LABEL_69;
    if ( (*((_BYTE *)i + 2) & 0x70) == 0x30 )
    {
      v16 = i;
    }
    else
    {
      if ( *(_DWORD *)((char *)i + 6) != 1179862595 )
        goto LABEL_69;
      v49 = *((unsigned __int16 *)i + 2);
      if ( v49 > v11 - 4 )
        goto LABEL_69;
      v16 = (const struct _ITEMIDLIST_RELATIVE *)((char *)i + 10);
      v50 = (unsigned __int16 *)((char *)i + 10);
      v51 = 2;
      if ( (unsigned int)v49 < 2 )
        goto LABEL_69;
      while ( 1 )
      {
        v52 = *v50;
        if ( (unsigned int)v52 < 2 || (unsigned int)v52 > (unsigned int)v49 - v51 )
          break;
        v51 += v52;
        v50 = (unsigned __int16 *)((char *)v50 + v52);
        if ( v51 > (unsigned int)v49 )
          goto LABEL_69;
      }
      if ( (_WORD)v52
        || v51 > (unsigned int)v49
        || (_WORD)v49 != *(_WORD *)v16 + 6
        || (unsigned __int16)(*(_WORD *)v16 + 6) < *(_WORD *)v16
        || i == (const struct _ITEMIDLIST_RELATIVE *)-10LL )
      {
LABEL_69:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3FF,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
          (const char *)0x80004005LL,
          lpWideCharStr);
        if ( pv )
          CoTaskMemFree(pv);
        return 2147500037LL;
      }
    }
    if ( *(_WORD *)v16 < 0xEu )
      goto LABEL_69;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl'::`2'::impl);
    v26 = *(_WORD *)i;
    if ( !IsEnabled || v26 >= 2u )
    {
      v27 = 0;
      v28 = *(unsigned __int16 *)((char *)i + v26 - 2);
      if ( (_WORD)v28 )
      {
        if ( v28 + 8 < (unsigned __int64)v26 )
        {
          v27 = (unsigned __int16 *)((char *)i + v28);
          v29 = *(unsigned __int16 *)((char *)i + v28);
          if ( v29 < 8 || HIWORD(*((_DWORD *)v27 + 1)) != 0xBEEF || (unsigned int)v28 + v29 > v26 )
            v27 = 0;
        }
      }
      v30 = (unsigned __int64)i + v26;
      if ( v27 )
      {
        while ( *((_DWORD *)v27 + 1) != -1091633148 )
        {
          v34 = 0;
          if ( (unsigned __int64)(v27 + 4) <= v30 )
          {
            v36 = (unsigned __int16 *)((char *)v27 + *v27);
            if ( v36 == (unsigned __int16 *)v30 )
              goto LABEL_78;
            if ( (unsigned __int64)v36 <= v30 )
            {
              if ( (unsigned __int64)(v36 + 4) > v30
                || HIWORD(*((_DWORD *)v36 + 1)) != 0xBEEF
                || (unsigned __int64)v36 + *v36 > v30
                || v36 < v27 + 4 )
              {
                goto LABEL_78;
              }
              v34 = (unsigned __int16 *)((char *)v27 + *v27);
            }
          }
          v27 = v34;
          if ( !v34 )
            goto LABEL_78;
        }
LABEL_61:
        v31 = (char *)v16 + 14;
        if ( v16 == (const struct _ITEMIDLIST_RELATIVE *)-14LL )
          goto LABEL_157;
        v32 = *(unsigned __int16 *)v16 - 14LL;
        if ( v32 > 0x7FFFFFFF )
          goto LABEL_157;
        if ( *(_WORD *)v16 != 14 )
        {
          do
          {
            if ( !*v31 )
              break;
            ++v31;
            --v32;
          }
          while ( v32 );
        }
        goto LABEL_66;
      }
    }
LABEL_78:
    if ( (*((_BYTE *)v16 + 2) & 0x34) != 0x34 )
      goto LABEL_61;
    v35 = (_WORD *)((char *)v16 + 14);
    if ( v16 == (const struct _ITEMIDLIST_RELATIVE *)-14LL
      || (v32 = ((unsigned __int64)*(unsigned __int16 *)v16 - 14) >> 1, v32 > 0x7FFFFFFF) )
    {
LABEL_157:
      v33 = -2147024809;
      goto LABEL_68;
    }
    for ( ; v32; --v32 )
    {
      if ( !*v35 )
        break;
      ++v35;
    }
LABEL_66:
    v33 = -2147024809;
    if ( v32 )
      v33 = 0;
LABEL_68:
    if ( v33 < 0 )
      goto LABEL_69;
    CFileSysItemString::CFileSysItemString((CFileSysItemString *)&v71, (CFSFolder *)((char *)this - 312), i, v16);
    if ( v80 )
    {
LABEL_115:
      v38 = v80;
      goto LABEL_100;
    }
    if ( (v81 & 1) == 0 )
    {
      if ( v79 )
      {
        v37 = (WCHAR *)(v79 + *(unsigned __int16 *)(v79 + 16));
        if ( ((unsigned __int8)v37 & 1) == 0 )
        {
          if ( v37 != WideCharStr )
          {
            v80 = (WCHAR *)(v79 + *(unsigned __int16 *)(v79 + 16));
            goto LABEL_98;
          }
LABEL_118:
          v81 = 1;
LABEL_98:
          if ( v80 )
            goto LABEL_115;
          goto LABEL_99;
        }
      }
      else
      {
        if ( (*(_BYTE *)(v78 + 2) & 0x34) != 0x34 )
        {
          MultiByteToWideChar(0, 0, (LPCCH)(v78 + 14), -1, WideCharStr, 260);
          goto LABEL_118;
        }
        v37 = (WCHAR *)(v78 + 14);
      }
      ualstrcpynW(WideCharStr, v37, 260);
      goto LABEL_118;
    }
LABEL_99:
    v38 = WideCharStr;
LABEL_100:
    v39 = -1;
    do
      ++v39;
    while ( v38[v39] );
    v9 += v39 + 1;
    v71 = &CFileSysItemString::`vftable';
    v40 = v77;
    v77 = 0;
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    v41 = v75;
    v75 = 0;
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v42 = v76;
    v76 = 0;
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    if ( v74 )
      CoTaskMemFree(v74);
    if ( v73 )
      CoTaskMemFree(v73);
    if ( v72 )
      CoTaskMemFree(v72);
  }
  v12 = 0;
  ppMalloc = 0;
  if ( !is_mul_ok(v9, 2u) )
  {
    v14 = -2147024362;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x406,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
      (const char *)(unsigned int)v14,
      lpWideCharStr);
    if ( v6 )
      LocalFree(v12);
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)v14;
  }
  v12 = CoTaskMemAlloc(2 * v9);
  if ( v12 )
  {
    v13 = 0;
    ppMalloc = 0;
    if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
    {
      v13 = ((__int64 (__fastcall *)(LPMALLOC, void *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v12);
      ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
    }
    memset_0(v12, 0, v13);
    v14 = 0;
  }
  else
  {
    v14 = -2147024882;
  }
  v6 = v12;
  if ( v14 < 0 )
    goto LABEL_13;
  v17 = PathCchCanonicalizeEx((PWSTR)v12, v9, v7, a3);
  v18 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x40B,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
      (const char *)(unsigned int)v17,
      lpWideCharStr);
    if ( v12 )
      goto LABEL_151;
    goto LABEL_152;
  }
  while ( 2 )
  {
    if ( !a2 || !*(_WORD *)a2 )
    {
      *a4 = (unsigned __int16 *)v12;
      if ( pv )
        CoTaskMemFree(pv);
      return 0;
    }
    CFileSysItemString::CFileSysItemString((CFileSysItemString *)v59, (CFSFolder *)((char *)this - 312), a2, 0);
    if ( v68 )
      goto LABEL_50;
    if ( (v69 & 1) != 0 )
      goto LABEL_32;
    if ( !v67 )
    {
      if ( (*(_BYTE *)(v66 + 2) & 0x34) != 0x34 )
      {
        MultiByteToWideChar(0, 0, (LPCCH)(v66 + 14), -1, pszMore, 260);
        goto LABEL_87;
      }
      v19 = (WCHAR *)(v66 + 14);
      goto LABEL_86;
    }
    v19 = (WCHAR *)(v67 + *(unsigned __int16 *)(v67 + 16));
    if ( ((unsigned __int8)v19 & 1) != 0 )
    {
LABEL_86:
      ualstrcpynW(pszMore, v19, 260);
      goto LABEL_87;
    }
    if ( v19 != pszMore )
    {
      v68 = (WCHAR *)(v67 + *(unsigned __int16 *)(v67 + 16));
      goto LABEL_31;
    }
LABEL_87:
    v69 = 1;
LABEL_31:
    if ( !v68 )
    {
LABEL_32:
      v20 = pszMore;
      goto LABEL_33;
    }
LABEL_50:
    v20 = v68;
LABEL_33:
    v21 = PathCchAppendEx((PWSTR)v12, v9, v20, a3);
    v18 = v21;
    if ( v21 >= 0 )
    {
      v59[0] = &CFileSysItemString::`vftable';
      v22 = v65;
      v65 = 0;
      if ( v22 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      v23 = v63;
      v63 = 0;
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      v24 = v64;
      v64 = 0;
      if ( v24 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      if ( v62 )
        CoTaskMemFree(v62);
      if ( v61 )
        CoTaskMemFree(v61);
      if ( v60 )
        CoTaskMemFree(v60);
      a2 = (const struct _ITEMIDLIST_RELATIVE *)((char *)a2 + *(unsigned __int16 *)a2);
      continue;
    }
    break;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x413,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
    (const char *)(unsigned int)v21,
    lpWideCharStr);
  CFileSysItemString::~CFileSysItemString((CFileSysItemString *)v59);
  if ( !v12 )
    goto LABEL_152;
LABEL_151:
  LocalFree(v12);
LABEL_152:
  if ( pv )
    CoTaskMemFree(pv);
  return v18;
}

```

## disassembly

```asm
0x180042990  push    rbp
0x180042992  push    rbx
0x180042993  push    rsi
0x180042994  push    rdi
0x180042995  push    r12
0x180042997  push    r13
0x180042999  push    r14
0x18004299b  push    r15
0x18004299d  lea     rbp, [rsp-4D8h]
0x1800429a5  sub     rsp, 5D8h
0x1800429ac  mov     rax, cs:__security_cookie
0x1800429b3  xor     rax, rsp
0x1800429b6  mov     [rbp+510h+var_50], rax
0x1800429bd  mov     [rsp+610h+var_5D8], r9
0x1800429c2  mov     [rsp+610h+dwFlags], r8d
0x1800429c7  mov     r12, rdx
0x1800429ca  mov     r13, rcx
0x1800429cd  xor     r14d, r14d
0x1800429d0  mov     [r9], r14
0x1800429d3  mov     [rsp+610h+pv], r14
0x1800429d8  mov     rdi, [rcx+88h]
0x1800429df  test    rdi, rdi
0x1800429e2  jz      loc_180043029
0x1800429e8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800429ef  nop
0x1800429f0  lea     rax, [rax+1]
0x1800429f4  cmp     word ptr [rdi+rax*2], 0
0x1800429f9  jnz     short loc_1800429F0
0x1800429fb  lea     r15, [rax+7]
0x1800429ff  mov     rbx, r12
0x180042a02  test    rbx, rbx
0x180042a05  jz      short loc_180042A13
0x180042a07  movzx   ecx, word ptr [rbx]
0x180042a0a  test    cx, cx
0x180042a0d  jnz     loc_180042B0C
0x180042a13  mov     rbx, r14
0x180042a16  mov     [rsp+610h+ppMalloc], r14
0x180042a1b  mov     eax, 2
0x180042a20  mul     r15
0x180042a23  test    rdx, rdx
0x180042a26  jnz     loc_180042B05
0x180042a2c  mov     rcx, rax; cb
0x180042a2f  call    cs:__imp_CoTaskMemAlloc
0x180042a35  mov     rbx, rax
0x180042a38  mov     [rsp+610h+var_5D0], rax
0x180042a3d  test    rax, rax
0x180042a40  jz      loc_180043205
0x180042a46  mov     rsi, r14
0x180042a49  mov     [rsp+610h+ppMalloc], r14
0x180042a4e  lea     rdx, [rsp+610h+ppMalloc]; ppMalloc
0x180042a53  mov     ecx, 1; dwMemContext
0x180042a58  call    cs:__imp_CoGetMalloc
0x180042a5e  test    eax, eax
0x180042a60  js      short loc_180042A8A
0x180042a62  mov     rcx, [rsp+610h+ppMalloc]
0x180042a67  mov     rax, [rcx]
0x180042a6a  mov     rdx, rbx
0x180042a6d  mov     rax, [rax+30h]
0x180042a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042a76  mov     rsi, rax
0x180042a79  mov     rcx, [rsp+610h+ppMalloc]
0x180042a7e  mov     rdx, [rcx]
0x180042a81  mov     rax, [rdx+10h]
0x180042a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042a8a  mov     r8, rsi; Size
0x180042a8d  xor     edx, edx; Val
0x180042a8f  mov     rcx, rbx; void *
0x180042a92  call    memset_0
0x180042a97  mov     esi, r14d
0x180042a9a  mov     r14, rbx
0x180042a9d  test    esi, esi
0x180042a9f  jns     loc_180042B2B
0x180042aa5  mov     rcx, [rbp+518h]; this
0x180042aac  mov     r9d, esi; char *
0x180042aaf  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x180042ab6  mov     edx, 406h; void *
0x180042abb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042ac0  nop
0x180042ac1  test    r14, r14
0x180042ac4  jz      short loc_180042AD0
0x180042ac6  mov     rcx, rbx; hMem
0x180042ac9  call    cs:__imp_LocalFree
0x180042acf  nop
0x180042ad0  mov     rcx, [rsp+610h+pv]; pv
0x180042ad5  test    rcx, rcx
0x180042ad8  jz      short loc_180042AE0
0x180042ada  call    cs:__imp_CoTaskMemFree
0x180042ae0  mov     eax, esi
0x180042ae2  mov     rcx, [rbp+510h+var_50]
0x180042ae9  xor     rcx, rsp; StackCookie
0x180042aec  call    __security_check_cookie
0x180042af1  add     rsp, 5D8h
0x180042af8  pop     r15
0x180042afa  pop     r14
0x180042afc  pop     r13
0x180042afe  pop     r12
0x180042b00  pop     rdi
0x180042b01  pop     rsi
0x180042b02  pop     rbx
0x180042b03  pop     rbp
0x180042b04  retn
0x180042b05  mov     esi, 80070216h
0x180042b0a  jmp     short loc_180042AA5
0x180042b0c  cmp     ecx, 0Bh
0x180042b0f  jbe     loc_180042D95
0x180042b15  movzx   eax, byte ptr [rbx+2]
0x180042b19  and     al, 70h
0x180042b1b  cmp     al, 30h ; '0'
0x180042b1d  jnz     loc_180043136
0x180042b23  mov     rsi, rbx
0x180042b26  jmp     loc_180042CB8
0x180042b2b  mov     esi, [rsp+610h+dwFlags]
0x180042b2f  mov     r9d, esi; dwFlags
0x180042b32  mov     r8, rdi; pszPathIn
0x180042b35  mov     rdx, r15; cchPathOut
0x180042b38  mov     rcx, rbx; pszPathOut
0x180042b3b  call    cs:__imp_PathCchCanonicalizeEx
0x180042b41  mov     edi, eax
0x180042b43  test    eax, eax
0x180042b45  js      loc_180043296
0x180042b4b  test    r12, r12
0x180042b4e  jz      loc_180042C76
0x180042b54  cmp     word ptr [r12], 0
0x180042b5a  jz      loc_180042C76
0x180042b60  lea     rdx, [r13-138h]; struct CFSFolder *
0x180042b67  xor     r9d, r9d; struct IDFOLDER *
0x180042b6a  mov     r8, r12; struct _ITEMIDLIST_RELATIVE *
0x180042b6d  lea     rcx, [rsp+610h+var_5B0]; this
0x180042b72  call    ??0CFileSysItemString@@QEAA@PEAVCFSFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEFBUIDFOLDER@@@Z; CFileSysItemString::CFileSysItemString(CFSFolder *,_ITEMIDLIST_RELATIVE const *,IDFOLDER const *)
0x180042b77  cmp     [rbp+510h+var_548], 0
0x180042b7c  jnz     loc_180042C95
0x180042b82  test    byte ptr [rbp+510h+var_530], 1
0x180042b86  jnz     short loc_180042BC1
0x180042b88  mov     rcx, [rbp+510h+var_558]
0x180042b8c  test    rcx, rcx
0x180042b8f  jz      loc_1800430F9
0x180042b95  movzx   edx, word ptr [rcx+10h]
0x180042b99  add     rdx, rcx
0x180042b9c  test    dl, 1
0x180042b9f  jnz     loc_180042E61
0x180042ba5  lea     rax, [rbp+510h+pszMore]
0x180042ba9  cmp     rdx, rax
0x180042bac  jz      loc_180042E71
0x180042bb2  mov     [rbp+510h+var_548], rdx
0x180042bb6  cmp     [rbp+510h+var_548], 0
0x180042bbb  jnz     loc_180042C95
0x180042bc1  lea     r8, [rbp+510h+pszMore]; pszMore
0x180042bc5  mov     r9d, esi; dwFlags
0x180042bc8  mov     rdx, r15; cchPath
0x180042bcb  mov     rcx, rbx; pszPath
0x180042bce  call    cs:__imp_PathCchAppendEx
0x180042bd4  mov     edi, eax
0x180042bd6  test    eax, eax
0x180042bd8  js      loc_18004320F
0x180042bde  lea     rax, ??_7CFileSysItemString@@6B@; const CFileSysItemString::`vftable'
0x180042be5  mov     [rsp+610h+var_5B0], rax
0x180042bea  mov     rcx, [rbp+510h+var_568]
0x180042bee  mov     [rbp+510h+var_568], 0
0x180042bf6  test    rcx, rcx
0x180042bf9  jz      short loc_180042C07
0x180042bfb  mov     rax, [rcx]
0x180042bfe  mov     rax, [rax+10h]
0x180042c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042c07  mov     rcx, [rbp+510h+var_578]
0x180042c0b  mov     [rbp+510h+var_578], 0
0x180042c13  test    rcx, rcx
0x180042c16  jnz     loc_180042C9E
0x180042c1c  mov     rcx, [rbp+510h+var_570]
0x180042c20  mov     [rbp+510h+var_570], 0
0x180042c28  test    rcx, rcx
0x180042c2b  jz      short loc_180042C39
0x180042c2d  mov     rax, [rcx]
0x180042c30  mov     rax, [rax+10h]
0x180042c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042c39  mov     rcx, [rbp+510h+var_580]; pv
0x180042c3d  test    rcx, rcx
0x180042c40  jz      short loc_180042C48
0x180042c42  call    cs:__imp_CoTaskMemFree
0x180042c48  mov     rcx, [rsp+610h+var_598]; pv
0x180042c4d  test    rcx, rcx
0x180042c50  jz      short loc_180042C58
0x180042c52  call    cs:__imp_CoTaskMemFree
0x180042c58  mov     rcx, [rsp+610h+var_5A0]; pv
0x180042c5d  test    rcx, rcx
0x180042c60  jz      short loc_180042C69
0x180042c62  call    cs:__imp_CoTaskMemFree
0x180042c68  nop
0x180042c69  movzx   eax, word ptr [r12]
0x180042c6e  add     r12, rax
0x180042c71  jmp     loc_180042B4B
0x180042c76  mov     rax, [rsp+610h+var_5D8]
0x180042c7b  mov     [rax], rbx
0x180042c7e  mov     rcx, [rsp+610h+pv]; pv
0x180042c83  test    rcx, rcx
0x180042c86  jz      short loc_180042C8E
0x180042c88  call    cs:__imp_CoTaskMemFree
0x180042c8e  xor     eax, eax
0x180042c90  jmp     loc_180042AE2
0x180042c95  mov     r8, [rbp+510h+var_548]
0x180042c99  jmp     loc_180042BC5
0x180042c9e  mov     rax, [rcx]
0x180042ca1  mov     rax, [rax+10h]
0x180042ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042caa  jmp     loc_180042C1C
0x180042caf  test    rsi, rsi
0x180042cb2  jz      loc_180042D95
0x180042cb8  cmp     word ptr [rsi], 0Eh
0x180042cbc  jb      loc_180042D95
0x180042cc2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow> `wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl(void)'::`2'::impl
0x180042cc9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(void)
0x180042cce  movzx   r8d, word ptr [rbx]
0x180042cd2  test    al, al
0x180042cd4  jnz     loc_180043286
0x180042cda  movzx   r10d, r8w
0x180042cde  mov     rdx, r14
0x180042ce1  movzx   ecx, r8w
0x180042ce5  movzx   r9d, word ptr [rcx+rbx-2]
0x180042ceb  test    r9w, r9w
0x180042cef  jz      short loc_180042D30
0x180042cf1  lea     rax, [r9+8]
0x180042cf5  cmp     rax, rcx
0x180042cf8  jnb     short loc_180042D30
0x180042cfa  lea     rdx, [r9+rbx]
0x180042cfe  movzx   ecx, word ptr [rdx]
0x180042d01  cmp     ecx, 8
0x180042d04  jb      loc_180043021
0x180042d0a  mov     eax, [rdx+4]
0x180042d0d  shr     rax, 10h
0x180042d11  mov     r11d, 0BEEFh
0x180042d17  cmp     ax, r11w
0x180042d1b  jnz     loc_180043021
0x180042d21  add     ecx, r9d
0x180042d24  movzx   eax, r8w
0x180042d28  cmp     ecx, eax
0x180042d2a  ja      loc_180043021
0x180042d30  movzx   ecx, r10w
0x180042d34  add     rcx, rbx
0x180042d37  test    rdx, rdx
0x180042d3a  jz      loc_180042E09
0x180042d40  cmp     dword ptr [rdx+4], 0BEEF0004h
0x180042d47  jnz     loc_180042E7D
0x180042d4d  lea     rcx, [rsi+0Eh]
0x180042d51  test    rcx, rcx
0x180042d54  jz      loc_180043272
0x180042d5a  movzx   edx, word ptr [rsi]
0x180042d5d  add     rdx, 0FFFFFFFFFFFFFFF2h
0x180042d61  cmp     rdx, 7FFFFFFFh
0x180042d68  ja      loc_180043272
0x180042d6e  test    rdx, rdx
0x180042d71  jz      short loc_180042D81
0x180042d73  cmp     byte ptr [rcx], 0
0x180042d76  jz      short loc_180042D81
0x180042d78  inc     rcx
0x180042d7b  sub     rdx, 1
0x180042d7f  jnz     short loc_180042D73
0x180042d81  mov     ecx, 80070057h
0x180042d86  test    rdx, rdx
0x180042d89  cmovnz  ecx, r14d
0x180042d8d  test    ecx, ecx
0x180042d8f  jns     loc_180042EA8
0x180042d95  mov     rcx, [rbp+518h]; this
0x180042d9c  mov     r9d, 80004005h; char *
0x180042da2  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x180042da9  mov     edx, 3FFh; void *
0x180042dae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042db3  nop
0x180042db4  mov     rcx, [rsp+610h+pv]; pv
0x180042db9  test    rcx, rcx
0x180042dbc  jz      short loc_180042DC4
0x180042dbe  call    cs:__imp_CoTaskMemFree
0x180042dc4  mov     eax, 80004005h
0x180042dc9  jmp     loc_180042AE2
0x180042dce  lea     rax, [r8+8]
0x180042dd2  cmp     rax, rcx
0x180042dd5  ja      short loc_180042E09
0x180042dd7  mov     eax, [r8+4]
0x180042ddb  shr     rax, 10h
0x180042ddf  mov     edx, 0BEEFh
0x180042de4  cmp     ax, dx
0x180042de7  jnz     short loc_180042E09
0x180042de9  movzx   eax, word ptr [r8]
0x180042ded  add     rax, r8
0x180042df0  cmp     rax, rcx
0x180042df3  ja      short loc_180042E09
0x180042df5  cmp     r8, r10
0x180042df8  jb      short loc_180042E09
0x180042dfa  mov     r9, r8
0x180042dfd  mov     rdx, r9
0x180042e00  test    r9, r9
0x180042e03  jnz     loc_180042D40
0x180042e09  movzx   eax, byte ptr [rsi+2]
0x180042e0d  and     al, 34h
0x180042e0f  cmp     al, 34h ; '4'
0x180042e11  jnz     loc_180042D4D
0x180042e17  lea     rax, [rsi+0Eh]
0x180042e1b  test    rax, rax
0x180042e1e  jz      loc_180043272
0x180042e24  movzx   edx, word ptr [rsi]
0x180042e27  sub     rdx, 0Eh
0x180042e2b  shr     rdx, 1
  ... truncated ...
```
