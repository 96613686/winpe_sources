# SystemSettings::StorageSenseHandlers::CAppInvisibleAdvanced::GenerateAppTileData(uchar *)

- ea: `0x18003e500`
- end: `0x18003f230`
- name: `?GenerateAppTileData@CAppInvisibleAdvanced@StorageSenseHandlers@SystemSettings@@AEAAJPEAE@Z`
- size: `3376`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAppInvisibleAdvanced *__hidden this, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800414f0`
- `0x18004b3e0`

## callees

- `0x180001b44`
- `0x180006e50`
- `0x18000c964`
- `0x18000e6cc`
- `0x180019fa8`
- `0x18001fe08`
- `0x180036bfc`
- `0x180036c38`
- `0x180037628`
- `0x18003c308`
- `0x18003e500`
- `0x180049fcc`
- `0x1800beb4c`
- `0x1800bec40`
- `0x1800c0c78`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e779`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e7b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e8ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e9b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ea6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003eea5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ef6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f01e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f1da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e779`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e7b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e8ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e9b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ea6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003eea5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ef6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f01e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f1da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e5e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e684`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e717`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e5e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e684`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e717`
- `api-ms-win-appmodel-runtime-l1-1-1!VerifyPackageFamilyName` at `0x18003e5ed`
- `api-ms-win-appmodel-runtime-l1-1-1!VerifyPackageFamilyName` at `0x18003e5ed`

## string_xrefs

- `0x18003e68f`: `Protocol`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppInvisibleAdvanced::GenerateAppTileData(
        SystemSettings::StorageSenseHandlers::CAppInvisibleAdvanced *this,
        unsigned __int8 *a2)
{
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  const WCHAR *StringRawBuffer; // rax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, HSTRING, __int64); // rbx
  int v11; // ebx
  struct SystemSettings::DataModel::StorageSense::IPackageInfo *v12; // rdi
  __int64 (__fastcall *v13)(struct SystemSettings::DataModel::StorageSense::IPackageInfo *, _QWORD, int *); // rbx
  const struct _tlgProvider_t *v14; // rax
  int v15; // edi
  int v16; // r8d
  int v17; // r9d
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, _QWORD, HSTRING, int *); // rbx
  const struct _tlgProvider_t *v20; // rax
  int v21; // edi
  int v22; // r8d
  int v23; // r9d
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, HSTRING *); // rbx
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, _QWORD, _QWORD, __int64 *); // rbx
  int v30; // eax
  __int64 v31; // rdx
  struct SystemSettings::DataModel::StorageSense::IPackageInfo *v32; // r15
  unsigned int i; // esi
  __int64 v34; // rdi
  void (__fastcall *v35)(__int64, _QWORD, __int64 *); // rbx
  __int64 v36; // rdi
  __int64 (__fastcall *v37)(__int64, HSTRING *); // rbx
  int v38; // eax
  __int64 v39; // rax
  __int64 v40; // rdx
  struct SystemSettings::StorageSenseHandlers::CAppInfo **v41; // rcx
  __int64 v42; // rdi
  void (__fastcall *v43)(__int64, _QWORD, __int64 *); // rbx
  int v44; // eax
  __int64 v45; // rdx
  int v46; // eax
  __int64 v47; // r9
  __int64 v48; // rdx
  __int64 v49; // rax
  struct SystemSettings::StorageSenseHandlers::CAppInfo **v50; // rcx
  int v51; // eax
  __int64 v52; // rdx
  __int64 v53; // rdi
  void (__fastcall *v54)(__int64, _QWORD, const char **); // rbx
  int v55; // eax
  __int64 v56; // rdx
  int v57; // eax
  __int64 v58; // r9
  __int64 v59; // rdx
  __int64 v60; // rax
  struct SystemSettings::DataModel::StorageSense::IPackageInfo *v61; // r15
  unsigned int v62; // esi
  __int64 v63; // rdi
  void (__fastcall *v64)(__int64, _QWORD, __int64 *); // rbx
  __int64 v65; // rdi
  __int64 (__fastcall *v66)(__int64, HSTRING *); // rbx
  int v67; // eax
  __int64 v68; // rax
  __int64 v69; // rdx
  __int64 v70; // rdi
  void (__fastcall *v71)(__int64, _QWORD, __int64 *); // rbx
  int v72; // eax
  __int64 v73; // rdx
  int v74; // eax
  __int64 v75; // r9
  __int64 v76; // rdx
  __int64 v77; // rax
  struct SystemSettings::DataModel::StorageSense::IPackageInfo **v78; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v80; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v81; // [rsp+50h] [rbp-B0h] BYREF
  struct SystemSettings::DataModel::StorageSense::IPackageInfo *v82; // [rsp+58h] [rbp-A8h] BYREF
  int v83[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v84; // [rsp+68h] [rbp-98h] BYREF
  struct SystemSettings::DataModel::StorageSense::IPackageInfo *v85; // [rsp+70h] [rbp-90h] BYREF
  struct SystemSettings::StorageSenseHandlers::CAppInfo *v86; // [rsp+78h] [rbp-88h] BYREF
  struct SystemSettings::StorageSenseHandlers::CAppInfo *v87; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v88; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v89; // [rsp+8Ch] [rbp-74h] BYREF
  HSTRING v90; // [rsp+90h] [rbp-70h] BYREF
  HSTRING v91; // [rsp+98h] [rbp-68h] BYREF
  struct SystemSettings::StorageSenseHandlers::CAppInfo *v92; // [rsp+A0h] [rbp-60h] BYREF
  struct SystemSettings::DataModel::StorageSense::IPackageInfo *v93; // [rsp+A8h] [rbp-58h] BYREF
  struct SystemSettings::DataModel::StorageSense::IPackageInfo *v94; // [rsp+B0h] [rbp-50h] BYREF
  const char *v95; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v96; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v97; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v98; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v99; // [rsp+D8h] [rbp-28h] BYREF
  struct SystemSettings::DataModel::StorageSense::IPackageInfo *v100; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v101; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v102; // [rsp+F0h] [rbp-10h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v104; // [rsp+110h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  if ( !SystemSettings::StorageSenseHandlers::g_callerIdentity )
  {
    *a2 = 0;
    return 0;
  }
  v101 = 0;
  v102 = 0;
  *(_QWORD *)v83 = 0;
  v104 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.Package",
    0x29u,
    0x28u);
  v5 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(
         v104,
         &v101);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 4319;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
      (const char *)(unsigned int)v5,
      (int)v78);
    goto LABEL_121;
  }
  v104 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.Application",
    0x2Du,
    0x2Cu);
  v5 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>(
         v104,
         &v102);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 4322;
    goto LABEL_7;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(SystemSettings::StorageSenseHandlers::g_callerIdentity, 0);
  if ( VerifyPackageFamilyName(StringRawBuffer) )
  {
    v18 = v101;
    v19 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, int *))(*(_QWORD *)v101 + 360LL);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v83);
    v11 = v19(v18, 0, SystemSettings::StorageSenseHandlers::g_callerIdentity, v83);
    v20 = SettingsHandlersStorageSenseLogging::Provider();
    v21 = (int)v20;
    if ( *(_DWORD *)v20 > 4u )
    {
      v82 = (struct SystemSettings::DataModel::StorageSense::IPackageInfo *)WindowsGetStringRawBuffer(
                                                                              SystemSettings::StorageSenseHandlers::g_callerIdentity,
                                                                              0);
      v85 = (struct SystemSettings::DataModel::StorageSense::IPackageInfo *)"Start";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v21,
        (unsigned int)byte_18014FAD1,
        v22,
        v23,
        (__int64)&v85,
        (__int64)&v82);
    }
  }
  else
  {
    v82 = 0;
    v9 = v101;
    v10 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, __int64))(*(_QWORD *)v101 + 424LL);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v82);
    v78 = &v82;
    v11 = v10(v9, 0, SystemSettings::StorageSenseHandlers::g_callerIdentity, 1);
    if ( v11 >= 0 )
    {
      v12 = v82;
      v13 = *(__int64 (__fastcall **)(struct SystemSettings::DataModel::StorageSense::IPackageInfo *, _QWORD, int *))(*(_QWORD *)v82 + 48LL);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v83);
      v11 = v13(v12, 0, v83);
    }
    v14 = SettingsHandlersStorageSenseLogging::Provider();
    v15 = (int)v14;
    if ( *(_DWORD *)v14 > 4u )
    {
      v85 = (struct SystemSettings::DataModel::StorageSense::IPackageInfo *)WindowsGetStringRawBuffer(
                                                                              SystemSettings::StorageSenseHandlers::g_callerIdentity,
                                                                              0);
      v95 = "Protocol";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v15,
        (unsigned int)byte_18014FB15,
        v16,
        v17,
        (__int64)&v95,
        (__int64)&v85);
    }
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v82);
  }
  if ( v11 < 0 )
  {
    *a2 = 0;
    goto LABEL_120;
  }
  string = 0;
  v88 = 0;
  v81 = 0;
  v24 = *(_QWORD *)v83;
  v25 = *(__int64 (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)v83 + 112LL);
  WindowsDeleteString(0);
  string = 0;
  v26 = v25(v24, &string);
  v6 = v26;
  if ( v26 < 0 )
  {
    v27 = 4361;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
      (const char *)(unsigned int)v26,
      (int)v78);
    goto LABEL_21;
  }
  v26 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)v83 + 128LL))(*(_QWORD *)v83, &v88);
  v6 = v26;
  if ( v26 < 0 )
  {
    v27 = 4362;
    goto LABEL_20;
  }
  v80 = 0;
  v89 = 0;
  v28 = v102;
  v29 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v102 + 304LL);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v80);
  v30 = v29(v28, 0, *(_QWORD *)v83, &v80);
  v6 = v30;
  if ( v30 < 0 )
  {
    v31 = 4366;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
      (const char *)(unsigned int)v30,
      (int)v78);
    goto LABEL_27;
  }
  v30 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v80 + 56LL))(v80, &v89);
  v6 = v30;
  if ( v30 < 0 )
  {
    v31 = 4367;
    goto LABEL_26;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UninstallApps>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UninstallApps>::GetImpl'::`2'::impl) )
  {
    if ( *(_DWORD *)(*((_QWORD *)this + 11) + 24LL) != 2 && *((_DWORD *)this + 58) != 2 )
    {
      v92 = 0;
      if ( v89 > 1 )
      {
        v51 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)v83 + 1008LL))(*(_QWORD *)v83, &v81);
        v6 = v51;
        if ( v51 < 0 )
        {
          v52 = 4473;
LABEL_70:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v52,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
            (const char *)(unsigned int)v51,
            (int)v78);
