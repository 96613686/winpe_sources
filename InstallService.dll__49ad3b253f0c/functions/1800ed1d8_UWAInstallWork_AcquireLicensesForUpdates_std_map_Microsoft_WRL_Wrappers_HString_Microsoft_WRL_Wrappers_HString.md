# UWAInstallWork::_AcquireLicensesForUpdates(std::map<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::Wrappers::HString>>> &)

- ea: `0x1800ed1d8`
- end: `0x1800edda9`
- name: `?_AcquireLicensesForUpdates@UWAInstallWork@@AEAAJAEAV?$map@VHString@Wrappers@WRL@Microsoft@@V1234@U?$less@VHString@Wrappers@WRL@Microsoft@@@std@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V1234@@std@@@6@@std@@@Z`
- size: `3025`
- prototype: ``
- caller_count: `2`
- callee_count: `52`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800ee950`
- `0x1800eef5c`

## callees

- `0x180009ea0`
- `0x18000ee20`
- `0x1800101f4`
- `0x1800116f4`
- `0x180012368`
- `0x1800123f8`
- `0x1800127c8`
- `0x18001c414`
- `0x18001c844`
- `0x18001c964`
- `0x1800228c4`
- `0x180028634`
- `0x18002c310`
- `0x18002ec2c`
- `0x18003dfd4`
- `0x18003f884`
- `0x18003fe8c`
- `0x180040150`
- `0x180044bc0`
- `0x180044c3c`
- `0x180044cb8`
- `0x180044e5c`
- `0x180046110`
- `0x18004f73c`
- `0x18004fa08`
- `0x180056d64`
- `0x1800649d4`
- `0x180064c7c`
- `0x18006c230`
- `0x18006c330`
- `0x18006cfec`
- `0x18006d154`
- `0x18007aa00`
- `0x18007c3c4`
- `0x1800e2288`
- `0x1800e41b4`
- `0x1800e464c`
- `0x1800e4ce0`
- `0x1800e4f74`
- `0x1800e9440`
- `0x1800ed1d8`
- `0x1800fbd44`
- `0x1800fbe84`
- `0x1800fdb60`
- `0x1800fe6dc`
- `0x1801137a0`
- `0x180116918`
- `0x180133d6c`
- `0x180149adc`
- `0x1801dec4c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800ed667`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800ed667`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800ed677`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800ed677`
- `msvcp_win!_Xtime_get_ticks` at `0x1800ed559`
- `msvcp_win!_Xtime_get_ticks` at `0x1800ed559`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ed3df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ed3df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ed25a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ed269`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ed3a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ed437`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ed44b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ed686`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ed6cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ed6df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ed6f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ed768`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ed856`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ed961`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ed9de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ed9f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800eda02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800edaa5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800edab7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800edac9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800edc08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800edc5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ed25a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ed269`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ed3a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ed437`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ed44b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ed686`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ed6cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ed6df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ed6f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ed768`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ed856`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ed961`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ed9de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ed9f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800eda02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800edaa5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800edab7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800edac9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800edc08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800edc5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800edb6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800edb6d`

## string_xrefs

- `0x1800ed243`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800ed2f8`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800ed40b`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800ed3be`: `data->StoreInContentIdCache(search->second.GetRawBuffer(nullptr))`
- `0x1800ed285`: `UWAInstallWork::_AcquireLicensesForUpdates`
- `0x1800ed3c5`: `UWAInstallWork::_AcquireLicensesForUpdates`
- `0x1800ed6ad`: `UWAInstallWork::_AcquireLicensesForUpdates`
- `0x1800ed96c`: `UWAInstallWork::_AcquireLicensesForUpdates`
- `0x1800edc35`: `UWAInstallWork::_AcquireLicensesForUpdates`
- `0x1800edc87`: `UWAInstallWork::_AcquireLicensesForUpdates`
- `0x1800ed7c3`: `StoreInstaller`
- `0x1800ed8b1`: `StoreInstaller`
- `0x1800edc76`: `Unable to cache a modern license, ContentId = %s`
- `0x1800edc24`: `Ignoring licensing failure for Update, content id: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall UWAInstallWork::_AcquireLicensesForUpdates(
        WindowsUpdate::Telemetry *this,
        struct UWAInstallWork *a2)
{
  const OLECHAR *StringRawBuffer; // rdi
  const WCHAR *v3; // rax
  int v4; // eax
  __int64 **v5; // rcx
  __int64 *i; // rax
  __int64 *v7; // rbx
  __int64 *j; // rcx
  const char *v9; // r9
  UWAInstallWork *v10; // r15
  struct UWAInstallWork *v11; // rsi
  int v12; // eax
  __int64 v13; // r12
  __int64 v14; // rcx
  WindowsUpdate::Internal::FulfillmentDataInfo *v15; // rbx
  const unsigned __int16 *v16; // rdx
  int v17; // eax
  WindowsUpdate::Internal::FulfillmentDataInfo **v18; // rdi
  __int64 ***v19; // r12
  WindowsUpdate::Internal::FulfillmentDataInfo **v20; // rax
  const char *v21; // r9
  __int64 *v22; // rbx
  struct UWAInstallWork *v23; // rdi
  char *v24; // r12
  char IsEnabled; // al
  WindowsUpdate::Telemetry *v26; // rsi
  struct UWAInstallWork *v27; // rsi
  struct IApplicationLicenseManager *v28; // rcx
  int v29; // eax
  int v30; // eax
  int v31; // edi
  int v32; // r12d
  _QWORD *v33; // rax
  BOOL (__stdcall *v34)(PINIT_ONCE, PVOID, PVOID *); // rdx
  union _RTL_RUN_ONCE *v35; // rcx
  const unsigned __int16 *v36; // rax
  const unsigned __int16 *v37; // rsi
  const unsigned __int16 *v38; // rdi
  WindowsUpdate::CommonTelemetry *v39; // rax
  int v40; // r12d
  PCWSTR v41; // rax
  const wchar_t *v42; // rcx
  const wchar_t *v43; // rcx
  char *v44; // rdi
  unsigned int v45; // eax
  PCWSTR v46; // rax
  const wchar_t *v47; // rcx
  const wchar_t *v48; // rcx
  char *v49; // rdi
  unsigned int v50; // eax
  const unsigned __int16 *v51; // rsi
  const unsigned __int16 *v52; // rdi
  WindowsUpdate::CommonTelemetry *v53; // rax
  const unsigned __int16 *v54; // rsi
  const unsigned __int16 *v55; // rdi
  WindowsUpdate::CommonTelemetry *v56; // rax
  __int64 v57; // rcx
  LPVOID v58; // rax
  wil::details::in1diag3 *v59; // rcx
  __int64 v60; // rdx
  __int64 v61; // rcx
  const unsigned __int16 *v62; // rax
  const unsigned __int16 *v63; // rax
  int DurationInMilliseconds; // eax
  __int64 **v65; // rcx
  __int64 *k; // rax
  __int64 *m; // rcx
  const char *v68; // r9
  __int64 result; // rax
  unsigned int v70; // eax
  struct UWAInstallWork *v71; // rsi
  int v72; // eax
  unsigned int updated; // ebx
  WindowsUpdate::Telemetry *v74; // rdi
  int v75; // eax
  unsigned int v76; // eax
  char *v77; // [rsp+20h] [rbp-1A8h]
  int v78; // [rsp+20h] [rbp-1A8h]
  char *v79; // [rsp+30h] [rbp-198h]
  char *v80; // [rsp+20h] [rbp-1A8h]
  char *v81; // [rsp+20h] [rbp-1A8h]
  int v82; // [rsp+28h] [rbp-1A0h]
  char *v83; // [rsp+30h] [rbp-198h]
  char *v84; // [rsp+30h] [rbp-198h]
  char *v85; // [rsp+38h] [rbp-190h]
  const unsigned __int16 *v86; // [rsp+38h] [rbp-190h]
  char *v87; // [rsp+38h] [rbp-190h]
  char *v88; // [rsp+38h] [rbp-190h]
  HSTRING string; // [rsp+50h] [rbp-178h] BYREF
  unsigned __int8 v90[8]; // [rsp+58h] [rbp-170h] BYREF
  struct IApplicationLicenseManager *v91; // [rsp+60h] [rbp-168h] BYREF
  struct UWAInstallWork *v92; // [rsp+68h] [rbp-160h]
  char *v93; // [rsp+70h] [rbp-158h]
  UWAInstallWork *v94; // [rsp+78h] [rbp-150h]
  HSTRING ticks; // [rsp+80h] [rbp-148h] BYREF
  WindowsUpdate::Telemetry *v96; // [rsp+88h] [rbp-140h]
  char v97[8]; // [rsp+90h] [rbp-138h] BYREF
  char v98[8]; // [rsp+98h] [rbp-130h] BYREF
  char v99[8]; // [rsp+A0h] [rbp-128h] BYREF
  char v100[8]; // [rsp+A8h] [rbp-120h] BYREF
  char v101[8]; // [rsp+B0h] [rbp-118h] BYREF
  struct UWAInstallWork *v102; // [rsp+B8h] [rbp-110h]
  char *v103; // [rsp+C0h] [rbp-108h]
  __int128 v104; // [rsp+C8h] [rbp-100h] BYREF
  __int64 v105; // [rsp+D8h] [rbp-F0h]
  wchar_t *String1[2]; // [rsp+E0h] [rbp-E8h] BYREF
  unsigned __int64 v107; // [rsp+F8h] [rbp-D0h]
  char v108[16]; // [rsp+100h] [rbp-C8h] BYREF
  __int128 v109; // [rsp+110h] [rbp-B8h]
  __int128 v110; // [rsp+120h] [rbp-A8h]
  __int128 v111; // [rsp+130h] [rbp-98h]
  __int128 v112; // [rsp+140h] [rbp-88h]
  __int128 v113; // [rsp+150h] [rbp-78h]
  __int128 v114; // [rsp+160h] [rbp-68h]
  __int128 v115; // [rsp+170h] [rbp-58h]
  char v116; // [rsp+180h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  try
  {
    try
    {
      v11 = a2;
      v10 = this;
      v92 = a2;
      v94 = this;
      v96 = this;
      v19 = (__int64 ***)a2;
      v93 = (char *)a2;
      CallerContext::ContextData::Impersonate((char *)this + 152, String1);
      v7 = **v19;
      while ( !*((_BYTE *)v7 + 25) )
      {
        StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)v7[5], 0);
        v3 = WindowsGetStringRawBuffer((HSTRING)v7[4], 0);
        v4 = SetContentIdForUAP(v3, StringRawBuffer);
        TraceHR(
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
          0xD1Du,
          "UWAInstallWork::_AcquireLicensesForUpdates",
          "SetContentIdForUAP(pfncidpair.first.GetRawBuffer(nullptr), pfncidpair.second.GetRawBuffer(nullptr))",
          v4,
          v82);
        v5 = (__int64 **)v7[2];
        if ( *((_BYTE *)v5 + 25) )
        {
          for ( i = (__int64 *)v7[1]; !*((_BYTE *)i + 25) && v7 == (__int64 *)i[2]; i = (__int64 *)i[1] )
            v7 = i;
          v7 = i;
        }
        else
        {
          v7 = (__int64 *)v7[2];
          for ( j = *v5; !*((_BYTE *)j + 25); j = (__int64 *)*j )
            v7 = j;
        }
      }
      TokenHelpers::ImpersonateContext::~ImpersonateContext((TokenHelpers::ImpersonateContext *)String1);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0xD1F,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
        v9);
      v10 = v94;
      v11 = v92;
      v19 = (__int64 ***)v92;
    }
    try
    {
      SuspendImpersonationScope::SuspendImpersonationScope((SuspendImpersonationScope *)String1);
      v18 = (WindowsUpdate::Internal::FulfillmentDataInfo **)*((_QWORD *)v10 + 146);
      v20 = (WindowsUpdate::Internal::FulfillmentDataInfo **)*((_QWORD *)v10 + 147);
      *(_QWORD *)v90 = v20;
      while ( v18 != v20 )
      {
        string = 0;
        ticks = (HSTRING)*((_QWORD *)*v18 + 14);
        v12 = Microsoft::WRL::Wrappers::HString::Set(&string, &ticks);
        if ( v12 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xD27,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
            (const char *)(unsigned int)v12,
            (int)v80);
        std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,bool,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,bool>>,0>>::_Find_lower_bound<Microsoft::WRL::Wrappers::HString>(
          (__int64)v19,
          &v104,
          &string);
        v13 = v105;
        if ( (unsigned __int8)std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,bool,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,bool>>,0>>::_Lower_bound_duplicate<Microsoft::WRL::Wrappers::HString>(
                                v14,
                                v105,
                                &string)
          && v13 != *(_QWORD *)v11 )
        {
          v15 = *v18;
          v16 = WindowsGetStringRawBuffer(*(HSTRING *)(v13 + 40), 0);
          v17 = WindowsUpdate::Internal::FulfillmentDataInfo::StoreInContentIdCache(v15, v16);
          TraceHR(
            "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
            0xD2Bu,
            "UWAInstallWork::_AcquireLicensesForUpdates",
            "data->StoreInContentIdCache(search->second.GetRawBuffer(nullptr))",
            v17,
            v82);
        }
        WindowsDeleteString(string);
        ++v18;
        v19 = (__int64 ***)v93;
        v20 = *(WindowsUpdate::Internal::FulfillmentDataInfo ***)v90;
      }
      SuspendImpersonationScope::~SuspendImpersonationScope((SuspendImpersonationScope *)String1);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0xD2E,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
        v21);
      v10 = v94;
      v11 = v92;
    }
    v91 = 0;
    v22 = **(__int64 ***)v11;
    while ( 1 )
    {
      if ( *((_BYTE *)v22 + 25) )
      {
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v91);
        return 0;
      }
      v23 = (struct UWAInstallWork *)WindowsGetStringRawBuffer((HSTRING)v22[5], 0);
      v92 = v23;
      v24 = (char *)WindowsGetStringRawBuffer((HSTRING)v22[4], 0);
      v93 = v24;
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AsyncLicensing>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AsyncLicensing>::GetImpl'::`2'::impl);
      v102 = v23;
      v103 = v24;
      v26 = v96;
      if ( IsEnabled )
      {
        wil::AcquireSRWLockExclusive(v97, (char *)v10 + 1048);
        TraceLoggingCorrelationVector::Increment(*((TraceLoggingCorrelationVector **)v26 + 37), (char *)v10 + 304);
        *(_OWORD *)v108 = *((_OWORD *)v10 + 19);
        v109 = *((_OWORD *)v10 + 20);
        v110 = *((_OWORD *)v10 + 21);
        v111 = *((_OWORD *)v10 + 22);
        v112 = *((_OWORD *)v10 + 23);
        v113 = *((_OWORD *)v10 + 24);
        v114 = *((_OWORD *)v10 + 25);
        v115 = *((_OWORD *)v10 + 26);
        v116 = *((_BYTE *)v10 + 432);
        Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)v97);
      }
      else
      {
        TraceLoggingCorrelationVector::Increment(*((TraceLoggingCorrelationVector **)v96 + 37), v108);
      }
      v27 = v92;
      WindowsUpdate::Telemetry::BeginAcquireLicense(
        v10,
        v92,
        (const unsigned __int16 *)v24,
        (const unsigned __int16 *)v108,
        v80);
      ticks = (HSTRING)_Xtime_get_ticks();
      try
      {
        v28 = v91;
        if ( !v91 )
        {
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v91);
          v29 = CoCreateLicenseManager(&v91);
          if ( v29 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xD4C,
              (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
              (const char *)(unsigned int)v29,
              (int)v81);
          v28 = v91;
        }
        v30 = (*(__int64 (__fastcall **)(struct IApplicationLicenseManager *, struct UWAInstallWork *, _QWORD, _QWORD))(*(_QWORD *)v28 + 24LL))(
                v28,
                v27,
                0,
                0);
        v31 = v30;
        *(_DWORD *)v90 = v30;
        v32 = v30;
        if ( v30 >= 0 )
        {
LABEL_70:
          if ( v32 < 0 )
            goto LABEL_71;
        }
        else
        {
          if ( IsImmediateRetryAcquireLicenseErrorCode(v30) )
          {
            ++*((_DWORD *)v10 + 270);
            string = 0;
            v33 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ImmediateRetryAcquireLicenseTipTest,TipTests::_tip_ImmediateRetryAcquireLicenseTipTest>>::ensure_data(&string);
            tip2::details::shared_data<1,0,0>::start(*v33 + 8LL, &v104);
            *(_OWORD *)((char *)v10 + 1356) = v104;
            *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ImmediateRetryAcquireLicenseTipTest,TipTests::_tip_ImmediateRetryAcquireLicenseTipTest>>::operator->(
                                     &string,
                                     v98)
                      + 272LL) = v32;
            tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_ImmediateRetryAcquireLicenseTipTest,TipTests::_tip_ImmediateRetryAcquireLicenseTipTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_ImmediateRetryAcquireLicenseTipTest,TipTests::_tip_ImmediateRetryAcquireLicenseTipTest>>(v98);
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CatalogCacheImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CatalogCacheImprovements>::GetImpl'::`2'::impl) )
            {
              v34 = InitializeOneSettingsConfiguration;
              v35 = &stru_1802E4F70;
            }
            else
            {
              v34 = InitializeInstallServiceConfiguration;
              v35 = &InitOnce;
            }
            InitOnceExecuteOnce(v35, v34, 0, 0);
            if ( dwMilliseconds )
              Sleep(dwMilliseconds);
            v36 = WindowsGetStringRawBuffer(*((HSTRING *)v10 + 59), 0);
            LogSimpleMessage(
              3u,
              "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
              0xD5Fu,
              "UWAInstallWork::_AcquireLicensesForUpdates",
              v31,
              L"Immediate Retry Acquire License for Error ",
              (const char *)v10 + 304,
              v36);
            v37 = WindowsGetStringRawBuffer(*((HSTRING *)v10 + 15), 0);
            v38 = WindowsGetStringRawBuffer(*((HSTRING *)v10 + 57), 0);
            v39 = (WindowsUpdate::CommonTelemetry *)WindowsGetStringRawBuffer(*((HSTRING *)v10 + 59), 0);
            v40 = *(_DWORD *)v90;
            LOBYTE(v85) = 3;
            WindowsUpdate::CommonTelemetry::StateTransition(
              v39,
              v38,
              v37,
              0,
              0,
              (const unsigned __int16 *)"Error",
              "ImmediateRetry",
              v85,
              v90[0],
              (__int64)v108,
              (const char *)string);
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_GetFreeEntitlementOnNoEntitlement>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_GetFreeEntitlementOnNoEntitlement>::GetImpl'::`2'::impl)
              && v40 == -2143322111 )
            {
              v41 = WindowsGetStringRawBuffer(*((HSTRING *)v10 + 14), 0);
              Utils::GetClientIdFromFullAppIdWithoutFulfillmentType(String1, v41);
              v42 = (const wchar_t *)String1;
              if ( v107 > 7 )
                v42 = String1[0];
              if ( !wcscmp_0(v42, L"Microsoft.WindowsStore_8wekyb3d8bbwe") )
                goto LABEL_44;
              v43 = (const wchar_t *)String1;
              if ( v107 > 7 )
                v43 = String1[0];
              if ( !wcscmp_0(v43, L"StoreInstaller") )
              {
LABEL_44:
                v44 = v93;
                v45 = UWAInstallWork::_TryAcquireFreeEntitlementForPfn(v10, (const unsigned __int16 *)v93, v108);
                wil::details::in1diag3::Log_IfFailedMsg(
                  retaddr,
                  (void *)0xD6C,
                  (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
                  (const char *)v45,
                  (int)"Failed to acquire free entitlement for PFN: %s",
                  v44);
              }
              std::wstring::_Tidy_deallocate(String1);
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_GetEntitlementIfNotPresent>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_GetEntitlementIfNotPresent>::GetImpl'::`2'::impl)
              && v40 == -2143322111
              && GetEnableGetEntitlementIfNotPresent() )
            {
              v46 = WindowsGetStringRawBuffer(*((HSTRING *)v10 + 14), 0);
              Utils::GetClientIdFromFullAppIdWithoutFulfillmentType2(String1, v46);
              v47 = (const wchar_t *)String1;
              if ( v107 > 7 )
                v47 = String1[0];
              if ( !wcscmp_0(v47, L"Microsoft.WindowsStore_8wekyb3d8bbwe") )
                goto LABEL_55;
              v48 = (const wchar_t *)String1;
              if ( v107 > 7 )
                v48 = String1[0];
              if ( !wcscmp_0(v48, L"StoreInstaller") )
              {
LABEL_55:
                v49 = v93;
                v50 = UWAInstallWork::_TryAcquireFreeEntitlementForPfn2(v10, (const unsigned __int16 *)v93, v108);
                wil::details::in1diag3::Log_IfFailedMsg(
                  retaddr,
                  (void *)0xD78,
                  (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
                  (const char *)v50,
                  (int)"Failed to acquire free entitlement for PFN: %s",
                  v49);
              }
              std::wstring::_Tidy_deallocate(String1);
            }
            v32 = (*(__int64 (__fastcall **)(struct IApplicationLicenseManager *, struct UWAInstallWork *, _QWORD, _QWORD))(*(_QWORD *)v91 + 24LL))(
                    v91,
                    v92,
                    0,
                    0);
            *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ImmediateRetryAcquireLicenseTipTest,TipTests::_tip_ImmediateRetryAcquireLicenseTipTest>>::operator->(
                                     &string,
                                     v99)
                      + 276LL) = v32;
            tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_ImmediateRetryAcquireLicenseTipTest,TipTests::_tip_ImmediateRetryAcquireLicenseTipTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_ImmediateRetryAcquireLicenseTipTest,TipTests::_tip_ImmediateRetryAcquireLicenseTipTest>>(v99);
            v86 = WindowsGetStringRawBuffer(*((HSTRING *)v10 + 59), 0);
            v84 = (char *)v10 + 304;
            if ( v32 < 0 )
            {
              LogSimpleMessage(
                1u,
                "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
                0xD88u,
                "UWAInstallWork::_AcquireLicensesForUpdates",
                v32,
                L"Immediate Retry Acquire License failed",
                v84,
                v86);
              *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ImmediateRetryAcquireLicenseTipTest,TipTests::_tip_ImmediateRetryAcquireLicenseTipTest>>::operator->(
                                      &string,
                                      v101)
                       + 280LL) = 0;
              tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_ImmediateRetryAcquireLicenseTipTest,TipTests::_tip_ImmediateRetryAcquireLicenseTipTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_ImmediateRetryAcquireLicenseTipTest,TipTests::_tip_ImmediateRetryAcquireLicenseTipTest>>(v101);
              v54 = WindowsGetStringRawBuffer(*((HSTRING *)v10 + 15), 0);
              v55 = WindowsGetStringRawBuffer(*((HSTRING *)v10 + 57), 0);
              v56 = (WindowsUpdate::CommonTelemetry *)WindowsGetStringRawBuffer(*((HSTRING *)v10 + 59), 0);
              v32 = *(_DWORD *)v90;
              LOBYTE(v88) = 3;
              WindowsUpdate::CommonTelemetry::StateTransition(
                v56,
                v55,
                v54,
                0,
                0,
                (const unsigned __int16 *)"ImmediateRetry",
                "Error",
                v88,
                v90[0],
                (__int64)v108,
                (const char *)string);
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupScan>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BackupScan>::GetImpl'::`2'::impl) )
                *((_BYTE *)v10 + 986) = 1;
            }
            else
            {
              LogSimpleMessage(
                3u,
                "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
                0xD81u,
                "UWAInstallWork::_AcquireLicensesForUpdates",
                -1,
                L"Immediate Retry Acquire License Succeeded",
                v84,
                v86);
              *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ImmediateRetryAcquireLicenseTipTest,TipTests::_tip_ImmediateRetryAcquireLicenseTipTest>>::operator->(
                                      &string,
                                      v100)
                       + 280LL) = 1;
              tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_ImmediateRetryAcquireLicenseTipTest,TipTests::_tip_ImmediateRetryAcquireLicenseTipTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_ImmediateRetryAcquireLicenseTipTest,TipTests::_tip_ImmediateRetryAcquireLicenseTipTest>>(v100);
              v51 = WindowsGetStringRawBuffer(*((HSTRING *)v10 + 15), 0);
              v52 = WindowsGetStringRawBuffer(*((HSTRING *)v10 + 57), 0);
              v53 = (WindowsUpdate::CommonTelemetry *)WindowsGetStringRawBuffer(*((HSTRING *)v10 + 59), 0);
              LOBYTE(v87) = 3;
              WindowsUpdate::CommonTelemetry::StateTransition(
                v53,
                v52,
                v51,
                0,
                0,
                (const unsigned __int16 *)"ImmediateRetry",
                "Working",
                v87,
                v90[0],
                (__int64)v108,
                (const char *)string);
            }
            *(_OWORD *)String1 = *(_OWORD *)((char *)v10 + 1356);
            if ( !string || (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started(string + 2) )
            {
              v58 = CoTaskMemAlloc(0x128u);
              if ( !v58 )
                wil::details::in1diag3::_FailFastImmediate_Unexpected(v59);
              *(_QWORD *)v90 = tip2::details::merged_data<TipTests::_tip_ImmediateRetryAcquireLicenseTipTest,TipTests::_tip_ImmediateRetryAcquireLicenseTipTest>::merged_data<TipTests::_tip_ImmediateRetryAcquireLicenseTipTest,TipTests::_tip_ImmediateRetryAcquireLicenseTipTest>(
                                 v58,
                                 String1);
              wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_ImmediateRetryAcquireLicenseTipTest,TipTests::_tip_ImmediateRetryAcquireLicenseTipTest>,wil::err_returncode_policy>::operator=(
                &string,
                v90);
              wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_ImmediateRetryAcquireLicenseTipTest,TipTests::_tip_ImmediateRetryAcquireLicenseTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_ImmediateRetryAcquireLicenseTipTest,TipTests::_tip_ImmediateRetryAcquireLicenseTipTest>,wil::err_returncode_policy>(v90);
            }
            else
            {
              tip2::details::shared_data<1,0,0>::open_without_lock(v57, String1);
            }
            if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started(string + 2) && v60 )
              tip2::details::shared_data<1,0,0>::complete_without_lock(v61);
            wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_ImmediateRetryAcquireLicenseTipTest,TipTests::_tip_ImmediateRetryAcquireLicenseTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_ImmediateRetryAcquireLicenseTipTest,TipTests::_tip_ImmediateRetryAcquireLicenseTipTest>,wil::err_returncode_policy>(&string);
            v27 = v92;
            goto LABEL_70;
          }
