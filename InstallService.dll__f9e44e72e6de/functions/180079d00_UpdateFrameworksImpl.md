# _UpdateFrameworksImpl

- ea: `0x180079d00`
- end: `0x18007a7a9`
- name: `_UpdateFrameworksImpl`
- size: `2729`
- prototype: `__int64 __fastcall(HANDLE ExistingTokenHandle)`
- caller_count: `2`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180078338`
- `0x180079b70`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x180010b54`
- `0x18001c414`
- `0x18001c844`
- `0x180023a9c`
- `0x18002548c`
- `0x18003f884`
- `0x180044da8`
- `0x18005bdd8`
- `0x1800649d4`
- `0x180064c7c`
- `0x18006f864`
- `0x180072420`
- `0x1800724a4`
- `0x180079878`
- `0x180079d00`
- `0x18007b3a0`
- `0x18007bff0`
- `0x18011425c`
- `0x180117c0c`
- `0x180215010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18007a064`
- `OLEAUT32!__imp_VariantInit` at `0x18007a376`
- `OLEAUT32!__imp_VariantInit` at `0x18007a43e`
- `OLEAUT32!__imp_VariantInit` at `0x18007a513`
- `OLEAUT32!__imp_VariantInit` at `0x18007a064`
- `OLEAUT32!__imp_VariantInit` at `0x18007a376`
- `OLEAUT32!__imp_VariantInit` at `0x18007a43e`
- `OLEAUT32!__imp_VariantInit` at `0x18007a513`
- `OLEAUT32!__imp_VariantClear` at `0x18007a0e3`
- `OLEAUT32!__imp_VariantClear` at `0x18007a3ef`
- `OLEAUT32!__imp_VariantClear` at `0x18007a4b9`
- `OLEAUT32!__imp_VariantClear` at `0x18007a58e`
- `OLEAUT32!__imp_VariantClear` at `0x18007a0e3`
- `OLEAUT32!__imp_VariantClear` at `0x18007a3ef`
- `OLEAUT32!__imp_VariantClear` at `0x18007a4b9`
- `OLEAUT32!__imp_VariantClear` at `0x18007a58e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180079eb4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180079eb4`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180079e58`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180079e58`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18007a421`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18007a4f6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18007a421`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18007a4f6`

## string_xrefs

- `0x180079ebe`: `CoCreateInstance(__uuidof(UpdateSession), nullptr, CLSCTX_INPROC_SERVER, IID_PPV_ARGS(&spSession))`
- `0x180079d5a`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x18007a115`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x18007a5ca`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x18007a02a`: `spDownloader->QueryInterface(IID_PPV_ARGS(&spInternalConfiguration))`
- `0x18007a0c3`: `spInternalConfiguration->put_InternalConfigurationProperty(IUPDATE_INTERNALPROPERTY_DOWNLOAD_USERTOKEN, var)`
- `0x18007a3cf`: `spInternalConfiguration->put_InternalConfigurationProperty(IUPDATE_INTERNALPROPERTY_INSTALL_USERTOKEN, var)`
- `0x18007a499`: `spInternalConfiguration->put_InternalConfigurationProperty(IUPDATE_INTERNALPROPERTY_INSTALL_USERTOKEN, var)`
- `0x18007a56e`: `spInternalConfiguration->put_InternalConfigurationProperty(IUPDATE_INTERNALPROPERTY_INSTALL_USERTOKEN, var)`
- `0x18007a318`: `spInstaller->QueryInterface(IID_PPV_ARGS(&spInternalConfiguration))`
- `0x180079d53`: `_UpdateFrameworksImpl`
- `0x18007a10e`: `_UpdateFrameworksImpl`
- `0x18007a5c3`: `_UpdateFrameworksImpl`
- `0x180079f13`: `spSession->CreateUpdateDownloader(&spDownloader)`
- `0x18007a16e`: `spDownloader->put_Updates(pFrameworkUpdates)`
- `0x18007a66d`: `spInstaller->put_Updates(pFrameworkUpdates)`
- `0x18007a250`: `spSession->CreateUpdateInstaller(&spInstaller)`
- `0x18007a6be`: `spInstaller->Install(&spResult)`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall UpdateFrameworksImpl(HANDLE ExistingTokenHandle, __int64 a2, const char *a3, __int16 a4)
{
  TraceLoggingCorrelationVector *v6; // rax
  TraceLoggingCorrelationVector *v7; // r13
  const char *v9; // rdx
  const char *v10; // r9
  unsigned int LastError; // ebx
  int v12; // eax
  int v13; // r8d
  LPVOID v14; // rdi
  __int64 (__fastcall *v15)(LPVOID, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v16; // eax
  __int64 (__fastcall ***v17)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v18)(_QWORD, GUID *, __int64 *); // rbx
  int v19; // eax
  int v20; // eax
  const char *v21; // r9
  int v22; // eax
  __int64 (__fastcall ***v23)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v24)(_QWORD, GUID *, __int64 *); // rbx
  int v25; // eax
  LPVOID v26; // rdi
  __int64 (__fastcall *v27)(LPVOID, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v28; // eax
  __int64 (__fastcall ***v29)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v30)(_QWORD, GUID *, __int64 *); // rbx
  int v31; // eax
  __int16 v32; // bx
  int v33; // eax
  int v34; // eax
  int v35; // eax
  const char *v36; // r9
  __int64 v37; // rdi
  int v38; // eax
  __int64 (__fastcall ***v39)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v40)(_QWORD, GUID *, __int64 *); // rbx
  int v41; // eax
  unsigned int v42; // edx
  HRESULT ppv; // [rsp+20h] [rbp-278h]
  int v44; // [rsp+28h] [rbp-270h]
  int v45; // [rsp+28h] [rbp-270h]
  int v46; // [rsp+28h] [rbp-270h]
  int v47; // [rsp+28h] [rbp-270h]
  char *v48; // [rsp+50h] [rbp-248h] BYREF
  __int64 (__fastcall ***v49)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-240h] BYREF
  __int64 v50; // [rsp+60h] [rbp-238h] BYREF
  __int64 v51; // [rsp+68h] [rbp-230h] BYREF
  __int64 v52; // [rsp+70h] [rbp-228h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-220h] BYREF
  void *DuplicateTokenHandle; // [rsp+90h] [rbp-208h] BYREF
  LPVOID v55; // [rsp+98h] [rbp-200h] BYREF
  VARIANTARG v56; // [rsp+A0h] [rbp-1F8h] BYREF
  __int64 v57; // [rsp+C0h] [rbp-1D8h] BYREF
  int v58; // [rsp+C8h] [rbp-1D0h]
  char v59; // [rsp+CCh] [rbp-1CCh]
  TraceLoggingCorrelationVector *v60; // [rsp+D0h] [rbp-1C8h]
  __int64 v61; // [rsp+D8h] [rbp-1C0h]
  int v62; // [rsp+E0h] [rbp-1B8h] BYREF
  char v63; // [rsp+E4h] [rbp-1B4h]
  int v64; // [rsp+E8h] [rbp-1B0h]
  char v65; // [rsp+ECh] [rbp-1ACh]
  int v66; // [rsp+F0h] [rbp-1A8h]
  char v67; // [rsp+F4h] [rbp-1A4h]
  int v68; // [rsp+F8h] [rbp-1A0h]
  char v69; // [rsp+FCh] [rbp-19Ch]
  int v70; // [rsp+100h] [rbp-198h]
  char v71; // [rsp+104h] [rbp-194h]
  int v72; // [rsp+108h] [rbp-190h]
  char v73; // [rsp+10Ch] [rbp-18Ch]
  int v74; // [rsp+110h] [rbp-188h]
  char v75; // [rsp+114h] [rbp-184h]
  char v76[24]; // [rsp+118h] [rbp-180h] BYREF
  char v77[144]; // [rsp+130h] [rbp-168h] BYREF
  char v78[144]; // [rsp+1C0h] [rbp-D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  v52 = a2;
  v51 = (__int64)ExistingTokenHandle;
  v57 = (__int64)ExistingTokenHandle;
  v61 = a2;
  if ( !TraceLoggingCorrelationVector::Validate(a3) )
    LogMessage(
      1u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
      0x660u,
      "_UpdateFrameworksImpl",
      -1,
      L"Assert (%s): %s",
      0,
      0,
      L"TraceLoggingCorrelationVector::Validate(cV)",
      L"Failed");
  v6 = TraceLoggingCorrelationVector::Extend(a3, 0);
  v7 = v6;
  v60 = v6;
  if ( !v6 )
    return 2147942414LL;
  TraceLoggingCorrelationVector::Increment(v6, v77);
  LogMessage(
    4u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
    0x66Au,
    "_UpdateFrameworksImpl",
    -1,
    L"Updating frameworks, cv = %hs",
    0,
    0);
  WindowsUpdate::Telemetry::BeginFrameworkUpdate((WindowsUpdate::Telemetry *)v77, v9);
  DuplicateTokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &DuplicateTokenHandle,
    0);
  if ( DuplicateToken(ExistingTokenHandle, SecurityImpersonation, &DuplicateTokenHandle) )
  {
    v55 = 0;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v55);
    ppv = CoCreateInstance(
            &GUID_4cb43d7f_7eee_4906_8698_60da1c38f2fe,
            0,
            1u,
            &GUID_816858a4_260d_4260_933a_2585f1abc76b,
            &v55);
    v12 = TraceHR(
            "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
            0x675u,
            "_UpdateFrameworksImpl",
            "CoCreateInstance(__uuidof(UpdateSession), nullptr, CLSCTX_INPROC_SERVER, IID_PPV_ARGS(&spSession))",
            ppv,
            v44);
    LODWORD(v48) = v12;
    if ( v12 >= 0 )
    {
      v49 = 0;
      v14 = v55;
      v15 = *(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v55 + 104LL);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v49);
      v16 = v15(v14, &v49);
      LODWORD(v48) = TraceHR(
                       "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                       0x67Au,
                       "_UpdateFrameworksImpl",
                       "spSession->CreateUpdateDownloader(&spDownloader)",
                       v16,
                       v45);
      if ( (int)v48 >= 0 )
      {
        v62 = 196611;
        v63 = 0;
        v64 = 196619;
        v65 = 0;
        v66 = 196618;
        v67 = 1;
        v68 = 196617;
        v69 = 0;
        v70 = 196610;
        v71 = 0;
        v72 = 196620;
        v73 = 1;
        v74 = 196615;
        v75 = 1;
        LODWORD(v48) = SetInternalConfigurationFlags(v49, &v62, 7, v77);
        if ( (int)v48 >= 0 )
        {
          try
          {
            SuspendImpersonationScope::SuspendImpersonationScope((SuspendImpersonationScope *)v76);
            v50 = 0;
            v17 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v49;
            v18 = **v49;
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v50);
            v19 = v18(v17, &GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b, &v50);
            LODWORD(v48) = TraceHR(
                             "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                             0x68Eu,
                             "_UpdateFrameworksImpl",
                             "spDownloader->QueryInterface(IID_PPV_ARGS(&spInternalConfiguration))",
                             v19,
                             v45);
            if ( (int)v48 >= 0 )
            {
              memset(&pvarg, 0, sizeof(pvarg));
              VariantInit(&pvarg);
              pvarg.vt = 19;
              pvarg.lVal = v51;
              v56 = pvarg;
              v20 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v50 + 32LL))(
                      v50,
                      196614,
                      &v56);
              LODWORD(v48) = TraceHR(
                               "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                               0x695u,
                               "_UpdateFrameworksImpl",
                               "spInternalConfiguration->put_InternalConfigurationProperty(IUPDATE_INTERNALPROPERTY_DOWNL"
                               "OAD_USERTOKEN, var)",
                               v20,
                               v45);
              VariantClear(&pvarg);
            }
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v50);
            SuspendImpersonationScope::~SuspendImpersonationScope((SuspendImpersonationScope *)v76);
          }
          catch ( ... )
          {
            LODWORD(v48) = wil::details::in1diag3::Log_CaughtException(
                             retaddr,
                             (void *)0x699,
                             (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                             v21);
            v7 = v60;
            v51 = v57;
            v52 = v61;
          }
        }
      }
      if ( (int)v48 >= 0 )
      {
        v22 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v49)[14])(v49);
        LODWORD(v48) = TraceHR(
                         "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                         0x69Du,
                         "_UpdateFrameworksImpl",
                         "spDownloader->put_Updates(pFrameworkUpdates)",
                         v22,
                         v45);
        if ( (int)v48 >= 0 )
        {
          v50 = 0;
          v23 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v49;
          v24 = (*v49)[16];
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v50);
          v25 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), __int64 *))v24)(v23, &v50);
          LODWORD(v48) = TraceHR(
                           "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                           0x6A2u,
                           "_UpdateFrameworksImpl",
                           "spDownloader->Download(&spResult)",
                           v25,
                           v45);
          if ( (int)v48 >= 0 )
            (*(void (__fastcall **)(__int64, char **))(*(_QWORD *)v50 + 56LL))(v50, &v48);
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v50);
        }
      }
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v49);
      v12 = (int)v48;
    }
    if ( v12 < 0 )
      goto LABEL_49;
    v49 = 0;
    v26 = v55;
    v27 = *(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v55 + 112LL);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v49);
    v28 = v27(v26, &v49);
    LODWORD(v48) = TraceHR(
                     "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                     0x6ADu,
                     "_UpdateFrameworksImpl",
                     "spSession->CreateUpdateInstaller(&spInstaller)",
                     v28,
                     v45);
    if ( (int)v48 < 0
      || (TraceLoggingCorrelationVector::Increment(v7, v78),
          LODWORD(v57) = 327681,
          BYTE4(v57) = 0,
          v58 = 327683,
          v59 = 0,
          LODWORD(v48) = SetInternalConfigurationFlags(v49, &v57, 2, v78),
          (int)v48 < 0) )
    {
      v32 = a4;
LABEL_37:
      v37 = v52;
LABEL_38:
      if ( (int)v48 >= 0 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixDependencyFrameworkInUse>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixDependencyFrameworkInUse>::GetImpl'::`2'::impl)
          && (v32 & 0x1008) != 0 )
        {
          v51 = 0;
          if ( (int)Microsoft::WRL::ComPtr<IUpdateInstaller>::As<IUpdateInstaller3>(&v49, &v51) >= 0 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v51 + 248LL))(v51, 0xFFFFFFFFLL);
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v51);
        }
        v38 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*v49)[16])(
                v49,
                v37);
        LODWORD(v48) = TraceHR(
                         "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                         0x702u,
                         "_UpdateFrameworksImpl",
                         "spInstaller->put_Updates(pFrameworkUpdates)",
                         v38,
                         v46);
        if ( (int)v48 >= 0 )
        {
          v52 = 0;
          v39 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v49;
          v40 = (*v49)[21];
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v52);
          v41 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), __int64 *))v40)(v39, &v52);
          LODWORD(v48) = TraceHR(
                           "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                           0x707u,
                           "_UpdateFrameworksImpl",
                           "spInstaller->Install(&spResult)",
                           v41,
                           v47);
          if ( (int)v48 >= 0 )
            (*(void (__fastcall **)(__int64, char **))(*(_QWORD *)v52 + 56LL))(v52, &v48);
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v52);
        }
      }
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v49);
      v12 = (int)v48;