LABEL_71:
          v41 = &v92;
          goto LABEL_50;
        }
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v92);
        LODWORD(v78) = v83[0];
        v51 = SystemSettings::StorageSenseHandlers::CAppInfo::CreateWithPackageOrigin(0, string, v88, v81);
        v6 = v51;
        if ( v51 < 0 )
        {
          v52 = 4474;
          goto LABEL_70;
        }
LABEL_80:
        v85 = 0;
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v85);
        v57 = SystemSettings::StorageSenseHandlers::CPackageInfo::Create(v92, &v85);
        v6 = v57;
        if ( v57 >= 0 )
        {
          v82 = v85;
          v84 = 0;
          v60 = Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppTileData,enum SystemSettings::StorageSenseHandlers::AppListType,SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo *>(
                  &v100,
                  &v84,
                  &v82);
          Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppTileData>::operator=((char *)this + 240, v60);
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v100);
          if ( *((_QWORD *)this + 30) )
          {
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v85);
            v50 = &v92;
            goto LABEL_119;
          }
          v6 = -2147024882;
          v58 = 2147942414LL;
          v59 = 4487;
        }
        else
        {
          v58 = (unsigned int)v57;
          v59 = 4485;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v59,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
          (const char *)v58,
          (int)v78);
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v85);
        goto LABEL_71;
      }
      v95 = 0;
      v53 = v80;
      v54 = *(void (__fastcall **)(__int64, _QWORD, const char **))(*(_QWORD *)v80 + 48LL);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v95);
      v54(v53, 0, &v95);
      v55 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)v83 + 1008LL))(*(_QWORD *)v83, &v81);
      v6 = v55;
      if ( v55 >= 0 )
      {
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v92);
        LODWORD(v78) = v83[0];
        v55 = SystemSettings::StorageSenseHandlers::CAppInfo::CreateWithPackageOrigin(
                SystemSettings::StorageSenseHandlers::g_callerIdentity,
                string,
                v88,
                v81);
        v6 = v55;
        if ( v55 >= 0 )
        {
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v95);
          goto LABEL_80;
        }
        v56 = 4481;
      }
      else
      {
        v56 = 4480;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v56,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
        (const char *)(unsigned int)v55,
        (int)v78);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v95);
      goto LABEL_71;
    }
    v87 = 0;
    if ( v89 > 1 )
    {
      v94 = 0;
      v61 = 0;
      v62 = 0;
      while ( 1 )
      {
        v97 = 0;
        v63 = v80;
        v64 = *(void (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v80 + 48LL);
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v97);
        v64(v63, v62, &v97);
        v91 = 0;
        v65 = v97;
        v66 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v97 + 232LL);
        WindowsDeleteString(0);
        v91 = 0;
        v67 = v66(v65, &v91);
        v6 = v67;
        if ( v67 < 0 )
        {
          v69 = 4432;
          goto LABEL_102;
        }
        v67 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)v83 + 1008LL))(*(_QWORD *)v83, &v81);
        v6 = v67;
        if ( v67 < 0 )
        {
          v69 = 4433;
          goto LABEL_102;
        }
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v87);
        LODWORD(v78) = v83[0];
        v67 = SystemSettings::StorageSenseHandlers::CAppInfo::CreateWithPackageOrigin(v91, string, v88, v81);
        v6 = v67;
        if ( v67 < 0 )
        {
          v69 = 4434;
          goto LABEL_102;
        }
        if ( v62 )
        {
          SystemSettings::StorageSenseHandlers::CPackageInfo::InsertApp(v61, v87);
        }
        else
        {
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v94);
          v67 = SystemSettings::StorageSenseHandlers::CPackageInfo::Create(v87, &v94);
          v6 = v67;
          if ( v67 < 0 )
          {
            v69 = 4438;
LABEL_102:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v69,
              (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
              (const char *)(unsigned int)v67,
              (int)v78);
            WindowsDeleteString(v91);
            v91 = 0;
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v97);
LABEL_103:
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v94);
LABEL_104:
            v41 = &v87;