LABEL_71:
          if ( (unsigned int)IsDeviceXbox() || v32 == -2143322104 )
          {
            v63 = WindowsGetStringRawBuffer(*((HSTRING *)v10 + 59), 0);
            LogMessage(
              2u,
              "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
              0xD9Fu,
              "UWAInstallWork::_AcquireLicensesForUpdates",
              v32,
              L"Unable to cache a modern license, ContentId = %s",
              (const char *)v10 + 304,
              v63);
          }
          else
          {
            if ( *((_DWORD *)v10 + 32) != 1 )
            {
              v70 = wil::verify_hresult<long>((unsigned int)v32);
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xDA7,
                (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
                (const char *)v70,
                (int)v81);
            }
            v62 = WindowsGetStringRawBuffer(*((HSTRING *)v10 + 59), 0);
            LogMessage(
              2u,
              "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
              0xDA3u,
              "UWAInstallWork::_AcquireLicensesForUpdates",
              v32,
              L"Ignoring licensing failure for Update, content id: %s",
              (const char *)v10 + 304,
              v62);
          }
        }
        DurationInMilliseconds = UWAInstallWork::StageTimer::GetDurationInMilliseconds((UWAInstallWork::StageTimer *)&ticks);
        LODWORD(v81) = 0;
        WindowsUpdate::Telemetry::EndAcquireLicense(
          v10,
          v27,
          (const unsigned __int16 *)v93,
          (const unsigned __int16 *)v108,
          v81,
          DurationInMilliseconds,
          (unsigned __int64)v83);
      }
      catch ( ... )
      {
        v71 = v102;
        v72 = wil::details::in1diag3::Log_CaughtExceptionMsg(
                retaddr,
                (void *)0xDAF,
                (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
                "Unable to get a modern license ContentId = %ws",
                (const char *)v102);
        updated = v72;
        v74 = v94;
        if ( v72 < 0 )
          updated = UWAInstallWork::_UpdateHrIfNetworkIssueWithNoInternet(v94, v72);
        v75 = UWAInstallWork::StageTimer::GetDurationInMilliseconds((UWAInstallWork::StageTimer *)&ticks);
        LODWORD(v77) = updated;
        WindowsUpdate::Telemetry::EndAcquireLicense(
          v74,
          v71,
          (const unsigned __int16 *)v103,
          (const unsigned __int16 *)v108,
          v77,
          v75,
          (unsigned __int64)v79);
        v76 = wil::verify_hresult<long>(updated);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xDB7,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
          (const char *)v76,
          v78);
      }
      v65 = (__int64 **)v22[2];
      if ( *((_BYTE *)v65 + 25) )
      {
        for ( k = (__int64 *)v22[1]; !*((_BYTE *)k + 25) && v22 == (__int64 *)k[2]; k = (__int64 *)k[1] )
          v22 = k;
        v22 = k;
      }
      else
      {
        v22 = (__int64 *)v22[2];
        for ( m = *v65; !*((_BYTE *)m + 25); m = (__int64 *)*m )
          v22 = m;
      }
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xDBC,
                           (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
                           v68);
  }
  return result;
}

