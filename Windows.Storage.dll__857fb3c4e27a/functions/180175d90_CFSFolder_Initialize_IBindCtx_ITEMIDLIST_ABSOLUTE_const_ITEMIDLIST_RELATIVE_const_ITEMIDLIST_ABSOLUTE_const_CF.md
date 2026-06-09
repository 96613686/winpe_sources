# CFSFolder::Initialize(IBindCtx *,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_ABSOLUTE const *,CFSFolder &)

- ea: `0x180175d90`
- end: `0x180176940`
- name: `?Initialize@CFSFolder@@UEAAJPEAUIBindCtx@@PEBU_ITEMIDLIST_ABSOLUTE@@PEFBU_ITEMIDLIST_RELATIVE@@1AEAV1@@Z`
- size: `2992`
- prototype: `__int64 __fastcall(CFSFolder *__hidden this, struct IBindCtx *, const struct _ITEMIDLIST_ABSOLUTE *, const struct _ITEMIDLIST_RELATIVE *, const struct _ITEMIDLIST_ABSOLUTE *Src, struct CFSFolder *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800432f0`
- `0x1800a08d0`
- `0x1800a5580`
- `0x180175d90`
- `0x180333018`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x1803a96d9`
- `0x1803a96e5`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18017617a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18017617a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180176166`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180176166`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801766fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801766fc`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180176776`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180176776`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180176648`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180176648`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180176768`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180176768`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x180175f5f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x180175f5f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180176741`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180176741`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18017671e`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18017671e`
- `OLEAUT32!__imp_SysAllocString` at `0x180175f3d`
- `OLEAUT32!__imp_SysAllocString` at `0x180175f3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180175e26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180175e26`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180175e4a`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180175e4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18017613b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180176172`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801765c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801768dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18017613b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180176172`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801765c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801768dc`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x180176562`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x180176562`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180176264`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18017627e`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180176298`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1801762b2`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1801762c1`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180176264`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18017627e`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180176298`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1801762b2`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1801762c1`

## string_xrefs