LABEL_50:
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v41);
LABEL_27:
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v80);
LABEL_21:
            WindowsDeleteString(string);
            string = 0;
            goto LABEL_121;
          }
          v61 = v94;
        }
        WindowsDeleteString(v91);
        v91 = 0;
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v97);
        if ( ++v62 >= v89 )
        {
          v82 = v94;
          v84 = 0;
          v68 = Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppTileData,enum SystemSettings::StorageSenseHandlers::AppListType,SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo *>(
                  &v85,
                  &v84,
                  &v82);
          Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppTileData>::operator=((char *)this + 240, v68);
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v85);
          if ( !*((_QWORD *)this + 30) )
          {
            v6 = -2147024882;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1160,
              (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
              (const char *)0x8007000ELL,
              (int)v78);
            goto LABEL_103;
          }
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v94);
LABEL_118:
          v50 = &v87;
          goto LABEL_119;
        }
      }
    }
    v99 = 0;
    v70 = v80;
    v71 = *(void (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v80 + 48LL);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v99);
    v71(v70, 0, &v99);
    v72 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)v83 + 1008LL))(*(_QWORD *)v83, &v81);
    v6 = v72;
    if ( v72 >= 0 )
    {
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v87);
      LODWORD(v78) = v83[0];
      v72 = SystemSettings::StorageSenseHandlers::CAppInfo::CreateWithPackageOrigin(
              SystemSettings::StorageSenseHandlers::g_callerIdentity,
              string,
              v88,
              v81);
      v6 = v72;
      if ( v72 >= 0 )
      {
        v82 = 0;
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v82);
        v74 = SystemSettings::StorageSenseHandlers::CPackageInfo::Create(v87, &v82);
        v6 = v74;
        if ( v74 >= 0 )
        {
          v85 = v82;
          v84 = 0;
          v77 = Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppTileData,enum SystemSettings::StorageSenseHandlers::AppListType,SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo *>(
                  &v95,
                  &v84,
                  &v85);
          Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppTileData>::operator=((char *)this + 240, v77);
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v95);
          if ( *((_QWORD *)this + 30) )
          {
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v82);
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v99);
            goto LABEL_118;
          }
          v6 = -2147024882;
          v75 = 2147942414LL;
          v76 = 4461;
        }
        else
        {
          v75 = (unsigned int)v74;
          v76 = 4458;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v76,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
          (const char *)v75,
          (int)v78);
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v82);
        goto LABEL_109;
      }
      v73 = 4455;
    }
    else
    {
      v73 = 4454;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v73,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
      (const char *)(unsigned int)v72,
      (int)v78);