LABEL_49:
      WindowsUpdate::Telemetry::EndFrameworkUpdate(
        (WindowsUpdate::Telemetry *)v77,
        (const char *)(unsigned int)v12,
        v13);
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
        0x710u,
        "_UpdateFrameworksImpl",
        (int)v48,
        L"Finished updating frameworks, cv = %hs",
        0,
        0,
        v77);
      TraceLoggingCorrelationVector::`scalar deleting destructor'(v7, v42);
      LastError = (unsigned int)v48;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v55);
      goto LABEL_50;
    }
    try
    {
      SuspendImpersonationScope::SuspendImpersonationScope((SuspendImpersonationScope *)v76);
      v50 = 0;
      v29 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v49;
      v30 = **v49;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v50);
      v31 = v30(v29, &GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b, &v50);
      LODWORD(v48) = TraceHR(
                       "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                       0x6BFu,
                       "_UpdateFrameworksImpl",
                       "spInstaller->QueryInterface(IID_PPV_ARGS(&spInternalConfiguration))",
                       v31,
                       v46);
      if ( (int)v48 >= 0 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixDependencyFrameworkInUse>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixDependencyFrameworkInUse>::GetImpl'::`2'::impl) )
        {
          v32 = a4;
          if ( (a4 & 8) != 0 )
          {
            memset(&pvarg, 0, sizeof(pvarg));
            VariantInit(&pvarg);
            pvarg.vt = 19;
            pvarg.lVal = v51;
            v56 = pvarg;
            v33 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v50 + 32LL))(v50, 327682, &v56);
            LODWORD(v48) = TraceHR(
                             "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                             0x6CEu,
                             "_UpdateFrameworksImpl",
                             "spInternalConfiguration->put_InternalConfigurationProperty(IUPDATE_INTERNALPROPERTY_INSTALL"
                             "_USERTOKEN, var)",
                             v33,
                             v46);
            VariantClear(&pvarg);
          }
          else
          {
            v51 = -1;
            LODWORD(v48) = wil::impersonate_token_nothrow(DuplicateTokenHandle);
            if ( (int)v48 >= 0 )
            {
              RevertToSelf();
              memset(&pvarg, 0, sizeof(pvarg));
              VariantInit(&pvarg);
              pvarg.vt = 19;
              pvarg.lVal = (int)DuplicateTokenHandle;
              v56 = pvarg;
              v34 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v50 + 32LL))(
                      v50,
                      327682,
                      &v56);
              LODWORD(v48) = TraceHR(
                               "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                               0x6DCu,
                               "_UpdateFrameworksImpl",
                               "spInternalConfiguration->put_InternalConfigurationProperty(IUPDATE_INTERNALPROPERTY_INSTA"
                               "LL_USERTOKEN, var)",
                               v34,
                               v46);
              VariantClear(&pvarg);
            }
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v51);
          }
          goto LABEL_35;
        }
        v51 = -1;
        LODWORD(v48) = wil::impersonate_token_nothrow(DuplicateTokenHandle);
        if ( (int)v48 >= 0 )
        {
          RevertToSelf();
          memset(&pvarg, 0, sizeof(pvarg));
          VariantInit(&pvarg);
          pvarg.vt = 19;
          pvarg.lVal = (int)DuplicateTokenHandle;
          v56 = pvarg;
          v35 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v50 + 32LL))(v50, 327682, &v56);
          LODWORD(v48) = TraceHR(
                           "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                           0x6ECu,
                           "_UpdateFrameworksImpl",
                           "spInternalConfiguration->put_InternalConfigurationProperty(IUPDATE_INTERNALPROPERTY_INSTALL_USERTOKEN, var)",
                           v35,
                           v46);
          VariantClear(&pvarg);
        }
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v51);
      }
      v32 = a4;
