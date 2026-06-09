# ImmersiveIcons::GetIconData(ushort const *,ImmersiveIcons::LoadIconParams const &,ImmersiveIcons::IconData2 *)

- ea: `0x180008c44`
- end: `0x180009dca`
- name: `?GetIconData@ImmersiveIcons@@YAJPEBGAEBULoadIconParams@1@PEAUIconData2@1@@Z`
- size: `4486`
- prototype: `__int64 __fastcall(PCWSTR pszItem, const unsigned __int16 *, const struct ImmersiveIcons::LoadIconParams *, struct ImmersiveIcons::IconData2 *)`
- caller_count: `1`
- callee_count: `37`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1803767cc`

## callees

- `0x180008c44`
- `0x180009dd0`
- `0x180009dfc`
- `0x18000a6a4`
- `0x18000a770`
- `0x18000a850`
- `0x18000e2b0`
- `0x18000edd4`
- `0x18001e1d4`
- `0x1800378dc`
- `0x180037b9c`
- `0x180041f54`
- `0x18005a16c`
- `0x18008c770`
- `0x1800ba13c`
- `0x1800eb924`
- `0x1800effd4`
- `0x1800f0034`
- `0x1800fd028`
- `0x1800fdb90`
- `0x18010303c`
- `0x180106af8`
- `0x180108970`
- `0x18010c7c0`
- `0x18010c864`
- `0x180123cd0`
- `0x180142e10`
- `0x180157fc0`
- `0x18016a92c`
- `0x180334280`
- `0x1803342e0`
- `0x180335a70`
- `0x18033a11c`
- `0x180375724`
- `0x18037589c`
- `0x180376270`
- `0x1803bb010`

## import_xrefs

- `SHELL32!SHCreateItemInKnownFolder` at `0x180008cad`
- `SHELL32!SHCreateItemInKnownFolder` at `0x180008cad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009aab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009b7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009c12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009aab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009b7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009c12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009b04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009b38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009b04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009b38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008e14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008e14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008e55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800097b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009802`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009833`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000985d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008e55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800097b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009802`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009833`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000985d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008ee4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009087`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008ee4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009087`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180009b13`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180009b13`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x180009021`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x180009021`

## pseudocode