LABEL_109:
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v99);
    goto LABEL_104;
  }
  v86 = 0;
  if ( v89 <= 1 )
  {
    v98 = 0;
    v42 = v80;
    v43 = *(void (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v80 + 48LL);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v98);
    v43(v42, 0, &v98);
    v44 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)v83 + 1008LL))(*(_QWORD *)v83, &v81);
    v6 = v44;
    if ( v44 >= 0 )
    {
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v86);
      LODWORD(v78) = v83[0];
      v44 = SystemSettings::StorageSenseHandlers::CAppInfo::CreateWithPackageOrigin(
              SystemSettings::StorageSenseHandlers::g_callerIdentity,
              string,
              v88,
              v81);
      v6 = v44;
      if ( v44 >= 0 )
      {
        v100 = 0;
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v100);
        v46 = SystemSettings::StorageSenseHandlers::CPackageInfo::Create(v86, &v100);
        v6 = v46;
        if ( v46 >= 0 )
        {
          v82 = v100;
          v84 = 0;
          v49 = Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppTileData,enum SystemSettings::StorageSenseHandlers::AppListType,SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo *>(
                  &v85,
                  &v84,
                  &v82);
          Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppTileData>::operator=((char *)this + 240, v49);
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v85);
          if ( *((_QWORD *)this + 30) )
          {
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v100);
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v98);
            goto LABEL_64;
          }
          v6 = -2147024882;
          v47 = 2147942414LL;
          v48 = 4412;
        }
        else
        {
          v47 = (unsigned int)v46;
          v48 = 4409;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v48,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
          (const char *)v47,
          (int)v78);
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v100);
        goto LABEL_55;
      }
      v45 = 4406;
    }
    else
    {
      v45 = 4405;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v45,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
      (const char *)(unsigned int)v44,
      (int)v78);
LABEL_55:
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v98);
LABEL_49:
    v41 = &v86;
    goto LABEL_50;
  }
  v93 = 0;
  v32 = 0;
  for ( i = 0; i < v89; ++i )
  {
    v96 = 0;
    v34 = v80;
    v35 = *(void (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v80 + 48LL);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v96);
    v35(v34, i, &v96);
    v90 = 0;
    v36 = v96;
    v37 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v96 + 232LL);
    WindowsDeleteString(0);
    v90 = 0;
    v38 = v37(v36, &v90);
    v6 = v38;
    if ( v38 < 0 )
    {
      v40 = 4384;
      goto LABEL_47;
    }
    v38 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)v83 + 1008LL))(*(_QWORD *)v83, &v81);
    v6 = v38;
    if ( v38 < 0 )
    {
      v40 = 4385;
      goto LABEL_47;
    }
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v86);
    LODWORD(v78) = v83[0];
    v38 = SystemSettings::StorageSenseHandlers::CAppInfo::CreateWithPackageOrigin(v90, string, v88, v81);
    v6 = v38;
    if ( v38 < 0 )
    {
      v40 = 4386;
      goto LABEL_47;
    }
    if ( !i )
    {
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v93);
      v38 = SystemSettings::StorageSenseHandlers::CPackageInfo::Create(v86, &v93);
      v6 = v38;
      if ( v38 >= 0 )
      {
        v32 = v93;
        goto LABEL_40;
      }
      v40 = 4390;
