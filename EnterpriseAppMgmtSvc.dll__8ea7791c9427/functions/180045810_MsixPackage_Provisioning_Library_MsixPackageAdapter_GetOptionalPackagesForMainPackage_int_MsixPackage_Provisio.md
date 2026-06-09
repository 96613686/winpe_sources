# MsixPackage::Provisioning::Library::MsixPackageAdapter::GetOptionalPackagesForMainPackage(int,MsixPackage::Provisioning::Library::MsixProvisioningContext *,bool *,std::vector<ushort const *,std::allocator<ushort const *>> &)

- ea: `0x180045810`
- end: `0x1800464de`
- name: `?GetOptionalPackagesForMainPackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJHPEAVMsixProvisioningContext@234@PEA_NAEAV?$vector@PEBGV?$allocator@PEBG@std@@@std@@@Z`
- size: `3278`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003925c`

## callees

- `0x18001bf0c`
- `0x18001c5b8`
- `0x18003167c`
- `0x180031ed8`
- `0x180039e9c`
- `0x18003ae3c`
- `0x18003af74`
- `0x180045810`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800459e5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180045ac8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180045c09`
- `msvcrt!??3@YAXPEAX@Z` at `0x180045d31`
- `msvcrt!??3@YAXPEAX@Z` at `0x180045ea7`
- `msvcrt!??3@YAXPEAX@Z` at `0x180046048`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004618f`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800462de`
- `msvcrt!??3@YAXPEAX@Z` at `0x180046423`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800459e5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180045ac8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180045c09`
- `msvcrt!??3@YAXPEAX@Z` at `0x180045d31`
- `msvcrt!??3@YAXPEAX@Z` at `0x180045ea7`
- `msvcrt!??3@YAXPEAX@Z` at `0x180046048`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004618f`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800462de`
- `msvcrt!??3@YAXPEAX@Z` at `0x180046423`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045e8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046147`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046296`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800463c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045e8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046147`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046296`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800463c0`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x18004597a`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x18004597a`
- `AppXAllUserStore!FindFullNameForFamilyNameInAppxAllUserStore` at `0x180046249`
- `AppXAllUserStore!FindFullNameForFamilyNameInAppxAllUserStore` at `0x180046249`

## string_xrefs