```c
__int64 __fastcall ImmersiveIcons::GetIconData(
        WCHAR *pszItem,
        ImmersiveIcons *a2,
        const struct ImmersiveIcons::LoadIconParams *a3,
        struct ImmersiveIcons::IconData2 *a4)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  int As; // eax
  __int64 v9; // rdx
  int v10; // eax
  __int64 v11; // rbx
  WCHAR *v12; // r14
  unsigned int v13; // eax
  UINT32 v14; // edx
  HRESULT v15; // eax
  HSTRING v16; // rdx
  unsigned int v17; // r8d
  HSTRING v18; // rdx
  unsigned __int16 **v19; // r8
  int v20; // eax
  __int64 v21; // rdx
  HRESULT v22; // eax
  int PackageFullNameForAppsFolderItem; // eax
  __int64 v24; // rdx
  LPVOID v25; // rdi
  __int64 (__fastcall *v26)(LPVOID, WCHAR *, _QWORD, _QWORD); // rbx
  HRESULT Instance; // eax
  int v28; // eax
  __int64 v29; // rdx
  HSTRING v30; // rdi
  __int64 (__fastcall *v31)(HSTRING, GUID *, _QWORD); // rbx
  int v32; // eax
  __int64 (__fastcall ***v33)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v34)(_QWORD, GUID *, __int64 *); // rdi
  int v35; // eax
  HSTRING v36; // rdx
  HSTRING v37; // rdx
  unsigned __int16 **v38; // r8
  int v39; // eax
  __int64 v40; // rdx
  HSTRING v41; // rdi
  __int64 (__fastcall *v42)(HSTRING, GUID *, struct ImmersiveIcons::LoadIconParams **); // rbx
  int v43; // eax
  __int64 v44; // rdx
  int v45; // r12d
  int v46; // r15d
  struct IResourceContext *v47; // r8
  ImmersiveIcons *v48; // rcx
  void *v49; // r13
  int inited; // eax
  __int64 v51; // rdi
  int (__fastcall *v52)(__int64, struct ImmersiveIcons::LoadIconParams *, void *, __int64 *); // rbx
  int v53; // eax
  __int64 *v54; // rcx
  __int64 v55; // rdi
  int (__fastcall *v56)(__int64, const wchar_t *, __int64 *); // rbx
  __int64 v57; // rbx
  __int64 v58; // rax
  int v59; // eax
  __int64 v60; // rdi
  int (__fastcall *v61)(__int64, struct ImmersiveIcons::LoadIconParams *, void *, __int64 *); // rbx
  int v62; // eax
  __int64 v63; // rdi
  __int64 (__fastcall *v64)(__int64, const wchar_t *, __int64 *); // rbx
  int v65; // r12d
  ImmersiveIcons *v66; // rbx
  int ContrastForParams; // eax
  __int64 v68; // rdx
  __int64 v69; // rdx
  int v70; // eax
  __int64 v71; // rdx
  __int64 v72; // rdi
  __int64 (__fastcall *v73)(__int64, struct ImmersiveIcons::LoadIconParams *, void *, ImmersiveIcons **); // rbx
  ImmersiveIcons *v74; // rbx
  __int64 (__fastcall *v75)(ImmersiveIcons *, GUID *, __int64 *); // rdi
  int v76; // eax
  ImmersiveIcons *v77; // rcx
  struct ImmersiveIcons::LoadIconParams *v78; // rcx
  __int64 v79; // rcx
  __int64 (__fastcall ***v80)(_QWORD, _QWORD, _QWORD); // rcx
  HSTRING v81; // rcx
  void *v82; // rcx
  __int64 v83; // rdi
  __int64 (__fastcall *v84)(__int64, const wchar_t *, __int64 *); // rbx
  int v85; // r12d
  __int64 v86; // rdi
  int (__fastcall *v87)(__int64, const wchar_t *, __int64 *); // rbx
  __int64 v88; // rdi
  int (__fastcall *v89)(__int64, const wchar_t *, HSTRING_HEADER *); // rbx
  char v90; // r14
  __int64 v91; // rdi
  __int64 (__fastcall *v92)(__int64, LPVOID *); // rbx
  int v93; // eax
  __int64 v94; // rdx
  HSTRING v95; // rbx
  __int64 v96; // rax
  int v97; // eax
  __int64 v98; // rdx
  const WCHAR *StringRawBuffer; // rax
  __int64 v100; // r9
  const unsigned __int16 *v101; // rax
  HSTRING v103; // rcx
  __int64 v104; // rdx
  HSTRING_HEADER *v105; // rbx
  int ppv; // [rsp+20h] [rbp-E0h]
  void **ppva; // [rsp+20h] [rbp-E0h]
  void **ppvb; // [rsp+20h] [rbp-E0h]
  int ppvc; // [rsp+20h] [rbp-E0h]
  __int64 v110; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING v111; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v112; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v113; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v114)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-B0h] BYREF
  struct ImmersiveIcons::LoadIconParams *v115; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v117; // [rsp+68h] [rbp-98h]
  __int64 v118; // [rsp+70h] [rbp-90h]
  HSTRING__ v119[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v120; // [rsp+80h] [rbp-80h]
  __int64 v121; // [rsp+88h] [rbp-78h]
  HSTRING v122; // [rsp+90h] [rbp-70h] BYREF
  PCWSTR sourceString; // [rsp+98h] [rbp-68h] BYREF
  UINT32 length[2]; // [rsp+A0h] [rbp-60h]
  __int64 v125; // [rsp+A8h] [rbp-58h]
  PCWSTR v126[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v127; // [rsp+C0h] [rbp-40h]
  ImmersiveIcons *v128; // [rsp+D0h] [rbp-30h] BYREF
  LPVOID v129; // [rsp+D8h] [rbp-28h] BYREF
  void *v130; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v131; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v132; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v133; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v134; // [rsp+100h] [rbp+0h] BYREF
  __int64 v135; // [rsp+108h] [rbp+8h]
  __int64 v136; // [rsp+110h] [rbp+10h]
  __int64 v137; // [rsp+118h] [rbp+18h] BYREF
  __int64 v138; // [rsp+120h] [rbp+20h]
  __int64 v139; // [rsp+128h] [rbp+28h]
  __int64 v140; // [rsp+130h] [rbp+30h] BYREF
  __int64 v141; // [rsp+138h] [rbp+38h]
  __int64 v142; // [rsp+140h] [rbp+40h]
  _QWORD v143[5]; // [rsp+148h] [rbp+48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+170h] [rbp+70h] BYREF
  HSTRING string; // [rsp+188h] [rbp+88h] BYREF
  HSTRING_HEADER v146; // [rsp+190h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  v128 = a2;
  v130 = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v130);
  v6 = SHCreateItemInKnownFolder(
         &FOLDERID_AppsFolder,
         0x4000u,
         pszItem,
         &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
         &v130);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDE,
      (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
      (const char *)(unsigned int)v6,
      ppv);
LABEL_158:
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v130);
    return v7;
  }
  v110 = 0;
  Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(&v110);
  As = wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(
         (unsigned int)&v110,
         (_DWORD)v130,
         1,
         (unsigned int)qword_18040A030,
         4);
  v7 = As;
  if ( As < 0 )
  {
    v9 = 237;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
      (const char *)(unsigned int)As,
      (int)ppva);
LABEL_157:
    Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::~ComPtr<Windows::Foundation::IUriRuntimeClass>(&v110);
    goto LABEL_158;
  }
  LODWORD(v127) = 4;
  *(_OWORD *)v126 = PKEY_Tile_Background;
  As = wil::PropertyStoreHelperBase<IPropertyStore>::GetAsUInt32<_tagpropertykey>(&v110, v126, (char *)a3 + 12);
  v7 = As;
  if ( As < 0 )
  {
    v9 = 239;
    goto LABEL_5;
  }
  sourceString = 0;
  *(_OWORD *)v126 = PKEY_Tile_SmallLogoPath;
  *(_QWORD *)length = -1;
  v125 = -1;
  LODWORD(v127) = 2;
  v10 = wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(&v110, v126, &sourceString);
  v7 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF2,
      (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
      (const char *)(unsigned int)v10,
      (int)ppva);
LABEL_156:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString);
    goto LABEL_157;
  }
  LODWORD(v11) = length[0];
  v12 = (WCHAR *)sourceString;
  if ( *(_QWORD *)length == -1 )
  {
    if ( sourceString )
    {
      v11 = -1;
      do
        ++v11;
      while ( sourceString[v11] );
    }
    else
    {
      v11 = 0;
    }
    *(_QWORD *)length = v11;
  }
  string = 0;
  v13 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v11);
  v14 = v13 - 1;
  if ( (unsigned int)v11 < v13 )
    v14 = v11;
  v15 = WindowsCreateStringReference(v12, v14, &hstringHeader, &string);
  if ( v15 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v15, (int)v16, v17);
    __debugbreak();
  }
  pv = 0;
  v117 = 0;
  v118 = 0;
  if ( ShellMRTHelper::Common::HasFileUriScheme((ShellMRTHelper::Common *)string, v16) )
  {
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v117 = -1;
    v118 = -1;
    v20 = TileUtils::ConvertFileUriToFilePath(v12, (const unsigned __int16 *)&pv, v19);
    v7 = v20;
    if ( v20 < 0 )
    {
      v21 = 260;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
        (const char *)(unsigned int)v20,
        (int)ppva);
LABEL_155:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
      string = 0;
      goto LABEL_156;
    }
  }
  else
  {
    if ( ShellMRTHelper::Common::HasMsAppDataUriScheme((ShellMRTHelper::Common *)string, v18) )
    {
      v129 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v129);
      v22 = CoCreateInstance(
              &GUID_a8ca4495_65ab_4333_9ff9_4feb6fbf5169,
              0,
              1u,
              &GUID_428bb582_2a87_4ea0_b529_30067cc4a4d7,
              &v129);
      v7 = v22;
      if ( v22 >= 0 )
      {
        *(_QWORD *)&v119[0].unused = 0;
        v120 = 0;
        v121 = 0;
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v119);
        v120 = -1;
        v121 = -1;
        PackageFullNameForAppsFolderItem = ImmersiveIcons::GetPackageFullNameForAppsFolderItem((CallerIdentity *)pszItem);
        v7 = PackageFullNameForAppsFolderItem;
        if ( PackageFullNameForAppsFolderItem >= 0 )
        {
          v25 = v129;
          v26 = *(__int64 (__fastcall **)(LPVOID, WCHAR *, _QWORD, _QWORD))(*(_QWORD *)v129 + 48LL);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
          ppva = &pv;
          v117 = -1;
          v118 = -1;
          PackageFullNameForAppsFolderItem = v26(v25, v12, *(_QWORD *)&v119[0].unused, 0);
          v7 = PackageFullNameForAppsFolderItem;
          if ( PackageFullNameForAppsFolderItem >= 0 )
          {
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v119);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v129);
            goto LABEL_37;
          }
          v24 = 270;
        }
        else
        {
          v24 = 268;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v24,
          (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
          (const char *)(unsigned int)PackageFullNameForAppsFolderItem,
          (int)ppva);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v119);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x109,
          (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
          (const char *)(unsigned int)v22,
          (int)ppva);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v129);
      goto LABEL_155;
    }
    if ( !PathIsRelativeW(v12) )
    {
      v20 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
              &pv,
              &sourceString);
      v7 = v20;
      if ( v20 < 0 )
      {
        v21 = 276;
        goto LABEL_26;
      }
    }
  }
LABEL_37:
  if ( !pv || !*(_WORD *)pv )
  {
    v111 = 0;
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v111);
    Instance = CoCreateInstance(
                 &GUID_dbce7e40_7345_439d_b12c_114a11819a09,
                 0,
                 1u,
                 &GUID_130a2f65_2be7_4309_9a58_a9052ff2b61c,
                 (LPVOID *)&v111);
    v7 = Instance;
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11D,
        (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
        (const char *)(unsigned int)Instance,
        (int)ppvb);
LABEL_154:
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v111);
      goto LABEL_155;
    }
    v126[0] = 0;
    v126[1] = (PCWSTR)-1LL;
    v127 = -1;
    v28 = ImmersiveIcons::GetPackageFullNameForAppsFolderItem((CallerIdentity *)pszItem);
    v7 = v28;
    if ( v28 < 0 )
    {
      v29 = 288;
LABEL_49:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v29,
        (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
        (const char *)(unsigned int)v28,
        (int)ppvb);
LABEL_153:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v126);
      goto LABEL_154;
    }
    v28 = (*(__int64 (__fastcall **)(HSTRING, PCWSTR))(*(_QWORD *)v111 + 40LL))(v111, v126[0]);
    v7 = v28;
    if ( v28 < 0 )
    {
      v29 = 290;
      goto LABEL_49;
    }
    v30 = v111;
    v114 = 0;
    v31 = *(__int64 (__fastcall **)(HSTRING, GUID *, _QWORD))(*(_QWORD *)v111 + 56LL);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v114);
    v32 = v31(v30, &GUID_6e21e72b_b9b0_42ae_a686_983cf784edcd, &v114);
    v7 = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x125,
        (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
        (const char *)(unsigned int)v32,
        (int)ppvb);
LABEL_152:
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v114);
      goto LABEL_153;
    }
    v33 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v114;
    v113 = 0;
    v34 = **v114;
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v113);
    v35 = v34(v33, &GUID_2fe6ec6e_da7e_4b2a_a8f9_90b289061f20, &v113);
    v7 = v35;
    if ( v35 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x128,
        (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
        (const char *)(unsigned int)v35,
        (int)ppvb);
LABEL_151:
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v113);
      goto LABEL_152;
    }
    *(_QWORD *)&v119[0].unused = 0;
    v120 = 0;
    v121 = 0;
    if ( ShellMRTHelper::Common::HasMsAppXUriScheme((ShellMRTHelper::Common *)string, v36) )
    {
      v120 = -1;
      v121 = -1;
      v39 = ShellMRTHelper::Common::ConvertMsAppXUriToMsResourceUri((ShellMRTHelper::Common *)string, v119, v38);
      v7 = v39;
      if ( v39 < 0 )
      {
        v40 = 303;
LABEL_59:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v40,
          (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
          (const char *)(unsigned int)v39,
          (int)ppvb);
LABEL_150:
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v119);
        goto LABEL_151;
      }
    }
    else if ( ShellMRTHelper::Common::HasMsResourceUriScheme((ShellMRTHelper::Common *)string, v37) )
    {
      v39 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
              v119,
              &sourceString);
      v7 = v39;
      if ( v39 < 0 )
      {
        v40 = 310;
        goto LABEL_59;
      }
    }
    else
    {
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&sourceString);
      v39 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              v119,
              L"Files\\",
              *(_QWORD *)length + 7LL);
      v7 = v39;
      if ( v39 < 0 )
      {
        v40 = 317;
        goto LABEL_59;
      }
      v39 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(
              v119,
              &sourceString);
      v7 = v39;
      if ( v39 < 0 )
      {
        v40 = 318;
        goto LABEL_59;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::ReplaceChars(v119);
      v12 = (WCHAR *)sourceString;
    }
    v41 = v111;
    v115 = 0;
    v42 = *(__int64 (__fastcall **)(HSTRING, GUID *, struct ImmersiveIcons::LoadIconParams **))(*(_QWORD *)v111 + 72LL);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v115);
    v43 = v42(v41, &GUID_e3c22b30_8502_4b2f_9133_559674587e51, &v115);
    v7 = v43;
    if ( v43 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x145,
        (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
        (const char *)(unsigned int)v43,
        (int)ppvb);
LABEL_149:
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v115);
      goto LABEL_150;
    }
    v112 = 0;
    v45 = 0;
    v46 = 0;
    LOBYTE(v44) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_SystemLightTheme>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_SystemLightTheme>::GetImpl'::`2'::impl,
      v44);
    v48 = v128;
    v49 = *(void **)&v119[0].unused;
    if ( *((_DWORD *)v128 + 11) == 1 && *((_DWORD *)v128 + 10) != 1 && *((_DWORD *)v128 + 9) != 2 )
    {
      inited = ImmersiveIcons::InitResourceContextForLightTheme(v128, v115, v47);
      v7 = inited;
      if ( inited < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x159,
          (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
          (const char *)(unsigned int)inited,
          (int)ppvb);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v112);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v115);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v119);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v113);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v114);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v126);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v111);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
        string = 0;
        goto LABEL_156;
      }
      v51 = v113;
      v133 = 0;
      v52 = *(int (__fastcall **)(__int64, struct ImmersiveIcons::LoadIconParams *, void *, __int64 *))(*(_QWORD *)v113 + 48LL);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v133);
      if ( v52(v51, v115, v49, &v133) >= 0 )
      {
        v132 = 0;
        v53 = Microsoft::WRL::ComPtr<IResourceCandidate2>::As<IResourceCandidate>(&v133, &v132);
        v7 = v53;
        if ( v53 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x15F,
            (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
            (const char *)(unsigned int)v53,
            (int)ppvb);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v132);
          v54 = &v133;
LABEL_78:
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(v54);
LABEL_79:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v112);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v115);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v119);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v113);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v114);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v126);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v111);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
          string = 0;
          goto LABEL_156;
        }
        v137 = 0;
        v138 = 0;
        v139 = 0;
        v55 = v132;
        v56 = *(int (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v132 + 64LL);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v137);
        v138 = -1;
        v139 = -1;
        if ( v56(v55, L"AlternateForm", &v137) >= 0
          && (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                             &v137,
                             L"lightunplated",
                             -1) == 2 )
        {
          v57 = v132;
          v46 = 1;
          v45 = 2;
          v58 = v112;
          if ( v112 != v132 )
          {
            if ( v132 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v132 + 8LL))(v132);
              v58 = v112;
            }
            v131 = v58;
            v112 = v57;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v131);
          }
        }
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v137);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v132);
      }
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v133);
      v48 = v128;
    }
    if ( v112 )
      goto LABEL_96;
    v59 = ImmersiveIcons::InitResourceContextForAllThemes(v48, v115, v47);
    v7 = v59;
    if ( v59 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x171,
        (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
        (const char *)(unsigned int)v59,
        (int)ppvb);
      goto LABEL_79;
    }
    v131 = 0;
    v60 = v113;
    v61 = *(int (__fastcall **)(__int64, struct ImmersiveIcons::LoadIconParams *, void *, __int64 *))(*(_QWORD *)v113 + 48LL);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v131);
    if ( v61(v60, v115, v49, &v131) >= 0 )
    {
      v62 = Microsoft::WRL::ComPtr<IResourceCandidate2>::As<IResourceCandidate>(&v131, &v112);
      v7 = v62;
      if ( v62 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x175,
          (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
          (const char *)(unsigned int)v62,
          (int)ppvb);
        v54 = &v131;
        goto LABEL_78;
      }
      v140 = 0;
      v141 = 0;
      v142 = 0;
      v63 = v112;
      v64 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v112 + 64LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v140);
      v141 = -1;
      v142 = -1;
      v65 = v64(v63, L"AlternateForm", &v140);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v140);
      v45 = (v65 >> 31) + 2;
    }
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v131);
    if ( v112 )
    {
LABEL_96:
      v66 = v128;
      ContrastForParams = ImmersiveIcons::GetContrastForParams(v128);
      LODWORD(v122) = ContrastForParams;
      if ( v45 != 1 || ContrastForParams )
        goto LABEL_126;
      v69 = *((unsigned __int16 *)v66 + 8);
      v128 = 0;
      v70 = (*(__int64 (__fastcall **)(struct ImmersiveIcons::LoadIconParams *, __int64))(*(_QWORD *)v115 + 112LL))(
              v115,
              v69);
      if ( v70 >= 0 )
      {
        v72 = v113;
        v73 = *(__int64 (__fastcall **)(__int64, struct ImmersiveIcons::LoadIconParams *, void *, ImmersiveIcons **))(*(_QWORD *)v113 + 48LL);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v128);
        v70 = v73(v72, v115, v49, &v128);
        if ( v70 >= 0 )
        {
          v74 = v128;
          v75 = **(__int64 (__fastcall ***)(ImmersiveIcons *, GUID *, __int64 *))v128;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v112);
          v76 = v75(v74, &GUID_f98ce1cb_901b_41f4_bf42_83d51895e1e2, &v112);
          v7 = v76;
          if ( v76 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x187,
              (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
              (const char *)(unsigned int)v76,
              (int)ppvb);
            v77 = v128;
            if ( v128 )
            {
              v128 = 0;
              (*(void (__fastcall **)(ImmersiveIcons *))(*(_QWORD *)v77 + 16LL))(v77);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v112);
            v78 = v115;
            if ( v115 )
            {
              v115 = 0;
              (*(void (__fastcall **)(struct ImmersiveIcons::LoadIconParams *))(*(_QWORD *)v78 + 16LL))(v78);
            }
            if ( v49 )
              CoTaskMemFree(v49);
            v79 = v113;
            if ( v113 )
            {
              v113 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
            }
            v80 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v114;
            if ( v114 )
            {
              v114 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v80)[2])(v80);
            }
            if ( v126[0] )
              CoTaskMemFree((LPVOID)v126[0]);
            v81 = v111;
            if ( v111 )
            {
              v111 = 0;
              (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v81 + 16LL))(v81);
            }
            if ( pv )
            {
              CoTaskMemFree(pv);
              pv = 0;
            }
            v117 = 0;
            v118 = 0;
            string = 0;
            if ( v12 )
              CoTaskMemFree(v12);
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v110);
            v82 = v130;
            if ( v130 )
            {
              v130 = 0;
              (*(void (__fastcall **)(void *))(*(_QWORD *)v82 + 16LL))(v82);
            }
            return v7;
          }
          v134 = 0;
          v135 = 0;
          v136 = 0;
          v83 = v112;
          v84 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v112 + 64LL);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v134);
          v135 = -1;
          v136 = -1;
          v85 = v84(v83, L"AlternateForm", &v134);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v134);
          v45 = (v85 >> 31) + 2;
          goto LABEL_125;
        }
        v71 = 389;
      }
      else
      {
        v71 = 388;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v71,
        (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
        (const char *)(unsigned int)v70,
        (int)ppvb);
LABEL_125:
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v128);
LABEL_126:
      LOBYTE(v68) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_SystemLightTheme>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_SystemLightTheme>::GetImpl'::`2'::impl,
        v68);
      v86 = v112;
      v134 = 0;
      v135 = 0;
      v136 = 0;
      v87 = *(int (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v112 + 64LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v134);
      v135 = -1;
      v136 = -1;
      if ( v87(v86, L"Theme", &v134) >= 0 )
      {
        if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                             &v134,
                             L"dark",
                             -1) == 2 )
        {
          v46 = 2;
        }
        else if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                                  &v134,
                                  L"light",
                                  -1) == 2 )
        {
          v46 = 1;
        }
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v134);
      memset(&v146, 0, sizeof(v146));
      if ( !(_DWORD)v122
        || (v88 = v112,
            v89 = *(int (__fastcall **)(__int64, const wchar_t *, HSTRING_HEADER *))(*(_QWORD *)v112 + 64LL),
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v146),
            *(_QWORD *)&v146.Reserved.Reserved2[8] = -1,
            *(_QWORD *)&v146.Reserved.Reserved2[16] = -1,
            v90 = 1,
            v89(v88, L"Contrast", &v146) < 0) )
      {
        v90 = 0;
      }
      v91 = v112;
      v92 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v112 + 32LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
      v117 = -1;
      v118 = -1;
      v93 = v92(v91, &pv);
      v7 = v93;
      if ( v93 < 0 )
      {
        v94 = 417;
LABEL_136:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v94,
          (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
          (const char *)(unsigned int)v93,
          (int)ppvb);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v146);