LABEL_47:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v40,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
        (const char *)(unsigned int)v38,
        (int)v78);
      WindowsDeleteString(v90);
      v90 = 0;
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v96);
      goto LABEL_48;
    }
    SystemSettings::StorageSenseHandlers::CPackageInfo::InsertApp(v32, v86);
LABEL_40:
    WindowsDeleteString(v90);
    v90 = 0;
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v96);
  }
  v82 = v93;
  v84 = 0;
  v39 = Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppTileData,enum SystemSettings::StorageSenseHandlers::AppListType,SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo *>(
          &v85,
          &v84,
          &v82);
  Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppTileData>::operator=((char *)this + 240, v39);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v85);
  if ( !*((_QWORD *)this + 30) )
  {
    v6 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x112F,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
      (const char *)0x8007000ELL,
      (int)v78);
LABEL_48:
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v93);
    goto LABEL_49;
  }
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v93);
LABEL_64:
  v50 = &v86;
LABEL_119:
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v50);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v80);
  WindowsDeleteString(string);
  string = 0;
LABEL_120:
  v6 = 0;
LABEL_121:
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v83);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v102);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v101);
  return v6;
}

```

## disassembly

```asm
0x18003e500  mov     [rsp-8+arg_10], rbx
0x18003e505  mov     [rsp-8+arg_18], rsi
0x18003e50a  push    rbp
0x18003e50b  push    rdi
0x18003e50c  push    r12
0x18003e50e  push    r14
0x18003e510  push    r15
0x18003e512  lea     rbp, [rsp-20h]
0x18003e517  sub     rsp, 120h
0x18003e51e  mov     rax, cs:__security_cookie
0x18003e525  xor     rax, rsp
0x18003e528  mov     [rbp+40h+var_28], rax
0x18003e52c  mov     rsi, rdx
0x18003e52f  mov     r14, rcx
0x18003e532  xor     r12d, r12d
0x18003e535  cmp     cs:?g_callerIdentity@StorageSenseHandlers@SystemSettings@@3VHString@Wrappers@WRL@Microsoft@@A, r12; Microsoft::WRL::Wrappers::HString SystemSettings::StorageSenseHandlers::g_callerIdentity
0x18003e53c  jnz     short loc_18003E548
0x18003e53e  mov     [rdx], r12b
0x18003e541  xor     eax, eax
0x18003e543  jmp     loc_18003F208
0x18003e548  mov     [rbp+40h+var_58], r12
0x18003e54c  mov     [rbp+40h+var_50], r12
0x18003e550  mov     qword ptr [rsp+140h+var_E0], r12
0x18003e555  mov     [rbp+40h+var_30], r12
0x18003e559  mov     r9d, 28h ; '('; unsigned int
0x18003e55f  lea     r8d, [r9+1]; unsigned int
0x18003e563  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18003e56a  lea     rcx, [rbp+40h+hstringHeader]; hstringHeader
0x18003e56e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003e573  lea     rdx, [rbp+40h+var_58]
0x18003e577  mov     rcx, [rbp+40h+var_30]
0x18003e57b  call    ??$GetActivationFactory@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>)
0x18003e580  mov     ebx, eax
0x18003e582  test    eax, eax
0x18003e584  jns     short loc_18003E58D
0x18003e586  mov     edx, 10DFh
0x18003e58b  jmp     short loc_18003E5C3
0x18003e58d  mov     [rbp+40h+var_30], r12
0x18003e591  mov     r9d, 2Ch ; ','; unsigned int
0x18003e597  lea     r8d, [r9+1]; unsigned int
0x18003e59b  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x18003e5a2  lea     rcx, [rbp+40h+hstringHeader]; hstringHeader
0x18003e5a6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003e5ab  lea     rdx, [rbp+40h+var_50]
0x18003e5af  mov     rcx, [rbp+40h+var_30]
0x18003e5b3  call    ??$GetActivationFactory@V?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>)
0x18003e5b8  mov     ebx, eax
0x18003e5ba  test    eax, eax
0x18003e5bc  jns     short loc_18003E5DB
0x18003e5be  mov     edx, 10E2h; void *
0x18003e5c3  lea     r8, aOnecoreuapShel_29; "onecoreuap\\shell\\coresettinghandlers"...
0x18003e5ca  mov     r9d, eax; char *
0x18003e5cd  mov     rcx, [rbp+48h]; this
0x18003e5d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e5d6  jmp     loc_18003F1E8
0x18003e5db  xor     edx, edx; length
0x18003e5dd  mov     rcx, cs:?g_callerIdentity@StorageSenseHandlers@SystemSettings@@3VHString@Wrappers@WRL@Microsoft@@A; string
0x18003e5e4  call    cs:__imp_WindowsGetStringRawBuffer
0x18003e5ea  mov     rcx, rax; packageFamilyName
0x18003e5ed  call    cs:__imp_VerifyPackageFamilyName
0x18003e5f3  test    eax, eax
0x18003e5f5  jnz     loc_18003E6CC
0x18003e5fb  mov     [rsp+140h+var_E8], r12
0x18003e600  mov     rdi, [rbp+40h+var_58]
0x18003e604  mov     rax, [rdi]
0x18003e607  mov     rbx, [rax+1A8h]
0x18003e60e  lea     rcx, [rsp+140h+var_E8]
0x18003e613  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18003e618  lea     rax, [rsp+140h+var_E8]
0x18003e61d  mov     qword ptr [rsp+140h+var_120], rax
0x18003e622  mov     r9d, 1
0x18003e628  mov     r8, cs:?g_callerIdentity@StorageSenseHandlers@SystemSettings@@3VHString@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::HString SystemSettings::StorageSenseHandlers::g_callerIdentity
0x18003e62f  xor     edx, edx
0x18003e631  mov     rcx, rdi
0x18003e634  mov     rax, rbx
0x18003e637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e63c  mov     ebx, eax
0x18003e63e  test    eax, eax
0x18003e640  js      short loc_18003E66C
0x18003e642  mov     rdi, [rsp+140h+var_E8]
0x18003e647  mov     rax, [rdi]
0x18003e64a  mov     rbx, [rax+30h]
0x18003e64e  lea     rcx, [rsp+140h+var_E0]
0x18003e653  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18003e658  lea     r8, [rsp+140h+var_E0]
0x18003e65d  xor     edx, edx
0x18003e65f  mov     rcx, rdi
0x18003e662  mov     rax, rbx
0x18003e665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e66a  mov     ebx, eax
0x18003e66c  call    ?Provider@SettingsHandlersStorageSenseLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsHandlersStorageSenseLogging::Provider(void)
0x18003e671  mov     rdi, rax
0x18003e674  mov     ecx, [rax]
0x18003e676  cmp     ecx, 4
0x18003e679  jbe     short loc_18003E6BD
0x18003e67b  xor     edx, edx; length
0x18003e67d  mov     rcx, cs:?g_callerIdentity@StorageSenseHandlers@SystemSettings@@3VHString@Wrappers@WRL@Microsoft@@A; string
0x18003e684  call    cs:__imp_WindowsGetStringRawBuffer
0x18003e68a  mov     [rsp+140h+var_D0], rax
0x18003e68f  lea     rax, aProtocol; "Protocol"
0x18003e696  mov     [rbp+40h+var_88], rax
0x18003e69a  lea     rax, [rsp+140h+var_D0]
0x18003e69f  mov     [rsp+140h+var_118], rax
0x18003e6a4  lea     rax, [rbp+40h+var_88]
0x18003e6a8  mov     qword ptr [rsp+140h+var_120], rax
0x18003e6ad  lea     rdx, byte_18014FB15
0x18003e6b4  mov     rcx, rdi
0x18003e6b7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18003e6bc  nop
0x18003e6bd  lea     rcx, [rsp+140h+var_E8]
0x18003e6c2  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18003e6c7  jmp     loc_18003E751
0x18003e6cc  mov     rdi, [rbp+40h+var_58]
0x18003e6d0  mov     rax, [rdi]
0x18003e6d3  mov     rbx, [rax+168h]
0x18003e6da  lea     rcx, [rsp+140h+var_E0]
0x18003e6df  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18003e6e4  lea     r9, [rsp+140h+var_E0]
0x18003e6e9  mov     r8, cs:?g_callerIdentity@StorageSenseHandlers@SystemSettings@@3VHString@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::HString SystemSettings::StorageSenseHandlers::g_callerIdentity
0x18003e6f0  xor     edx, edx
0x18003e6f2  mov     rcx, rdi
0x18003e6f5  mov     rax, rbx
0x18003e6f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e6fd  mov     ebx, eax
0x18003e6ff  call    ?Provider@SettingsHandlersStorageSenseLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsHandlersStorageSenseLogging::Provider(void)
0x18003e704  mov     rdi, rax
0x18003e707  mov     ecx, [rax]
0x18003e709  cmp     ecx, 4
0x18003e70c  jbe     short loc_18003E751
0x18003e70e  xor     edx, edx; length
0x18003e710  mov     rcx, cs:?g_callerIdentity@StorageSenseHandlers@SystemSettings@@3VHString@Wrappers@WRL@Microsoft@@A; string
0x18003e717  call    cs:__imp_WindowsGetStringRawBuffer
0x18003e71d  mov     [rsp+140h+var_E8], rax
0x18003e722  lea     rax, aStart; "Start"
0x18003e729  mov     [rsp+140h+var_D0], rax
0x18003e72e  lea     rax, [rsp+140h+var_E8]
0x18003e733  mov     [rsp+140h+var_118], rax
0x18003e738  lea     rax, [rsp+140h+var_D0]
0x18003e73d  mov     qword ptr [rsp+140h+var_120], rax; int
0x18003e742  lea     rdx, byte_18014FAD1
0x18003e749  mov     rcx, rdi
0x18003e74c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18003e751  test    ebx, ebx
0x18003e753  jns     short loc_18003E75D
0x18003e755  mov     [rsi], r12b
0x18003e758  jmp     loc_18003F1E5
0x18003e75d  mov     [rsp+140h+string], r12
0x18003e762  mov     [rbp+40h+var_B8], r12d
0x18003e766  mov     [rsp+140h+var_F0], r12d
0x18003e76b  mov     rdi, qword ptr [rsp+140h+var_E0]
0x18003e770  mov     rax, [rdi]
0x18003e773  mov     rbx, [rax+70h]
0x18003e777  xor     ecx, ecx; string
0x18003e779  call    cs:__imp_WindowsDeleteString
0x18003e77f  mov     [rsp+140h+string], r12
0x18003e784  lea     rdx, [rsp+140h+string]
0x18003e789  mov     rcx, rdi
0x18003e78c  mov     rax, rbx
0x18003e78f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e794  mov     ebx, eax
0x18003e796  test    eax, eax
0x18003e798  jns     short loc_18003E7C8
0x18003e79a  mov     edx, 1109h; void *
0x18003e79f  lea     r8, aOnecoreuapShel_29; "onecoreuap\\shell\\coresettinghandlers"...
0x18003e7a6  mov     r9d, eax; char *
0x18003e7a9  mov     rcx, [rbp+48h]; this
0x18003e7ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e7b2  nop
0x18003e7b3  mov     rcx, [rsp+140h+string]; string
0x18003e7b8  call    cs:__imp_WindowsDeleteString
0x18003e7be  mov     [rsp+140h+string], r12
0x18003e7c3  jmp     loc_18003F1E8
0x18003e7c8  mov     rcx, qword ptr [rsp+140h+var_E0]
0x18003e7cd  mov     rax, [rcx]
0x18003e7d0  lea     rdx, [rbp+40h+var_B8]
0x18003e7d4  mov     rax, [rax+80h]
0x18003e7db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e7e0  mov     ebx, eax
0x18003e7e2  test    eax, eax
0x18003e7e4  jns     short loc_18003E7ED
0x18003e7e6  mov     edx, 110Ah
0x18003e7eb  jmp     short loc_18003E79F
0x18003e7ed  mov     [rsp+140h+var_F8], r12
0x18003e7f2  mov     [rbp+40h+var_B4], r12d
0x18003e7f6  mov     rdi, [rbp+40h+var_50]
0x18003e7fa  mov     rax, [rdi]
0x18003e7fd  mov     rbx, [rax+130h]
0x18003e804  lea     rcx, [rsp+140h+var_F8]
0x18003e809  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18003e80e  lea     r9, [rsp+140h+var_F8]
0x18003e813  mov     r8, qword ptr [rsp+140h+var_E0]
0x18003e818  xor     edx, edx
0x18003e81a  mov     rcx, rdi
0x18003e81d  mov     rax, rbx
0x18003e820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e825  mov     ebx, eax
0x18003e827  test    eax, eax
0x18003e829  jns     short loc_18003E853
0x18003e82b  mov     edx, 110Eh; void *
0x18003e830  lea     r8, aOnecoreuapShel_29; "onecoreuap\\shell\\coresettinghandlers"...
0x18003e837  mov     r9d, eax; char *
0x18003e83a  mov     rcx, [rbp+48h]; this
0x18003e83e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e843  nop
0x18003e844  lea     rcx, [rsp+140h+var_F8]
0x18003e849  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18003e84e  jmp     loc_18003E7B3
0x18003e853  mov     rcx, [rsp+140h+var_F8]
0x18003e858  mov     rax, [rcx]
0x18003e85b  lea     rdx, [rbp+40h+var_B4]
0x18003e85f  mov     rax, [rax+38h]
0x18003e863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e868  mov     ebx, eax
0x18003e86a  test    eax, eax
0x18003e86c  jns     short loc_18003E875
0x18003e86e  mov     edx, 110Fh
0x18003e873  jmp     short loc_18003E830
0x18003e875  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UninstallApps@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UninstallApps@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UninstallApps> `wil::Feature<__WilFeatureTraits_Feature_UninstallApps>::GetImpl(void)'::`2'::impl
0x18003e87c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UninstallApps@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UninstallApps>::__private_IsEnabled(void)
0x18003e881  test    al, al
0x18003e883  jz      loc_18003EC1B
0x18003e889  mov     [rsp+140h+var_C8], r12
0x18003e88e  mov     ecx, [rbp+40h+var_B4]
0x18003e891  cmp     ecx, 1
0x18003e894  jbe     loc_18003EAA5
0x18003e89a  mov     rax, r12
0x18003e89d  mov     [rbp+40h+var_98], rax
0x18003e8a1  mov     r15, r12
0x18003e8a4  mov     esi, r12d
0x18003e8a7  test    ecx, ecx
0x18003e8a9  jz      loc_18003E9DA
0x18003e8af  mov     [rbp+40h+var_80], r12
0x18003e8b3  mov     rdi, [rsp+140h+var_F8]
0x18003e8b8  mov     rax, [rdi]
0x18003e8bb  mov     rbx, [rax+30h]
0x18003e8bf  lea     rcx, [rbp+40h+var_80]
0x18003e8c3  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18003e8c8  lea     r8, [rbp+40h+var_80]
0x18003e8cc  mov     edx, esi
0x18003e8ce  mov     rcx, rdi
0x18003e8d1  mov     rax, rbx
0x18003e8d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e8d9  mov     [rbp+40h+var_B0], r12
0x18003e8dd  mov     rdi, [rbp+40h+var_80]
0x18003e8e1  mov     rax, [rdi]
0x18003e8e4  mov     rbx, [rax+0E8h]
0x18003e8eb  xor     ecx, ecx; string
0x18003e8ed  call    cs:__imp_WindowsDeleteString
0x18003e8f3  mov     [rbp+40h+var_B0], r12
0x18003e8f7  lea     rdx, [rbp+40h+var_B0]
0x18003e8fb  mov     rcx, rdi
0x18003e8fe  mov     rax, rbx
0x18003e901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e906  mov     ebx, eax
0x18003e908  test    eax, eax
0x18003e90a  js      loc_18003EA4D
0x18003e910  mov     rcx, qword ptr [rsp+140h+var_E0]
0x18003e915  mov     rax, [rcx]
0x18003e918  lea     rdx, [rsp+140h+var_F0]
0x18003e91d  mov     rax, [rax+3F0h]
0x18003e924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e929  mov     ebx, eax
0x18003e92b  test    eax, eax
0x18003e92d  js      loc_18003EA46
0x18003e933  lea     rcx, [rsp+140h+var_C8]
0x18003e938  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18003e93d  mov     rax, [rbp+40h+var_80]
0x18003e941  mov     r10, qword ptr [rsp+140h+var_E0]
0x18003e946  lea     rcx, [rsp+140h+var_C8]
0x18003e94b  mov     [rsp+140h+var_110], rcx
0x18003e950  mov     [rsp+140h+var_118], rax
0x18003e955  mov     qword ptr [rsp+140h+var_120], r10; int
0x18003e95a  mov     r9d, [rsp+140h+var_F0]
0x18003e95f  mov     r8d, [rbp+40h+var_B8]
0x18003e963  mov     rdx, [rsp+140h+string]
0x18003e968  mov     rcx, [rbp+40h+var_B0]
0x18003e96c  call    ?CreateWithPackageOrigin@CAppInfo@StorageSenseHandlers@SystemSettings@@SAJPEAUHSTRING__@@0W4PackageType@StateRepository@Internal@Windows@@W4PackageOrigin@678@PEAUIPackage@678@PEAUIApplication@678@PEAPEAV123@@Z; SystemSettings::StorageSenseHandlers::CAppInfo::CreateWithPackageOrigin(HSTRING__ *,HSTRING__ *,Windows::Internal::StateRepository::PackageType,Windows::Internal::StateRepository::PackageOrigin,Windows::Internal::StateRepository::IPackage *,Windows::Internal::StateRepository::IApplication *,SystemSettings::StorageSenseHandlers::CAppInfo * *)
0x18003e971  mov     ebx, eax
0x18003e973  test    eax, eax
0x18003e975  js      loc_18003EA3F
0x18003e97b  test    esi, esi
0x18003e97d  jnz     short loc_18003E9A6
0x18003e97f  lea     rcx, [rbp+40h+var_98]
0x18003e983  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18003e988  lea     rdx, [rbp+40h+var_98]; struct SystemSettings::DataModel::StorageSense::IPackageInfo **
0x18003e98c  mov     rcx, [rsp+140h+var_C8]; struct SystemSettings::StorageSenseHandlers::CAppInfo *
0x18003e991  call    ?Create@CPackageInfo@StorageSenseHandlers@SystemSettings@@SAJPEAVCAppInfo@23@PEAPEAUIPackageInfo@StorageSense@DataModel@3@@Z; SystemSettings::StorageSenseHandlers::CPackageInfo::Create(SystemSettings::StorageSenseHandlers::CAppInfo *,SystemSettings::DataModel::StorageSense::IPackageInfo * *)
0x18003e996  mov     ebx, eax
0x18003e998  test    eax, eax
0x18003e99a  js      loc_18003EA38
0x18003e9a0  mov     r15, [rbp+40h+var_98]
0x18003e9a4  jmp     short loc_18003E9B4
0x18003e9a6  mov     rdx, [rsp+140h+var_C8]; struct SystemSettings::StorageSenseHandlers::CAppInfo *
0x18003e9ab  mov     rcx, r15; this
0x18003e9ae  call    ?InsertApp@CPackageInfo@StorageSenseHandlers@SystemSettings@@QEAAJPEAVCAppInfo@23@@Z; SystemSettings::StorageSenseHandlers::CPackageInfo::InsertApp(SystemSettings::StorageSenseHandlers::CAppInfo *)
0x18003e9b3  nop
0x18003e9b4  mov     rcx, [rbp+40h+var_B0]; string
0x18003e9b8  call    cs:__imp_WindowsDeleteString
0x18003e9be  mov     [rbp+40h+var_B0], r12
0x18003e9c2  lea     rcx, [rbp+40h+var_80]
  ... truncated ...
```
