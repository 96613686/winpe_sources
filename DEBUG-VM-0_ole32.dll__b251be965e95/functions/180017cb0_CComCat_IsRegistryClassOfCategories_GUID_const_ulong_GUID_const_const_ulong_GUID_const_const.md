# CComCat::IsRegistryClassOfCategories(_GUID const &,ulong,_GUID const * const,ulong,_GUID const * const)

- ea: `0x180017cb0`
- end: `0x1800185e4`
- name: `?IsRegistryClassOfCategories@CComCat@@SAJAEBU_GUID@@KQEBU2@K1@Z`
- size: `2356`
- prototype: `HRESULT __fastcall(const _GUID *clsid, unsigned int cImplemented, const _GUID *rgcatidImpl, unsigned int cRequired, const _GUID *rgcatidReq)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180017940`
- `0x180019f40`

## callees

- `0x180017c88`
- `0x180017cb0`
- `0x1800185ec`
- `0x18001a3c8`
- `0x18001b810`
- `0x1800472ec`
- `0x18004e8f0`
- `0x18004fdfc`
- `0x180052390`
- `0x180053014`
- `0x1800aa558`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018530`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018530`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017fc6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018102`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001819f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800181b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001827b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800183f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001844f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001845a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800184b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800184c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800184db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001858a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018595`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800185a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800185bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800185cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017fc6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018102`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001819f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800181b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001827b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800183f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001844f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001845a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800184b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800184c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800184db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001858a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018595`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800185a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800185bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800185cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017f1c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017f5c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800180ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001849b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001850a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017f1c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017f5c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800180ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001849b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001850a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180017ea4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180017ea4`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x180017d1e`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x1800182db`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x180017d1e`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x1800182db`

## string_xrefs

- `0x180017da5`: `com\ole32\comcat\src\comcat.cpp`
- `0x1800181f7`: `com\ole32\comcat\src\comcat.cpp`
- `0x1800182f2`: `com\ole32\comcat\src\comcat.cpp`
- `0x18001834e`: `com\ole32\comcat\src\comcat.cpp`
- `0x180018425`: `com\ole32\comcat\src\comcat.cpp`

## pseudocode

```c
__int64 __fastcall CComCat::IsRegistryClassOfCategories(
        _GUID *clsid,
        unsigned int cImplemented,
        _GUID *rgcatidImpl,
        unsigned int cRequired,
        const _GUID *rgcatidReq)
{
  __int64 v7; // rsi
  __int64 v8; // r13
  const wchar_t *v9; // r8
  __int64 v10; // rax
  wchar_t *v11; // r9
  __int64 v12; // rdx
  wchar_t *v13; // rcx
  unsigned int v14; // r14d
  HRESULT v15; // ebx
  unsigned int v16; // edx
  __int64 v18; // rdx
  wchar_t *v19; // rax
  const wchar_t *v20; // r15
  __int64 v21; // rcx
  const wchar_t *v22; // r9
  wchar_t *v23; // r8
  wchar_t *v24; // rcx
  unsigned int j; // edi
  unsigned int v26; // eax
  __int64 v27; // rcx
  wchar_t *v28; // rdx
  __int64 v29; // r8
  wchar_t *v30; // r9
  wchar_t *v31; // rcx
  unsigned int v32; // edi
  unsigned int k; // ebx
  const tagCATEGORYINFO *v34; // r8
  HKEY v35; // rcx
  __int64 v36; // rax
  wchar_t *v37; // rax
  __int64 v38; // rdx
  const wchar_t *v39; // rdi
  __int64 v40; // rcx
  const wchar_t *v41; // r9
  wchar_t *v42; // r8
  wchar_t *v43; // rcx
  wchar_t *v44; // rax
  wchar_t *v45; // rdx
  wchar_t *v46; // rcx
  _GUID *v47; // rbx
  _GUID *v48; // rax
  int v49; // eax
  int v50; // ecx
  bool v51; // zf
  HKEY__ *v52; // rcx
  HKEY__ *m_ptr; // rcx
  HRESULT v54; // eax
  IEnterpriseDropTarget *ptr; // rcx
  const _GUID *v56; // rcx
  __int64 v57; // rax
  unsigned int i; // edx
  HRESULT v59; // eax
  unsigned int v60; // esi
  LSTATUS v61; // eax
  CEnumCategoriesOfClass *v62; // rax
  CEnumCategoriesOfClass *v63; // rax
  CEnumCategoriesOfClass *v64; // rbx
  struct IUnknownVtbl *lpVtbl; // rcx
  unsigned int v66; // edx
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (__cdecl*)(HKEY__ *),&RegCloseKey,wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t> > > hkeyClsid; // [rsp+30h] [rbp-D0h] BYREF
  bool v68; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int celtFetched; // [rsp+40h] [rbp-C0h] BYREF
  IEnumGUID *ppenumCatid; // [rsp+48h] [rbp-B8h] BYREF
  Microsoft::WRL::ComPtr<IEnterpriseDropTarget> v71; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HKEY__ *hkeyImpCat; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v74; // [rsp+68h] [rbp-98h]
  _GUID *v75; // [rsp+70h] [rbp-90h] BYREF
  HKEY__ *hKeyReq; // [rsp+78h] [rbp-88h] BYREF
  _GUID guid[1]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t wszKey[260]; // [rsp+90h] [rbp-70h] BYREF
  OLECHAR wszCat[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  void *retaddr; // [rsp+4F8h] [rbp+3F8h]

  hKey = (HKEY)rgcatidImpl;
  celtFetched = cImplemented;
  v75 = clsid;
  v74 = cRequired;
  memset_0(wszKey, 0, sizeof(wszKey));
  hkeyClsid.m_ptr = 0;
  if ( (int)InternalRegOpenClassKey(clsid, 131097, &hkeyClsid) < 0 )
    goto LABEL_83;
  v7 = 2147483646;
  v8 = 260;
  if ( cImplemented - 1 > 0xFFFFFFFD )
  {
    v14 = -2147024774;
    v20 = L"\\";
LABEL_53:
    if ( v74 == -1 )
      goto LABEL_94;
    hKeyReq = 0;
    v37 = wszKey;
    v38 = 260;
    do
    {
      if ( !*v37 )
        break;
      ++v37;
      --v38;
    }
    while ( v38 );
    v15 = -2147024809;
    if ( !v38 )
      goto LABEL_139;
    v39 = Com::Catalog::Constants::Required_Categories;
    v40 = 2147483646;
    v41 = Com::Catalog::Constants::Required_Categories;
    v42 = wszCat - v38 + 3;
    do
    {
      if ( !v40 )
        break;
      if ( !*v41 )
        break;
      *v42++ = *v41++;
      --v40;
      --v38;
    }
    while ( v38 );
    v43 = v42 - 1;
    v15 = -2147024774;
    if ( v38 )
    {
      v43 = v42;
      v15 = 0;
    }
    *v43 = 0;
    if ( !v38 )
    {
LABEL_139:
      v16 = 974;
      goto LABEL_13;
    }
    v44 = wszKey;
    do
    {
      if ( !*v44 )
        break;
      ++v44;
      --v8;
    }
    while ( v8 );
    if ( v8 )
    {
      v45 = wszCat - v8 + 3;
      do
      {
        if ( !v7 )
          break;
        if ( !*v20 )
          break;
        *v45++ = *v20++;
        --v7;
        --v8;
      }
      while ( v8 );
      v46 = v45 - 1;
      if ( v8 )
      {
        v46 = v45;
        v14 = 0;
      }
      *v46 = 0;
      if ( v8 )
      {
        if ( RegOpenKeyExW(hkeyClsid.m_ptr, wszKey, 0, 0x20019u, &hKeyReq) )
        {
          m_ptr = hkeyClsid.m_ptr;
          if ( hkeyClsid.m_ptr )
LABEL_95:
            RegCloseKey(m_ptr);
          return 0;
        }
        RegCloseKey(hKeyReq);
        ppenumCatid = 0;
        v71.ptr_ = 0;
        Microsoft::WRL::ComPtr<IEnterpriseDropTarget>::InternalRelease(&v71);
        v47 = v75;
        if ( GetClassInfoWithInprocOrLocalServer(v75, 0, &GUID_00d489b0_06a7_0074_9ce0_065132561673, (void **)&v71.ptr_) < 0 )
        {
          hKey = 0;
          v54 = InternalRegOpenClassKey(v47, 131097, &hKey);
          v15 = v54;
          if ( v54 < 0 )
          {
            wil::details::in1diag3::Return_Hr(retaddr, 0x479u, "com\\ole32\\comcat\\src\\comcat.cpp", v54);
            if ( hKey )
              RegCloseKey(hKey);
            ptr = v71.ptr_;
            if ( v71.ptr_ )
            {
              v71.ptr_ = 0;
              ((void (__fastcall *)(IEnterpriseDropTarget *))ptr->lpVtbl->Release)(ptr);
              v16 = 990;
              goto LABEL_13;
            }
            goto LABEL_105;
          }
          hkeyImpCat = 0;
          v61 = RegOpenKeyExW(hKey, Com::Catalog::Constants::Required_Categories, 0, 0x20019u, &hkeyImpCat);
          if ( !v61 )
          {
            ppenumCatid = 0;
            v62 = (CEnumCategoriesOfClass *)HeapAlloc(g_hHeap, 0, 0x40u);
            if ( v62 )
            {
              CEnumCategoriesOfClass::CEnumCategoriesOfClass(v62);
              v64 = v63;
              if ( v63 )
              {
                v63->m_hKey = hkeyImpCat;
                lpVtbl = v63->lpVtbl;
                v63->m_bMapOldKeys = 0;
                if ( ((int (__fastcall *)(CEnumCategoriesOfClass *, GUID *, IEnumGUID **))lpVtbl->QueryInterface)(
                       v63,
                       &IID_IEnumGUID,
                       &ppenumCatid) < 0 )
                {
                  CEnumCategoriesOfClass::`scalar deleting destructor'(v64, v66);
                  if ( hKey )
                    RegCloseKey(hKey);
                  Microsoft::WRL::ComPtr<IEnterpriseDropTarget>::InternalRelease(&v71);
                  v16 = 990;
                  v15 = -2147418113;
                  goto LABEL_13;
                }
                if ( hKey )
                  RegCloseKey(hKey);
                Microsoft::WRL::ComPtr<IEnterpriseDropTarget>::InternalRelease(&v71);
                goto LABEL_91;
              }
            }
            RegCloseKey(hkeyImpCat);
            if ( hKey )
              RegCloseKey(hKey);
            Microsoft::WRL::ComPtr<IEnterpriseDropTarget>::InternalRelease(&v71);
            v15 = -2147024882;
LABEL_105:
            v16 = 990;
            goto LABEL_13;
          }
          v15 = wil::details::in1diag3::Return_Win32(retaddr, 0x47Cu, "com\\ole32\\comcat\\src\\comcat.cpp", v61);
          if ( hKey )
            RegCloseKey(hKey);
        }
        else
        {
          v48 = (_GUID *)((char *)Com::Catalog::Constants::Implemented_Categories
                        - (char *)Com::Catalog::Constants::Required_Categories);
          v75 = (_GUID *)((char *)Com::Catalog::Constants::Implemented_Categories
                        - (char *)Com::Catalog::Constants::Required_Categories);
          do
          {
            v49 = *(unsigned __int16 *)((char *)&v48->Data1 + (_QWORD)v39);
            v50 = *v39 - v49;
            if ( v50 )
              break;
            ++v39;
            v51 = v49 == 0;
            v48 = v75;
          }
          while ( !v51 );
          v75 = (_GUID *)v71.ptr_;
          v68 = v50 == 0;
          v15 = Microsoft::WRL::Details::MakeAndInitialize<CEnumCategoriesOfCatalogClass,IEnumGUID,IComClassCategoryInfo * &,bool &>(
                  &ppenumCatid,
                  (IComClassCategoryInfo **)&v75,
                  &v68);
        }
        Microsoft::WRL::ComPtr<IEnterpriseDropTarget>::InternalRelease(&v71);
        if ( v15 >= 0 )
        {
LABEL_91:
          celtFetched = 0;
LABEL_92:
          if ( !((unsigned int (__fastcall *)(IEnumGUID *, __int64, _GUID *, unsigned int *))ppenumCatid->lpVtbl[1].QueryInterface)(
                  ppenumCatid,
                  1,
                  guid,
                  &celtFetched) )
          {
            for ( i = 0; i < v74; ++i )
            {
              v56 = &rgcatidReq[i];
              v57 = *(_QWORD *)&guid[0].Data1 - *(_QWORD *)&v56->Data1;
              if ( *(_QWORD *)&guid[0].Data1 == *(_QWORD *)&v56->Data1 )
                v57 = *(_QWORD *)guid[0].Data4 - *(_QWORD *)v56->Data4;
              if ( !v57 )
                goto LABEL_92;
            }
            ((void (__fastcall *)(IEnumGUID *))ppenumCatid->lpVtbl->Release)(ppenumCatid);
            v52 = hkeyClsid.m_ptr;
            if ( !hkeyClsid.m_ptr )
              return 1;
            goto LABEL_84;
          }
          ((void (__fastcall *)(IEnumGUID *))ppenumCatid->lpVtbl->Release)(ppenumCatid);
LABEL_94:
          m_ptr = hkeyClsid.m_ptr;
          if ( hkeyClsid.m_ptr )
            goto LABEL_95;
          return 0;
        }
        goto LABEL_105;
      }
    }
    else
    {
      v14 = -2147024809;
    }
    wil::details::in1diag3::Return_Hr(retaddr, 0x3CFu, "com\\ole32\\comcat\\src\\comcat.cpp", v14);
    if ( hkeyClsid.m_ptr )
      RegCloseKey(hkeyClsid.m_ptr);
    return v14;
  }
  ppenumCatid = 0;
  v9 = Com::Catalog::Constants::Implemented_Categories;
  v10 = 2147483646;
  v11 = wszKey;
  v12 = 260;
  do
  {
    if ( !v10 )
      break;
    if ( !*v9 )
      break;
    *v11++ = *v9++;
    --v10;
    --v12;
  }
  while ( v12 );
  v13 = v11 - 1;
  v14 = -2147024774;
  if ( v12 )
    v13 = v11;
  v15 = -2147024774;
  if ( v12 )
    v15 = 0;
  *v13 = 0;
  if ( !v12 )
  {
    v16 = 875;
    goto LABEL_13;
  }
  v18 = 260;
  v19 = wszKey;
  do
  {
    if ( !*v19 )
      break;
    ++v19;
    --v18;
  }
  while ( v18 );
  v15 = -2147024809;
  if ( !v18 )
    goto LABEL_129;
  v20 = L"\\";
  v21 = 2147483646;
  v22 = L"\\";
  v23 = wszCat - v18 + 3;
  do
  {
    if ( !v21 )
      break;
    if ( !*v22 )
      break;
    *v23++ = *v22++;
    --v21;
    --v18;
  }
  while ( v18 );
  v24 = v23 - 1;
  v15 = -2147024774;
  if ( v18 )
  {
    v24 = v23;
    v15 = 0;
  }
  *v24 = 0;
  if ( !v18 )
  {
LABEL_129:
    v16 = 876;
    goto LABEL_13;
  }
  if ( cImplemented <= 1 )
  {
LABEL_28:
    for ( j = 0; ; ++j )
    {
      v26 = celtFetched;
      if ( j >= celtFetched )
        goto LABEL_43;
      if ( !StringFromGUID2((const GUID *const)hKey + j, wszCat, 261) )
      {
        if ( hkeyClsid.m_ptr )
          RegCloseKey(hkeyClsid.m_ptr);
        return 2147942487LL;
      }
      v27 = 2147483646;
      v28 = wszCat;
      v29 = 237;
      v30 = &wszKey[23];
      do
      {
        if ( !v27 )
          break;
        if ( !*v28 )
          break;
        *v30++ = *v28++;
        --v27;
        --v29;
      }
      while ( v29 );
      v31 = v30 - 1;
      v15 = -2147024774;
      if ( v29 )
      {
        v31 = v30;
        v15 = 0;
      }
      *v31 = 0;
      if ( !v29 )
        break;
      if ( !RegOpenKeyExW(hkeyClsid.m_ptr, wszKey, 0, 0x20019u, (PHKEY)&ppenumCatid) )
      {
        RegCloseKey((HKEY)ppenumCatid);
        goto LABEL_53;
      }
    }
    v16 = 913;
LABEL_13:
    wil::details::in1diag3::Return_Hr(retaddr, v16, "com\\ole32\\comcat\\src\\comcat.cpp", v15);
    if ( hkeyClsid.m_ptr )
      RegCloseKey(hkeyClsid.m_ptr);
    return (unsigned int)v15;
  }
  hkeyImpCat = 0;
  if ( !RegOpenKeyExW(hkeyClsid.m_ptr, wszKey, 0, 0x20019u, &hkeyImpCat) )
  {
    RegCloseKey(hkeyImpCat);
    goto LABEL_28;
  }
  v26 = cImplemented;
LABEL_43:
  v32 = 0;
LABEL_44:
  if ( v32 >= v26 )
  {
LABEL_83:
    v52 = hkeyClsid.m_ptr;
    if ( !hkeyClsid.m_ptr )
      return 1;
LABEL_84:
    RegCloseKey(v52);
    return 1;
  }
  for ( k = 0; ; ++k )
  {
    if ( k >= 5 )
    {
      v26 = celtFetched;
      ++v32;
      goto LABEL_44;
    }
    v34 = &g_oldkeyinfo[k];
    v35 = hKey + 4 * v32;
    v36 = *(_QWORD *)v35 - *(_QWORD *)&v34->catid.Data1;
    if ( *(_QWORD *)v35 == *(_QWORD *)&v34->catid.Data1 )
      v36 = *((_QWORD *)v35 + 1) - *(_QWORD *)v34->catid.Data4;
    if ( v36 )
      continue;
    v59 = StringCchCopyW(wszKey, 0x104u, v34->szDescription);
    v60 = v59;
    if ( v59 < 0 )
      break;
    if ( !RegOpenKeyExW(hkeyClsid.m_ptr, wszKey, 0, 0x20019u, (PHKEY)&ppenumCatid) )
    {
      RegCloseKey((HKEY)ppenumCatid);
      v7 = 2147483646;
      goto LABEL_53;
    }
  }
  wil::details::in1diag3::Return_Hr(retaddr, 0x3ADu, "com\\ole32\\comcat\\src\\comcat.cpp", v59);
  if ( hkeyClsid.m_ptr )
    RegCloseKey(hkeyClsid.m_ptr);
  return v60;
}

```

## disassembly

```asm
0x180017cb0  mov     [rsp-8+arg_8], rbx
0x180017cb5  push    rbp
0x180017cb6  push    rsi
0x180017cb7  push    rdi
0x180017cb8  push    r12
0x180017cba  push    r13
0x180017cbc  push    r14
0x180017cbe  push    r15
0x180017cc0  lea     rbp, [rsp-3C0h]
0x180017cc8  sub     rsp, 4C0h
0x180017ccf  mov     rax, cs:__security_cookie
0x180017cd6  xor     rax, rsp
0x180017cd9  mov     [rbp+3F0h+var_40], rax
0x180017ce0  mov     [rsp+4F0h+hKey], rgcatidImpl
0x180017ce5  mov     edi, cImplemented
0x180017ce7  mov     [rsp+4F0h+celtFetched], cImplemented
0x180017ceb  mov     rbx, clsid
0x180017cee  mov     [rsp+4F0h+var_480], clsid
0x180017cf3  xor     cImplemented, cImplemented; Val
0x180017cf5  mov     r8d, 208h; Size
0x180017cfb  mov     [rsp+4F0h+var_488], cRequired
0x180017d00  lea     clsid, [rbp+3F0h+wszKey]; void *
0x180017d04  call    memset_0
0x180017d09  xor     r15d, r15d
0x180017d0c  lea     rgcatidImpl, [rsp+4F0h+hkeyClsid]
0x180017d11  mov     cImplemented, 20019h
0x180017d16  mov     [rsp+4F0h+hkeyClsid.m_ptr], r15
0x180017d1b  mov     clsid, rbx
0x180017d1e  call    cs:__imp_InternalRegOpenClassKey
0x180017d24  test    eax, eax
0x180017d26  js      loc_1800181AA
0x180017d2c  lea     eax, [rdi-1]
0x180017d2f  mov     esi, 7FFFFFFEh
0x180017d34  mov     r13d, 104h
0x180017d3a  cmp     eax, 0FFFFFFFDh
0x180017d3d  ja      loc_1800181D8
0x180017d43  mov     [rsp+4F0h+ppenumCatid], r15
0x180017d48  lea     rgcatidImpl, ?Implemented_Categories@Constants@Catalog@Com@@3QBGB; ushort const near * const Com::Catalog::Constants::Implemented_Categories
0x180017d4f  mov     eax, esi
0x180017d51  lea     r9, [rbp+3F0h+wszKey]
0x180017d55  mov     cImplemented, r13d
0x180017d58  test    rax, rax
0x180017d5b  jz      short loc_180017D7B
0x180017d5d  movzx   ecx, word ptr [rgcatidImpl]
0x180017d61  test    cx, cx
0x180017d64  jz      short loc_180017D7B
0x180017d66  mov     [r9], cx
0x180017d6a  add     rgcatidImpl, 2
0x180017d6e  add     r9, 2
0x180017d72  dec     rax
0x180017d75  sub     rdx, 1
0x180017d79  jnz     short loc_180017D58
0x180017d7b  test    rdx, rdx
0x180017d7e  lea     clsid, [r9-2]
0x180017d82  mov     r14d, 8007007Ah
0x180017d88  cmovnz  clsid, r9
0x180017d8c  mov     ebx, r14d
0x180017d8f  cmovnz  ebx, r15d
0x180017d93  mov     [clsid], r15w
0x180017d97  jnz     short loc_180017DEE
0x180017d99  mov     cImplemented, 36Bh; lineNumber
0x180017d9e  mov     clsid, [rbp+3F8h]; callerReturnAddress
0x180017da5  lea     rgcatidImpl, aComOle32Comcat; "com\\ole32\\comcat\\src\\comcat.cpp"
0x180017dac  mov     cRequired, ebx; hr
0x180017daf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017db4  mov     clsid, [rsp+4F0h+hkeyClsid.m_ptr]; hKey
0x180017db9  test    clsid, clsid
0x180017dbc  jnz     loc_18001844F
0x180017dc2  mov     eax, ebx
0x180017dc4  mov     clsid, [rbp+3F0h+var_40]
0x180017dcb  xor     clsid, rsp; StackCookie
0x180017dce  call    __security_check_cookie
0x180017dd3  mov     rbx, [rsp+4F0h+arg_8]
0x180017ddb  add     rsp, 4C0h
0x180017de2  pop     r15
0x180017de4  pop     r14
0x180017de6  pop     r13
0x180017de8  pop     r12
0x180017dea  pop     rdi
0x180017deb  pop     rsi
0x180017dec  pop     rbp
0x180017ded  retn
0x180017dee  mov     rdx, r13
0x180017df1  lea     rax, [rbp+3F0h+wszKey]
0x180017df5  cmp     [rax], r15w
0x180017df9  jz      short loc_180017E05
0x180017dfb  add     rax, 2
0x180017dff  sub     rdx, 1
0x180017e03  jnz     short loc_180017DF5
0x180017e05  mov     r12d, 80070057h
0x180017e0b  test    rdx, rdx
0x180017e0e  mov     ebx, r12d
0x180017e11  cmovnz  ebx, r15d
0x180017e15  jz      loc_1800184D1
0x180017e1b  lea     r15, asc_1800DDB08; "\\"
0x180017e22  mov     clsid, rsi
0x180017e25  lea     rax, [rdx+rdx]
0x180017e29  mov     r9, r15
0x180017e2c  lea     rgcatidImpl, [rbp+3F0h+var_258]
0x180017e33  sub     rgcatidImpl, rax
0x180017e36  test    clsid, clsid
0x180017e39  jz      short loc_180017E59
0x180017e3b  movzx   eax, word ptr [r9]
0x180017e3f  test    ax, ax
0x180017e42  jz      short loc_180017E59
0x180017e44  mov     [rgcatidImpl], ax
0x180017e48  add     r9, 2
0x180017e4c  add     rgcatidImpl, 2
0x180017e50  dec     clsid
0x180017e53  sub     rdx, 1
0x180017e57  jnz     short loc_180017E36
0x180017e59  xor     eax, eax
0x180017e5b  lea     clsid, [rgcatidImpl-2]
0x180017e5f  test    rdx, rdx
0x180017e62  mov     ebx, r14d
0x180017e65  cmovnz  clsid, rgcatidImpl
0x180017e69  cmovnz  ebx, eax
0x180017e6c  mov     [clsid], ax
0x180017e6f  jz      loc_1800184D1
0x180017e75  cmp     edi, 1
0x180017e78  ja      loc_180017F3B
0x180017e7e  xor     edi, edi
0x180017e80  mov     eax, [rsp+4F0h+celtFetched]
0x180017e84  cmp     edi, eax
0x180017e86  jnb     loc_180017F6C
0x180017e8c  mov     ecx, edi
0x180017e8e  lea     rdx, [rbp+3F0h+wszCat]; lpsz
0x180017e95  shl     clsid, 4
0x180017e99  mov     r8d, 105h; cchMax
0x180017e9f  add     clsid, [rsp+4F0h+hKey]; rguid
0x180017ea4  call    cs:__imp_StringFromGUID2
0x180017eaa  test    eax, eax
0x180017eac  jz      loc_1800182AF
0x180017eb2  mov     clsid, rsi
0x180017eb5  lea     rdx, [rbp+3F0h+wszCat]
0x180017ebc  mov     r8d, 0EDh
0x180017ec2  lea     r9, [rbp+3F0h+wszKey+2Eh]
0x180017ec6  test    clsid, clsid
0x180017ec9  jz      short loc_180017EE8
0x180017ecb  movzx   eax, word ptr [rdx]
0x180017ece  test    ax, ax
0x180017ed1  jz      short loc_180017EE8
0x180017ed3  mov     [r9], ax
0x180017ed7  add     rdx, 2
0x180017edb  add     r9, 2
0x180017edf  dec     clsid
0x180017ee2  sub     rgcatidImpl, 1
0x180017ee6  jnz     short loc_180017EC6
0x180017ee8  xor     eax, eax
0x180017eea  lea     clsid, [r9-2]
0x180017eee  test    rgcatidImpl, rgcatidImpl
0x180017ef1  mov     ebx, r14d
0x180017ef4  cmovnz  clsid, r9
0x180017ef8  cmovnz  ebx, eax
0x180017efb  mov     [clsid], ax
0x180017efe  jz      short loc_180017F31
0x180017f00  mov     clsid, [rsp+4F0h+hkeyClsid.m_ptr]; hKey
0x180017f05  lea     rax, [rsp+4F0h+ppenumCatid]
0x180017f0a  mov     cRequired, 20019h; samDesired
0x180017f10  mov     [rsp+4F0h+phkResult], rax; phkResult
0x180017f15  xor     r8d, r8d; ulOptions
0x180017f18  lea     rdx, [rbp+3F0h+wszKey]; lpSubKey
0x180017f1c  call    cs:__imp_RegOpenKeyExW
0x180017f22  test    eax, eax
0x180017f24  jz      loc_180017FC1
0x180017f2a  inc     edi
0x180017f2c  jmp     loc_180017E80
0x180017f31  mov     cImplemented, 391h
0x180017f36  jmp     loc_180017D9E
0x180017f3b  mov     clsid, [rsp+4F0h+hkeyClsid.m_ptr]; hKey
0x180017f40  lea     rdx, [rbp+3F0h+wszKey]; lpSubKey
0x180017f44  mov     [rsp+4F0h+hkeyImpCat], rax
0x180017f49  mov     cRequired, 20019h; samDesired
0x180017f4f  lea     rax, [rsp+4F0h+hkeyImpCat]
0x180017f54  xor     r8d, r8d; ulOptions
0x180017f57  mov     [rsp+4F0h+phkResult], rax; phkResult
0x180017f5c  call    cs:__imp_RegOpenKeyExW
0x180017f62  test    eax, eax
0x180017f64  jz      loc_18001819A
0x180017f6a  mov     eax, edi
0x180017f6c  xor     edi, edi
0x180017f6e  lea     rdx, g_oldkeyinfo
0x180017f75  cmp     edi, eax
0x180017f77  jnb     loc_1800181AA
0x180017f7d  xor     ebx, ebx
0x180017f7f  nop
0x180017f80  cmp     ebx, 5
0x180017f83  jnb     short loc_180017FB9
0x180017f85  mov     eax, ebx
0x180017f87  imul    rgcatidImpl, rax, 114h
0x180017f8e  mov     ecx, edi
0x180017f90  shl     clsid, 4
0x180017f94  add     rgcatidImpl, rdx
0x180017f97  add     clsid, [rsp+4F0h+hKey]
0x180017f9c  mov     rax, [clsid]
0x180017f9f  sub     rax, [rgcatidImpl]
0x180017fa2  jnz     short loc_180017FAC
0x180017fa4  mov     rax, [clsid+8]
0x180017fa8  sub     rax, [rgcatidImpl+8]
0x180017fac  test    rax, rax
0x180017faf  jz      loc_180018465
0x180017fb5  inc     ebx
0x180017fb7  jmp     short loc_180017F80
0x180017fb9  mov     eax, [rsp+4F0h+celtFetched]
0x180017fbd  inc     edi
0x180017fbf  jmp     short loc_180017F75
0x180017fc1  mov     clsid, [rsp+4F0h+ppenumCatid]; hKey
0x180017fc6  call    cs:__imp_RegCloseKey
0x180017fcc  cmp     [rsp+4F0h+var_488], 0FFFFFFFFh
0x180017fd1  jz      loc_18001826D
0x180017fd7  mov     [rsp+4F0h+hKeyReq], 0
0x180017fe0  lea     rax, [rbp+3F0h+wszKey]
0x180017fe4  mov     rdx, r13
0x180017fe7  cmp     word ptr [rax], 0
0x180017feb  jz      short loc_180017FF7
0x180017fed  add     rax, 2
0x180017ff1  sub     rdx, 1
0x180017ff5  jnz     short loc_180017FE7
0x180017ff7  xor     eax, eax
0x180017ff9  mov     ebx, r12d
0x180017ffc  test    rdx, rdx
0x180017fff  cmovnz  ebx, eax
0x180018002  jz      loc_1800185DA
0x180018008  lea     rdi, ?Required_Categories@Constants@Catalog@Com@@3QBGB; ushort const near * const Com::Catalog::Constants::Required_Categories
0x18001800f  mov     clsid, rsi
0x180018012  lea     rax, [rdx+rdx]
0x180018016  mov     r9, rdi
0x180018019  lea     rgcatidImpl, [rbp+3F0h+var_258]
0x180018020  sub     rgcatidImpl, rax
0x180018023  test    clsid, clsid
0x180018026  jz      short loc_180018046
0x180018028  movzx   eax, word ptr [r9]
0x18001802c  test    ax, ax
0x18001802f  jz      short loc_180018046
0x180018031  mov     [rgcatidImpl], ax
0x180018035  add     r9, 2
0x180018039  add     rgcatidImpl, 2
0x18001803d  dec     clsid
0x180018040  sub     rdx, 1
0x180018044  jnz     short loc_180018023
0x180018046  xor     eax, eax
0x180018048  lea     clsid, [rgcatidImpl-2]
0x18001804c  test    rdx, rdx
0x18001804f  mov     ebx, r14d
0x180018052  cmovnz  clsid, rgcatidImpl
0x180018056  cmovnz  ebx, eax
0x180018059  mov     [clsid], ax
0x18001805c  jz      loc_1800185DA
0x180018062  lea     rax, [rbp+3F0h+wszKey]
0x180018066  cmp     word ptr [rax], 0
0x18001806a  jz      short loc_180018076
0x18001806c  add     rax, 2
0x180018070  sub     r13, 1
0x180018074  jnz     short loc_180018066
0x180018076  xor     eax, eax
0x180018078  test    r13, r13
0x18001807b  cmovnz  r12d, eax
0x18001807f  jz      loc_1800185C7
0x180018085  lea     rax, ds:0[r13*2]
0x18001808d  lea     rdx, [rbp+3F0h+var_258]
0x180018094  sub     rdx, rax
0x180018097  test    rsi, rsi
0x18001809a  jz      short loc_1800180B9
0x18001809c  movzx   eax, word ptr [r15]
0x1800180a0  test    ax, ax
0x1800180a3  jz      short loc_1800180B9
0x1800180a5  mov     [rdx], ax
0x1800180a8  add     r15, 2
0x1800180ac  add     rdx, 2
0x1800180b0  dec     rsi
0x1800180b3  sub     r13, 1
0x1800180b7  jnz     short loc_180018097
0x1800180b9  xor     eax, eax
0x1800180bb  lea     clsid, [rdx-2]
0x1800180bf  test    r13, r13
0x1800180c2  cmovnz  clsid, rdx
0x1800180c6  cmovnz  r14d, eax
0x1800180ca  mov     [clsid], ax
0x1800180cd  jz      loc_18001841E
0x1800180d3  mov     clsid, [rsp+4F0h+hkeyClsid.m_ptr]; hKey
0x1800180d8  lea     rax, [rsp+4F0h+hKeyReq]
0x1800180dd  mov     cRequired, 20019h; samDesired
0x1800180e3  mov     [rsp+4F0h+phkResult], rax; phkResult
0x1800180e8  xor     r8d, r8d; ulOptions
0x1800180eb  lea     rdx, [rbp+3F0h+wszKey]; lpSubKey
0x1800180ef  call    cs:__imp_RegOpenKeyExW
0x1800180f5  test    eax, eax
0x1800180f7  jnz     loc_1800181C3
0x1800180fd  mov     clsid, [rsp+4F0h+hKeyReq]; hKey
0x180018102  call    cs:__imp_RegCloseKey
0x180018108  lea     clsid, [rsp+4F0h+var_4A0]; this
0x18001810d  mov     [rsp+4F0h+ppenumCatid], 0
0x180018116  mov     [rsp+4F0h+var_4A0.ptr_], 0
0x18001811f  call    ?InternalRelease@?$ComPtr@UIEnterpriseDropTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IEnterpriseDropTarget>::InternalRelease(void)
0x180018124  mov     rbx, [rsp+4F0h+var_480]
0x180018129  lea     r9, [rsp+4F0h+var_4A0]; ppv
0x18001812e  mov     clsid, rbx; clsid
0x180018131  lea     rgcatidImpl, _GUID_00d489b0_06a7_0074_9ce0_065132561673; riid
0x180018138  xor     cImplemented, cImplemented; pComCatalog
0x18001813a  call    ?GetClassInfoWithInprocOrLocalServer@@YAJAEBU_GUID@@PEAUIComCatalogSCM@@0PEAPEAX@Z; GetClassInfoWithInprocOrLocalServer(_GUID const &,IComCatalogSCM *,_GUID const &,void * *)
  ... truncated ...
```
