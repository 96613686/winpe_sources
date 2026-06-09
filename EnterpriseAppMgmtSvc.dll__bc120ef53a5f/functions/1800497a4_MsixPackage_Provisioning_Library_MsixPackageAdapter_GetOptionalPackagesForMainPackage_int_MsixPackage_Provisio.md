# MsixPackage::Provisioning::Library::MsixPackageAdapter::GetOptionalPackagesForMainPackage(int,MsixPackage::Provisioning::Library::MsixProvisioningContext *,bool *,std::vector<ushort const *,std::allocator<ushort const *>> &)

- ea: `0x1800497a4`
- end: `0x18004a4cc`
- name: `?GetOptionalPackagesForMainPackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJHPEAVMsixProvisioningContext@234@PEA_NAEAV?$vector@PEBGV?$allocator@PEBG@std@@@std@@@Z`
- size: `3368`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003c81c`

## callees

- `0x18001d160`
- `0x18001d65c`
- `0x1800344e4`
- `0x180034d7c`
- `0x18003d4ec`
- `0x18003e50c`
- `0x18003e644`
- `0x1800497a4`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18004997f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180049a68`
- `msvcrt!??3@YAXPEAX@Z` at `0x180049baf`
- `msvcrt!??3@YAXPEAX@Z` at `0x180049cdd`
- `msvcrt!??3@YAXPEAX@Z` at `0x180049e5f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004a006`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004a159`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004a2ba`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004a40b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004997f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180049a68`
- `msvcrt!??3@YAXPEAX@Z` at `0x180049baf`
- `msvcrt!??3@YAXPEAX@Z` at `0x180049cdd`
- `msvcrt!??3@YAXPEAX@Z` at `0x180049e5f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004a006`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004a159`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004a2ba`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004a40b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049e3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a10b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a26c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a3a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049e3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a10b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a26c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a3a2`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x18004990e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x18004990e`
- `AppXAllUserStore!FindFullNameForFamilyNameInAppxAllUserStore` at `0x18004a219`
- `AppXAllUserStore!FindFullNameForFamilyNameInAppxAllUserStore` at `0x18004a219`

## string_xrefs

- `0x18004994b`: `Failed to open '%ws'.`
- `0x180049b7b`: `Failed to create appx bundle manifest reader for %ws.`
- `0x180049a34`: `Failed to create appx bundle factory.`
- `0x1800498bc`: `\AppxMetadata\AppxBundleManifest.xml`
- `0x18004995a`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180049a43`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180049b8a`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180049cb8`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180049df3`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180049e25`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180049f55`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180049fb3`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004a0ef`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004a250`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180049c9d`: `Failed to bundle manifest reader 2 interface`
- `0x18004a241`: `Failed to find an existing version for optional package %ws in registry store`

## pseudocode

```c
// Hidden C++ exception states: #wind=18 #try_helpers=1
__int64 __fastcall MsixPackage::Provisioning::Library::MsixPackageAdapter::GetOptionalPackagesForMainPackage(
        char *a1,
        __int64 a2,
        __int64 a3,
        _BYTE *a4,
        __int64 a5)
{
  _BYTE *v5; // r13
  _WORD *v8; // rdx
  __int64 v9; // rbx
  __int64 v10; // r8
  char *v11; // rdi
  char *v12; // rdx
  IStream *v13; // rcx
  const WCHAR *v14; // rcx
  HRESULT v15; // ebx
  LPCWSTR *v16; // rdx
  int v18; // ebx
  __int64 v19; // rbx
  __int64 (__fastcall *v20)(__int64, IStream *, _QWORD **); // r15
  _QWORD *v21; // rcx
  int v22; // r15d
  LPCWSTR *v23; // rdx
  _QWORD *v24; // r15
  __int64 (__fastcall *v25)(_QWORD *, GUID *, _QWORD **); // r12
  _QWORD *v26; // rcx
  int v27; // r15d
  _QWORD *v28; // r15
  __int64 (__fastcall *v29)(_QWORD *, _QWORD **); // r12
  _QWORD *v30; // rcx
  int v31; // r15d
  int v32; // eax
  void *v33; // rdi
  _QWORD *v34; // r15
  __int64 v35; // r12
  __int64 v36; // rax
  int v37; // eax
  __int64 v38; // rax
  int v39; // edi
  __int64 v40; // rax
  int v41; // edi
  int FullNameForFamilyNameInAppxAllUserStore; // edi
  int v43; // [rsp+20h] [rbp-E8h]
  char *v44; // [rsp+28h] [rbp-E0h]
  char v45[8]; // [rsp+30h] [rbp-D8h] BYREF
  _QWORD *v46; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD *v47; // [rsp+40h] [rbp-C8h] BYREF
  _QWORD *v48; // [rsp+48h] [rbp-C0h] BYREF
  IStream *ppstm; // [rsp+50h] [rbp-B8h] BYREF
  int v50; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v51; // [rsp+60h] [rbp-A8h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-A0h] BYREF
  char *v53; // [rsp+70h] [rbp-98h] BYREF
  __int64 *v54; // [rsp+78h] [rbp-90h] BYREF
  __int64 v55; // [rsp+80h] [rbp-88h]
  char *v56; // [rsp+88h] [rbp-80h]
  __int64 v57; // [rsp+90h] [rbp-78h]
  _BYTE *v58; // [rsp+98h] [rbp-70h]
  LPCWSTR pszFile[2]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v60; // [rsp+B0h] [rbp-58h]
  unsigned __int64 v61; // [rsp+B8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v5 = a4;
  pv = a1;
  v56 = a1;
  v58 = a4;
  v51 = a5;
  v57 = a5;
  ppstm = 0;
  v55 = 0;
  v48 = 0;
  v47 = 0;
  v46 = 0;
  *a4 = 0;
  v61 = 7;
  v60 = 0;
  LOWORD(pszFile[0]) = 0;
  v8 = *(_WORD **)(a3 + 560);
  v9 = -1;
  if ( *v8 )
  {
    v10 = -1;
    do
      ++v10;
    while ( v8[v10] );
  }
  std::wstring::assign(pszFile, v8);
  std::wstring::append(pszFile, (void *)L"\\");
  v11 = a1 + 48;
  if ( *((_QWORD *)v11 + 3) < 8u )
    v12 = v11;
  else
    v12 = *(char **)v11;
  if ( *(_WORD *)v12 )
  {
    do
      ++v9;
    while ( *(_WORD *)&v12[2 * v9] );
  }
  std::wstring::append(pszFile, v12);
  std::wstring::append(pszFile, L"\\AppxMetadata\\AppxBundleManifest.xml");
  v13 = ppstm;
  ppstm = 0;
  if ( v13 )
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v13 + 16LL))(v13);
  v14 = (const WCHAR *)pszFile;
  if ( v61 >= 8 )
    v14 = pszFile[0];
  v15 = SHCreateStreamOnFileW(v14, 0, &ppstm);
  if ( v15 >= 0 )
  {
    v55 = 0;
    v18 = MsixPackage::Provisioning::Library::MsixAppxPackaging::CreateFactory<IAppxBundleFactory>((MsixPackage::Provisioning::Library::MsixAppxPackaging *)(a3 + 216));
    if ( v18 >= 0 )
    {
      v19 = v55;
      v20 = *(__int64 (__fastcall **)(__int64, IStream *, _QWORD **))(*(_QWORD *)v55 + 40LL);
      v21 = v48;
      v48 = 0;
      if ( v21 )
        (*(void (__fastcall **)(_QWORD *, _QWORD))(*v21 + 16LL))(v21, *v21);
      v22 = v20(v19, ppstm, &v48);
      if ( v22 >= 0 )
      {
        v24 = v48;
        v25 = *(__int64 (__fastcall **)(_QWORD *, GUID *, _QWORD **))*v48;
        v26 = v47;
        v47 = 0;
        if ( v26 )
          (*(void (__fastcall **)(_QWORD *, _QWORD))(*v26 + 16LL))(v26, *v26);
        v27 = v25(v24, &IID_IAppxBundleManifestReader2, &v47);
        if ( v27 >= 0 )
        {
          v50 = 0;
          v28 = v47;
          v29 = *(__int64 (__fastcall **)(_QWORD *, _QWORD **))(*v47 + 24LL);
          v30 = v46;
          v46 = 0;
          if ( v30 )
            (*(void (__fastcall **)(_QWORD *, _QWORD))(*v30 + 16LL))(v30, *v30);
          v31 = v29(v28, &v46);
          if ( v31 >= 0 )
          {
            (*(void (__fastcall **)(_QWORD *, int *))(*v46 + 32LL))(v46, &v50);
            v34 = pv;
            v35 = v51;
            while ( v50 )
            {
              v51 = 0;
              v36 = *v46;
              v51 = 0;
              v37 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(v36 + 24))(v46, &v51);
              if ( v37 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x7E8,
                  (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                  (const char *)(unsigned int)v37,
                  v43);
              v54 = 0;
              v38 = *(_QWORD *)v51;
              v54 = 0;
              v39 = (*(__int64 (__fastcall **)(__int64, __int64 **))(v38 + 24))(v51, &v54);
              if ( v39 < 0 )
              {
                wil::details::in1diag3::Return_HrMsg(
                  retaddr,
                  (void *)0x7EE,
                  (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                  (const char *)(unsigned int)v39,
                  (int)"%ws",
                  L"Failed to get package Id for optional bundle");
                if ( v54 )
                  (*(void (__fastcall **)(__int64 *))(*v54 + 16))(v54);
                if ( v51 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
                if ( v61 >= 8 )
                  operator delete((void *)pszFile[0]);
                v61 = 7;
                v60 = 0;
                LOWORD(pszFile[0]) = 0;
                if ( v46 )
                  (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
                if ( v47 )
                  (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
                if ( v48 )
                  (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
                if ( v19 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
                if ( ppstm )
                  (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
                return (unsigned int)v39;
              }
              v53 = 0;
              v40 = *v54;
              v53 = 0;
              v41 = (*(__int64 (__fastcall **)(__int64 *, char **))(v40 + 80))(v54, &v53);
              if ( v41 < 0 )
              {
                wil::details::in1diag3::Return_HrMsg(
                  retaddr,
                  (void *)0x7F4,
                  (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                  (const char *)(unsigned int)v41,
                  (int)"%ws",
                  L"Failed to get package family name for optional bundle");
                if ( v53 )
                  CoTaskMemFree(v53);
                if ( v54 )
                  (*(void (__fastcall **)(__int64 *))(*v54 + 16))(v54);
                if ( v51 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
                if ( v61 >= 8 )
                  operator delete((void *)pszFile[0]);
                v61 = 7;
                v60 = 0;
                LOWORD(pszFile[0]) = 0;
                if ( v46 )
                  (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
                if ( v47 )
                  (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
                if ( v48 )
                  (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
                if ( v19 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
                if ( ppstm )
                  (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
                return (unsigned int)v41;
              }
              pv = 0;
              v45[0] = 0;
              FullNameForFamilyNameInAppxAllUserStore = FindFullNameForFamilyNameInAppxAllUserStore(
                                                          *(_QWORD *)(v34[2] + 584LL),
                                                          v53,
                                                          v45,
                                                          &pv);
              if ( FullNameForFamilyNameInAppxAllUserStore < 0 )
              {
                wil::details::in1diag3::Return_HrMsg(
                  retaddr,
                  (void *)0x802,
                  (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                  (const char *)(unsigned int)FullNameForFamilyNameInAppxAllUserStore,
                  (int)"Failed to find an existing version for optional package %ws in registry store",
                  v53);
                if ( v53 )
                  CoTaskMemFree(v53);
                if ( v54 )
                  (*(void (__fastcall **)(__int64 *))(*v54 + 16))(v54);
                if ( v51 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
                if ( v61 >= 8 )
                  operator delete((void *)pszFile[0]);
                v61 = 7;
                v60 = 0;
                LOWORD(pszFile[0]) = 0;
                if ( v46 )
                  (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
                if ( v47 )
                  (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
                if ( v48 )
                  (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
                if ( v19 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
                if ( ppstm )
                  (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
                return (unsigned int)FullNameForFamilyNameInAppxAllUserStore;
              }
              if ( v45[0] )
              {
                try
                {
                  std::vector<unsigned short const *>::push_back(v35, pv);
                }
                catch ( ... )
                {
                  wil::details::in1diag3::Log_CaughtExceptionMsg(
                    retaddr,
                    (void *)0x809,
                    (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                    "Failed to add optional package full name %ws to optional list",
                    *(const char **)pv);
                  v19 = v55;
                  v34 = v56;
                  v35 = v57;
                  v5 = v58;
                }
                *v5 = 1;
              }
              if ( v53 )
                CoTaskMemFree(v53);
              if ( v54 )
                (*(void (__fastcall **)(__int64 *))(*v54 + 16))(v54);
              if ( v51 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
              (*(void (__fastcall **)(_QWORD *, int *))(*v46 + 40LL))(v46, &v50);
            }
            if ( v61 >= 8 )
              operator delete((void *)pszFile[0]);
            v61 = 7;
            v60 = 0;
            LOWORD(pszFile[0]) = 0;
            if ( v46 )
              (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
            if ( v47 )
              (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
            if ( v48 )
              (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
            if ( v19 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
            if ( ppstm )
              (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
            return 0;
          }
          else
          {
            pv = 0;
            if ( *((_QWORD *)v11 + 3) >= 8u )
              v11 = *(char **)v11;
            v32 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                    &pv,
                    L"Failed to get optional packages for main package '%s'",
                    v11);
            if ( v32 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x7E3,
                (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                (const char *)(unsigned int)v32,
                v43);
            v33 = pv;
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0x7E3,
              (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
              (const char *)(unsigned int)v31,
              (int)"%ws",
              (const char *)pv);
            if ( v33 )
              CoTaskMemFree(v33);
            if ( v61 >= 8 )
              operator delete((void *)pszFile[0]);
            v61 = 7;
            v60 = 0;
            LOWORD(pszFile[0]) = 0;
            if ( v46 )
              (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
            if ( v47 )
              (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
            if ( v48 )
              (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
            if ( v19 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
            if ( ppstm )
              (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
            return (unsigned int)v31;
          }
        }
        else
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x7DD,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            (const char *)(unsigned int)v27,
            (int)"%ws",
            L"Failed to bundle manifest reader 2 interface");
          if ( v61 >= 8 )
            operator delete((void *)pszFile[0]);
          v61 = 7;
          v60 = 0;
          LOWORD(pszFile[0]) = 0;
          if ( v46 )
            (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
          if ( v47 )
            (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
          if ( v48 )
            (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
          if ( v19 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          if ( ppstm )
            (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
          return (unsigned int)v27;
        }
      }
      else
      {
        v23 = pszFile;
        if ( v61 >= 8 )
          v23 = (LPCWSTR *)pszFile[0];
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x7D8,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v22,
          (int)"Failed to create appx bundle manifest reader for %ws.",
          (const char *)v23);
        if ( v61 >= 8 )
          operator delete((void *)pszFile[0]);
        v61 = 7;
        v60 = 0;
        LOWORD(pszFile[0]) = 0;
        if ( v46 )
          (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
        if ( v47 )
          (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
        if ( v48 )
          (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
        if ( v19 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        if ( ppstm )
          (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
        return (unsigned int)v22;
      }
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x7D3,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v18,
        (int)"Failed to create appx bundle factory.",
        v44);
      if ( v61 >= 8 )
        operator delete((void *)pszFile[0]);
      v61 = 7;
      v60 = 0;
      LOWORD(pszFile[0]) = 0;
      if ( v46 )
        (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
      if ( v47 )
        (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
      if ( v48 )
        (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
      if ( v55 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
      if ( ppstm )
        (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
      return (unsigned int)v18;
    }
  }
  else
  {
    v16 = pszFile;
    if ( v61 >= 8 )
      v16 = (LPCWSTR *)pszFile[0];
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x7D1,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v15,
      (int)"Failed to open '%ws'.",
      (const char *)v16);
    if ( v61 >= 8 )
      operator delete((void *)pszFile[0]);
    v61 = 7;
    v60 = 0;
    LOWORD(pszFile[0]) = 0;
    if ( v46 )
      (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
    if ( v47 )
      (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
    if ( v48 )
      (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
    if ( ppstm )
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
    return (unsigned int)v15;
  }
}

```

## disassembly

```asm
0x1800497a4  mov     r11, rsp
0x1800497a7  push    rbx
0x1800497a8  push    rsi
0x1800497a9  push    rdi
0x1800497aa  push    r12
0x1800497ac  push    r13
0x1800497ae  push    r14
0x1800497b0  push    r15
0x1800497b2  sub     rsp, 0D0h
0x1800497b9  mov     rax, cs:__security_cookie
0x1800497c0  xor     rax, rsp
0x1800497c3  mov     [rsp+108h+var_48], rax
0x1800497cb  mov     r13, r9
0x1800497ce  mov     r15, r8
0x1800497d1  mov     rdi, rcx
0x1800497d4  mov     [rsp+108h+pv], rcx
0x1800497d9  mov     [rsp+108h+var_80], rcx
0x1800497e1  mov     [rsp+108h+var_70], r9
0x1800497e9  mov     rax, [rsp+108h+arg_20]
0x1800497f1  mov     [rsp+108h+var_A8], rax
0x1800497f6  mov     [rsp+108h+var_78], rax
0x1800497fe  xor     esi, esi
0x180049800  mov     [rsp+108h+ppstm], rsi
0x180049805  mov     [r11-88h], rsi
0x18004980c  mov     [rsp+108h+var_C0], rsi
0x180049811  mov     [rsp+108h+var_C8], rsi
0x180049816  mov     [rsp+108h+var_D0], rsi
0x18004981b  mov     [r9], sil
0x18004981e  lea     r14d, [rsi+7]
0x180049822  mov     [r11-50h], r14
0x180049826  mov     [r11-58h], rsi
0x18004982a  mov     [r11-68h], si
0x18004982f  mov     rdx, [r8+230h]; Src
0x180049836  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004983a  cmp     [rdx], si
0x18004983d  jnz     short loc_180049844
0x18004983f  mov     r8d, esi
0x180049842  jmp     short loc_180049851
0x180049844  mov     r8, rbx
0x180049847  inc     r8
0x18004984a  cmp     [rdx+r8*2], si
0x18004984f  jnz     short loc_180049847
0x180049851  lea     rcx, [rsp+108h+pszFile]; void *
0x180049859  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18004985e  mov     r8, rsi
0x180049861  cmp     word ptr cs:pszSrc, si; "\\"
0x180049868  setnz   r8b
0x18004986c  lea     rdx, pszSrc; "\\"
0x180049873  lea     rcx, [rsp+108h+pszFile]; Src
0x18004987b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180049880  add     rdi, 30h ; '0'
0x180049884  cmp     qword ptr [rdi+18h], 8
0x180049889  jb      short loc_180049890
0x18004988b  mov     rdx, [rdi]
0x18004988e  jmp     short loc_180049893
0x180049890  mov     rdx, rdi; void *
0x180049893  cmp     [rdx], si
0x180049896  jnz     short loc_18004989D
0x180049898  mov     rbx, rsi
0x18004989b  jmp     short loc_1800498A6
0x18004989d  inc     rbx
0x1800498a0  cmp     [rdx+rbx*2], si
0x1800498a4  jnz     short loc_18004989D
0x1800498a6  mov     r8, rbx
0x1800498a9  lea     rcx, [rsp+108h+pszFile]; Src
0x1800498b1  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x1800498b6  mov     r8d, 24h ; '$'
0x1800498bc  lea     rdx, aAppxmetadataAp; "\\AppxMetadata\\AppxBundleManifest.xml"
0x1800498c3  lea     rcx, [rsp+108h+pszFile]; Src
0x1800498cb  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x1800498d0  nop
0x1800498d1  mov     rcx, [rsp+108h+ppstm]
0x1800498d6  mov     [rsp+108h+ppstm], rsi
0x1800498db  test    rcx, rcx
0x1800498de  jz      short loc_1800498ED
0x1800498e0  mov     rax, [rcx]
0x1800498e3  mov     rax, [rax+10h]
0x1800498e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800498ec  nop
0x1800498ed  lea     rcx, [rsp+108h+pszFile]
0x1800498f5  cmp     [rsp+108h+var_50], 8
0x1800498fe  cmovnb  rcx, [rsp+108h+pszFile]; pszFile
0x180049907  lea     r8, [rsp+108h+ppstm]; ppstm
0x18004990c  xor     edx, edx; grfMode
0x18004990e  call    cs:__imp_SHCreateStreamOnFileW
0x180049915  nop     dword ptr [rax+rax+00h]
0x18004991a  mov     ebx, eax
0x18004991c  test    eax, eax
0x18004991e  jns     loc_180049A06
0x180049924  lea     rdx, [rsp+108h+pszFile]
0x18004992c  cmp     [rsp+108h+var_50], 8
0x180049935  cmovnb  rdx, [rsp+108h+pszFile]
0x18004993e  mov     rcx, [rsp+108h]; this
0x180049946  mov     [rsp+108h+var_E0], rdx; char *
0x18004994b  lea     rax, aFailedToOpenWs; "Failed to open '%ws'."
0x180049952  mov     qword ptr [rsp+108h+var_E8], rax; int
0x180049957  mov     r9d, ebx; char *
0x18004995a  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180049961  mov     edx, 7D1h; void *
0x180049966  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004996b  nop
0x18004996c  cmp     [rsp+108h+var_50], 8
0x180049975  jb      short loc_18004998B
0x180049977  mov     rcx, [rsp+108h+pszFile]
0x18004997f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180049986  nop     dword ptr [rax+rax+00h]
0x18004998b  mov     [rsp+108h+var_50], r14
0x180049993  mov     [rsp+108h+var_58], rsi
0x18004999b  mov     word ptr [rsp+108h+pszFile], si
0x1800499a3  mov     rcx, [rsp+108h+var_D0]
0x1800499a8  test    rcx, rcx
0x1800499ab  jz      short loc_1800499BA
0x1800499ad  mov     rax, [rcx]
0x1800499b0  mov     rax, [rax+10h]
0x1800499b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800499b9  nop
0x1800499ba  mov     rcx, [rsp+108h+var_C8]
0x1800499bf  test    rcx, rcx
0x1800499c2  jz      short loc_1800499D1
0x1800499c4  mov     rax, [rcx]
0x1800499c7  mov     rax, [rax+10h]
0x1800499cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800499d0  nop
0x1800499d1  mov     rcx, [rsp+108h+var_C0]
0x1800499d6  test    rcx, rcx
0x1800499d9  jz      short loc_1800499E8
0x1800499db  mov     rax, [rcx]
0x1800499de  mov     rax, [rax+10h]
0x1800499e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800499e7  nop
0x1800499e8  mov     rcx, [rsp+108h+ppstm]
0x1800499ed  test    rcx, rcx
0x1800499f0  jz      short loc_1800499FF
0x1800499f2  mov     rax, [rcx]
0x1800499f5  mov     rax, [rax+10h]
0x1800499f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800499fe  nop
0x1800499ff  mov     eax, ebx
0x180049a01  jmp     loc_18004A4A8
0x180049a06  lea     rcx, [r15+0D8h]
0x180049a0d  mov     [rsp+108h+var_88], rsi
0x180049a15  lea     r8, [rsp+108h+var_88]
0x180049a1d  call    ??$CreateFactory@UIAppxBundleFactory@@@MsixAppxPackaging@Library@Provisioning@MsixPackage@@IEAAJAEBU_GUID@@PEAPEAUIAppxBundleFactory@@@Z; MsixPackage::Provisioning::Library::MsixAppxPackaging::CreateFactory<IAppxBundleFactory>(_GUID const &,IAppxBundleFactory * *)
0x180049a22  mov     ebx, eax
0x180049a24  test    eax, eax
0x180049a26  jns     loc_180049B09
0x180049a2c  mov     rcx, [rsp+108h]; this
0x180049a34  lea     rax, aFailedToCreate_10; "Failed to create appx bundle factory."
0x180049a3b  mov     qword ptr [rsp+108h+var_E8], rax; int
0x180049a40  mov     r9d, ebx; char *
0x180049a43  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180049a4a  mov     edx, 7D3h; void *
0x180049a4f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180049a54  nop
0x180049a55  cmp     [rsp+108h+var_50], 8
0x180049a5e  jb      short loc_180049A74
0x180049a60  mov     rcx, [rsp+108h+pszFile]
0x180049a68  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180049a6f  nop     dword ptr [rax+rax+00h]
0x180049a74  mov     [rsp+108h+var_50], r14
0x180049a7c  mov     [rsp+108h+var_58], rsi
0x180049a84  mov     word ptr [rsp+108h+pszFile], si
0x180049a8c  mov     rcx, [rsp+108h+var_D0]
0x180049a91  test    rcx, rcx
0x180049a94  jz      short loc_180049AA3
0x180049a96  mov     rax, [rcx]
0x180049a99  mov     rax, [rax+10h]
0x180049a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049aa2  nop
0x180049aa3  mov     rcx, [rsp+108h+var_C8]
0x180049aa8  test    rcx, rcx
0x180049aab  jz      short loc_180049ABA
0x180049aad  mov     rax, [rcx]
0x180049ab0  mov     rax, [rax+10h]
0x180049ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ab9  nop
0x180049aba  mov     rcx, [rsp+108h+var_C0]
0x180049abf  test    rcx, rcx
0x180049ac2  jz      short loc_180049AD1
0x180049ac4  mov     rax, [rcx]
0x180049ac7  mov     rax, [rax+10h]
0x180049acb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ad0  nop
0x180049ad1  mov     rcx, [rsp+108h+var_88]
0x180049ad9  test    rcx, rcx
0x180049adc  jz      short loc_180049AEB
0x180049ade  mov     rax, [rcx]
0x180049ae1  mov     rax, [rax+10h]
0x180049ae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049aea  nop
0x180049aeb  mov     rcx, [rsp+108h+ppstm]
0x180049af0  test    rcx, rcx
0x180049af3  jz      short loc_180049B02
0x180049af5  mov     rax, [rcx]
0x180049af8  mov     rax, [rax+10h]
0x180049afc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b01  nop
0x180049b02  mov     eax, ebx
0x180049b04  jmp     loc_18004A4A8
0x180049b09  mov     rbx, [rsp+108h+var_88]
0x180049b11  mov     rax, [rbx]
0x180049b14  mov     r15, [rax+28h]
0x180049b18  mov     rcx, [rsp+108h+var_C0]
0x180049b1d  mov     [rsp+108h+var_C0], rsi
0x180049b22  test    rcx, rcx
0x180049b25  jz      short loc_180049B34
0x180049b27  mov     rdx, [rcx]
0x180049b2a  mov     rax, [rdx+10h]
0x180049b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b33  nop
0x180049b34  lea     r8, [rsp+108h+var_C0]
0x180049b39  mov     rdx, [rsp+108h+ppstm]
0x180049b3e  mov     rcx, rbx
0x180049b41  mov     rax, r15
0x180049b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b49  mov     r15d, eax
0x180049b4c  test    eax, eax
0x180049b4e  jns     loc_180049C4C
0x180049b54  lea     rdx, [rsp+108h+pszFile]
0x180049b5c  cmp     [rsp+108h+var_50], 8
0x180049b65  cmovnb  rdx, [rsp+108h+pszFile]
0x180049b6e  mov     rcx, [rsp+108h]; this
0x180049b76  mov     [rsp+108h+var_E0], rdx; char *
0x180049b7b  lea     rax, aFailedToCreate_8; "Failed to create appx bundle manifest r"...
0x180049b82  mov     qword ptr [rsp+108h+var_E8], rax; int
0x180049b87  mov     r9d, r15d; char *
0x180049b8a  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180049b91  mov     edx, 7D8h; void *
0x180049b96  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180049b9b  nop
0x180049b9c  cmp     [rsp+108h+var_50], 8
0x180049ba5  jb      short loc_180049BBB
0x180049ba7  mov     rcx, [rsp+108h+pszFile]
0x180049baf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180049bb6  nop     dword ptr [rax+rax+00h]
0x180049bbb  mov     [rsp+108h+var_50], r14
0x180049bc3  mov     [rsp+108h+var_58], rsi
0x180049bcb  mov     word ptr [rsp+108h+pszFile], si
0x180049bd3  mov     rcx, [rsp+108h+var_D0]
0x180049bd8  test    rcx, rcx
0x180049bdb  jz      short loc_180049BEA
0x180049bdd  mov     rax, [rcx]
0x180049be0  mov     rax, [rax+10h]
0x180049be4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049be9  nop
0x180049bea  mov     rcx, [rsp+108h+var_C8]
0x180049bef  test    rcx, rcx
0x180049bf2  jz      short loc_180049C01
0x180049bf4  mov     rax, [rcx]
0x180049bf7  mov     rax, [rax+10h]
0x180049bfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c00  nop
0x180049c01  mov     rcx, [rsp+108h+var_C0]
0x180049c06  test    rcx, rcx
0x180049c09  jz      short loc_180049C18
0x180049c0b  mov     rax, [rcx]
0x180049c0e  mov     rax, [rax+10h]
0x180049c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c17  nop
0x180049c18  test    rbx, rbx
0x180049c1b  jz      short loc_180049C2D
0x180049c1d  mov     rax, [rbx]
0x180049c20  mov     rcx, rbx
0x180049c23  mov     rax, [rax+10h]
0x180049c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c2c  nop
0x180049c2d  mov     rcx, [rsp+108h+ppstm]
0x180049c32  test    rcx, rcx
0x180049c35  jz      short loc_180049C44
0x180049c37  mov     rax, [rcx]
0x180049c3a  mov     rax, [rax+10h]
0x180049c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c43  nop
0x180049c44  mov     eax, r15d
0x180049c47  jmp     loc_18004A4A8
0x180049c4c  mov     r15, [rsp+108h+var_C0]
0x180049c51  mov     rax, [r15]
0x180049c54  mov     r12, [rax]
0x180049c57  mov     rcx, [rsp+108h+var_C8]
0x180049c5c  mov     [rsp+108h+var_C8], rsi
0x180049c61  test    rcx, rcx
0x180049c64  jz      short loc_180049C73
0x180049c66  mov     rdx, [rcx]
0x180049c69  mov     rax, [rdx+10h]
0x180049c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c72  nop
0x180049c73  lea     r8, [rsp+108h+var_C8]
0x180049c78  lea     rdx, IID_IAppxBundleManifestReader2
0x180049c7f  mov     rcx, r15
0x180049c82  mov     rax, r12
0x180049c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c8a  mov     r15d, eax
0x180049c8d  test    eax, eax
0x180049c8f  jns     loc_180049D7A
0x180049c95  mov     rcx, [rsp+108h]; this
0x180049c9d  lea     rax, aFailedToBundle; "Failed to bundle manifest reader 2 inte"...
0x180049ca4  mov     [rsp+108h+var_E0], rax; char *
0x180049ca9  lea     rdx, aWs; "%ws"
0x180049cb0  mov     qword ptr [rsp+108h+var_E8], rdx; int
0x180049cb5  mov     r9d, r15d; char *
  ... truncated ...
```