- `0x1800459b1`: `Failed to open '%ws'.`
- `0x180045a94`: `Failed to create appx bundle factory.`
- `0x180045bd5`: `Failed to create appx bundle manifest reader for %ws.`
- `0x180045928`: `\AppxMetadata\AppxBundleManifest.xml`
- `0x1800459c0`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180045aa3`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180045be4`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180045d0c`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180045e41`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180045e73`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180045f97`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180045ff5`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004612b`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004627a`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180045cf1`: `Failed to bundle manifest reader 2 interface`
- `0x18004626b`: `Failed to find an existing version for optional package %ws in registry store`

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
  char *v8; // rdx
  unsigned __int64 v9; // rbx
  unsigned __int64 v10; // r8
  char *v11; // rdi
  char *v12; // rdx
  IStream *v13; // rcx
  const WCHAR *v14; // rcx
  _QWORD *v15; // rdx
  HRESULT v16; // ebx
  LPCWSTR *v17; // rdx
  int v19; // ebx
  __int64 v20; // rbx
  __int64 (__fastcall *v21)(__int64, IStream *, _QWORD **); // r15
  _QWORD *v22; // rcx
  int v23; // r15d
  LPCWSTR *v24; // rdx
  _QWORD *v25; // r15
  __int64 (__fastcall *v26)(_QWORD *, GUID *, _QWORD **); // r12
  _QWORD *v27; // rcx
  int v28; // r15d
  _QWORD *v29; // r15
  __int64 (__fastcall *v30)(_QWORD *, _QWORD **); // r12
  _QWORD *v31; // rcx
  int v32; // r15d
  int v33; // eax
  void *v34; // rdi
  _QWORD *v35; // r15
  __int64 v36; // r12
  __int64 v37; // rax
  int v38; // eax
  __int64 v39; // rax
  int v40; // edi
  __int64 v41; // rax
  int v42; // edi
  int FullNameForFamilyNameInAppxAllUserStore; // edi
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
  struct _GUID v55; // [rsp+80h] [rbp-88h] BYREF
  __int64 v56; // [rsp+90h] [rbp-78h]
  _BYTE *v57; // [rsp+98h] [rbp-70h]
  LPCWSTR pszFile[2]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v59; // [rsp+B0h] [rbp-58h]
  unsigned __int64 v60; // [rsp+B8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v5 = a4;
  pv = a1;
  *(_QWORD *)v55.Data4 = a1;
  v57 = a4;
  v51 = a5;
  v56 = a5;
  ppstm = 0;
  *(_QWORD *)&v55.Data1 = 0;
  v48 = 0;
  v47 = 0;
  v46 = 0;
  *a4 = 0;
  v60 = 7;
  v59 = 0;
  LOWORD(pszFile[0]) = 0;
  v8 = *(char **)(a3 + 560);
  v9 = -1;
  if ( *(_WORD *)v8 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)&v8[2 * v10] );
  }
  else
  {
    v10 = 0;
  }
  std::wstring::assign(pszFile, v8, v10);
  std::wstring::append(pszFile, (char *)L"\\", pszSrc[0] != 0);
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
  else
  {
    v9 = 0;
  }
  std::wstring::append(pszFile, v12, v9);
  std::wstring::append(pszFile, (char *)L"\\AppxMetadata\\AppxBundleManifest.xml", 0x24u);
  v13 = ppstm;
  ppstm = 0;
  if ( v13 )
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v13 + 16LL))(v13);
  v14 = (const WCHAR *)pszFile;
  if ( v60 >= 8 )
    v14 = pszFile[0];
  v16 = SHCreateStreamOnFileW(v14, 0, &ppstm);
  if ( v16 >= 0 )
  {
    *(_QWORD *)&v55.Data1 = 0;
    v19 = MsixPackage::Provisioning::Library::MsixAppxPackaging::CreateFactory<IAppxBundleFactory>(
            (MsixPackage::Provisioning::Library::MsixAppxPackaging *)(a3 + 216),
            v15,
            &v55);
    if ( v19 >= 0 )
    {
      v20 = *(_QWORD *)&v55.Data1;
      v21 = *(__int64 (__fastcall **)(__int64, IStream *, _QWORD **))(**(_QWORD **)&v55.Data1 + 40LL);
      v22 = v48;
      v48 = 0;
      if ( v22 )
        (*(void (__fastcall **)(_QWORD *, _QWORD))(*v22 + 16LL))(v22, *v22);
      v23 = v21(v20, ppstm, &v48);
      if ( v23 >= 0 )
      {
        v25 = v48;
        v26 = *(__int64 (__fastcall **)(_QWORD *, GUID *, _QWORD **))*v48;
        v27 = v47;
        v47 = 0;
        if ( v27 )
          (*(void (__fastcall **)(_QWORD *, _QWORD))(*v27 + 16LL))(v27, *v27);
        v28 = v26(v25, &IID_IAppxBundleManifestReader2, &v47);
        if ( v28 >= 0 )
        {
          v50 = 0;
          v29 = v47;
          v30 = *(__int64 (__fastcall **)(_QWORD *, _QWORD **))(*v47 + 24LL);
          v31 = v46;
          v46 = 0;
          if ( v31 )
            (*(void (__fastcall **)(_QWORD *, _QWORD))(*v31 + 16LL))(v31, *v31);
          v32 = v30(v29, &v46);
          if ( v32 >= 0 )
          {
            (*(void (__fastcall **)(_QWORD *, int *))(*v46 + 32LL))(v46, &v50);
            v35 = pv;
            v36 = v51;
            while ( v50 )
            {
              v51 = 0;
              v37 = *v46;
              v51 = 0;
              v38 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(v37 + 24))(v46, &v51);
              if ( v38 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x7E8,
                  (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                  (const char *)(unsigned int)v38);
              v54 = 0;
              v39 = *(_QWORD *)v51;
              v54 = 0;
              v40 = (*(__int64 (__fastcall **)(__int64, __int64 **))(v39 + 24))(v51, &v54);
              if ( v40 < 0 )
              {
                wil::details::in1diag3::Return_HrMsg(
                  retaddr,
                  (void *)0x7EE,
                  (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                  (const char *)(unsigned int)v40,
                  (int)"%ws",
                  L"Failed to get package Id for optional bundle");
                if ( v54 )
                  (*(void (__fastcall **)(__int64 *))(*v54 + 16))(v54);
                if ( v51 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
                if ( v60 >= 8 )
                  operator delete((void *)pszFile[0]);
                v60 = 7;
                v59 = 0;
                LOWORD(pszFile[0]) = 0;
                if ( v46 )
                  (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
                if ( v47 )
                  (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
                if ( v48 )
                  (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
                if ( v20 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
                if ( ppstm )
                  (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
                return (unsigned int)v40;
              }
              v53 = 0;
              v41 = *v54;
              v53 = 0;
              v42 = (*(__int64 (__fastcall **)(__int64 *, char **))(v41 + 80))(v54, &v53);
              if ( v42 < 0 )
              {
                wil::details::in1diag3::Return_HrMsg(
                  retaddr,
                  (void *)0x7F4,
                  (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                  (const char *)(unsigned int)v42,
                  (int)"%ws",
                  L"Failed to get package family name for optional bundle");
                if ( v53 )
                  CoTaskMemFree(v53);
                if ( v54 )
                  (*(void (__fastcall **)(__int64 *))(*v54 + 16))(v54);
                if ( v51 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
                if ( v60 >= 8 )
                  operator delete((void *)pszFile[0]);
                v60 = 7;
                v59 = 0;
                LOWORD(pszFile[0]) = 0;
                if ( v46 )
                  (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
                if ( v47 )
                  (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
                if ( v48 )
                  (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
                if ( v20 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
                if ( ppstm )
                  (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
                return (unsigned int)v42;
              }
              pv = 0;
              v45[0] = 0;
              FullNameForFamilyNameInAppxAllUserStore = FindFullNameForFamilyNameInAppxAllUserStore(
                                                          *(_QWORD *)(v35[2] + 584LL),
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
                if ( v60 >= 8 )
                  operator delete((void *)pszFile[0]);
                v60 = 7;
                v59 = 0;
                LOWORD(pszFile[0]) = 0;
                if ( v46 )
                  (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
                if ( v47 )
                  (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
                if ( v48 )
                  (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
                if ( v20 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
                if ( ppstm )
                  (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
                return (unsigned int)FullNameForFamilyNameInAppxAllUserStore;
              }
              if ( v45[0] )
              {
                try
                {
                  std::vector<unsigned short const *>::push_back(v36, pv);
                }
                catch ( ... )
                {
                  wil::details::in1diag3::Log_CaughtExceptionMsg(
                    retaddr,
                    (void *)0x809,
                    (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                    "Failed to add optional package full name %ws to optional list",
                    *(const char **)pv);
                  v20 = *(_QWORD *)&v55.Data1;
                  v35 = *(_QWORD **)v55.Data4;
                  v36 = v56;
                  v5 = v57;
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
            if ( v60 >= 8 )
              operator delete((void *)pszFile[0]);
            v60 = 7;
            v59 = 0;
            LOWORD(pszFile[0]) = 0;
            if ( v46 )
              (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
            if ( v47 )
              (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
            if ( v48 )
              (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
            if ( v20 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
            if ( ppstm )
              (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
            return 0;
          }
          else
          {
            pv = 0;
            if ( *((_QWORD *)v11 + 3) >= 8u )
              v11 = *(char **)v11;
            v33 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                    (char *)&pv,
                    L"Failed to get optional packages for main package '%s'",
                    v11);
            if ( v33 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x7E3,
                (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                (const char *)(unsigned int)v33);
            v34 = pv;
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0x7E3,
              (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
              (const char *)(unsigned int)v32,
              (int)"%ws",
              (const char *)pv);
            if ( v34 )
              CoTaskMemFree(v34);
            if ( v60 >= 8 )
              operator delete((void *)pszFile[0]);
            v60 = 7;
            v59 = 0;
            LOWORD(pszFile[0]) = 0;
            if ( v46 )
              (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
            if ( v47 )
              (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
            if ( v48 )
              (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
            if ( v20 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
            if ( ppstm )
              (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
            return (unsigned int)v32;
          }
        }
        else
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x7DD,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            (const char *)(unsigned int)v28,
            (int)"%ws",
            L"Failed to bundle manifest reader 2 interface");
          if ( v60 >= 8 )
            operator delete((void *)pszFile[0]);
          v60 = 7;
          v59 = 0;
          LOWORD(pszFile[0]) = 0;
          if ( v46 )
            (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
          if ( v47 )
            (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
          if ( v48 )
            (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
          if ( v20 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          if ( ppstm )
            (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
          return (unsigned int)v28;
        }
      }
      else
      {
        v24 = pszFile;
        if ( v60 >= 8 )
          v24 = (LPCWSTR *)pszFile[0];
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x7D8,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v23,
          (int)"Failed to create appx bundle manifest reader for %ws.",
          (const char *)v24);
        if ( v60 >= 8 )
          operator delete((void *)pszFile[0]);
        v60 = 7;
        v59 = 0;
        LOWORD(pszFile[0]) = 0;
        if ( v46 )
          (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
        if ( v47 )
          (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
        if ( v48 )
          (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
        if ( v20 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        if ( ppstm )
          (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
        return (unsigned int)v23;
      }
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x7D3,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v19,
        (int)"Failed to create appx bundle factory.",
        v44);
      if ( v60 >= 8 )
        operator delete((void *)pszFile[0]);
      v60 = 7;
      v59 = 0;
      LOWORD(pszFile[0]) = 0;
      if ( v46 )
        (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
      if ( v47 )
        (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
      if ( v48 )
        (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
      if ( *(_QWORD *)&v55.Data1 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v55.Data1 + 16LL))(*(_QWORD *)&v55.Data1);
      if ( ppstm )
        (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
      return (unsigned int)v19;
    }
  }
  else
  {
    v17 = pszFile;
    if ( v60 >= 8 )
      v17 = (LPCWSTR *)pszFile[0];
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x7D1,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v16,
      (int)"Failed to open '%ws'.",
      (const char *)v17);
    if ( v60 >= 8 )
      operator delete((void *)pszFile[0]);
    v60 = 7;
    v59 = 0;
    LOWORD(pszFile[0]) = 0;
    if ( v46 )
      (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
    if ( v47 )
      (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
    if ( v48 )
      (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
    if ( ppstm )
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
    return (unsigned int)v16;
  }
}

```

## disassembly

```asm
0x180045810  mov     r11, rsp
0x180045813  push    rbx
0x180045814  push    rsi
0x180045815  push    rdi
0x180045816  push    r12
0x180045818  push    r13
0x18004581a  push    r14
0x18004581c  push    r15
0x18004581e  sub     rsp, 0D0h
0x180045825  mov     rax, cs:__security_cookie
0x18004582c  xor     rax, rsp
0x18004582f  mov     [rsp+108h+var_48], rax
0x180045837  mov     r13, r9
0x18004583a  mov     r15, r8
0x18004583d  mov     rdi, rcx
0x180045840  mov     [rsp+108h+pv], rcx
0x180045845  mov     [rsp+108h+var_80], rcx
0x18004584d  mov     [rsp+108h+var_70], r9
0x180045855  mov     rax, [rsp+108h+arg_20]
0x18004585d  mov     [rsp+108h+var_A8], rax
0x180045862  mov     [rsp+108h+var_78], rax
0x18004586a  xor     esi, esi
0x18004586c  mov     [rsp+108h+ppstm], rsi
0x180045871  mov     [r11-88h], rsi
0x180045878  mov     [rsp+108h+var_C0], rsi
0x18004587d  mov     [rsp+108h+var_C8], rsi
0x180045882  mov     [rsp+108h+var_D0], rsi
0x180045887  mov     [r9], sil
0x18004588a  lea     r14d, [rsi+7]
0x18004588e  mov     [r11-50h], r14
0x180045892  mov     [r11-58h], rsi
0x180045896  mov     [r11-68h], si
0x18004589b  mov     rdx, [r8+230h]; Src
0x1800458a2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800458a6  cmp     [rdx], si
0x1800458a9  jnz     short loc_1800458B0
0x1800458ab  mov     r8d, esi
0x1800458ae  jmp     short loc_1800458BD
0x1800458b0  mov     r8, rbx
0x1800458b3  inc     r8
0x1800458b6  cmp     [rdx+r8*2], si
0x1800458bb  jnz     short loc_1800458B3
0x1800458bd  lea     rcx, [rsp+108h+pszFile]; void *
0x1800458c5  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800458ca  mov     r8, rsi
0x1800458cd  cmp     word ptr cs:pszSrc, si; "\\"
0x1800458d4  setnz   r8b
0x1800458d8  lea     rdx, pszSrc; "\\"
0x1800458df  lea     rcx, [rsp+108h+pszFile]; Src
0x1800458e7  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x1800458ec  add     rdi, 30h ; '0'
0x1800458f0  cmp     qword ptr [rdi+18h], 8
0x1800458f5  jb      short loc_1800458FC
0x1800458f7  mov     rdx, [rdi]
0x1800458fa  jmp     short loc_1800458FF
0x1800458fc  mov     rdx, rdi; void *
0x1800458ff  cmp     [rdx], si
0x180045902  jnz     short loc_180045909
0x180045904  mov     rbx, rsi
0x180045907  jmp     short loc_180045912
0x180045909  inc     rbx
0x18004590c  cmp     [rdx+rbx*2], si
0x180045910  jnz     short loc_180045909
0x180045912  mov     r8, rbx
0x180045915  lea     rcx, [rsp+108h+pszFile]; Src
0x18004591d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180045922  mov     r8d, 24h ; '$'
0x180045928  lea     rdx, aAppxmetadataAp; "\\AppxMetadata\\AppxBundleManifest.xml"
0x18004592f  lea     rcx, [rsp+108h+pszFile]; Src
0x180045937  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18004593c  nop
0x18004593d  mov     rcx, [rsp+108h+ppstm]
0x180045942  mov     [rsp+108h+ppstm], rsi
0x180045947  test    rcx, rcx
0x18004594a  jz      short loc_180045959
0x18004594c  mov     rax, [rcx]
0x18004594f  mov     rax, [rax+10h]
0x180045953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045958  nop
0x180045959  lea     rcx, [rsp+108h+pszFile]
0x180045961  cmp     [rsp+108h+var_50], 8
0x18004596a  cmovnb  rcx, [rsp+108h+pszFile]; pszFile
0x180045973  lea     r8, [rsp+108h+ppstm]; ppstm
0x180045978  xor     edx, edx; grfMode
0x18004597a  call    cs:__imp_SHCreateStreamOnFileW
0x180045980  mov     ebx, eax
0x180045982  test    eax, eax
0x180045984  jns     loc_180045A66
0x18004598a  lea     rdx, [rsp+108h+pszFile]
0x180045992  cmp     [rsp+108h+var_50], 8
0x18004599b  cmovnb  rdx, [rsp+108h+pszFile]
0x1800459a4  mov     rcx, [rsp+108h]; this
0x1800459ac  mov     [rsp+108h+var_E0], rdx; char *
0x1800459b1  lea     rax, aFailedToOpenWs; "Failed to open '%ws'."
0x1800459b8  mov     qword ptr [rsp+108h+var_E8], rax; int
0x1800459bd  mov     r9d, ebx; char *
0x1800459c0  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800459c7  mov     edx, 7D1h; void *
0x1800459cc  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800459d1  nop
0x1800459d2  cmp     [rsp+108h+var_50], 8
0x1800459db  jb      short loc_1800459EB
0x1800459dd  mov     rcx, [rsp+108h+pszFile]
0x1800459e5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800459eb  mov     [rsp+108h+var_50], r14
0x1800459f3  mov     [rsp+108h+var_58], rsi
0x1800459fb  mov     word ptr [rsp+108h+pszFile], si
0x180045a03  mov     rcx, [rsp+108h+var_D0]
0x180045a08  test    rcx, rcx
0x180045a0b  jz      short loc_180045A1A
0x180045a0d  mov     rax, [rcx]
0x180045a10  mov     rax, [rax+10h]
0x180045a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a19  nop
0x180045a1a  mov     rcx, [rsp+108h+var_C8]
0x180045a1f  test    rcx, rcx
0x180045a22  jz      short loc_180045A31
0x180045a24  mov     rax, [rcx]
0x180045a27  mov     rax, [rax+10h]
0x180045a2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a30  nop
0x180045a31  mov     rcx, [rsp+108h+var_C0]
0x180045a36  test    rcx, rcx
0x180045a39  jz      short loc_180045A48
0x180045a3b  mov     rax, [rcx]
0x180045a3e  mov     rax, [rax+10h]
0x180045a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a47  nop
0x180045a48  mov     rcx, [rsp+108h+ppstm]
0x180045a4d  test    rcx, rcx
0x180045a50  jz      short loc_180045A5F
0x180045a52  mov     rax, [rcx]
0x180045a55  mov     rax, [rax+10h]
0x180045a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a5e  nop
0x180045a5f  mov     eax, ebx
0x180045a61  jmp     loc_1800464BA
0x180045a66  lea     rcx, [r15+0D8h]
0x180045a6d  mov     [rsp+108h+var_88], rsi
0x180045a75  lea     r8, [rsp+108h+var_88]
0x180045a7d  call    ??$CreateFactory@UIAppxBundleFactory@@@MsixAppxPackaging@Library@Provisioning@MsixPackage@@IEAAJAEBU_GUID@@PEAPEAUIAppxBundleFactory@@@Z; MsixPackage::Provisioning::Library::MsixAppxPackaging::CreateFactory<IAppxBundleFactory>(_GUID const &,IAppxBundleFactory * *)
0x180045a82  mov     ebx, eax
0x180045a84  test    eax, eax
0x180045a86  jns     loc_180045B63
0x180045a8c  mov     rcx, [rsp+108h]; this
0x180045a94  lea     rax, aFailedToCreate_10; "Failed to create appx bundle factory."
0x180045a9b  mov     qword ptr [rsp+108h+var_E8], rax; int
0x180045aa0  mov     r9d, ebx; char *
0x180045aa3  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180045aaa  mov     edx, 7D3h; void *
0x180045aaf  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180045ab4  nop
0x180045ab5  cmp     [rsp+108h+var_50], 8
0x180045abe  jb      short loc_180045ACE
0x180045ac0  mov     rcx, [rsp+108h+pszFile]
0x180045ac8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180045ace  mov     [rsp+108h+var_50], r14
0x180045ad6  mov     [rsp+108h+var_58], rsi
0x180045ade  mov     word ptr [rsp+108h+pszFile], si
0x180045ae6  mov     rcx, [rsp+108h+var_D0]
0x180045aeb  test    rcx, rcx
0x180045aee  jz      short loc_180045AFD
0x180045af0  mov     rax, [rcx]
0x180045af3  mov     rax, [rax+10h]
0x180045af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045afc  nop
0x180045afd  mov     rcx, [rsp+108h+var_C8]
0x180045b02  test    rcx, rcx
0x180045b05  jz      short loc_180045B14
0x180045b07  mov     rax, [rcx]
0x180045b0a  mov     rax, [rax+10h]
0x180045b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b13  nop
0x180045b14  mov     rcx, [rsp+108h+var_C0]
0x180045b19  test    rcx, rcx
0x180045b1c  jz      short loc_180045B2B
0x180045b1e  mov     rax, [rcx]
0x180045b21  mov     rax, [rax+10h]
0x180045b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b2a  nop
0x180045b2b  mov     rcx, [rsp+108h+var_88]
0x180045b33  test    rcx, rcx
0x180045b36  jz      short loc_180045B45
0x180045b38  mov     rax, [rcx]
0x180045b3b  mov     rax, [rax+10h]
0x180045b3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b44  nop
0x180045b45  mov     rcx, [rsp+108h+ppstm]
0x180045b4a  test    rcx, rcx
0x180045b4d  jz      short loc_180045B5C
0x180045b4f  mov     rax, [rcx]
0x180045b52  mov     rax, [rax+10h]
0x180045b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b5b  nop
0x180045b5c  mov     eax, ebx
0x180045b5e  jmp     loc_1800464BA
0x180045b63  mov     rbx, [rsp+108h+var_88]
0x180045b6b  mov     rax, [rbx]
0x180045b6e  mov     r15, [rax+28h]
0x180045b72  mov     rcx, [rsp+108h+var_C0]
0x180045b77  mov     [rsp+108h+var_C0], rsi
0x180045b7c  test    rcx, rcx
0x180045b7f  jz      short loc_180045B8E
0x180045b81  mov     rdx, [rcx]
0x180045b84  mov     rax, [rdx+10h]
0x180045b88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b8d  nop
0x180045b8e  lea     r8, [rsp+108h+var_C0]
0x180045b93  mov     rdx, [rsp+108h+ppstm]
0x180045b98  mov     rcx, rbx
0x180045b9b  mov     rax, r15
0x180045b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045ba3  mov     r15d, eax
0x180045ba6  test    eax, eax
0x180045ba8  jns     loc_180045CA0
0x180045bae  lea     rdx, [rsp+108h+pszFile]
0x180045bb6  cmp     [rsp+108h+var_50], 8
0x180045bbf  cmovnb  rdx, [rsp+108h+pszFile]
0x180045bc8  mov     rcx, [rsp+108h]; this
0x180045bd0  mov     [rsp+108h+var_E0], rdx; char *
0x180045bd5  lea     rax, aFailedToCreate_8; "Failed to create appx bundle manifest r"...
0x180045bdc  mov     qword ptr [rsp+108h+var_E8], rax; int
0x180045be1  mov     r9d, r15d; char *
0x180045be4  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180045beb  mov     edx, 7D8h; void *
0x180045bf0  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180045bf5  nop
0x180045bf6  cmp     [rsp+108h+var_50], 8
0x180045bff  jb      short loc_180045C0F
0x180045c01  mov     rcx, [rsp+108h+pszFile]
0x180045c09  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180045c0f  mov     [rsp+108h+var_50], r14
0x180045c17  mov     [rsp+108h+var_58], rsi
0x180045c1f  mov     word ptr [rsp+108h+pszFile], si
0x180045c27  mov     rcx, [rsp+108h+var_D0]
0x180045c2c  test    rcx, rcx
0x180045c2f  jz      short loc_180045C3E
0x180045c31  mov     rax, [rcx]
0x180045c34  mov     rax, [rax+10h]
0x180045c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c3d  nop
0x180045c3e  mov     rcx, [rsp+108h+var_C8]
0x180045c43  test    rcx, rcx
0x180045c46  jz      short loc_180045C55
0x180045c48  mov     rax, [rcx]
0x180045c4b  mov     rax, [rax+10h]
0x180045c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c54  nop
0x180045c55  mov     rcx, [rsp+108h+var_C0]
0x180045c5a  test    rcx, rcx
0x180045c5d  jz      short loc_180045C6C
0x180045c5f  mov     rax, [rcx]
0x180045c62  mov     rax, [rax+10h]
0x180045c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c6b  nop
0x180045c6c  test    rbx, rbx
0x180045c6f  jz      short loc_180045C81
0x180045c71  mov     rax, [rbx]
0x180045c74  mov     rcx, rbx
0x180045c77  mov     rax, [rax+10h]
0x180045c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c80  nop
0x180045c81  mov     rcx, [rsp+108h+ppstm]
0x180045c86  test    rcx, rcx
0x180045c89  jz      short loc_180045C98
0x180045c8b  mov     rax, [rcx]
0x180045c8e  mov     rax, [rax+10h]
0x180045c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c97  nop
0x180045c98  mov     eax, r15d
0x180045c9b  jmp     loc_1800464BA
0x180045ca0  mov     r15, [rsp+108h+var_C0]
0x180045ca5  mov     rax, [r15]
0x180045ca8  mov     r12, [rax]
0x180045cab  mov     rcx, [rsp+108h+var_C8]
0x180045cb0  mov     [rsp+108h+var_C8], rsi
0x180045cb5  test    rcx, rcx
0x180045cb8  jz      short loc_180045CC7
0x180045cba  mov     rdx, [rcx]
0x180045cbd  mov     rax, [rdx+10h]
0x180045cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045cc6  nop
0x180045cc7  lea     r8, [rsp+108h+var_C8]
0x180045ccc  lea     rdx, IID_IAppxBundleManifestReader2
0x180045cd3  mov     rcx, r15
0x180045cd6  mov     rax, r12
0x180045cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045cde  mov     r15d, eax
0x180045ce1  test    eax, eax
0x180045ce3  jns     loc_180045DC8
0x180045ce9  mov     rcx, [rsp+108h]; this
0x180045cf1  lea     rax, aFailedToBundle; "Failed to bundle manifest reader 2 inte"...
0x180045cf8  mov     [rsp+108h+var_E0], rax; char *
0x180045cfd  lea     rdx, aWs; "%ws"
0x180045d04  mov     qword ptr [rsp+108h+var_E8], rdx; int
0x180045d09  mov     r9d, r15d; char *
0x180045d0c  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180045d13  mov     edx, 7DDh; void *
0x180045d18  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180045d1d  nop
  ... truncated ...
```