LABEL_148:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v112);
        goto LABEL_149;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::ReplaceChars(&pv);
      v93 = StringCchCopyW((unsigned __int16 *)a3 + 8, 0x104u, (const unsigned __int16 *)pv);
      v7 = v93;
      if ( v93 < 0 )
      {
        v94 = 421;
        goto LABEL_136;
      }
      *(_DWORD *)a3 = v45;
      *((_DWORD *)a3 + 1) = v46;
      *((_BYTE *)a3 + 8) = v90;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v146);
LABEL_161:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v112);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v115);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v119);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v113);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v114);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v126);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v111);
      goto LABEL_162;
    }
    v122 = 0;
    WindowsDeleteString(0);
    v95 = string;
    v122 = 0;
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(v126);
    v96 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v146, v126[0], (unsigned int)v126[1]);
    v97 = ShellMRTHelper::Common::TryFallbackToFilePath(0, *(HSTRING *)(v96 + 24), v95, (HSTRING)&v122, (HSTRING *)ppvb);
    v7 = v97;
    if ( v97 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(v122, 0);
      if ( !PathFileExistsW(StringRawBuffer) )
      {
        v7 = -2147024893;
        v98 = 436;
        v100 = 2147942403LL;
LABEL_147:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v98,
          (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
          (const char *)v100,
          ppvc);
        WindowsDeleteString(v122);
        v122 = 0;
        goto LABEL_148;
      }
      v101 = WindowsGetStringRawBuffer(v122, 0);
      v97 = StringCchCopyW((unsigned __int16 *)a3 + 8, 0x104u, v101);
      v7 = v97;
      if ( v97 >= 0 )
      {
        v103 = v122;
        *(_QWORD *)a3 = 0;
        *((_BYTE *)a3 + 8) = 0;
        WindowsDeleteString(v103);
        goto LABEL_161;
      }
      v98 = 437;
    }
    else
    {
      v98 = 435;
    }
    v100 = (unsigned int)v97;
    goto LABEL_147;
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::ReplaceChars(&pv);
  v20 = StringCchCopyW((unsigned __int16 *)a3 + 8, 0x104u, (const unsigned __int16 *)pv);
  v7 = v20;
  if ( v20 < 0 )
  {
    v21 = 452;
    goto LABEL_26;
  }
  *(_QWORD *)a3 = 0;
  *((_BYTE *)a3 + 8) = 0;