- `0x18017673a`: `%SystemRoot%\System32\RuntimeBroker.exe`
- `0x1801761fe`: `ItemCacheContext`
- `0x18017626e`: `FSFolder_ConvertToSidString`
- `0x180176250`: `FSFolder_ResolveSidToUserName`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFSFolder::Initialize(
        CFSFolder *this,
        struct IBindCtx *a2,
        const struct _ITEMIDLIST_ABSOLUTE *a3,
        const struct _ITEMIDLIST_RELATIVE *a4,
        const struct _ITEMIDLIST_ABSOLUTE *Src,
        struct CFSFolder *a6)
{
  struct CFSFolder *v9; // r13
  int v10; // eax
  unsigned int v11; // edi
  const struct _ITEMIDLIST_ABSOLUTE *v12; // rdx
  unsigned int v13; // r8d
  __int64 v14; // rcx
  size_t v15; // r12
  void *v16; // rdi
  size_t v17; // r13
  int v18; // edi
  char *v19; // r14
  int v20; // edi
  BSTR v21; // rax
  const WCHAR *v22; // rcx
  __int64 (__fastcall *v23)(char *, const struct _ITEMIDLIST_RELATIVE *, char *); // r13
  void *v24; // r12
  unsigned __int16 v25; // ax
  const struct _ITEMIDLIST_RELATIVE *v26; // rdi
  const struct _ITEMIDLIST_RELATIVE *v27; // r15
  __int64 v28; // rcx
  const struct _ITEMIDLIST_RELATIVE *v29; // rbx
  char IsEnabled; // al
  unsigned __int16 v31; // r8
  unsigned __int16 *v32; // rdx
  __int64 v33; // r9
  unsigned int v34; // ecx
  unsigned __int64 v35; // rcx
  _BYTE *v36; // rcx
  unsigned __int64 v37; // rdx
  int v38; // ecx
  int v39; // r14d
  DWORD LastError; // edi
  _WORD *v42; // rax
  int v43; // edi
  int v44; // edi
  int v45; // edi
  int v46; // edi
  char v47; // di
  char v48; // di
  char v49; // di
  int v50; // edi
  int (__fastcall ***v51)(_QWORD, GUID *, _BYTE *); // rcx
  __int64 v52; // rdx
  unsigned __int16 *v53; // r9
  unsigned __int16 *v54; // r8
  __int16 v55; // r11
  HANDLE CurrentProcess; // rdi
  BOOL FullProcessImageNameW; // eax
  unsigned __int16 v58; // ax
  const struct _ITEMIDLIST_RELATIVE *v59; // rdi
  unsigned __int16 v60; // r9
  unsigned __int16 *v61; // rdx
  __int64 v62; // r8
  unsigned int v63; // ecx
  unsigned __int64 v64; // r8
  unsigned __int16 *v65; // rcx
  unsigned __int16 *v66; // r10
  unsigned __int16 *v67; // r9
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  _BYTE v69[12]; // [rsp+30h] [rbp-D0h] BYREF
  int v70; // [rsp+3Ch] [rbp-C4h]
  LPMALLOC ppMalloc[2]; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR *psz; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Dst[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ExeName[264]; // [rsp+270h] [rbp+170h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4D8h] [rbp+3D8h]

  v9 = a6;
  *(_QWORD *)v69 = a6;
  v10 = (*(__int64 (__fastcall **)(char *, const struct _ITEMIDLIST_ABSOLUTE *))(*((_QWORD *)this - 30) + 32LL))(
          (char *)this - 240,
          a3);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2542,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
      (const char *)(unsigned int)v10,
      bIgnoreCase);
    return v11;
  }
  if ( Src )
  {
    v12 = Src;
    v13 = 2;
    do
    {
      v14 = *(unsigned __int16 *)v12;
      if ( !(_WORD)v14 )
        break;
      v13 += v14;
      v12 = (const struct _ITEMIDLIST_ABSOLUTE *)((char *)v12 + v14);
    }
    while ( v12 );
    v15 = v13;
    v16 = CoTaskMemAlloc(v13);
    if ( !v16 )
    {
      *((_QWORD *)this + 16) = 0;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2547,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
        (const char *)0x8007000ELL,
        bIgnoreCase);
      return 2147942414LL;
    }
    v17 = 0;
    ppMalloc[0] = 0;
    if ( CoGetMalloc(1u, ppMalloc) >= 0 )
    {
      v17 = ((__int64 (__fastcall *)(LPMALLOC, void *))ppMalloc[0]->lpVtbl->GetSize)(ppMalloc[0], v16);
      ((void (__fastcall *)(LPMALLOC))ppMalloc[0]->lpVtbl->Release)(ppMalloc[0]);
    }
    memset_0(v16, 0, v17);
    memcpy_0(v16, Src, v15);
    *((_QWORD *)this + 16) = v16;
    v9 = *(struct CFSFolder **)v69;
  }
  v18 = 32;
  if ( a2
    && (*(_DWORD *)v69 = 16,
        *(_QWORD *)&v69[4] = 0,
        v70 = 0,
        ((int (__fastcall *)(struct IBindCtx *, _BYTE *))a2->lpVtbl->GetBindOptions)(a2, v69) >= 0)
    && (v18 = *(_DWORD *)&v69[8], (*(_DWORD *)&v69[8] & 0x10000) != 0)
    || (*((_DWORD *)this + 73) = v18, a2) )
  {
    ppMalloc[0] = 0;
    *(_QWORD *)v69 = 0;
    if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, _BYTE *))a2->lpVtbl->GetObjectParam)(
           a2,
           L"ItemCacheContext",
           v69) >= 0 )
    {
      v43 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, LPMALLOC *))v69)(
              *(_QWORD *)v69,
              &GUID_0000000e_0000_0000_c000_000000000046,
              ppMalloc);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v69 + 16LL))(*(_QWORD *)v69);
      if ( v43 >= 0 )
      {
        *((_QWORD *)this + 4) = L"FSFolder_ResolveSidToUserName";
        IUnknown_Set((IUnknown **)this + 2, (IUnknown *)ppMalloc[0]);
        *((_QWORD *)this + 7) = L"FSFolder_ConvertToSidString";
        IUnknown_Set((IUnknown **)this + 5, (IUnknown *)ppMalloc[0]);
        *((_QWORD *)this + 10) = L"FSFolder_InplaceShareEngine";
        IUnknown_Set((IUnknown **)this + 8, (IUnknown *)ppMalloc[0]);
        *((_QWORD *)this + 13) = L"FSFolder_SmbShareEngine";
        IUnknown_Set((IUnknown **)this + 11, (IUnknown *)ppMalloc[0]);
        IUnknown_Set((IUnknown **)this + 14, (IUnknown *)ppMalloc[0]);
        ((void (__fastcall *)(LPMALLOC))ppMalloc[0]->lpVtbl->Release)(ppMalloc[0]);
      }
    }
    v44 = 0;
    *(_QWORD *)v69 = 0;
    if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, _BYTE *))a2->lpVtbl->GetObjectParam)(
           a2,
           L"Avoid Drive Restriction Policy",
           v69) >= 0 )
    {
      v44 = 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v69 + 16LL))(*(_QWORD *)v69);
    }
    *((_DWORD *)this + 64) = v44;
    v45 = 0;
    *(_QWORD *)v69 = 0;
    if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, _BYTE *))a2->lpVtbl->GetObjectParam)(
           a2,
           L"Enable Extended DAV Features",
           v69) >= 0 )
    {
      v45 = 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v69 + 16LL))(*(_QWORD *)v69);
    }
    *((_DWORD *)this + 56) &= ~0x20u;
    *((_DWORD *)this + 56) |= 32 * v45;
    v46 = 0;
    *(_QWORD *)v69 = 0;
    if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, _BYTE *))a2->lpVtbl->GetObjectParam)(
           a2,
           L"AssumeWritable",
           v69) >= 0 )
    {
      v46 = 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v69 + 16LL))(*(_QWORD *)v69);
    }
    *((_DWORD *)this + 56) &= ~0x40u;
    *((_DWORD *)this + 56) |= v46 << 6;
    v47 = 0;
    *(_QWORD *)v69 = 0;
    if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, _BYTE *))a2->lpVtbl->GetObjectParam)(
           a2,
           L"Folder is in an aliased location",
           v69) >= 0 )
    {
      v47 = 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v69 + 16LL))(*(_QWORD *)v69);
    }
    *((_BYTE *)this + 228) = v47;
    v48 = 0;
    *(_QWORD *)v69 = 0;
    if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, _BYTE *))a2->lpVtbl->GetObjectParam)(
           a2,
           L"Allow Child Alias Registration",
           v69) >= 0 )
    {
      v48 = 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v69 + 16LL))(*(_QWORD *)v69);
    }
    *((_BYTE *)this + 229) = v48;
    *((_DWORD *)this + 56) &= ~0x80u;
    v49 = 0;
    *(_QWORD *)v69 = 0;
    if ( ((int (__fastcall *)(struct IBindCtx *, const unsigned __int16 *, _BYTE *))a2->lpVtbl->GetObjectParam)(
           a2,
           L"EnableOverlayHandlers",
           v69) >= 0 )
    {
      v49 = 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v69 + 16LL))(*(_QWORD *)v69);
    }
    *((_BYTE *)this + 632) = v49;
    *((_QWORD *)this + 40) = 0;
    *(_QWORD *)v69 = 0;
    if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, _BYTE *))a2->lpVtbl->GetObjectParam)(
           a2,
           L"ParentFolder",
           v69) >= 0 )
    {
      v50 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, char *))v69)(
              *(_QWORD *)v69,
              &GUID_000214e6_0000_0000_c000_000000000046,
              (char *)this + 320);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v69 + 16LL))(*(_QWORD *)v69);
      if ( v50 >= 0 )
      {
        v51 = (int (__fastcall ***)(_QWORD, GUID *, _BYTE *))*((_QWORD *)this + 40);
        *(_QWORD *)v69 = 0;
        if ( v51 && (**v51)(v51, &GUID_c938b119_d3ad_4d02_b5ee_164c2ec8160e, v69) >= 0 )
        {
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v69 + 24LL))(*(_QWORD *)v69);
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v69 + 16LL))(*(_QWORD *)v69);
        }
        *(_OWORD *)ppMalloc = 0;
        if ( !*((_BYTE *)this + 229)
          && (int)IUnknown_GetClassID(*((_QWORD *)this + 40), ppMalloc) >= 0
          && !memcmp_0(ppMalloc, &CLSID_ShellFSFolder, 0x10u) )
        {
          *((_DWORD *)this + 56) |= 0x80u;
        }
      }
    }
  }
  if ( !*((_DWORD *)this + 64) )
  {
    if ( !CallerIdentity::g_fRuntimeBrokerProcessIdInitialize )
    {
      CurrentProcess = GetCurrentProcess();
      LODWORD(ppMalloc[0]) = 260;
      FullProcessImageNameW = QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, (PDWORD)ppMalloc);
      if ( (int)ResultFromWin32Bool(FullProcessImageNameW) >= 0
        && ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\RuntimeBroker.exe", Dst, 0x104u)
        && CompareStringOrdinal(ExeName, -1, Dst, -1, 1) == 2 )
      {
        CallerIdentity::g_dwRuntimeBrokerProcessId = GetProcessId(CurrentProcess);
      }
      CallerIdentity::g_fRuntimeBrokerProcessIdInitialize = 1;
    }
    if ( GetCurrentProcessId() == CallerIdentity::g_dwRuntimeBrokerProcessId )
      *((_DWORD *)this + 64) = 1;
  }
  v19 = (char *)v9 + 312;
  psz = 0;
  v20 = (*(__int64 (__fastcall **)(__int64, const struct _ITEMIDLIST_RELATIVE *, __int64, OLECHAR **))(*((_QWORD *)v9 + 39) + 112LL))(
          (__int64)v9 + 312,
          a4,
          1,
          &psz);
  if ( v20 < 0 )
  {
    v52 = 9550;
LABEL_87:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v52,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
      (const char *)(unsigned int)v20,
      bIgnoreCase);
    if ( psz )
      CoTaskMemFree(psz);
    return (unsigned int)v20;
  }
  v21 = SysAllocString(psz);
  *((_QWORD *)this + 17) = v21;
  if ( v21 )
  {
    v22 = (const WCHAR *)*((_QWORD *)v9 + 58);
    if ( v22 )
      *((_QWORD *)this + 19) = StrDupW(v22);
    v23 = *(__int64 (__fastcall **)(char *, const struct _ITEMIDLIST_RELATIVE *, char *))(*(_QWORD *)v19 + 120LL);
    v24 = (void *)*((_QWORD *)this + 18);
    if ( v24 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v24);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 18) = 0;
    v20 = v23(v19, a4, (char *)this + 144);
    if ( v20 >= 0 )
    {
      if ( !a4 )
        goto LABEL_50;
      v25 = *(_WORD *)a4;
      if ( *(_WORD *)a4 )
      {
        do
        {
          v26 = a4;
          a4 = (const struct _ITEMIDLIST_RELATIVE *)((char *)a4 + v25);
          v25 = *(_WORD *)a4;
        }
        while ( *(_WORD *)a4 );
      }
      else
      {
        v26 = a4;
      }
      v27 = 0;
      if ( v26 )
      {
        v28 = *(unsigned __int16 *)v26;
        if ( (unsigned int)v28 > 0xB )
        {
          if ( (*((_BYTE *)v26 + 2) & 0x70) == 0x30 )
          {
            v27 = v26;
            v29 = v26;
            goto LABEL_31;
          }
          if ( *(_DWORD *)((char *)v26 + 6) == 1179862595 )
          {
            if ( *((unsigned __int16 *)v26 + 2) > (unsigned __int64)(v28 - 4) )
              goto LABEL_50;
            v27 = (const struct _ITEMIDLIST_RELATIVE *)((char *)v26 + 10);
            if ( !IDListContainerIsConsistent((LPCITEMIDLIST)((char *)v26 + 10), *((unsigned __int16 *)v26 + 2))
              || v55 != *(_WORD *)v27 + 6
              || (unsigned __int16)(*(_WORD *)v27 + 6) < *(_WORD *)v27 )
            {
              goto LABEL_50;
            }
          }
        }
      }
      if ( !v27 )
        goto LABEL_50;
      v29 = v27;
LABEL_31:
      if ( *(_WORD *)v27 < 0xEu )
        goto LABEL_50;
      if ( !v26 )
        goto LABEL_55;
      if ( !*(_WORD *)v26 )
        goto LABEL_55;
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl'::`2'::impl);
      v31 = *(_WORD *)v26;
      if ( IsEnabled )
      {
        if ( v31 < 2u )
          goto LABEL_55;
      }
      v32 = 0;
      v33 = *(unsigned __int16 *)((char *)v26 + v31 - 2);
      if ( (_WORD)v33 )
      {
        if ( v33 + 8 < (unsigned __int64)v31 )
        {
          v32 = (unsigned __int16 *)((char *)v26 + v33);
          v34 = *(unsigned __int16 *)((char *)v26 + v33);
          if ( v34 < 8 || HIWORD(*((_DWORD *)v32 + 1)) != 0xBEEF || (unsigned int)v33 + v34 > v31 )
            v32 = 0;
        }
      }
      v35 = (unsigned __int64)v26 + v31;
      if ( v32 )
      {
        while ( *((_DWORD *)v32 + 1) != -1091633148 )
        {
          v53 = 0;
          if ( (unsigned __int64)(v32 + 4) <= v35 )
          {
            v54 = (unsigned __int16 *)((char *)v32 + *v32);
            if ( v54 == (unsigned __int16 *)v35 )
              goto LABEL_55;
            if ( (unsigned __int64)v54 <= v35 )
            {
              if ( (unsigned __int64)(v54 + 4) > v35
                || HIWORD(*((_DWORD *)v54 + 1)) != 0xBEEF
                || (unsigned __int64)v54 + *v54 > v35
                || v54 < v32 + 4 )
              {
                goto LABEL_55;
              }
              v53 = (unsigned __int16 *)((char *)v32 + *v32);
            }
          }
          v32 = v53;
          if ( !v53 )
            goto LABEL_55;
        }
      }
      else
      {
LABEL_55:
        if ( (*((_BYTE *)v27 + 2) & 0x34) == 0x34 )
        {
          v42 = (_WORD *)((char *)v27 + 14);
          if ( v27 != (const struct _ITEMIDLIST_RELATIVE *)-14LL )
          {
            v37 = ((unsigned __int64)*(unsigned __int16 *)v27 - 14) >> 1;
            if ( v37 <= 0x7FFFFFFF )
            {
              for ( ; v37; --v37 )
              {
                if ( !*v42 )
                  break;
                ++v42;
              }
LABEL_47:
              v38 = -2147024809;
              if ( v37 )
                v38 = 0;
LABEL_49:
              if ( v38 >= 0 )
              {
                v39 = *((unsigned __int16 *)v27 + 6);
                v58 = *(_WORD *)v27;
                if ( !*(_WORD *)v27 )
                  goto LABEL_51;
                do
                {
                  v59 = v29;
                  v29 = (const struct _ITEMIDLIST_RELATIVE *)((char *)v29 + v58);
                  v58 = *(_WORD *)v29;
                }
                while ( *(_WORD *)v29 );
                if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl'::`2'::impl) )
                {
                  if ( !v59 || (v60 = *(_WORD *)v59, *(_WORD *)v59 < 2u) )
                  {
LABEL_51:
                    *((_DWORD *)this + 45) = v39;
                    *((_DWORD *)this + 56) &= ~0x100u;
                    *((_DWORD *)this + 56) |= *((_QWORD *)this + 16) != 0 ? 0x100 : 0;
                    if ( psz )
                      CoTaskMemFree(psz);
                    return 0;
                  }
                }
                else
                {
                  v60 = *(_WORD *)v59;
                }
                v61 = 0;
                v62 = *(unsigned __int16 *)((char *)v59 + v60 - 2);
                if ( (_WORD)v62 )
                {
                  if ( v62 + 8 < (unsigned __int64)v60 )
                  {
                    v61 = (unsigned __int16 *)((char *)v59 + v62);
                    v63 = *(unsigned __int16 *)((char *)v59 + v62);
                    if ( v63 < 8 || HIWORD(*((_DWORD *)v61 + 1)) != 0xBEEF || (unsigned int)v62 + v63 > v60 )
                      v61 = 0;
                  }
                }
                v64 = (unsigned __int64)v59 + *(unsigned __int16 *)v59;
                if ( v61 )
                {
                  while ( 1 )
                  {
                    v65 = v61 + 4;
                    if ( *((_DWORD *)v61 + 1) == -1091633111 )
                      break;
                    v66 = 0;
                    if ( (unsigned __int64)v65 <= v64 )
                    {
                      v67 = (unsigned __int16 *)((char *)v61 + *v61);
                      if ( v67 == (unsigned __int16 *)v64 )
                        goto LABEL_51;
                      if ( (unsigned __int64)v67 <= v64 )
                      {
                        if ( (unsigned __int64)(v67 + 4) > v64
                          || HIWORD(*((_DWORD *)v67 + 1)) != 0xBEEF
                          || (unsigned __int64)v67 + *v67 > v64
                          || v67 < v65 )
                        {
                          goto LABEL_51;
                        }
                        v66 = (unsigned __int16 *)((char *)v61 + *v61);
                      }
                    }
                    v61 = v66;
                    if ( !v66 )
                      goto LABEL_51;
                  }
                  v39 = *((unsigned __int16 *)v27 + 6) | (*v65 << 16);
                }
                goto LABEL_51;
              }
LABEL_50:
              v39 = 0;
              goto LABEL_51;
            }
          }
