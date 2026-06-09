# CFSFolder::TryGetShortPath(_ITEMIDLIST_RELATIVE const *,ushort * *)

- ea: `0x180041ec0`
- end: `0x18004297d`
- name: `?TryGetShortPath@CFSFolder@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAG@Z`
- size: `2749`
- prototype: `int(CFSFolder *__hidden this, const struct _ITEMIDLIST_RELATIVE *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `12`
- tags: `reparse_path, service_task, installer_update, broker_com_uri`

## callees

- `0x1800412a0`
- `0x180041ec0`
- `0x1800432f0`
- `0x180043320`
- `0x180091870`
- `0x180148460`
- `0x180155330`
- `0x1801553f0`
- `0x180333018`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042406`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042781`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042406`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042781`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x18004205d`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x18004205d`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x1800420ee`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x1800420ee`
- `OLEAUT32!__imp_SysAllocString` at `0x180042843`
- `OLEAUT32!__imp_SysAllocString` at `0x180042843`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180041fd3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180041fd3`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180042000`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180042000`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041f64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042162`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042172`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042182`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004231f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042419`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800424b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042647`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042657`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042667`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800426df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800426ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800426ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042794`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041f64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042162`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042172`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042182`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004231f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042419`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800424b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042647`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042657`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042667`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800426df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800426ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800426ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042794`
- `SHCORE!__imp_ualstrlenW` at `0x1800428ea`
- `SHCORE!__imp_ualstrlenW` at `0x180042935`
- `SHCORE!__imp_ualstrlenW` at `0x1800428ea`
- `SHCORE!__imp_ualstrlenW` at `0x180042935`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x1800420da`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x1800420da`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CFSFolder::TryGetShortPath(
        CFSFolder *this,
        const struct _ITEMIDLIST_RELATIVE *a2,
        unsigned __int16 **a3)
{
  void *v5; // r14
  const WCHAR *v6; // rdi
  __int64 v7; // rax
  size_t v8; // r12
  const struct _ITEMIDLIST_RELATIVE *i; // rbx
  __int64 v10; // rcx
  void *v11; // rcx
  const struct _ITEMIDLIST_RELATIVE *v13; // rsi
  void *v14; // rbx
  size_t v15; // rsi
  int v16; // esi
  HRESULT v17; // eax
  unsigned int v18; // edi
  __int64 v19; // rdx
  unsigned __int64 *v20; // r8
  unsigned int v21; // r9d
  HRESULT v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  WCHAR *v27; // rdx
  __int64 v28; // r9
  WCHAR *v29; // r8
  WCHAR v30; // ax
  WCHAR *v31; // rcx
  char IsEnabled; // al
  unsigned __int16 v33; // r8
  unsigned __int16 *v34; // rdx
  __int64 v35; // r10
  unsigned int v36; // ecx
  unsigned __int64 v37; // rcx
  _BYTE *v38; // rcx
  unsigned __int64 v39; // rdx
  int v40; // ecx
  unsigned __int16 *v41; // r8
  _WORD *v42; // rax
  unsigned __int16 *v43; // r9
  const KNOWNFOLDERID *v44; // rcx
  __int64 v45; // rax
  HRESULT v46; // eax
  unsigned int v47; // ebx
  __int64 v48; // rdx
  const ITEMIDLIST *v49; // rcx
  unsigned __int64 v50; // r11
  unsigned __int16 *v51; // r9
  unsigned int v52; // edx
  __int64 v53; // rcx
  __int64 v54; // rdx
  __int64 v55; // r9
  unsigned __int64 *v56; // rcx
  unsigned int v57; // r8d
  char *v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  __int64 v64; // rcx
  __int64 v65; // rcx
  char *v66; // rdx
  __int64 v67; // r8
  unsigned __int64 *v68; // r8
  unsigned int v69; // edx
  int v70; // eax
  __int64 v71; // r9
  unsigned int v72; // r9d
  unsigned int v73; // ecx
  int v74; // eax
  const ITEMIDLIST *v75; // rcx
  int v76; // eax
  unsigned int v77; // edx
  int v78; // eax
  int v79; // eax
  unsigned int v80; // ecx
  int v81; // eax
  int v82[2]; // [rsp+20h] [rbp-E0h]
  WCHAR pwszDst[16]; // [rsp+28h] [rbp-D8h] BYREF
  void *v84; // [rsp+48h] [rbp-B8h]
  _QWORD v85[2]; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v86; // [rsp+60h] [rbp-A0h]
  LPVOID v87; // [rsp+68h] [rbp-98h]
  LPVOID v88; // [rsp+80h] [rbp-80h]
  __int64 v89; // [rsp+88h] [rbp-78h]
  __int64 v90; // [rsp+90h] [rbp-70h]
  __int64 v91; // [rsp+98h] [rbp-68h]
  unsigned __int64 *v92; // [rsp+A0h] [rbp-60h]
  __int64 v93; // [rsp+A8h] [rbp-58h]
  LPVOID pv; // [rsp+300h] [rbp+200h] BYREF
  LPMALLOC ppMalloc; // [rsp+308h] [rbp+208h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+258h]

  *(_QWORD *)v82 = a3;
  v5 = 0;
  *a3 = 0;
  pv = 0;
  v6 = (const WCHAR *)*((_QWORD *)this + 18);
  if ( v6 )
    goto LABEL_3;
  v6 = (const WCHAR *)*((_QWORD *)this + 17);
  if ( v6 )
    goto LABEL_3;
  pv = 0;
  v44 = (const KNOWNFOLDERID *)((char *)this + 184);
  v45 = *(_QWORD *)&v44->Data1 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *(_QWORD *)&v44->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
    v45 = *(_QWORD *)v44->Data4 - *(_QWORD *)GUID_NULL.Data4;
  if ( !v45 )
  {
    v49 = (const ITEMIDLIST *)*((_QWORD *)this + 16);
    if ( v49 )
    {
      v46 = SHGetNameFromIDList(v49, SIGDN_DESKTOPABSOLUTEPARSING, (PWSTR *)&pv);
      v47 = v46;
      if ( v46 < 0 )
      {
        v48 = 1177;
        goto LABEL_100;
      }
    }
    else
    {
      v75 = (const ITEMIDLIST *)*((_QWORD *)this + 15);
      if ( v75 )
      {
        v46 = SHGetNameFromIDList(v75, SIGDN_DESKTOPABSOLUTEPARSING, (PWSTR *)&pv);
        v47 = v46;
        if ( v46 < 0 )
        {
          v48 = 1181;
          goto LABEL_100;
        }
      }
    }
    if ( !pv )
    {
      v47 = -2147024893;
      goto LABEL_101;
    }
    *((_QWORD *)this + 17) = SysAllocString((const OLECHAR *)pv);
LABEL_173:
    v6 = (const WCHAR *)pv;
LABEL_3:
    v7 = -1;
    do
      ++v7;
    while ( v6[v7] );
    v8 = v7 + 1;
    for ( i = a2; ; i = (const struct _ITEMIDLIST_RELATIVE *)((char *)i + *(unsigned __int16 *)i) )
    {
      if ( !i || (v10 = *(unsigned __int16 *)i, !(_WORD)v10) )
      {
        if ( v8 >= 0x104 )
        {
LABEL_9:
          v11 = pv;
          if ( pv )
            goto LABEL_10;
          return 0;
        }
        v14 = 0;
        ppMalloc = 0;
        if ( is_mul_ok(v8, 2u) )
        {
          v14 = CoTaskMemAlloc(2 * v8);
          v84 = v14;
          if ( v14 )
          {
            v15 = 0;
            ppMalloc = 0;
            if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
            {
              v15 = ((__int64 (__fastcall *)(LPMALLOC, void *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v14);
              ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
            }
            memset_0(v14, 0, v15);
            v16 = 0;
          }
          else
          {
            v16 = -2147024882;
          }
          v5 = v14;
          if ( v16 >= 0 )
          {
            v17 = PathCchCanonicalizeEx((PWSTR)v14, v8, v6, 0);
            v18 = v17;
            if ( v17 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x470,
                (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
                (const char *)(unsigned int)v17,
                v82[0]);
              if ( v14 )
                goto LABEL_158;
            }
            else
            {
              while ( 1 )
              {
                if ( !a2 || !*(_WORD *)a2 )
                {
                  **(_QWORD **)v82 = v14;
                  goto LABEL_9;
                }
                CFileSysItemString::CFileSysItemString(
                  (CFileSysItemString *)v85,
                  (CFSFolder *)((char *)this - 312),
                  a2,
                  0);
                memset(pwszDst, 0, 26);
                v20 = v92;
                v21 = 0;
                if ( (*((_BYTE *)v92 + 2) & 0x34) == 0x34 )
                {
                  if ( !v93 )
                  {
                    v79 = ualstrlenW((char *)v92 + 14, v19, v92, 0);
                    v20 = v92;
                    v80 = *(unsigned __int16 *)v92;
                    if ( v80 <= 2 * v79 + 16
                      || (v81 = UnalignedStringCbLengthW(
                                  (const unsigned __int16 *)((char *)v92 + (unsigned int)(2 * v79 + 2) + 14),
                                  v80 - (2 * v79 + 2) - 14,
                                  v92),
                          v20 = v92,
                          v81 < 0) )
                    {
                      v21 = 0;
                    }
                  }
                  v26 = 2147483646;
                  v27 = (WCHAR *)((char *)v20 + v21 + 14);
                  v28 = 13;
                  v29 = pwszDst;
                  do
                  {
                    if ( !v26 )
                      break;
                    v30 = *v27;
                    if ( !*v27 )
                      break;
                    ++v27;
                    *v29++ = v30;
                    --v26;
                    --v28;
                  }
                  while ( v28 );
                  v31 = v29 - 1;
                  if ( v28 )
                    v31 = v29;
                  *v31 = 0;
                }
                else
                {
                  if ( !v93 )
                  {
                    v71 = -1;
                    do
                      ++v71;
                    while ( *((_BYTE *)v92 + v71 + 14) );
                    v72 = v71 + 1;
                    v73 = *(unsigned __int16 *)v92;
                    if ( v73 <= v72 + 14
                      || (v74 = StringCbLengthA((const char *)v92 + v72 + 14, v73 - v72 - 14, v92), v20 = v92, v74 < 0) )
                    {
                      v21 = 0;
                    }
                  }
                  SHAnsiToUnicode((PCSTR)v20 + v21 + 14, pwszDst, 13);
                }
                v22 = PathCchAppendEx((PWSTR)v14, v8, pwszDst, 0);
                v18 = v22;
                if ( v22 < 0 )
                  break;
                v85[0] = &CFileSysItemString::`vftable';
                v23 = v91;
                v91 = 0;
                if ( v23 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
                v24 = v89;
                v89 = 0;
                if ( v24 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
                v25 = v90;
                v90 = 0;
                if ( v25 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
                if ( v88 )
                  CoTaskMemFree(v88);
                if ( v87 )
                  CoTaskMemFree(v87);
                if ( v86 )
                  CoTaskMemFree(v86);
                a2 = (const struct _ITEMIDLIST_RELATIVE *)((char *)a2 + *(unsigned __int16 *)a2);
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x479,
                (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
                (const char *)(unsigned int)v22,
                v82[0]);
              CFileSysItemString::~CFileSysItemString((CFileSysItemString *)v85);
              if ( v14 )
LABEL_158:
                LocalFree(v14);
            }
            if ( pv )
              CoTaskMemFree(pv);
            return v18;
          }
        }
        else
        {
          v16 = -2147024362;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x46B,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
          (const char *)(unsigned int)v16,
          v82[0]);
        if ( v5 )
          LocalFree(v14);
        if ( pv )
          CoTaskMemFree(pv);
        return (unsigned int)v16;
      }
      if ( (unsigned int)v10 <= 0xB )
        goto LABEL_68;
      if ( (*((_BYTE *)i + 2) & 0x70) == 0x30 )
      {
        v13 = i;
      }
      else
      {
        if ( *(_DWORD *)((char *)i + 6) != 1179862595 )
          goto LABEL_68;
        v50 = *((unsigned __int16 *)i + 2);
        if ( v50 > v10 - 4 )
          goto LABEL_68;
        v13 = (const struct _ITEMIDLIST_RELATIVE *)((char *)i + 10);
        v51 = (unsigned __int16 *)((char *)i + 10);
        v52 = 2;
        if ( (unsigned int)v50 < 2 )
          goto LABEL_68;
        while ( 1 )
        {
          v53 = *v51;
          if ( (unsigned int)v53 < 2 || (unsigned int)v53 > (unsigned int)v50 - v52 )
            break;
          v52 += v53;
          v51 = (unsigned __int16 *)((char *)v51 + v53);
          if ( v52 > (unsigned int)v50 )
            goto LABEL_68;
        }
        if ( (_WORD)v53
          || v52 > (unsigned int)v50
          || (_WORD)v50 != *(_WORD *)v13 + 6
          || (unsigned __int16)(*(_WORD *)v13 + 6) < *(_WORD *)v13
          || i == (const struct _ITEMIDLIST_RELATIVE *)-10LL )
        {
LABEL_68:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x458,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
            (const char *)0x80070057LL,
            v82[0]);
          if ( pv )
            CoTaskMemFree(pv);
          return 2147942487LL;
        }
      }
      if ( *(_WORD *)v13 < 0xEu )
        goto LABEL_68;
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl'::`2'::impl);
      v33 = *(_WORD *)i;
      if ( !IsEnabled || v33 >= 2u )
      {
        v34 = 0;
        v35 = *(unsigned __int16 *)((char *)i + v33 - 2);
        if ( (_WORD)v35 )
        {
          if ( v35 + 8 < (unsigned __int64)v33 )
          {
            v34 = (unsigned __int16 *)((char *)i + v35);
            v36 = *(unsigned __int16 *)((char *)i + v35);
            if ( v36 < 8 || HIWORD(*((_DWORD *)v34 + 1)) != 0xBEEF || (unsigned int)v35 + v36 > v33 )
              v34 = 0;
          }
        }
        v37 = (unsigned __int64)i + v33;
        if ( v34 )
          break;
      }
LABEL_77:
      if ( (*((_BYTE *)v13 + 2) & 0x34) != 0x34 )
        goto LABEL_60;
      v42 = (_WORD *)((char *)v13 + 14);
      if ( v13 == (const struct _ITEMIDLIST_RELATIVE *)-14LL
        || (v39 = ((unsigned __int64)*(unsigned __int16 *)v13 - 14) >> 1, v39 > 0x7FFFFFFF) )
      {
LABEL_174:
        v40 = -2147024809;
        goto LABEL_67;
      }
      for ( ; v39; --v39 )
      {
        if ( !*v42 )
          break;
        ++v42;
      }
LABEL_65:
      v40 = -2147024809;
      if ( v39 )
        v40 = 0;
LABEL_67:
      if ( v40 < 0 )
        goto LABEL_68;
      CFileSysItemString::CFileSysItemString((CFileSysItemString *)v85, (CFSFolder *)((char *)this - 312), i, v13);
      v56 = v92;
      v57 = 0;
      if ( (*((_BYTE *)v92 + 2) & 0x34) == 0x34 )
      {
        if ( !v93 )
        {
          v76 = ualstrlenW((char *)v92 + 14, v54, 0, v55);
          v56 = v92;
          v77 = *(unsigned __int16 *)v92;
          if ( v77 <= 2 * v76 + 16
            || (v78 = UnalignedStringCbLengthW(
                        (const unsigned __int16 *)((char *)v92 + (unsigned int)(2 * v76 + 2) + 14),
                        v77 - (2 * v76 + 2) - 14,
                        (unsigned __int64 *)(unsigned int)(2 * v76 + 2)),
                v56 = v92,
                v78 < 0) )
          {
            v57 = 0;
          }
        }
        v66 = (char *)v56 + v57;
        v59 = -1;
        do
          ++v59;
        while ( *(_WORD *)&v66[2 * v59 + 14] );
      }
      else
      {
        if ( !v93 )
        {
          v67 = -1;
          do
            ++v67;
          while ( *((_BYTE *)v92 + v67 + 14) );
          v68 = (unsigned __int64 *)(unsigned int)(v67 + 1);
          v69 = *(unsigned __int16 *)v92;
          if ( v69 <= (int)v68 + 14
            || (v70 = StringCbLengthA((const char *)v92 + (unsigned int)v68 + 14, v69 - (unsigned int)v68 - 14, v68),
                v56 = v92,
                v70 < 0) )
          {
            v57 = 0;
          }
        }
        v58 = (char *)v56 + v57;
        v59 = -1;
        do
          ++v59;
        while ( v58[v59 + 14] );
      }
      if ( (unsigned __int64)(v59 - 1) > 0xB )
      {
        v85[0] = &CFileSysItemString::`vftable';
        v63 = v91;
        v91 = 0;
        if ( v63 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
        v64 = v89;
        v89 = 0;
        if ( v64 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
        v65 = v90;
        v90 = 0;
        if ( v65 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
        if ( v88 )
          CoTaskMemFree(v88);
        if ( v87 )
          CoTaskMemFree(v87);
        if ( v86 )
          CoTaskMemFree(v86);
        v11 = pv;
        if ( pv )
LABEL_10:
          CoTaskMemFree(v11);
        return 0;
      }
      v8 += v59 + 1;
      v85[0] = &CFileSysItemString::`vftable';
      v60 = v91;
      v91 = 0;
      if ( v60 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
      v61 = v89;
      v89 = 0;
      if ( v61 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
      v62 = v90;
      v90 = 0;
      if ( v62 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
      if ( v88 )
        CoTaskMemFree(v88);
      if ( v87 )
        CoTaskMemFree(v87);
      if ( v86 )
        CoTaskMemFree(v86);
    }
    while ( *((_DWORD *)v34 + 1) != -1091633148 )
    {
      v41 = 0;
      if ( (unsigned __int64)(v34 + 4) <= v37 )
      {
        v43 = (unsigned __int16 *)((char *)v34 + *v34);
        if ( v43 == (unsigned __int16 *)v37 )
          goto LABEL_77;
        if ( (unsigned __int64)v43 <= v37 )
        {
          if ( (unsigned __int64)(v43 + 4) > v37
            || HIWORD(*((_DWORD *)v43 + 1)) != 0xBEEF
            || (unsigned __int64)v43 + *v43 > v37
            || v43 < v34 + 4 )
          {
            goto LABEL_77;
          }
          v41 = (unsigned __int16 *)((char *)v34 + *v34);
        }
      }
      v34 = v41;
      if ( !v41 )
        goto LABEL_77;
    }
LABEL_60:
    v38 = (char *)v13 + 14;
    if ( v13 == (const struct _ITEMIDLIST_RELATIVE *)-14LL )
      goto LABEL_174;
    v39 = *(unsigned __int16 *)v13 - 14LL;
    if ( v39 > 0x7FFFFFFF )
      goto LABEL_174;
    if ( *(_WORD *)v13 != 14 )
    {
      do
      {
        if ( !*v38 )
          break;
        ++v38;
        --v39;
      }
      while ( v39 );
    }
    goto LABEL_65;
  }
  v46 = SHGetKnownFolderPath(v44, 0x4000u, 0, (PWSTR *)&pv);
  v47 = v46;
  if ( v46 >= 0 )
    goto LABEL_173;
  v48 = 1163;
LABEL_100:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v48,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
    (const char *)(unsigned int)v46,
    v82[0]);
LABEL_101:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x44B,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
    (const char *)v47,
    v82[0]);
  if ( pv )
    CoTaskMemFree(pv);
  return v47;
}

```

## disassembly

```asm
0x180041ec0  mov     [rsp-8+arg_18], rbx
0x180041ec5  push    rbp
0x180041ec6  push    rsi
0x180041ec7  push    rdi
0x180041ec8  push    r12
0x180041eca  push    r13
0x180041ecc  push    r14
0x180041ece  push    r15
0x180041ed0  lea     rbp, [rsp-220h]
0x180041ed8  sub     rsp, 320h
0x180041edf  mov     rax, cs:__security_cookie
0x180041ee6  xor     rax, rsp
0x180041ee9  mov     [rbp+250h+var_40], rax
0x180041ef0  mov     qword ptr [rsp+350h+var_330], r8; int
0x180041ef5  mov     r15, rdx
0x180041ef8  mov     r13, rcx
0x180041efb  xor     r14d, r14d
0x180041efe  mov     [r8], r14
0x180041f01  mov     [rbp+250h+pv], r14
0x180041f08  mov     rdi, [rcx+90h]
0x180041f0f  test    rdi, rdi
0x180041f12  jnz     short loc_180041F24
0x180041f14  mov     rdi, [rcx+88h]
0x180041f1b  test    rdi, rdi
0x180041f1e  jz      loc_18004242E
0x180041f24  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180041f2b  nop     dword ptr [rax+rax+00h]
0x180041f30  lea     rax, [rax+1]
0x180041f34  cmp     word ptr [rdi+rax*2], 0
0x180041f39  jnz     short loc_180041F30
0x180041f3b  lea     r12, [rax+1]
0x180041f3f  mov     rbx, r15
0x180041f42  test    rbx, rbx
0x180041f45  jz      short loc_180041F4F
0x180041f47  movzx   ecx, word ptr [rbx]
0x180041f4a  test    cx, cx
0x180041f4d  jnz     short loc_180041F96
0x180041f4f  cmp     r12, 104h
0x180041f56  jb      short loc_180041FB5
0x180041f58  mov     rcx, [rbp+250h+pv]; pv
0x180041f5f  test    rcx, rcx
0x180041f62  jz      short loc_180041F6A
0x180041f64  call    cs:__imp_CoTaskMemFree
0x180041f6a  xor     eax, eax
0x180041f6c  mov     rcx, [rbp+250h+var_40]
0x180041f73  xor     rcx, rsp; StackCookie
0x180041f76  call    __security_check_cookie
0x180041f7b  mov     rbx, [rsp+350h+arg_18]
0x180041f83  add     rsp, 320h
0x180041f8a  pop     r15
0x180041f8c  pop     r14
0x180041f8e  pop     r13
0x180041f90  pop     r12
0x180041f92  pop     rdi
0x180041f93  pop     rsi
0x180041f94  pop     rbp
0x180041f95  retn
0x180041f96  cmp     ecx, 0Bh
0x180041f99  jbe     loc_1800422F4
0x180041f9f  movzx   eax, byte ptr [rbx+2]
0x180041fa3  and     al, 70h
0x180041fa5  cmp     al, 30h ; '0'
0x180041fa7  jnz     loc_180042508
0x180041fad  mov     rsi, rbx
0x180041fb0  jmp     loc_180042217
0x180041fb5  mov     rbx, r14
0x180041fb8  mov     [rbp+250h+ppMalloc], r14
0x180041fbf  mov     eax, 2
0x180041fc4  mul     r12
0x180041fc7  test    rdx, rdx
0x180041fca  jnz     loc_1800423DD
0x180041fd0  mov     rcx, rax; cb
0x180041fd3  call    cs:__imp_CoTaskMemAlloc
0x180041fd9  mov     rbx, rax
0x180041fdc  mov     [rsp+350h+var_308], rax
0x180041fe1  test    rax, rax
0x180041fe4  jz      loc_180042753
0x180041fea  mov     rsi, r14
0x180041fed  mov     [rbp+250h+ppMalloc], r14
0x180041ff4  lea     rdx, [rbp+250h+ppMalloc]; ppMalloc
0x180041ffb  mov     ecx, 1; dwMemContext
0x180042000  call    cs:__imp_CoGetMalloc
0x180042006  test    eax, eax
0x180042008  js      short loc_180042036
0x18004200a  mov     rcx, [rbp+250h+ppMalloc]
0x180042011  mov     rax, [rcx]
0x180042014  mov     rdx, rbx
0x180042017  mov     rax, [rax+30h]
0x18004201b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042020  mov     rsi, rax
0x180042023  mov     rcx, [rbp+250h+ppMalloc]
0x18004202a  mov     rdx, [rcx]
0x18004202d  mov     rax, [rdx+10h]
0x180042031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042036  mov     r8, rsi; Size
0x180042039  xor     edx, edx; Val
0x18004203b  mov     rcx, rbx; void *
0x18004203e  call    memset_0
0x180042043  mov     esi, r14d
0x180042046  mov     r14, rbx
0x180042049  test    esi, esi
0x18004204b  js      loc_1800423E2
0x180042051  xor     r9d, r9d; dwFlags
0x180042054  mov     r8, rdi; pszPathIn
0x180042057  mov     rdx, r12; cchPathOut
0x18004205a  mov     rcx, rbx; pszPathOut
0x18004205d  call    cs:__imp_PathCchCanonicalizeEx
0x180042063  mov     edi, eax
0x180042065  test    eax, eax
0x180042067  js      loc_18004275D
0x18004206d  test    r15, r15
0x180042070  jz      loc_180042195
0x180042076  cmp     word ptr [r15], 0
0x18004207b  jz      loc_180042195
0x180042081  lea     rdx, [r13-138h]; struct CFSFolder *
0x180042088  xor     r9d, r9d; struct IDFOLDER *
0x18004208b  mov     r8, r15; struct _ITEMIDLIST_RELATIVE *
0x18004208e  lea     rcx, [rsp+350h+var_300]; this
0x180042093  call    ??0CFileSysItemString@@QEAA@PEAVCFSFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEFBUIDFOLDER@@@Z; CFileSysItemString::CFileSysItemString(CFSFolder *,_ITEMIDLIST_RELATIVE const *,IDFOLDER const *)
0x180042098  xorps   xmm0, xmm0
0x18004209b  movups  xmmword ptr [rsp+350h+pwszDst], xmm0
0x1800420a0  movups  xmmword ptr [rsp+350h+pwszDst+0Ah], xmm0
0x1800420a5  mov     r8, [rbp+250h+var_2B0]; unsigned __int64 *
0x1800420a9  movzx   eax, byte ptr [r8+2]
0x1800420ae  and     al, 34h
0x1800420b0  xor     r9d, r9d
0x1800420b3  cmp     al, 34h ; '4'
0x1800420b5  jz      loc_1800421A2
0x1800420bb  cmp     [rbp+250h+var_2A8], r9
0x1800420bf  jz      loc_1800427F2
0x1800420c5  mov     ecx, r9d
0x1800420c8  add     rcx, 0Eh
0x1800420cc  add     rcx, r8; pszSrc
0x1800420cf  mov     r8d, 0Dh; cwchBuf
0x1800420d5  lea     rdx, [rsp+350h+pwszDst]; pwszDst
0x1800420da  call    cs:__imp_SHAnsiToUnicode
0x1800420e0  xor     r9d, r9d; dwFlags
0x1800420e3  lea     r8, [rsp+350h+pwszDst]; pszMore
0x1800420e8  mov     rdx, r12; cchPath
0x1800420eb  mov     rcx, rbx; pszPath
0x1800420ee  call    cs:__imp_PathCchAppendEx
0x1800420f4  mov     edi, eax
0x1800420f6  test    eax, eax
0x1800420f8  js      loc_180042880
0x1800420fe  lea     rax, ??_7CFileSysItemString@@6B@; const CFileSysItemString::`vftable'
0x180042105  mov     [rsp+350h+var_300], rax
0x18004210a  mov     rcx, [rbp+250h+var_2B8]
0x18004210e  mov     [rbp+250h+var_2B8], 0
0x180042116  test    rcx, rcx
0x180042119  jz      short loc_180042127
0x18004211b  mov     rax, [rcx]
0x18004211e  mov     rax, [rax+10h]
0x180042122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042127  mov     rcx, [rbp+250h+var_2C8]
0x18004212b  mov     [rbp+250h+var_2C8], 0
0x180042133  test    rcx, rcx
0x180042136  jnz     loc_1800421FD
0x18004213c  mov     rcx, [rbp+250h+var_2C0]
0x180042140  mov     [rbp+250h+var_2C0], 0
0x180042148  test    rcx, rcx
0x18004214b  jz      short loc_180042159
0x18004214d  mov     rax, [rcx]
0x180042150  mov     rax, [rax+10h]
0x180042154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042159  mov     rcx, [rbp+250h+var_2D0]; pv
0x18004215d  test    rcx, rcx
0x180042160  jz      short loc_180042168
0x180042162  call    cs:__imp_CoTaskMemFree
0x180042168  mov     rcx, [rsp+350h+var_2E8]; pv
0x18004216d  test    rcx, rcx
0x180042170  jz      short loc_180042178
0x180042172  call    cs:__imp_CoTaskMemFree
0x180042178  mov     rcx, [rsp+350h+var_2F0]; pv
0x18004217d  test    rcx, rcx
0x180042180  jz      short loc_180042189
0x180042182  call    cs:__imp_CoTaskMemFree
0x180042188  nop
0x180042189  movzx   eax, word ptr [r15]
0x18004218d  add     r15, rax
0x180042190  jmp     loc_18004206D
0x180042195  mov     rax, qword ptr [rsp+350h+var_330]
0x18004219a  mov     [rax], rbx
0x18004219d  jmp     loc_180041F58
0x1800421a2  cmp     [rbp+250h+var_2A8], r9
0x1800421a6  jz      loc_180042931
0x1800421ac  mov     ecx, 7FFFFFFEh
0x1800421b1  mov     eax, r9d
0x1800421b4  lea     rdx, [r8+0Eh]
0x1800421b8  add     rdx, rax
0x1800421bb  mov     r9d, 0Dh
0x1800421c1  lea     r8, [rsp+350h+pwszDst]
0x1800421c6  test    rcx, rcx
0x1800421c9  jz      short loc_1800421E8
0x1800421cb  movzx   eax, word ptr [rdx]
0x1800421ce  test    ax, ax
0x1800421d1  jz      short loc_1800421E8
0x1800421d3  add     rdx, 2
0x1800421d7  mov     [r8], ax
0x1800421db  add     r8, 2
0x1800421df  dec     rcx
0x1800421e2  sub     r9, 1
0x1800421e6  jnz     short loc_1800421C6
0x1800421e8  lea     rcx, [r8-2]
0x1800421ec  test    r9, r9
0x1800421ef  cmovnz  rcx, r8
0x1800421f3  xor     eax, eax
0x1800421f5  mov     [rcx], ax
0x1800421f8  jmp     loc_1800420E0
0x1800421fd  mov     rax, [rcx]
0x180042200  mov     rax, [rax+10h]
0x180042204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042209  jmp     loc_18004213C
0x18004220e  test    rsi, rsi
0x180042211  jz      loc_1800422F4
0x180042217  cmp     word ptr [rsi], 0Eh
0x18004221b  jb      loc_1800422F4
0x180042221  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow> `wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl(void)'::`2'::impl
0x180042228  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(void)
0x18004222d  movzx   r8d, word ptr [rbx]
0x180042231  test    al, al
0x180042233  jnz     loc_180042870
0x180042239  movzx   r9d, r8w
0x18004223d  mov     rdx, r14
0x180042240  movzx   ecx, r8w
0x180042244  movzx   r10d, word ptr [rcx+rbx-2]
0x18004224a  test    r10w, r10w
0x18004224e  jz      short loc_18004228F
0x180042250  lea     rax, [r10+8]
0x180042254  cmp     rax, rcx
0x180042257  jnb     short loc_18004228F
0x180042259  lea     rdx, [r10+rbx]
0x18004225d  movzx   ecx, word ptr [rdx]
0x180042260  cmp     ecx, 8
0x180042263  jb      loc_180042426
0x180042269  mov     eax, [rdx+4]
0x18004226c  shr     rax, 10h
0x180042270  mov     r11d, 0BEEFh
0x180042276  cmp     ax, r11w
0x18004227a  jnz     loc_180042426
0x180042280  add     ecx, r10d
0x180042283  movzx   eax, r8w
0x180042287  cmp     ecx, eax
0x180042289  ja      loc_180042426
0x18004228f  movzx   ecx, r9w
0x180042293  add     rcx, rbx
0x180042296  test    rdx, rdx
0x180042299  jz      loc_18004236A
0x18004229f  cmp     dword ptr [rdx+4], 0BEEF0004h
0x1800422a6  jnz     loc_1800423BE
0x1800422ac  lea     rcx, [rsi+0Eh]
0x1800422b0  test    rcx, rcx
0x1800422b3  jz      loc_18004285C
0x1800422b9  movzx   edx, word ptr [rsi]
0x1800422bc  add     rdx, 0FFFFFFFFFFFFFFF2h
0x1800422c0  cmp     rdx, 7FFFFFFFh
0x1800422c7  ja      loc_18004285C
0x1800422cd  test    rdx, rdx
0x1800422d0  jz      short loc_1800422E0
0x1800422d2  cmp     byte ptr [rcx], 0
0x1800422d5  jz      short loc_1800422E0
0x1800422d7  inc     rcx
0x1800422da  sub     rdx, 1
0x1800422de  jnz     short loc_1800422D2
0x1800422e0  mov     ecx, 80070057h
0x1800422e5  test    rdx, rdx
0x1800422e8  cmovnz  ecx, r14d
0x1800422ec  test    ecx, ecx
0x1800422ee  jns     loc_180042592
0x1800422f4  mov     rcx, [rbp+258h]; this
0x1800422fb  mov     r9d, 80070057h; char *
0x180042301  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x180042308  mov     edx, 458h; void *
0x18004230d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042312  nop
0x180042313  mov     rcx, [rbp+250h+pv]; pv
0x18004231a  test    rcx, rcx
0x18004231d  jz      short loc_180042325
0x18004231f  call    cs:__imp_CoTaskMemFree
0x180042325  mov     eax, 80070057h
0x18004232a  jmp     loc_180041F6C
0x18004232f  lea     rax, [r9+8]
0x180042333  cmp     rax, rcx
0x180042336  ja      short loc_18004236A
0x180042338  mov     eax, [r9+4]
0x18004233c  shr     rax, 10h
0x180042340  mov     edx, 0BEEFh
0x180042345  cmp     ax, dx
0x180042348  jnz     short loc_18004236A
0x18004234a  movzx   eax, word ptr [r9]
0x18004234e  add     rax, r9
0x180042351  cmp     rax, rcx
0x180042354  ja      short loc_18004236A
0x180042356  cmp     r9, r10
0x180042359  jb      short loc_18004236A
0x18004235b  mov     r8, r9
0x18004235e  mov     rdx, r8
0x180042361  test    r8, r8
0x180042364  jnz     loc_18004229F
0x18004236a  movzx   eax, byte ptr [rsi+2]
0x18004236e  and     al, 34h
  ... truncated ...
```