LABEL_162:
  if ( !*(_DWORD *)a3 )
  {
    *(_QWORD *)&v119[0].unused = 0;
    v120 = 0;
    v121 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v119);
    v120 = -1;
    *(_OWORD *)v126 = PKEY_AppUserModel_ParentID;
    v121 = -1;
    LODWORD(v127) = 19;
    if ( (int)wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(&v110, v126, v119) >= 0 )
    {
      if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                           v119,
                           L"Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge",
                           -1) == 2 )
      {
LABEL_169:
        *(_DWORD *)a3 = 3;
      }
      else
      {
        LOBYTE(v104) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_UnplateMicrosoftEdgeTiles_25482738>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_Servicing_UnplateMicrosoftEdgeTiles_25482738>::GetImpl'::`2'::impl,
          v104);
        v143[0] = L"Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!App";
        v105 = (HSTRING_HEADER *)v143;
        v143[1] = L"Microsoft.MicrosoftEdge.Beta_8wekyb3d8bbwe!App";
        v143[2] = L"Microsoft.MicrosoftEdge.Dev_8wekyb3d8bbwe!App";
        v143[3] = L"Microsoft.MicrosoftEdge.Canary_8wekyb3d8bbwe!App";
        v143[4] = L"Microsoft.MicrosoftEdge.Internal_8wekyb3d8bbwe!App";
        while ( v105 != &hstringHeader )
        {
          if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                               v119,
                               v105->Reserved.Reserved1,
                               -1) == 2 )
            goto LABEL_169;
          v105 = (HSTRING_HEADER *)((char *)v105 + 8);
        }
      }
      if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                           v119,
                           L"Microsoft.YourPhone_8wekyb3d8bbwe!App",
                           -1) == 2 )
        *(_DWORD *)a3 = 3;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v119);
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
  string = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString);
  Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::~ComPtr<Windows::Foundation::IUriRuntimeClass>(&v110);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v130);
  return 0;
}