LABEL_144:
          v38 = -2147024809;
          goto LABEL_49;
        }
      }
      v36 = (char *)v27 + 14;
      if ( v27 != (const struct _ITEMIDLIST_RELATIVE *)-14LL )
      {
        v37 = *(unsigned __int16 *)v27 - 14LL;
        if ( v37 <= 0x7FFFFFFF )
        {
          if ( *(_WORD *)v27 != 14 )
          {
            do
            {
              if ( !*v36 )
                break;
              ++v36;
              --v37;
            }
            while ( v37 );
          }
          goto LABEL_47;
        }
      }
      goto LABEL_144;
    }
    v52 = 9562;
    goto LABEL_87;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2553,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
    (const char *)0x8007000ELL,
    bIgnoreCase);
  if ( psz )
    CoTaskMemFree(psz);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180175d90  push    rbp
0x180175d92  push    rbx
0x180175d93  push    rsi
0x180175d94  push    rdi
0x180175d95  push    r12
0x180175d97  push    r13
0x180175d99  push    r14
0x180175d9b  push    r15
0x180175d9d  lea     rbp, [rsp-398h]
0x180175da5  sub     rsp, 498h
0x180175dac  mov     rax, cs:__security_cookie
0x180175db3  xor     rax, rsp
0x180175db6  mov     [rbp+3D0h+var_50], rax
0x180175dbd  mov     rbx, r9
0x180175dc0  mov     r14, rdx
0x180175dc3  mov     rsi, rcx
0x180175dc6  mov     r15, [rbp+3D0h+Src]
0x180175dcd  mov     r13, [rbp+3D0h+arg_28]
0x180175dd4  mov     [rsp+4D0h+var_4A0], r13
0x180175dd9  add     rcx, 0FFFFFFFFFFFFFF10h
0x180175de0  mov     rax, [rcx]
0x180175de3  mov     rdx, r8
0x180175de6  mov     rax, [rax+20h]
0x180175dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180175def  mov     edi, eax
0x180175df1  test    eax, eax
0x180175df3  js      loc_1801768EC
0x180175df9  xor     r12d, r12d
0x180175dfc  test    r15, r15
0x180175dff  jz      loc_180175EA6
0x180175e05  mov     rdx, r15
0x180175e08  mov     r8d, 2
0x180175e0e  xchg    ax, ax
0x180175e10  movzx   ecx, word ptr [rdx]
0x180175e13  test    cx, cx
0x180175e16  jz      short loc_180175E20
0x180175e18  add     r8d, ecx
0x180175e1b  add     rdx, rcx
0x180175e1e  jnz     short loc_180175E10
0x180175e20  mov     r12d, r8d
0x180175e23  mov     ecx, r8d; cb
0x180175e26  call    cs:__imp_CoTaskMemAlloc
0x180175e2c  mov     rdi, rax
0x180175e2f  test    rax, rax
0x180175e32  jz      loc_1801766CD
0x180175e38  xor     r13d, r13d
0x180175e3b  mov     [rsp+4D0h+ppMalloc], r13
0x180175e40  lea     rdx, [rsp+4D0h+ppMalloc]; ppMalloc
0x180175e45  mov     ecx, 1; dwMemContext
0x180175e4a  call    cs:__imp_CoGetMalloc
0x180175e50  test    eax, eax
0x180175e52  js      short loc_180175E7C
0x180175e54  mov     rcx, [rsp+4D0h+ppMalloc]
0x180175e59  mov     rax, [rcx]
0x180175e5c  mov     rdx, rdi
0x180175e5f  mov     rax, [rax+30h]
0x180175e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180175e68  mov     r13, rax
0x180175e6b  mov     rcx, [rsp+4D0h+ppMalloc]
0x180175e70  mov     r9, [rcx]
0x180175e73  mov     rax, [r9+10h]
0x180175e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180175e7c  mov     r8, r13; Size
0x180175e7f  xor     edx, edx; Val
0x180175e81  mov     rcx, rdi; void *
0x180175e84  call    memset_0
0x180175e89  mov     r8, r12; Size
0x180175e8c  mov     rdx, r15; Src
0x180175e8f  mov     rcx, rdi; void *
0x180175e92  call    memcpy_0
0x180175e97  mov     [rsi+80h], rdi
0x180175e9e  mov     r13, [rsp+4D0h+var_4A0]
0x180175ea3  xor     r12d, r12d
0x180175ea6  mov     edi, 20h ; ' '
0x180175eab  test    r14, r14
0x180175eae  jz      short loc_180175EE9
0x180175eb0  mov     dword ptr [rsp+4D0h+var_4A0], 10h
0x180175eb8  xor     eax, eax
0x180175eba  mov     [rsp+4D0h+var_4A0+4], rax
0x180175ebf  mov     [rsp+4D0h+var_494], eax
0x180175ec3  mov     rax, [r14]
0x180175ec6  lea     rdx, [rsp+4D0h+var_4A0]
0x180175ecb  mov     rcx, r14
0x180175ece  mov     rax, [rax+38h]
0x180175ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180175ed7  test    eax, eax
0x180175ed9  js      short loc_180175EE9
0x180175edb  mov     edi, [rsp+4D0h+var_498]
0x180175edf  bt      edi, 10h
0x180175ee3  jb      loc_1801761EC
0x180175ee9  mov     [rsi+124h], edi
0x180175eef  test    r14, r14
0x180175ef2  jnz     loc_1801761EC
0x180175ef8  cmp     dword ptr [rsi+100h], 0
0x180175eff  jz      loc_18017663B
0x180175f05  lea     r14, [r13+138h]
0x180175f0c  mov     [rsp+4D0h+psz], r12
0x180175f11  mov     rax, [r14]
0x180175f14  lea     r9, [rsp+4D0h+psz]
0x180175f19  mov     r8d, 1
0x180175f1f  mov     rdx, rbx
0x180175f22  mov     rcx, r14
0x180175f25  mov     rax, [rax+70h]
0x180175f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180175f2e  mov     edi, eax
0x180175f30  test    eax, eax
0x180175f32  js      loc_180176935
0x180175f38  mov     rcx, [rsp+4D0h+psz]; psz
0x180175f3d  call    cs:__imp_SysAllocString
0x180175f43  mov     [rsi+88h], rax
0x180175f4a  test    rax, rax
0x180175f4d  jz      loc_1801768B3
0x180175f53  mov     rcx, [r13+1D0h]; pszSrch
0x180175f5a  test    rcx, rcx
0x180175f5d  jz      short loc_180175F6C
0x180175f5f  call    cs:__imp_StrDupW
0x180175f65  mov     [rsi+98h], rax
0x180175f6c  mov     rax, [r14]
0x180175f6f  mov     r13, [rax+78h]
0x180175f73  mov     r12, [rsi+90h]
0x180175f7a  test    r12, r12
0x180175f7d  jnz     loc_180176166
0x180175f83  mov     qword ptr [rsi+90h], 0
0x180175f8e  lea     r8, [rsi+90h]
0x180175f95  mov     rdx, rbx
0x180175f98  mov     rcx, r14
0x180175f9b  mov     rax, r13
0x180175f9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180175fa3  mov     edi, eax
0x180175fa5  test    eax, eax
0x180175fa7  js      loc_18017659E
0x180175fad  test    rbx, rbx
0x180175fb0  jz      loc_180176105
0x180175fb6  movzx   eax, word ptr [rbx]
0x180175fb9  test    ax, ax
0x180175fbc  jz      loc_180176670
0x180175fc2  nop     dword ptr [rax+00h]
0x180175fc6  nop     word ptr [rax+rax+00000000h]
0x180175fd0  mov     rdi, rbx
0x180175fd3  movzx   eax, ax
0x180175fd6  add     rbx, rax
0x180175fd9  movzx   eax, word ptr [rbx]
0x180175fdc  test    ax, ax
0x180175fdf  jnz     short loc_180175FD0
0x180175fe1  xor     r15d, r15d
0x180175fe4  test    rdi, rdi
0x180175fe7  jz      short loc_180176007
0x180175fe9  movzx   ecx, word ptr [rdi]
0x180175fec  cmp     ecx, 0Bh
0x180175fef  jbe     short loc_180176007
0x180175ff1  movzx   eax, byte ptr [rdi+2]
0x180175ff5  and     al, 70h
0x180175ff7  cmp     al, 30h ; '0'
0x180175ff9  jnz     loc_180176678
0x180175fff  mov     r15, rdi
0x180176002  mov     rbx, rdi
0x180176005  jmp     short loc_180176013
0x180176007  test    r15, r15
0x18017600a  jz      loc_180176105
0x180176010  mov     rbx, r15
0x180176013  cmp     word ptr [r15], 0Eh
0x180176018  jb      loc_180176105
0x18017601e  test    rdi, rdi
0x180176021  jz      loc_180176190
0x180176027  cmp     word ptr [rdi], 0
0x18017602b  jz      loc_180176190
0x180176031  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow> `wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl(void)'::`2'::impl
0x180176038  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(void)
0x18017603d  movzx   r8d, word ptr [rdi]
0x180176041  test    al, al
0x180176043  jnz     loc_180176185
0x180176049  movzx   r11d, r8w
0x18017604d  xor     edx, edx
0x18017604f  movzx   ecx, r8w
0x180176053  movzx   r9d, word ptr [rcx+rdi-2]
0x180176059  mov     r12d, 0BEEFh
0x18017605f  test    r9w, r9w
0x180176063  jz      short loc_18017609E
0x180176065  lea     rax, [r9+8]
0x180176069  cmp     rax, rcx
0x18017606c  jnb     short loc_18017609E
0x18017606e  lea     rdx, [r9+rdi]
0x180176072  movzx   ecx, word ptr [rdx]
0x180176075  cmp     ecx, 8
0x180176078  jb      loc_180176669
0x18017607e  mov     eax, [rdx+4]
0x180176081  shr     rax, 10h
0x180176085  cmp     ax, r12w
0x180176089  jnz     loc_180176669
0x18017608f  add     ecx, r9d
0x180176092  movzx   eax, r8w
0x180176096  cmp     ecx, eax
0x180176098  ja      loc_180176669
0x18017609e  movzx   ecx, r11w
0x1801760a2  add     rcx, rdi
0x1801760a5  test    rdx, rdx
0x1801760a8  jz      loc_180176196
0x1801760ae  cmp     dword ptr [rdx+4], 0BEEF0004h
0x1801760b5  jnz     loc_1801765D1
0x1801760bb  lea     rcx, [r15+0Eh]
0x1801760bf  test    rcx, rcx
0x1801760c2  jz      loc_18017690E
0x1801760c8  movzx   edx, word ptr [r15]
0x1801760cc  add     rdx, 0FFFFFFFFFFFFFFF2h
0x1801760d0  cmp     rdx, 7FFFFFFFh
0x1801760d7  ja      loc_18017690E
0x1801760dd  test    rdx, rdx
0x1801760e0  jz      short loc_1801760F0
0x1801760e2  cmp     byte ptr [rcx], 0
0x1801760e5  jz      short loc_1801760F0
0x1801760e7  inc     rcx
0x1801760ea  sub     rdx, 1
0x1801760ee  jnz     short loc_1801760E2
0x1801760f0  xor     eax, eax
0x1801760f2  mov     ecx, 80070057h
0x1801760f7  test    rdx, rdx
0x1801760fa  cmovnz  ecx, eax
0x1801760fd  test    ecx, ecx
0x1801760ff  jns     loc_18017678E
0x180176105  xor     r14d, r14d
0x180176108  mov     [rsi+0B4h], r14d
0x18017610f  and     dword ptr [rsi+0E0h], 0FFFFFEFFh
0x180176119  mov     rax, [rsi+80h]
0x180176120  neg     rax
0x180176123  sbb     ecx, ecx
0x180176125  and     ecx, 100h
0x18017612b  or      [rsi+0E0h], ecx
0x180176131  mov     rcx, [rsp+4D0h+psz]; pv
0x180176136  test    rcx, rcx
0x180176139  jz      short loc_180176141
0x18017613b  call    cs:__imp_CoTaskMemFree
0x180176141  xor     eax, eax
0x180176143  mov     rcx, [rbp+3D0h+var_50]
0x18017614a  xor     rcx, rsp; StackCookie
0x18017614d  call    __security_check_cookie
0x180176152  add     rsp, 498h
0x180176159  pop     r15
0x18017615b  pop     r14
0x18017615d  pop     r13
0x18017615f  pop     r12
0x180176161  pop     rdi
0x180176162  pop     rsi
0x180176163  pop     rbx
0x180176164  pop     rbp
0x180176165  retn
0x180176166  call    cs:__imp_GetLastError
0x18017616c  nop
0x18017616d  mov     edi, eax
0x18017616f  mov     rcx, r12; pv
0x180176172  call    cs:__imp_CoTaskMemFree
0x180176178  mov     ecx, edi; dwErrCode
0x18017617a  call    cs:__imp_SetLastError
0x180176180  jmp     loc_180175F83
0x180176185  cmp     r8w, 2
0x18017618a  jnb     loc_180176049
0x180176190  mov     r12d, 0BEEFh
0x180176196  movzx   eax, byte ptr [r15+2]
0x18017619b  and     al, 34h
0x18017619d  cmp     al, 34h ; '4'
0x18017619f  jnz     loc_1801760BB
0x1801761a5  lea     rax, [r15+0Eh]
0x1801761a9  test    rax, rax
0x1801761ac  jz      loc_18017690E
0x1801761b2  movzx   edx, word ptr [r15]
0x1801761b6  sub     rdx, 0Eh
0x1801761ba  shr     rdx, 1
0x1801761bd  cmp     rdx, 7FFFFFFFh
0x1801761c4  ja      loc_18017690E
0x1801761ca  test    rdx, rdx
0x1801761cd  jz      loc_1801760F0
0x1801761d3  cmp     word ptr [rax], 0
0x1801761d7  jz      loc_1801760F0
0x1801761dd  add     rax, 2
0x1801761e1  sub     rdx, 1
0x1801761e5  jnz     short loc_1801761D3
0x1801761e7  jmp     loc_1801760F0
0x1801761ec  mov     [rsp+4D0h+ppMalloc], r12
0x1801761f1  mov     [rsp+4D0h+var_4A0], r12
0x1801761f6  mov     rax, [r14]
0x1801761f9  lea     r8, [rsp+4D0h+var_4A0]
0x1801761fe  lea     rdx, aItemcacheconte; "ItemCacheContext"
0x180176205  mov     rcx, r14
0x180176208  mov     rax, [rax+50h]
0x18017620c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180176211  test    eax, eax
0x180176213  js      loc_1801762D8
0x180176219  mov     rcx, [rsp+4D0h+var_4A0]
0x18017621e  mov     rax, [rcx]
0x180176221  lea     r8, [rsp+4D0h+ppMalloc]
0x180176226  lea     rdx, _GUID_0000000e_0000_0000_c000_000000000046
0x18017622d  mov     rax, [rax]
0x180176230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180176235  mov     edi, eax
0x180176237  mov     rcx, [rsp+4D0h+var_4A0]
0x18017623c  mov     rdx, [rcx]
0x18017623f  mov     rax, [rdx+10h]
0x180176243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180176248  test    edi, edi
0x18017624a  js      loc_1801762D8
0x180176250  lea     rax, aFsfolderResolv; "FSFolder_ResolveSidToUserName"
  ... truncated ...
```