```

## disassembly

```asm
0x1800ed1d8  mov     [rsp+arg_10], rbx
0x1800ed1dd  mov     [rsp+arg_18], rsi
0x1800ed1e2  push    rdi
0x1800ed1e3  push    r12
0x1800ed1e5  push    r13
0x1800ed1e7  push    r14
0x1800ed1e9  push    r15
0x1800ed1eb  sub     rsp, 1A0h
0x1800ed1f2  mov     rax, cs:__security_cookie
0x1800ed1f9  xor     rax, rsp
0x1800ed1fc  mov     [rsp+1C8h+var_38], rax
0x1800ed204  mov     rsi, rdx
0x1800ed207  mov     r15, rcx
0x1800ed20a  mov     [rsp+1C8h+var_160], rdx
0x1800ed20f  mov     [rsp+1C8h+var_150], rcx
0x1800ed214  mov     [rsp+1C8h+var_140], rcx
0x1800ed21c  mov     r12, rdx
0x1800ed21f  mov     [rsp+1C8h+var_158], rdx
0x1800ed224  xor     r14d, r14d
0x1800ed227  add     rcx, 98h
0x1800ed22e  lea     rdx, [rsp+1C8h+String1]
0x1800ed236  call    ?Impersonate@ContextData@CallerContext@@QEAA?AVImpersonateContext@TokenHelpers@@XZ; CallerContext::ContextData::Impersonate(void)
0x1800ed23b  nop
0x1800ed23c  mov     rbx, [r12]
0x1800ed240  mov     rbx, [rbx]
0x1800ed243  lea     r13, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800ed24a  cmp     [rbx+19h], r14b
0x1800ed24e  jnz     loc_1800ED2E5
0x1800ed254  xor     edx, edx; length
0x1800ed256  mov     rcx, [rbx+28h]; string
0x1800ed25a  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ed260  mov     rdi, rax
0x1800ed263  xor     edx, edx; length
0x1800ed265  mov     rcx, [rbx+20h]; string
0x1800ed269  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ed26f  mov     rdx, rdi; lpsz
0x1800ed272  mov     rcx, rax; packageFamilyName
0x1800ed275  call    SetContentIdForUAP
0x1800ed27a  mov     dword ptr [rsp+1C8h+var_1A8], eax; int
0x1800ed27e  lea     r9, aSetcontentidfo; "SetContentIdForUAP(pfncidpair.first.Get"...
0x1800ed285  lea     r8, aUwainstallwork_39; "UWAInstallWork::_AcquireLicensesForUpda"...
0x1800ed28c  mov     edx, 0D1Dh; unsigned int
0x1800ed291  mov     rcx, r13; char *
0x1800ed294  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x1800ed299  mov     rcx, [rbx+10h]
0x1800ed29d  cmp     [rcx+19h], r14b
0x1800ed2a1  jz      short loc_1800ED2C1
0x1800ed2a3  mov     rax, [rbx+8]
0x1800ed2a7  jmp     short loc_1800ED2B6
0x1800ed2a9  cmp     rbx, [rax+10h]
0x1800ed2ad  jnz     short loc_1800ED2BC
0x1800ed2af  mov     rbx, rax
0x1800ed2b2  mov     rax, [rax+8]
0x1800ed2b6  cmp     [rax+19h], r14b
0x1800ed2ba  jz      short loc_1800ED2A9
0x1800ed2bc  mov     rbx, rax
0x1800ed2bf  jmp     short loc_1800ED24A
0x1800ed2c1  mov     rbx, rcx
0x1800ed2c4  mov     rcx, [rcx]
0x1800ed2c7  cmp     [rcx+19h], r14b
0x1800ed2cb  jnz     loc_1800ED24A
0x1800ed2d1  mov     rbx, rcx
0x1800ed2d4  mov     rax, [rcx]
0x1800ed2d7  mov     rcx, rax
0x1800ed2da  cmp     [rax+19h], r14b
0x1800ed2de  jz      short loc_1800ED2D1
0x1800ed2e0  jmp     loc_1800ED24A
0x1800ed2e5  lea     rcx, [rsp+1C8h+String1]; this
0x1800ed2ed  call    ??1ImpersonateContext@TokenHelpers@@QEAA@XZ; TokenHelpers::ImpersonateContext::~ImpersonateContext(void)
0x1800ed2f2  nop
0x1800ed2f3  jmp     short loc_1800ED30C
0x1800ed2f5  xor     r14d, r14d
0x1800ed2f8  lea     r13, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800ed2ff  mov     r15, [rsp+1C8h+var_150]
0x1800ed304  mov     rsi, [rsp+1C8h+var_160]
0x1800ed309  mov     r12, rsi
0x1800ed30c  lea     rcx, [rsp+1C8h+String1]; this
0x1800ed314  call    ??0SuspendImpersonationScope@@QEAA@XZ; SuspendImpersonationScope::SuspendImpersonationScope(void)
0x1800ed319  nop
0x1800ed31a  mov     rdi, [r15+490h]
0x1800ed321  mov     rax, [r15+498h]
0x1800ed328  mov     qword ptr [rsp+1C8h+var_170], rax
0x1800ed32d  cmp     rdi, rax
0x1800ed330  jz      loc_1800ED3F8
0x1800ed336  mov     [rsp+1C8h+string], r14
0x1800ed33b  mov     rax, [rdi]
0x1800ed33e  mov     rcx, [rax+70h]
0x1800ed342  mov     [rsp+1C8h+var_148], rcx
0x1800ed34a  lea     rdx, [rsp+1C8h+var_148]; HSTRING *
0x1800ed352  lea     rcx, [rsp+1C8h+string]; newString
0x1800ed357  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800ed35c  mov     rcx, [rsp+1C8h]; this
0x1800ed364  test    eax, eax
0x1800ed366  js      loc_1800EDD5F
0x1800ed36c  lea     r8, [rsp+1C8h+string]
0x1800ed371  lea     rdx, [rsp+1C8h+var_100]
0x1800ed379  mov     rcx, r12
0x1800ed37c  call    ??$_Find_lower_bound@VHString@Wrappers@WRL@Microsoft@@@?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@_NU?$less@VHString@Wrappers@WRL@Microsoft@@@std@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@_N@std@@@6@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@_N@std@@PEAX@std@@@1@AEBVHString@Wrappers@WRL@Microsoft@@@Z; std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,bool,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,bool>>,0>>::_Find_lower_bound<Microsoft::WRL::Wrappers::HString>(Microsoft::WRL::Wrappers::HString const &)
0x1800ed381  lea     r8, [rsp+1C8h+string]
0x1800ed386  mov     r12, [rsp+1C8h+var_F0]
0x1800ed38e  mov     rdx, r12
0x1800ed391  call    ??$_Lower_bound_duplicate@VHString@Wrappers@WRL@Microsoft@@@?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@_NU?$less@VHString@Wrappers@WRL@Microsoft@@@std@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@_N@std@@@6@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@_N@std@@PEAX@1@AEBVHString@Wrappers@WRL@Microsoft@@@Z; std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,bool,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,bool>>,0>>::_Lower_bound_duplicate<Microsoft::WRL::Wrappers::HString>(std::_Tree_node<std::pair<Microsoft::WRL::Wrappers::HString const,bool>,void *> * const,Microsoft::WRL::Wrappers::HString const &)
0x1800ed396  test    al, al
0x1800ed398  jz      short loc_1800ED3DA
0x1800ed39a  cmp     r12, [rsi]
0x1800ed39d  jz      short loc_1800ED3DA
0x1800ed39f  mov     rbx, [rdi]
0x1800ed3a2  xor     edx, edx; length
0x1800ed3a4  mov     rcx, [r12+28h]; string
0x1800ed3a9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ed3af  mov     rdx, rax; unsigned __int16 *
0x1800ed3b2  mov     rcx, rbx; this
0x1800ed3b5  call    ?StoreInContentIdCache@FulfillmentDataInfo@Internal@WindowsUpdate@@QEAAJPEBG@Z; WindowsUpdate::Internal::FulfillmentDataInfo::StoreInContentIdCache(ushort const *)
0x1800ed3ba  mov     dword ptr [rsp+1C8h+var_1A8], eax; int
0x1800ed3be  lea     r9, aDataStoreincon; "data->StoreInContentIdCache(search->sec"...
0x1800ed3c5  lea     r8, aUwainstallwork_39; "UWAInstallWork::_AcquireLicensesForUpda"...
0x1800ed3cc  mov     edx, 0D2Bh; unsigned int
0x1800ed3d1  mov     rcx, r13; char *
0x1800ed3d4  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x1800ed3d9  nop
0x1800ed3da  mov     rcx, [rsp+1C8h+string]; string
0x1800ed3df  call    cs:__imp_WindowsDeleteString
0x1800ed3e5  add     rdi, 8
0x1800ed3e9  mov     r12, [rsp+1C8h+var_158]
0x1800ed3ee  mov     rax, qword ptr [rsp+1C8h+var_170]
0x1800ed3f3  jmp     loc_1800ED32D
0x1800ed3f8  lea     rcx, [rsp+1C8h+String1]; this
0x1800ed400  call    ??1SuspendImpersonationScope@@QEAA@XZ; SuspendImpersonationScope::~SuspendImpersonationScope(void)
0x1800ed405  nop
0x1800ed406  jmp     short loc_1800ED41C
0x1800ed408  xor     r14d, r14d
0x1800ed40b  lea     r13, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800ed412  mov     r15, [rsp+1C8h+var_150]
0x1800ed417  mov     rsi, [rsp+1C8h+var_160]
0x1800ed41c  mov     [rsp+1C8h+var_168], r14
0x1800ed421  mov     rbx, [rsi]
0x1800ed424  mov     rbx, [rbx]
0x1800ed427  cmp     [rbx+19h], r14b
0x1800ed42b  jnz     loc_1800EDD20
0x1800ed431  xor     edx, edx; length
0x1800ed433  mov     rcx, [rbx+28h]; string
0x1800ed437  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ed43d  mov     rdi, rax
0x1800ed440  mov     [rsp+1C8h+var_160], rax
0x1800ed445  xor     edx, edx; length
0x1800ed447  mov     rcx, [rbx+20h]; string
0x1800ed44b  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ed451  mov     r12, rax
0x1800ed454  mov     [rsp+1C8h+var_158], rax
0x1800ed459  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AsyncLicensing@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AsyncLicensing@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AsyncLicensing> `wil::Feature<__WilFeatureTraits_Feature_AsyncLicensing>::GetImpl(void)'::`2'::impl
0x1800ed460  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AsyncLicensing@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AsyncLicensing>::__private_IsEnabled(void)
0x1800ed465  mov     [rsp+1C8h+var_110], rdi
0x1800ed46d  mov     [rsp+1C8h+var_108], r12
0x1800ed475  mov     rsi, [rsp+1C8h+var_140]
0x1800ed47d  test    al, al
0x1800ed47f  jz      loc_1800ED52A
0x1800ed485  lea     rdx, [r15+418h]
0x1800ed48c  lea     rcx, [rsp+1C8h+var_138]
0x1800ed494  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1800ed499  lea     rdi, [r15+130h]
0x1800ed4a0  mov     rdx, rdi; char *
0x1800ed4a3  mov     rcx, [rsi+128h]; this
0x1800ed4aa  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x1800ed4af  movups  xmm0, xmmword ptr [rdi]
0x1800ed4b2  movups  xmmword ptr [rsp+1C8h+var_C8], xmm0
0x1800ed4ba  movups  xmm1, xmmword ptr [rdi+10h]
0x1800ed4be  movups  [rsp+1C8h+var_B8], xmm1
0x1800ed4c6  movups  xmm0, xmmword ptr [rdi+20h]
0x1800ed4ca  movups  [rsp+1C8h+var_A8], xmm0
0x1800ed4d2  movups  xmm1, xmmword ptr [rdi+30h]
0x1800ed4d6  movups  [rsp+1C8h+var_98], xmm1
0x1800ed4de  movups  xmm0, xmmword ptr [rdi+40h]
0x1800ed4e2  movups  [rsp+1C8h+var_88], xmm0
0x1800ed4ea  movups  xmm1, xmmword ptr [rdi+50h]
0x1800ed4ee  movups  [rsp+1C8h+var_78], xmm1
0x1800ed4f6  movups  xmm0, xmmword ptr [rdi+60h]
0x1800ed4fa  movups  [rsp+1C8h+var_68], xmm0
0x1800ed502  movups  xmm1, xmmword ptr [rdi+70h]
0x1800ed506  movups  [rsp+1C8h+var_58], xmm1
0x1800ed50e  mov     al, [rdi+80h]
0x1800ed514  mov     [rsp+1C8h+var_48], al
0x1800ed51b  lea     rcx, [rsp+1C8h+var_138]; this
0x1800ed523  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1800ed528  jmp     short loc_1800ED53E
0x1800ed52a  lea     rdx, [rsp+1C8h+var_C8]; char *
0x1800ed532  mov     rcx, [rsi+128h]; this
0x1800ed539  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x1800ed53e  lea     r9, [rsp+1C8h+var_C8]; unsigned __int16 *
0x1800ed546  mov     r8, r12; unsigned __int16 *
0x1800ed549  mov     rsi, [rsp+1C8h+var_160]
0x1800ed54e  mov     rdx, rsi; struct UWAInstallWork *
0x1800ed551  mov     rcx, r15; this
0x1800ed554  call    ?BeginAcquireLicense@Telemetry@WindowsUpdate@@YAXPEAVUWAInstallWork@@PEBG1PEBD@Z; WindowsUpdate::Telemetry::BeginAcquireLicense(UWAInstallWork *,ushort const *,ushort const *,char const *)
0x1800ed559  call    cs:__imp__Xtime_get_ticks
0x1800ed55f  mov     [rsp+1C8h+var_148], rax
0x1800ed567  mov     rcx, [rsp+1C8h+var_168]
0x1800ed56c  test    rcx, rcx
0x1800ed56f  jnz     short loc_1800ED59A
0x1800ed571  lea     rcx, [rsp+1C8h+var_168]
0x1800ed576  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800ed57b  lea     rcx, [rsp+1C8h+var_168]; struct IApplicationLicenseManager **
0x1800ed580  call    ?CoCreateLicenseManager@@YAJPEAPEAUIApplicationLicenseManager@@@Z; CoCreateLicenseManager(IApplicationLicenseManager * *)
0x1800ed585  mov     rcx, [rsp+1C8h]; this
0x1800ed58d  test    eax, eax
0x1800ed58f  js      loc_1800EDD70
0x1800ed595  mov     rcx, [rsp+1C8h+var_168]
0x1800ed59a  mov     rax, [rcx]
0x1800ed59d  xor     r9d, r9d
0x1800ed5a0  xor     r8d, r8d
0x1800ed5a3  mov     rdx, rsi
0x1800ed5a6  mov     rax, [rax+18h]
0x1800ed5aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed5af  mov     edi, eax
0x1800ed5b1  mov     dword ptr [rsp+1C8h+var_170], eax
0x1800ed5b5  mov     r12d, eax
0x1800ed5b8  test    eax, eax
0x1800ed5ba  jns     loc_1800EDBD6
0x1800ed5c0  mov     ecx, eax; int
0x1800ed5c2  call    ?IsImmediateRetryAcquireLicenseErrorCode@@YA_NJ@Z; IsImmediateRetryAcquireLicenseErrorCode(long)
0x1800ed5c7  test    al, al
0x1800ed5c9  jz      loc_1800EDBDF
0x1800ed5cf  inc     dword ptr [r15+438h]
0x1800ed5d6  mov     [rsp+1C8h+string], r14; char *
0x1800ed5db  lea     rcx, [rsp+1C8h+string]
0x1800ed5e0  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_ImmediateRetryAcquireLicenseTipTest@TipTests@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_ImmediateRetryAcquireLicenseTipTest@TipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ImmediateRetryAcquireLicenseTipTest,TipTests::_tip_ImmediateRetryAcquireLicenseTipTest>>::ensure_data(void)
0x1800ed5e5  mov     rcx, [rax]
0x1800ed5e8  add     rcx, 8
0x1800ed5ec  lea     rdx, [rsp+1C8h+var_100]
0x1800ed5f4  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x1800ed5f9  movups  xmm0, [rsp+1C8h+var_100]
0x1800ed601  movdqu  xmmword ptr [r15+54Ch], xmm0
0x1800ed60a  lea     rdx, [rsp+1C8h+var_130]
0x1800ed612  lea     rcx, [rsp+1C8h+string]
0x1800ed617  call    ??C?$tip_test@V?$merged_data@U_tip_ImmediateRetryAcquireLicenseTipTest@TipTests@@U12@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ImmediateRetryAcquireLicenseTipTest@TipTests@@U12@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ImmediateRetryAcquireLicenseTipTest,TipTests::_tip_ImmediateRetryAcquireLicenseTipTest>>::operator->(void)
0x1800ed61c  mov     rcx, [rax]
0x1800ed61f  mov     [rcx+110h], r12d
0x1800ed626  lea     rcx, [rsp+1C8h+var_130]
0x1800ed62e  call    ??1?$test_data_control@V?$merged_data@U_tip_ImmediateRetryAcquireLicenseTipTest@TipTests@@U12@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_ImmediateRetryAcquireLicenseTipTest,TipTests::_tip_ImmediateRetryAcquireLicenseTipTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_ImmediateRetryAcquireLicenseTipTest,TipTests::_tip_ImmediateRetryAcquireLicenseTipTest>>(void)
0x1800ed633  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CatalogCacheImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CatalogCacheImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CatalogCacheImprovements> `wil::Feature<__WilFeatureTraits_Feature_CatalogCacheImprovements>::GetImpl(void)'::`2'::impl
0x1800ed63a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CatalogCacheImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CatalogCacheImprovements>::__private_IsEnabled(void)
0x1800ed63f  xor     r9d, r9d; Context
0x1800ed642  xor     r8d, r8d; Parameter
0x1800ed645  test    al, al
0x1800ed647  jz      short loc_1800ED659
0x1800ed649  lea     rdx, InitializeOneSettingsConfiguration
0x1800ed650  lea     rcx, stru_1802E4F70
0x1800ed657  jmp     short loc_1800ED667
0x1800ed659  lea     rdx, InitializeInstallServiceConfiguration; InitFn
0x1800ed660  lea     rcx, InitOnce; InitOnce
0x1800ed667  call    cs:__imp_InitOnceExecuteOnce
0x1800ed66d  mov     ecx, cs:dwMilliseconds; dwMilliseconds
0x1800ed673  test    ecx, ecx
0x1800ed675  jz      short loc_1800ED67D
0x1800ed677  call    cs:__imp_Sleep
0x1800ed67d  xor     edx, edx; length
0x1800ed67f  mov     rcx, [r15+1D8h]; string
0x1800ed686  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ed68c  lea     rcx, [r15+130h]
0x1800ed693  mov     [rsp+1C8h+var_190], rax; unsigned __int16 *
0x1800ed698  mov     [rsp+1C8h+var_198], rcx; char *
0x1800ed69d  lea     rax, aImmediateRetry_11; "Immediate Retry Acquire License for Err"...
0x1800ed6a4  mov     [rsp+1C8h+var_1A0], rax; unsigned __int16 *
0x1800ed6a9  mov     dword ptr [rsp+1C8h+var_1A8], edi; int
0x1800ed6ad  lea     r9, aUwainstallwork_39; "UWAInstallWork::_AcquireLicensesForUpda"...
0x1800ed6b4  mov     r8d, 0D5Fh; unsigned int
0x1800ed6ba  mov     rdx, r13; char *
0x1800ed6bd  mov     ecx, 3; unsigned int
0x1800ed6c2  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x1800ed6c7  xor     edx, edx; length
0x1800ed6c9  mov     rcx, [r15+78h]; string
0x1800ed6cd  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ed6d3  mov     rsi, rax
0x1800ed6d6  xor     edx, edx; length
0x1800ed6d8  mov     rcx, [r15+1C8h]; string
0x1800ed6df  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ed6e5  mov     rdi, rax
0x1800ed6e8  xor     edx, edx; length
0x1800ed6ea  mov     rcx, [r15+1D8h]; string
0x1800ed6f1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ed6f7  lea     rcx, [rsp+1C8h+var_C8]
0x1800ed6ff  mov     [rsp+1C8h+var_180], rcx; __int64
0x1800ed704  mov     r12d, dword ptr [rsp+1C8h+var_170]
0x1800ed709  mov     dword ptr [rsp+1C8h+var_188], r12d; unsigned __int8
0x1800ed70e  mov     byte ptr [rsp+1C8h+var_190], 3; char *
0x1800ed713  lea     rcx, aImmediateretry_18; "ImmediateRetry"
0x1800ed71a  mov     [rsp+1C8h+var_198], rcx; char *
0x1800ed71f  lea     rcx, aError_0; "Error"
0x1800ed726  mov     [rsp+1C8h+var_1A0], rcx; unsigned __int16 *
0x1800ed72b  mov     [rsp+1C8h+var_1A8], r14; unsigned __int16 *
0x1800ed730  xor     r9d, r9d; unsigned __int16 *
0x1800ed733  mov     r8, rsi; unsigned __int16 *
0x1800ed736  mov     rdx, rdi; unsigned __int16 *
0x1800ed739  mov     rcx, rax; this
0x1800ed73c  call    ?StateTransition@CommonTelemetry@WindowsUpdate@@YAXPEBG0000PEBD1EJ1@Z; WindowsUpdate::CommonTelemetry::StateTransition(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,char const *,char const *,uchar,long,char const *)
0x1800ed741  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GetFreeEntitlementOnNoEntitlement@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GetFreeEntitlementOnNoEntitlement@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GetFreeEntitlementOnNoEntitlement> `wil::Feature<__WilFeatureTraits_Feature_GetFreeEntitlementOnNoEntitlement>::GetImpl(void)'::`2'::impl
0x1800ed748  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_GetFreeEntitlementOnNoEntitlement@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GetFreeEntitlementOnNoEntitlement>::__private_IsEnabled(void)
0x1800ed74d  test    al, al
0x1800ed74f  jz      loc_1800ED822
0x1800ed755  cmp     r12d, 803F8001h
0x1800ed75c  jnz     loc_1800ED822
  ... truncated ...
```