```

## disassembly

```asm
0x180008c44  mov     [rsp-8+arg_18], rbx
0x180008c49  push    rbp
0x180008c4a  push    rsi
0x180008c4b  push    rdi
0x180008c4c  push    r12
0x180008c4e  push    r13
0x180008c50  push    r14
0x180008c52  push    r15
0x180008c54  lea     rbp, [rsp-0C0h]
0x180008c5c  sub     rsp, 1C0h
0x180008c63  mov     rax, cs:__security_cookie
0x180008c6a  xor     rax, rsp
0x180008c6d  mov     [rbp+0F0h+var_40], rax
0x180008c74  mov     r15, rcx
0x180008c77  mov     [rbp+0F0h+var_120], rdx
0x180008c7b  xor     r13d, r13d
0x180008c7e  lea     rcx, [rbp+0F0h+var_110]
0x180008c82  mov     [rbp+0F0h+var_110], r13
0x180008c86  mov     rsi, r8
0x180008c89  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180008c8e  lea     rax, [rbp+0F0h+var_110]
0x180008c92  mov     r8, r15; pszItem
0x180008c95  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180008c9c  mov     [rsp+1F0h+ppv], rax; int
0x180008ca1  mov     edx, 4000h; dwKFFlags
0x180008ca6  lea     rcx, FOLDERID_AppsFolder; kfid
0x180008cad  call    cs:__imp_SHCreateItemInKnownFolder
0x180008cb4  nop     dword ptr [rax+rax+00h]
0x180008cb9  mov     ebx, eax
0x180008cbb  test    eax, eax
0x180008cbd  jns     short loc_180008CDF
0x180008cbf  mov     rcx, [rbp+0F8h]; this
0x180008cc6  lea     r8, aShellLibImmers; "shell\\lib\\immersiveapphelpers\\immers"...
0x180008ccd  mov     r9d, eax; char *
0x180008cd0  mov     edx, 0DEh; void *
0x180008cd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008cda  jmp     loc_180009BF7
0x180008cdf  lea     rcx, [rsp+1F0h+var_1C0]
0x180008ce4  mov     [rsp+1F0h+var_1C0], r13
0x180008ce9  call    ?InternalAddRef@?$ComPtr@UIWindowingEnvironmentConfig@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(void)
0x180008cee  mov     rdx, [rbp+0F0h+var_110]
0x180008cf2  lea     r9, qword_18040A030
0x180008cf9  mov     edi, 1
0x180008cfe  mov     dword ptr [rsp+1F0h+ppv], 4; int
0x180008d06  mov     r8d, edi
0x180008d09  lea     rcx, [rsp+1F0h+var_1C0]
0x180008d0e  call    ?InitFromItem@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@PEBU_tagpropertykey@@I@Z; wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS,_tagpropertykey const *,uint)
0x180008d13  mov     ebx, eax
0x180008d15  test    eax, eax
0x180008d17  jns     short loc_180008D39
0x180008d19  mov     edx, 0EDh; void *
0x180008d1e  mov     rcx, [rbp+0F8h]; this
0x180008d25  lea     r8, aShellLibImmers; "shell\\lib\\immersiveapphelpers\\immers"...
0x180008d2c  mov     r9d, eax; char *
0x180008d2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d34  jmp     loc_180009BED
0x180008d39  movups  xmm0, cs:PKEY_Tile_Background
0x180008d40  mov     eax, cs:dword_180409FD0
0x180008d46  lea     r8, [rsi+0Ch]
0x180008d4a  lea     rdx, [rbp+0F0h+var_140]
0x180008d4e  mov     dword ptr [rbp+0F0h+var_130], eax
0x180008d51  lea     rcx, [rsp+1F0h+var_1C0]
0x180008d56  movaps  xmmword ptr [rbp+0F0h+var_140], xmm0
0x180008d5a  call    ??$GetAsUInt32@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAK@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetAsUInt32<_tagpropertykey>(_tagpropertykey,ulong *)
0x180008d5f  mov     ebx, eax
0x180008d61  test    eax, eax
0x180008d63  jns     short loc_180008D6C
0x180008d65  mov     edx, 0EFh
0x180008d6a  jmp     short loc_180008D1E
0x180008d6c  movups  xmm0, cs:PKEY_Tile_SmallLogoPath
0x180008d73  mov     eax, cs:dword_180409FE8
0x180008d79  lea     r8, [rbp+0F0h+sourceString]
0x180008d7d  or      r12, 0FFFFFFFFFFFFFFFFh
0x180008d81  mov     [rbp+0F0h+sourceString], r13
0x180008d85  lea     rdx, [rbp+0F0h+var_140]
0x180008d89  movaps  xmmword ptr [rbp+0F0h+var_140], xmm0
0x180008d8d  lea     rcx, [rsp+1F0h+var_1C0]
0x180008d92  mov     qword ptr [rbp+0F0h+length], r12
0x180008d96  mov     [rbp+0F0h+var_148], r12
0x180008d9a  mov     dword ptr [rbp+0F0h+var_130], eax
0x180008d9d  call    ??$GetString@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAPEAG@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x180008da2  mov     ebx, eax
0x180008da4  test    eax, eax
0x180008da6  jns     short loc_180008DC8
0x180008da8  mov     rcx, [rbp+0F8h]; this
0x180008daf  lea     r8, aShellLibImmers; "shell\\lib\\immersiveapphelpers\\immers"...
0x180008db6  mov     r9d, eax; char *
0x180008db9  mov     edx, 0F2h; void *
0x180008dbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008dc3  jmp     loc_180009BE4
0x180008dc8  mov     rbx, qword ptr [rbp+0F0h+length]
0x180008dcc  mov     r14, [rbp+0F0h+sourceString]
0x180008dd0  cmp     rbx, r12
0x180008dd3  jnz     short loc_180008DF0
0x180008dd5  test    r14, r14
0x180008dd8  jz      short loc_180008DE9
0x180008dda  mov     rbx, r12
0x180008ddd  inc     rbx
0x180008de0  cmp     [r14+rbx*2], r13w
0x180008de5  jnz     short loc_180008DDD
0x180008de7  jmp     short loc_180008DEC
0x180008de9  mov     rbx, r13
0x180008dec  mov     qword ptr [rbp+0F0h+length], rbx
0x180008df0  mov     ecx, ebx; unsigned int
0x180008df2  mov     [rbp+0F0h+string], r13
0x180008df9  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180008dfe  cmp     ebx, eax
0x180008e00  lea     r9, [rbp+0F0h+string]; string
0x180008e07  lea     r8, [rbp+0F0h+hstringHeader]; hstringHeader
0x180008e0b  mov     rcx, r14; sourceString
0x180008e0e  lea     edx, [rax-1]
0x180008e11  cmovb   edx, ebx; length
0x180008e14  call    cs:__imp_WindowsCreateStringReference
0x180008e1b  nop     dword ptr [rax+rax+00h]
0x180008e20  test    eax, eax
0x180008e22  jns     short loc_180008E2C
0x180008e24  mov     ecx, eax; this
0x180008e26  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180008e2b  int     3; Trap to Debugger
0x180008e2c  mov     rcx, [rbp+0F0h+string]; this
0x180008e33  mov     [rsp+1F0h+pv], r13
0x180008e38  mov     [rsp+1F0h+var_188], r13
0x180008e3d  mov     [rsp+1F0h+var_180], r13
0x180008e42  call    ?HasFileUriScheme@Common@ShellMRTHelper@@YA_NPEAUHSTRING__@@@Z; ShellMRTHelper::Common::HasFileUriScheme(HSTRING__ *)
0x180008e47  test    al, al
0x180008e49  jz      short loc_180008EA7
0x180008e4b  mov     rcx, [rsp+1F0h+pv]; pv
0x180008e50  test    rcx, rcx
0x180008e53  jz      short loc_180008E66
0x180008e55  call    cs:__imp_CoTaskMemFree
0x180008e5c  nop     dword ptr [rax+rax+00h]
0x180008e61  mov     [rsp+1F0h+pv], r13
0x180008e66  lea     rdx, [rsp+1F0h+pv]; unsigned __int16 *
0x180008e6b  mov     [rsp+1F0h+var_188], r12
0x180008e70  mov     rcx, r14; pwzURI
0x180008e73  mov     [rsp+1F0h+var_180], r12
0x180008e78  call    ?ConvertFileUriToFilePath@TileUtils@@YAJPEBGPEAPEAG@Z; TileUtils::ConvertFileUriToFilePath(ushort const *,ushort * *)
0x180008e7d  mov     ebx, eax
0x180008e7f  test    eax, eax
0x180008e81  jns     loc_180008FE1
0x180008e87  mov     edx, 104h; void *
0x180008e8c  mov     rcx, [rbp+0F8h]; this
0x180008e93  lea     r8, aShellLibImmers; "shell\\lib\\immersiveapphelpers\\immers"...
0x180008e9a  mov     r9d, eax; char *
0x180008e9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008ea2  jmp     loc_180009BD3
0x180008ea7  mov     rcx, [rbp+0F0h+string]; this
0x180008eae  call    ?HasMsAppDataUriScheme@Common@ShellMRTHelper@@YA_NPEAUHSTRING__@@@Z; ShellMRTHelper::Common::HasMsAppDataUriScheme(HSTRING__ *)
0x180008eb3  test    al, al
0x180008eb5  jz      loc_18000901E
0x180008ebb  lea     rcx, [rbp+0F0h+var_118]
0x180008ebf  mov     [rbp+0F0h+var_118], r13
0x180008ec3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180008ec8  lea     rax, [rbp+0F0h+var_118]
0x180008ecc  mov     r8d, edi; dwClsContext
0x180008ecf  lea     r9, _GUID_428bb582_2a87_4ea0_b529_30067cc4a4d7; riid
0x180008ed6  mov     [rsp+1F0h+ppv], rax; int
0x180008edb  xor     edx, edx; pUnkOuter
0x180008edd  lea     rcx, _GUID_a8ca4495_65ab_4333_9ff9_4feb6fbf5169; rclsid
0x180008ee4  call    cs:__imp_CoCreateInstance
0x180008eeb  nop     dword ptr [rax+rax+00h]
0x180008ef0  mov     ebx, eax
0x180008ef2  test    eax, eax
0x180008ef4  jns     short loc_180008F1F
0x180008ef6  mov     rcx, [rbp+0F8h]; this
0x180008efd  lea     r8, aShellLibImmers; "shell\\lib\\immersiveapphelpers\\immers"...
0x180008f04  mov     r9d, eax; char *
0x180008f07  mov     edx, 109h; void *
0x180008f0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008f11  lea     rcx, [rbp+0F0h+var_118]
0x180008f15  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180008f1a  jmp     loc_180009BD3
0x180008f1f  lea     rcx, [rsp+1F0h+var_178]
0x180008f24  mov     qword ptr [rsp+1F0h+var_178.unused], r13
0x180008f29  mov     [rbp+0F0h+var_170], r13
0x180008f2d  mov     [rbp+0F0h+var_168], r13
0x180008f31  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180008f36  lea     r8, [rsp+1F0h+var_178]
0x180008f3b  mov     [rbp+0F0h+var_170], r12
0x180008f3f  lea     rdx, [rsp+1F0h+var_1C0]
0x180008f44  mov     [rbp+0F0h+var_168], r12
0x180008f48  mov     rcx, r15; this
0x180008f4b  call    ImmersiveIcons__GetPackageFullNameForAppsFolderItem
0x180008f50  mov     ebx, eax
0x180008f52  test    eax, eax
0x180008f54  jns     short loc_180008F7D
0x180008f56  mov     edx, 10Ch; void *
0x180008f5b  mov     rcx, [rbp+0F8h]; this
0x180008f62  lea     r8, aShellLibImmers; "shell\\lib\\immersiveapphelpers\\immers"...
0x180008f69  mov     r9d, eax; char *
0x180008f6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008f71  lea     rcx, [rsp+1F0h+var_178]
0x180008f76  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180008f7b  jmp     short loc_180008F11
0x180008f7d  mov     rdi, [rbp+0F0h+var_118]
0x180008f81  lea     rcx, [rsp+1F0h+pv]
0x180008f86  mov     rax, [rdi]
0x180008f89  mov     rbx, [rax+30h]
0x180008f8d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180008f92  mov     r8, qword ptr [rsp+1F0h+var_178.unused]
0x180008f97  lea     rax, [rsp+1F0h+pv]
0x180008f9c  mov     [rsp+1F0h+ppv], rax
0x180008fa1  xor     r9d, r9d
0x180008fa4  mov     rax, rbx
0x180008fa7  mov     [rsp+1F0h+var_188], r12
0x180008fac  mov     rdx, r14
0x180008faf  mov     [rsp+1F0h+var_180], r12
0x180008fb4  mov     rcx, rdi
0x180008fb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fbc  mov     ebx, eax
0x180008fbe  test    eax, eax
0x180008fc0  jns     short loc_180008FC9
0x180008fc2  mov     edx, 10Eh
0x180008fc7  jmp     short loc_180008F5B
0x180008fc9  lea     rcx, [rsp+1F0h+var_178]
0x180008fce  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180008fd3  lea     rcx, [rbp+0F0h+var_118]
0x180008fd7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180008fdc  mov     edi, 1
0x180008fe1  mov     rax, [rsp+1F0h+pv]
0x180008fe6  test    rax, rax
0x180008fe9  jz      short loc_18000905B
0x180008feb  cmp     [rax], r13w
0x180008fef  jz      short loc_18000905B
0x180008ff1  lea     rcx, [rsp+1F0h+pv]
0x180008ff6  call    ?ReplaceChars@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAXGG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::ReplaceChars(ushort,ushort)
0x180008ffb  mov     r8, [rsp+1F0h+pv]; unsigned __int16 *
0x180009000  lea     rcx, [rsi+10h]; unsigned __int16 *
0x180009004  mov     edx, 104h; unsigned __int64
0x180009009  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000900e  mov     ebx, eax
0x180009010  test    eax, eax
0x180009012  jns     short loc_18000904F
0x180009014  mov     edx, 1C4h
0x180009019  jmp     loc_180008E8C
0x18000901e  mov     rcx, r14; pszPath
0x180009021  call    cs:__imp_PathIsRelativeW
0x180009028  nop     dword ptr [rax+rax+00h]
0x18000902d  test    eax, eax
0x18000902f  jnz     short loc_180008FE1
0x180009031  lea     rdx, [rbp+0F0h+sourceString]
0x180009035  lea     rcx, [rsp+1F0h+pv]
0x18000903a  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJAEBV123@@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &)
0x18000903f  mov     ebx, eax
0x180009041  test    eax, eax
0x180009043  jns     short loc_180008FE1
0x180009045  mov     edx, 114h
0x18000904a  jmp     loc_180008E8C
0x18000904f  mov     [rsi], r13
0x180009052  mov     [rsi+8], r13b
0x180009056  jmp     loc_180009C67
0x18000905b  lea     rcx, [rsp+1F0h+var_1B8]
0x180009060  mov     [rsp+1F0h+var_1B8], r13
0x180009065  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18000906a  lea     rax, [rsp+1F0h+var_1B8]
0x18000906f  mov     r8d, edi; dwClsContext
0x180009072  lea     r9, _GUID_130a2f65_2be7_4309_9a58_a9052ff2b61c; riid
0x180009079  mov     [rsp+1F0h+ppv], rax; int
0x18000907e  xor     edx, edx; pUnkOuter
0x180009080  lea     rcx, _GUID_dbce7e40_7345_439d_b12c_114a11819a09; rclsid
0x180009087  call    cs:__imp_CoCreateInstance
0x18000908e  nop     dword ptr [rax+rax+00h]
0x180009093  mov     ebx, eax
0x180009095  test    eax, eax
0x180009097  jns     short loc_1800090B9
0x180009099  mov     rcx, [rbp+0F8h]; this
0x1800090a0  lea     r8, aShellLibImmers; "shell\\lib\\immersiveapphelpers\\immers"...
0x1800090a7  mov     r9d, eax; char *
0x1800090aa  mov     edx, 11Dh; void *
0x1800090af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800090b4  jmp     loc_180009BC9
0x1800090b9  lea     r8, [rbp+0F0h+var_140]
0x1800090bd  mov     [rbp+0F0h+var_140], r13
0x1800090c1  lea     rdx, [rsp+1F0h+var_1C0]
0x1800090c6  mov     [rbp+0F0h+var_140+8], r12
0x1800090ca  mov     rcx, r15; this
0x1800090cd  mov     [rbp+0F0h+var_130], r12
0x1800090d1  call    ImmersiveIcons__GetPackageFullNameForAppsFolderItem
0x1800090d6  mov     ebx, eax
0x1800090d8  test    eax, eax
0x1800090da  jns     short loc_1800090FC
0x1800090dc  mov     edx, 120h; void *
0x1800090e1  mov     rcx, [rbp+0F8h]; this
0x1800090e8  lea     r8, aShellLibImmers; "shell\\lib\\immersiveapphelpers\\immers"...
0x1800090ef  mov     r9d, eax; char *
0x1800090f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800090f7  jmp     loc_180009BC0
0x1800090fc  mov     rcx, [rsp+1F0h+var_1B8]
0x180009101  mov     rdx, [rbp+0F0h+var_140]
0x180009105  mov     rax, [rcx]
0x180009108  mov     rax, [rax+28h]
0x18000910c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009111  mov     ebx, eax
0x180009113  test    eax, eax
0x180009115  jns     short loc_18000911E
0x180009117  mov     edx, 122h
0x18000911c  jmp     short loc_1800090E1
0x18000911e  mov     rdi, [rsp+1F0h+var_1B8]
0x180009123  lea     rcx, [rsp+1F0h+var_1A0]
0x180009128  mov     [rsp+1F0h+var_1A0], r13
  ... truncated ...
```