LABEL_35:
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v50);
      SuspendImpersonationScope::~SuspendImpersonationScope((SuspendImpersonationScope *)v76);
    }
    catch ( ... )
    {
      LODWORD(v48) = wil::details::in1diag3::Log_CaughtException(
                       retaddr,
                       (void *)0x6F2,
                       (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                       v36);
      v7 = v60;
      v37 = v61;
      v32 = a4;
      goto LABEL_38;
    }
    goto LABEL_37;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x672,
                (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                v10);
LABEL_50:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&DuplicateTokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x180079d00  mov     [rsp+arg_18], r9d
0x180079d05  push    rbx
0x180079d06  push    rsi
0x180079d07  push    rdi
0x180079d08  push    r12
0x180079d0a  push    r13
0x180079d0c  push    r14
0x180079d0e  push    r15
0x180079d10  sub     rsp, 260h
0x180079d17  mov     rax, cs:__security_cookie
0x180079d1e  xor     rax, rsp
0x180079d21  mov     [rsp+298h+var_48], rax
0x180079d29  mov     rbx, r8
0x180079d2c  mov     [rsp+298h+var_228], rdx
0x180079d31  mov     rdi, rcx
0x180079d34  mov     [rsp+298h+var_230], rcx
0x180079d39  mov     [rsp+298h+var_1D8], rcx
0x180079d41  mov     [rsp+298h+var_1C0], rdx
0x180079d49  mov     rcx, r8; char *
0x180079d4c  call    ?Validate@TraceLoggingCorrelationVector@@SA_NPEBD@Z; TraceLoggingCorrelationVector::Validate(char const *)
0x180079d51  xor     esi, esi
0x180079d53  lea     r15, aUpdateframewor_2; "_UpdateFrameworksImpl"
0x180079d5a  lea     r14, aOnecoreuapEndu_18; "onecoreuap\\enduser\\winstore\\installs"...
0x180079d61  test    al, al
0x180079d63  jnz     short loc_180079DAF
0x180079d65  lea     rax, aFailed_1; "Failed"
0x180079d6c  mov     [rsp+298h+var_250], rax
0x180079d71  lea     rax, aTraceloggingco_0; "TraceLoggingCorrelationVector::Validate"...
0x180079d78  mov     [rsp+298h+var_258], rax
0x180079d7d  mov     [rsp+298h+var_260], rsi; unsigned __int16 *
0x180079d82  mov     [rsp+298h+var_268], rsi; char *
0x180079d87  lea     rax, aAssertSS; "Assert (%s): %s"
0x180079d8e  mov     [rsp+298h+var_270], rax; unsigned __int16 *
0x180079d93  mov     dword ptr [rsp+298h+ppv], 0FFFFFFFFh; int
0x180079d9b  mov     r9, r15; char *
0x180079d9e  mov     r8d, 660h; unsigned int
0x180079da4  mov     rdx, r14; char *
0x180079da7  lea     ecx, [rsi+1]; unsigned int
0x180079daa  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180079daf  xor     edx, edx; bool
0x180079db1  mov     rcx, rbx; char *
0x180079db4  call    ?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Extend(char const *,bool)
0x180079db9  mov     r13, rax
0x180079dbc  mov     [rsp+298h+var_1C8], rax
0x180079dc4  test    rax, rax
0x180079dc7  jnz     short loc_180079DD3
0x180079dc9  mov     eax, 8007000Eh
0x180079dce  jmp     loc_18007A786
0x180079dd3  lea     rdx, [rsp+298h+var_168]; char *
0x180079ddb  mov     rcx, rax; this
0x180079dde  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x180079de3  lea     rax, [rsp+298h+var_168]
0x180079deb  mov     [rsp+298h+var_258], rax
0x180079df0  mov     [rsp+298h+var_260], rsi; unsigned __int16 *
0x180079df5  mov     [rsp+298h+var_268], rsi; char *
0x180079dfa  lea     rax, aUpdatingFramew; "Updating frameworks, cv = %hs"
0x180079e01  mov     [rsp+298h+var_270], rax; int
0x180079e06  mov     dword ptr [rsp+298h+ppv], 0FFFFFFFFh; int
0x180079e0e  mov     r9, r15; char *
0x180079e11  mov     r8d, 66Ah; unsigned int
0x180079e17  mov     rdx, r14; char *
0x180079e1a  mov     ecx, 4; unsigned int
0x180079e1f  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180079e24  lea     rcx, [rsp+298h+var_168]; this
0x180079e2c  call    ?BeginFrameworkUpdate@Telemetry@WindowsUpdate@@YAXPEBD@Z; WindowsUpdate::Telemetry::BeginFrameworkUpdate(char const *)
0x180079e31  mov     [rsp+298h+DuplicateTokenHandle], rsi
0x180079e39  xor     edx, edx
0x180079e3b  lea     rcx, [rsp+298h+DuplicateTokenHandle]
0x180079e43  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180079e48  lea     r8, [rsp+298h+DuplicateTokenHandle]; DuplicateTokenHandle
0x180079e50  mov     edx, 2; ImpersonationLevel
0x180079e55  mov     rcx, rdi; ExistingTokenHandle
0x180079e58  call    cs:__imp_DuplicateToken
0x180079e5e  test    eax, eax
0x180079e60  jnz     short loc_180079E7E
0x180079e62  mov     rcx, [rsp+298h]; this
0x180079e6a  mov     r8, r14; unsigned int
0x180079e6d  mov     edx, 672h; void *
0x180079e72  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180079e77  mov     ebx, eax
0x180079e79  jmp     loc_18007A777
0x180079e7e  mov     [rsp+298h+var_200], rsi
0x180079e86  lea     rcx, [rsp+298h+var_200]
0x180079e8e  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180079e93  lea     rax, [rsp+298h+var_200]
0x180079e9b  mov     [rsp+298h+ppv], rax; ppv
0x180079ea0  lea     r9, _GUID_816858a4_260d_4260_933a_2585f1abc76b; riid
0x180079ea7  xor     edx, edx; pUnkOuter
0x180079ea9  lea     r8d, [rdx+1]; dwClsContext
0x180079ead  lea     rcx, _GUID_4cb43d7f_7eee_4906_8698_60da1c38f2fe; rclsid
0x180079eb4  call    cs:__imp_CoCreateInstance
0x180079eba  mov     dword ptr [rsp+298h+ppv], eax; int
0x180079ebe  lea     r9, aCocreateinstan_1; "CoCreateInstance(__uuidof(UpdateSession"...
0x180079ec5  mov     r8, r15; char *
0x180079ec8  mov     edx, 675h; unsigned int
0x180079ecd  mov     rcx, r14; char *
0x180079ed0  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x180079ed5  mov     dword ptr [rsp+298h+var_248], eax
0x180079ed9  test    eax, eax
0x180079edb  js      loc_18007A210
0x180079ee1  mov     [rsp+298h+var_240], rsi
0x180079ee6  mov     rdi, [rsp+298h+var_200]
0x180079eee  mov     rax, [rdi]
0x180079ef1  mov     rbx, [rax+68h]
0x180079ef5  lea     rcx, [rsp+298h+var_240]
0x180079efa  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180079eff  lea     rdx, [rsp+298h+var_240]
0x180079f04  mov     rcx, rdi
0x180079f07  mov     rax, rbx
0x180079f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079f0f  mov     dword ptr [rsp+298h+ppv], eax; int
0x180079f13  lea     r9, aSpsessionCreat; "spSession->CreateUpdateDownloader(&spDo"...
0x180079f1a  mov     r8, r15; char *
0x180079f1d  mov     edx, 67Ah; unsigned int
0x180079f22  mov     rcx, r14; char *
0x180079f25  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x180079f2a  mov     dword ptr [rsp+298h+var_248], eax
0x180079f2e  test    eax, eax
0x180079f30  js      loc_18007A144
0x180079f36  mov     [rsp+298h+var_1B8], 30003h
0x180079f41  mov     [rsp+298h+var_1B4], sil
0x180079f49  mov     [rsp+298h+var_1B0], 3000Bh
0x180079f54  mov     [rsp+298h+var_1AC], sil
0x180079f5c  mov     [rsp+298h+var_1A8], 3000Ah
0x180079f67  mov     [rsp+298h+var_1A4], 1
0x180079f6f  mov     [rsp+298h+var_1A0], 30009h
0x180079f7a  mov     [rsp+298h+var_19C], sil
0x180079f82  mov     [rsp+298h+var_198], 30002h
0x180079f8d  mov     [rsp+298h+var_194], sil
0x180079f95  mov     [rsp+298h+var_190], 3000Ch
0x180079fa0  mov     [rsp+298h+var_18C], 1
0x180079fa8  mov     [rsp+298h+var_188], 30007h
0x180079fb3  mov     [rsp+298h+var_184], 1
0x180079fbb  lea     r9, [rsp+298h+var_168]
0x180079fc3  mov     r8d, 7
0x180079fc9  lea     rdx, [rsp+298h+var_1B8]
0x180079fd1  mov     rcx, [rsp+298h+var_240]
0x180079fd6  call    _SetInternalConfigurationFlags
0x180079fdb  mov     dword ptr [rsp+298h+var_248], eax
0x180079fdf  test    eax, eax
0x180079fe1  js      loc_18007A144
0x180079fe7  lea     rcx, [rsp+298h+var_180]; this
0x180079fef  call    ??0SuspendImpersonationScope@@QEAA@XZ; SuspendImpersonationScope::SuspendImpersonationScope(void)
0x180079ff4  nop
0x180079ff5  mov     [rsp+298h+var_238], rsi
0x180079ffa  mov     rdi, [rsp+298h+var_240]
0x180079fff  mov     rax, [rdi]
0x18007a002  mov     rbx, [rax]
0x18007a005  lea     rcx, [rsp+298h+var_238]
0x18007a00a  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007a00f  lea     r8, [rsp+298h+var_238]
0x18007a014  lea     rdx, _GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b
0x18007a01b  mov     rcx, rdi
0x18007a01e  mov     rax, rbx
0x18007a021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a026  mov     dword ptr [rsp+298h+ppv], eax; int
0x18007a02a  lea     r9, aSpdownloaderQu; "spDownloader->QueryInterface(IID_PPV_AR"...
0x18007a031  mov     r8, r15; char *
0x18007a034  mov     edx, 68Eh; unsigned int
0x18007a039  mov     rcx, r14; char *
0x18007a03c  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x18007a041  mov     dword ptr [rsp+298h+var_248], eax
0x18007a045  test    eax, eax
0x18007a047  js      loc_18007A0EB
0x18007a04d  xorps   xmm0, xmm0
0x18007a050  xor     eax, eax
0x18007a052  movups  xmmword ptr [rsp+298h+pvarg], xmm0
0x18007a057  mov     qword ptr [rsp+298h+pvarg+10h], rax
0x18007a05f  lea     rcx, [rsp+298h+pvarg]; pvarg
0x18007a064  call    cs:__imp_VariantInit
0x18007a06a  mov     r12d, 13h
0x18007a070  mov     word ptr [rsp+298h+pvarg], r12w
0x18007a076  mov     rax, [rsp+298h+var_230]
0x18007a07b  mov     dword ptr [rsp+298h+pvarg+8], eax
0x18007a082  mov     rcx, [rsp+298h+var_238]
0x18007a087  movups  xmm0, xmmword ptr [rsp+298h+pvarg]
0x18007a08c  movaps  [rsp+298h+var_1F8], xmm0
0x18007a094  movsd   xmm1, qword ptr [rsp+298h+pvarg+10h]
0x18007a09d  movsd   [rsp+298h+var_1E8], xmm1
0x18007a0a6  mov     rax, [rcx]
0x18007a0a9  lea     r8, [rsp+298h+var_1F8]
0x18007a0b1  mov     edx, 30006h
0x18007a0b6  mov     rax, [rax+20h]
0x18007a0ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a0bf  mov     dword ptr [rsp+298h+ppv], eax; int
0x18007a0c3  lea     r9, aSpinternalconf_0; "spInternalConfiguration->put_InternalCo"...
0x18007a0ca  mov     r8, r15; char *
0x18007a0cd  mov     edx, 695h; unsigned int
0x18007a0d2  mov     rcx, r14; char *
0x18007a0d5  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x18007a0da  mov     dword ptr [rsp+298h+var_248], eax
0x18007a0de  lea     rcx, [rsp+298h+pvarg]; pvarg
0x18007a0e3  call    cs:__imp_VariantClear
0x18007a0e9  jmp     short loc_18007A0F1
0x18007a0eb  mov     r12d, 13h
0x18007a0f1  lea     rcx, [rsp+298h+var_238]
0x18007a0f6  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007a0fb  nop
0x18007a0fc  lea     rcx, [rsp+298h+var_180]; this
0x18007a104  call    ??1SuspendImpersonationScope@@QEAA@XZ; SuspendImpersonationScope::~SuspendImpersonationScope(void)
0x18007a109  nop
0x18007a10a  jmp     short loc_18007A14A
0x18007a10c  xor     esi, esi
0x18007a10e  lea     r15, aUpdateframewor_2; "_UpdateFrameworksImpl"
0x18007a115  lea     r14, aOnecoreuapEndu_18; "onecoreuap\\enduser\\winstore\\installs"...
0x18007a11c  lea     r12d, [rsi+13h]
0x18007a120  mov     r13, [rsp+298h+var_1C8]
0x18007a128  mov     rax, [rsp+298h+var_1D8]
0x18007a130  mov     [rsp+298h+var_230], rax
0x18007a135  mov     rdx, [rsp+298h+var_1C0]
0x18007a13d  mov     [rsp+298h+var_228], rdx
0x18007a142  jmp     short loc_18007A14F
0x18007a144  mov     r12d, 13h
0x18007a14a  mov     rdx, [rsp+298h+var_228]
0x18007a14f  cmp     dword ptr [rsp+298h+var_248], esi
0x18007a153  jl      loc_18007A200
0x18007a159  mov     rcx, [rsp+298h+var_240]
0x18007a15e  mov     rax, [rcx]
0x18007a161  mov     rax, [rax+70h]
0x18007a165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a16a  mov     dword ptr [rsp+298h+ppv], eax; int
0x18007a16e  lea     r9, aSpdownloaderPu_2; "spDownloader->put_Updates(pFrameworkUpd"...
0x18007a175  mov     r8, r15; char *
0x18007a178  mov     edx, 69Dh; unsigned int
0x18007a17d  mov     rcx, r14; char *
0x18007a180  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x18007a185  mov     dword ptr [rsp+298h+var_248], eax
0x18007a189  test    eax, eax
0x18007a18b  js      short loc_18007A200
0x18007a18d  mov     [rsp+298h+var_238], rsi
0x18007a192  mov     rdi, [rsp+298h+var_240]
0x18007a197  mov     rax, [rdi]
0x18007a19a  mov     rbx, [rax+80h]
0x18007a1a1  lea     rcx, [rsp+298h+var_238]
0x18007a1a6  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007a1ab  lea     rdx, [rsp+298h+var_238]
0x18007a1b0  mov     rcx, rdi
0x18007a1b3  mov     rax, rbx
0x18007a1b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a1bb  mov     dword ptr [rsp+298h+ppv], eax; int
0x18007a1bf  lea     r9, aSpdownloaderDo; "spDownloader->Download(&spResult)"
0x18007a1c6  mov     r8, r15; char *
0x18007a1c9  mov     edx, 6A2h; unsigned int
0x18007a1ce  mov     rcx, r14; char *
0x18007a1d1  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x18007a1d6  mov     dword ptr [rsp+298h+var_248], eax
0x18007a1da  test    eax, eax
0x18007a1dc  js      short loc_18007A1F5
0x18007a1de  mov     rcx, [rsp+298h+var_238]
0x18007a1e3  mov     rax, [rcx]
0x18007a1e6  lea     rdx, [rsp+298h+var_248]
0x18007a1eb  mov     rax, [rax+38h]
0x18007a1ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a1f4  nop
0x18007a1f5  lea     rcx, [rsp+298h+var_238]
0x18007a1fa  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007a1ff  nop
0x18007a200  lea     rcx, [rsp+298h+var_240]
0x18007a205  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007a20a  mov     eax, dword ptr [rsp+298h+var_248]
0x18007a20e  jmp     short loc_18007A216
0x18007a210  mov     r12d, 13h
0x18007a216  test    eax, eax
0x18007a218  js      loc_18007A70D
0x18007a21e  mov     [rsp+298h+var_240], rsi
0x18007a223  mov     rdi, [rsp+298h+var_200]
0x18007a22b  mov     rax, [rdi]
0x18007a22e  mov     rbx, [rax+70h]
0x18007a232  lea     rcx, [rsp+298h+var_240]
0x18007a237  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007a23c  lea     rdx, [rsp+298h+var_240]
0x18007a241  mov     rcx, rdi
0x18007a244  mov     rax, rbx
0x18007a247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a24c  mov     dword ptr [rsp+298h+ppv], eax; int
0x18007a250  lea     r9, aSpsessionCreat_0; "spSession->CreateUpdateInstaller(&spIns"...
0x18007a257  mov     r8, r15; char *
0x18007a25a  mov     edx, 6ADh; unsigned int
0x18007a25f  mov     rcx, r14; char *
0x18007a262  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x18007a267  mov     dword ptr [rsp+298h+var_248], eax
0x18007a26b  test    eax, eax
0x18007a26d  js      loc_18007A5EA
0x18007a273  lea     rdx, [rsp+298h+var_D8]; char *
0x18007a27b  mov     rcx, r13; this
0x18007a27e  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x18007a283  mov     dword ptr [rsp+298h+var_1D8], 50001h
0x18007a28e  mov     byte ptr [rsp+298h+var_1D8+4], sil
0x18007a296  mov     [rsp+298h+var_1D0], 50003h
0x18007a2a1  mov     [rsp+298h+var_1CC], sil
0x18007a2a9  lea     r9, [rsp+298h+var_D8]
0x18007a2b1  mov     r8d, 2
0x18007a2b7  lea     rdx, [rsp+298h+var_1D8]
0x18007a2bf  mov     rcx, [rsp+298h+var_240]
0x18007a2c4  call    _SetInternalConfigurationFlags
0x18007a2c9  mov     dword ptr [rsp+298h+var_248], eax
0x18007a2cd  test    eax, eax
0x18007a2cf  js      loc_18007A5EA
0x18007a2d5  lea     rcx, [rsp+298h+var_180]; this
0x18007a2dd  call    ??0SuspendImpersonationScope@@QEAA@XZ; SuspendImpersonationScope::SuspendImpersonationScope(void)
  ... truncated ...
```
