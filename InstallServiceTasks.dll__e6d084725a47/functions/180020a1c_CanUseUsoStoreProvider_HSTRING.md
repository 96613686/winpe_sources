# CanUseUsoStoreProvider(HSTRING__ *)

- ea: `0x180020a1c`
- end: `0x180020ea0`
- name: `?CanUseUsoStoreProvider@@YA_NPEAUHSTRING__@@@Z`
- size: `1156`
- prototype: `bool __fastcall(HSTRING)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180016044`

## callees

- `0x180003450`
- `0x18000760c`
- `0x18000d544`
- `0x180010150`
- `0x180012118`
- `0x180013f58`
- `0x180014428`
- `0x180015338`
- `0x180015818`
- `0x1800185e4`
- `0x180019794`
- `0x18001f400`
- `0x180020a1c`
- `0x180020ea8`
- `0x180020fe4`
- `0x1800211d8`
- `0x180026b68`
- `0x180026e10`
- `0x180027178`
- `0x180028ac4`
- `0x180028b44`
- `0x180028c50`
- `0x18002ad48`
- `0x180033990`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020db6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020db6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020ac8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020ac8`

## string_xrefs

- `0x180020aad`: `ScanForUpdates`
- `0x180020adf`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x180020d7b`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x180020e0f`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x180020e63`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x180020e78`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x180020e8d`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x180020af8`: `Auto update is paused`
- `0x180020c02`: `Re-enabling auto update, as it should no longer be paused`
- `0x180020bc5`: `AutoUpdateState_Disabled`
- `0x180020ce8`: `AutoUpdateState_Enabled`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
bool __fastcall CanUseUsoStoreProvider(HSTRING a1)
{
  struct Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem *v2; // rcx
  int AutoUpdateState; // eax
  __int64 v4; // rbx
  int v5; // eax
  CorrelationVector *v6; // rax
  __int64 v7; // r8
  const unsigned __int16 *v8; // rdx
  WindowsUpdate::CommonTelemetry *v9; // rcx
  const unsigned __int16 *v10; // r8
  const unsigned __int16 *v11; // r9
  __int64 v12; // rdx
  int v13; // eax
  CorrelationVector *v14; // rax
  __int64 v15; // r8
  const unsigned __int16 *v16; // rdx
  WindowsUpdate::CommonTelemetry *v17; // rcx
  const unsigned __int16 *v18; // r8
  const unsigned __int16 *v19; // r9
  const char *v20; // r9
  bool result; // al
  int ppv; // [rsp+20h] [rbp-128h]
  int ppva; // [rsp+20h] [rbp-128h]
  LPVOID *ppvc; // [rsp+20h] [rbp-128h]
  int ppvb; // [rsp+20h] [rbp-128h]
  LPVOID *ppvd; // [rsp+20h] [rbp-128h]
  unsigned __int16 *v27; // [rsp+28h] [rbp-120h]
  unsigned __int16 *v28; // [rsp+28h] [rbp-120h]
  char *v29; // [rsp+38h] [rbp-110h]
  char *v30; // [rsp+38h] [rbp-110h]
  unsigned __int8 v31; // [rsp+40h] [rbp-108h]
  int v32; // [rsp+48h] [rbp-100h]
  char *v33; // [rsp+50h] [rbp-F8h] BYREF
  HSTRING string; // [rsp+58h] [rbp-F0h] BYREF
  __int64 v35; // [rsp+60h] [rbp-E8h] BYREF
  LPVOID v36; // [rsp+68h] [rbp-E0h] BYREF
  unsigned __int16 v37[4]; // [rsp+70h] [rbp-D8h] BYREF
  __int64 v38; // [rsp+78h] [rbp-D0h] BYREF
  unsigned __int16 v39[4]; // [rsp+80h] [rbp-C8h] BYREF
  unsigned __int16 v40[4]; // [rsp+88h] [rbp-C0h] BYREF
  HSTRING v41[20]; // [rsp+90h] [rbp-B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  try
  {
    *(_QWORD *)v37 = a1;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PauseAutoAppUpdates>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PauseAutoAppUpdates>::GetImpl'::`2'::impl)
      && IsAutoUpdatePauseFlagSetInOneSettings()
      && ShouldHonorAppUpdatePauseFlow(v2) )
    {
      LODWORD(string) = 1;
      AutoUpdateState = GetAutoUpdateState((enum WindowsUpdate::Internal::AutoUpdateState *)&string);
      if ( AutoUpdateState < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE0F,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
          (const char *)(unsigned int)AutoUpdateState,
          ppv);
      if ( !(_DWORD)string )
      {
        if ( !a1 )
        {
          string = 0;
          Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, L"ScanForUpdates", 0xEu);
          *(_QWORD *)v37 = string;
          WindowsDeleteString(string);
        }
        if ( ShouldPauseAppUpdates() )
        {
          LogSimpleMessage(
            3u,
            "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
            0xE1Bu,
            "CanUseUsoStoreProvider",
            -1,
            L"Auto update is paused",
            0,
            0);
          Microsoft::WRL::Details::Make<Windows::ApplicationModel::Store::Preview::InstallControl::AppUpdateOptions,>(&v38);
          v4 = v38;
          v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(v38 + 16) + 56LL))(v38 + 16, 0);
          if ( v5 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xE1D,
              (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
              (const char *)(unsigned int)v5,
              ppva);
          wil::ActivateInstance<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppInstallManagerInternal7>((__int64)&string);
          *(_QWORD *)v39 = v4;
          v6 = CorrelationVector::CorrelationVector((CorrelationVector *)v41);
          *(_QWORD *)v40 = CorrelationVector::hstring(v6);
          LOBYTE(v33) = 0;
          ___CallAndWaitForCompletion_UIAppInstallManagerInternal7_Internal_InstallControl_Preview_Store_ApplicationModel_Windows__EPEAUHSTRING____PEAU8_PEAUIAppUpdateOptions_34567_PEAPEAU__IAsyncOperation_PEAU__IVectorView_PEAVAppInstallItem_InstallControl_Preview_Store_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_7___Z_NPEAU8_AEAPEAU8_PEAVAppUpdateOptions_34567__wil__YA_A_PPEAUIAppInstallManagerInternal7_Internal_InstallControl_Preview_Store_ApplicationModel_Windows__P81234567_EAAJEPEAUHSTRING____1PEAUIAppUpdateOptions_34567_PEAPEAU__IAsyncOperation_PEAU__IVectorView_PEAVAppInstallItem_InstallControl_Preview_Store_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_7__Z__QEA_N__QEAPEAU8_AEAPEAU8___QEAPEAVAppUpdateOptions_34567__Z(
            (__int64)&v35,
            (__int64)string,
            v7,
            &v33,
            v40,
            v37,
            v39);
          CorrelationVector::~CorrelationVector(v41);
          WindowsUpdate::CommonTelemetry::StateTransition(
            v9,
            v8,
            v10,
            v11,
            (const unsigned __int16 *)ppvc,
            v27,
            "AutoUpdateState_Disabled",
            v29,
            v31,
            v32,
            v33);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
          wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>((__int64 *)&string);
          if ( !v4 )
            goto LABEL_16;
        }
        else
        {
          LogSimpleMessage(
            3u,
            "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
            0xE35u,
            "CanUseUsoStoreProvider",
            -1,
            L"Re-enabling auto update, as it should no longer be paused",
            0,
            0);
          SetAutoUpdateState(1);
          v35 = 0;
          GetAutoUpdatePauseEndTime(&v35);
          Microsoft::WRL::Details::Make<Windows::ApplicationModel::Store::Preview::InstallControl::AppUpdateOptions,>(&v35);
          v4 = v35;
          LOBYTE(v12) = 1;
          v13 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)(v35 + 16) + 56LL))(v35 + 16, v12);
          if ( v13 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xE3C,
              (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
              (const char *)(unsigned int)v13,
              ppvb);
          wil::ActivateInstance<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppInstallManagerInternal7>((__int64)&string);
          *(_QWORD *)v40 = v4;
          v14 = CorrelationVector::CorrelationVector((CorrelationVector *)v41);
          *(_QWORD *)v39 = CorrelationVector::hstring(v14);
          LOBYTE(v33) = 0;
          ___CallAndWaitForCompletion_UIAppInstallManagerInternal7_Internal_InstallControl_Preview_Store_ApplicationModel_Windows__EPEAUHSTRING____PEAU8_PEAUIAppUpdateOptions_34567_PEAPEAU__IAsyncOperation_PEAU__IVectorView_PEAVAppInstallItem_InstallControl_Preview_Store_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_7___Z_NPEAU8_AEAPEAU8_PEAVAppUpdateOptions_34567__wil__YA_A_PPEAUIAppInstallManagerInternal7_Internal_InstallControl_Preview_Store_ApplicationModel_Windows__P81234567_EAAJEPEAUHSTRING____1PEAUIAppUpdateOptions_34567_PEAPEAU__IAsyncOperation_PEAU__IVectorView_PEAVAppInstallItem_InstallControl_Preview_Store_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_7__Z__QEA_N__QEAPEAU8_AEAPEAU8___QEAPEAVAppUpdateOptions_34567__Z(
            (__int64)&v38,
            (__int64)string,
            v15,
            &v33,
            v39,
            v37,
            v40);
          CorrelationVector::~CorrelationVector(v41);
          WindowsUpdate::CommonTelemetry::StateTransition(
            v17,
            v16,
            v18,
            v19,
            (const unsigned __int16 *)ppvd,
            v28,
            "AutoUpdateState_Enabled",
            v30,
            v31,
            v32,
            v33);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
          wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>((__int64 *)&string);
          if ( !v4 )
            goto LABEL_16;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
LABEL_16:
        RecordSuccessUpdatesSearch();
        return 1;
      }
      v35 = 0;
      GetAutoUpdatePauseEndTime(&v35);
    }
    else
    {
      DeleteAutoUpdatePauseEndTimeKey();
    }
    if ( GetDisableUsoStoreProviderFromOneSettings() )
    {
      LogSimpleMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
        0xE69u,
        "CanUseUsoStoreProvider",
        -1,
        L"USO store provider is disabled by OneSettings.",
        0,
        0);
      result = 0;
    }
    else
    {
      v36 = 0;
      if ( CoCreateInstance(
             &GUID_46687f54_2097_4fc1_9173_3863021dc370,
             0,
             4u,
             &GUID_39cdd716_77a8_4031_93bb_bd7492d52b4d,
             &v36) >= 0
        && (LODWORD(string) = 0, (*(int (__fastcall **)(LPVOID, HSTRING *))(*(_QWORD *)v36 + 24LL))(v36, &string) >= 0)
        && (_DWORD)string )
      {
        LogSimpleMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
          0xE78u,
          "CanUseUsoStoreProvider",
          -1,
          L"USO store provider is enabled.",
          0,
          0);
        wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>((__int64 *)&v36);
        result = 1;
      }
      else
      {
        wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>((__int64 *)&v36);
        result = 0;
      }
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xE7F,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
      v20);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180020a1c  mov     [rsp+arg_8], rbx
0x180020a21  push    rdi
0x180020a22  sub     rsp, 140h
0x180020a29  mov     rax, cs:__security_cookie
0x180020a30  xor     rax, rsp
0x180020a33  mov     [rsp+148h+var_18], rax
0x180020a3b  mov     rbx, rcx
0x180020a3e  mov     qword ptr [rsp+148h+var_D8], rcx
0x180020a43  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PauseAutoAppUpdates@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PauseAutoAppUpdates@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PauseAutoAppUpdates> `wil::Feature<__WilFeatureTraits_Feature_PauseAutoAppUpdates>::GetImpl(void)'::`2'::impl
0x180020a4a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PauseAutoAppUpdates@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PauseAutoAppUpdates>::__private_IsEnabled(void)
0x180020a4f  xor     edi, edi
0x180020a51  test    al, al
0x180020a53  jz      loc_180020D42
0x180020a59  call    ?IsAutoUpdatePauseFlagSetInOneSettings@@YA_NXZ; IsAutoUpdatePauseFlagSetInOneSettings(void)
0x180020a5e  test    al, al
0x180020a60  jz      loc_180020D42
0x180020a66  call    ?ShouldHonorAppUpdatePauseFlow@@YA_NPEAUIAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Z; ShouldHonorAppUpdatePauseFlow(Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem *)
0x180020a6b  test    al, al
0x180020a6d  jz      loc_180020D42
0x180020a73  mov     dword ptr [rsp+148h+string], 1
0x180020a7b  lea     rcx, [rsp+148h+string]; enum WindowsUpdate::Internal::AutoUpdateState *
0x180020a80  call    ?GetAutoUpdateState@@YAJPEAW4AutoUpdateState@Internal@WindowsUpdate@@@Z; GetAutoUpdateState(WindowsUpdate::Internal::AutoUpdateState *)
0x180020a85  mov     rcx, [rsp+148h]; this
0x180020a8d  test    eax, eax
0x180020a8f  js      loc_180020E60
0x180020a95  cmp     dword ptr [rsp+148h+string], edi
0x180020a99  jnz     loc_180020D31
0x180020a9f  test    rbx, rbx
0x180020aa2  jnz     short loc_180020ACE
0x180020aa4  mov     [rsp+148h+string], rdi
0x180020aa9  lea     r8d, [rbx+0Eh]; unsigned int
0x180020aad  lea     rdx, aScanforupdates_2; "ScanForUpdates"
0x180020ab4  lea     rcx, [rsp+148h+string]; this
0x180020ab9  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180020abe  mov     rcx, [rsp+148h+string]; string
0x180020ac3  mov     qword ptr [rsp+148h+var_D8], rcx
0x180020ac8  call    cs:__imp_WindowsDeleteString
0x180020ace  call    ?ShouldPauseAppUpdates@@YA_NXZ; ShouldPauseAppUpdates(void)
0x180020ad3  mov     [rsp+148h+var_110], rdi; char *
0x180020ad8  lea     r9, aCanuseusostore; "CanUseUsoStoreProvider"
0x180020adf  lea     rdx, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x180020ae6  mov     ecx, 3; unsigned int
0x180020aeb  mov     [rsp+148h+var_118], rdi; char *
0x180020af0  test    al, al
0x180020af2  jz      loc_180020C02
0x180020af8  lea     rax, aAutoUpdateIsPa; "Auto update is paused"
0x180020aff  mov     [rsp+148h+var_120], rax; unsigned __int16 *
0x180020b04  mov     dword ptr [rsp+148h+ppv], 0FFFFFFFFh; int
0x180020b0c  mov     r8d, 0E1Bh; unsigned int
0x180020b12  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x180020b17  lea     rcx, [rsp+148h+var_D0]
0x180020b1c  call    ??$Make@VAppUpdateOptions@InstallControl@Preview@Store@ApplicationModel@Windows@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VAppUpdateOptions@InstallControl@Preview@Store@ApplicationModel@Windows@@@12@XZ; Microsoft::WRL::Details::Make<Windows::ApplicationModel::Store::Preview::InstallControl::AppUpdateOptions,>(void)
0x180020b21  nop
0x180020b22  mov     rbx, [rsp+148h+var_D0]
0x180020b27  lea     rcx, [rbx+10h]
0x180020b2b  mov     rax, [rcx]
0x180020b2e  xor     edx, edx
0x180020b30  mov     rax, [rax+38h]
0x180020b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b39  mov     rcx, [rsp+148h]; this
0x180020b41  test    eax, eax
0x180020b43  js      loc_180020E75
0x180020b49  lea     rcx, [rsp+148h+string]
0x180020b4e  call    ??$ActivateInstance@UIAppInstallManagerInternal7@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@wil@@YA?AV?$com_ptr_t@UIAppInstallManagerInternal7@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::ActivateInstance<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppInstallManagerInternal7>(ushort const *)
0x180020b53  nop
0x180020b54  mov     qword ptr [rsp+148h+var_C8], rbx
0x180020b5c  lea     rcx, [rsp+148h+var_B8]; this
0x180020b64  call    ??0CorrelationVector@@QEAA@XZ; CorrelationVector::CorrelationVector(void)
0x180020b69  nop
0x180020b6a  mov     rcx, rax; this
0x180020b6d  call    ?hstring@CorrelationVector@@QEAAPEAUHSTRING__@@XZ; CorrelationVector::hstring(void)
0x180020b72  mov     qword ptr [rsp+148h+var_C0], rax
0x180020b7a  mov     byte ptr [rsp+148h+var_F8], dil; char *
0x180020b7f  lea     rax, [rsp+148h+var_C8]
0x180020b87  mov     [rsp+148h+var_118], rax
0x180020b8c  lea     rax, [rsp+148h+var_D8]
0x180020b91  mov     [rsp+148h+var_120], rax; unsigned __int16 *
0x180020b96  lea     rax, [rsp+148h+var_C0]
0x180020b9e  mov     [rsp+148h+ppv], rax; unsigned __int16 *
0x180020ba3  lea     r9, [rsp+148h+var_F8]
0x180020ba8  mov     rdx, [rsp+148h+string]
0x180020bad  lea     rcx, [rsp+148h+var_E8]
0x180020bb2  call    ??$CallAndWaitForCompletion@UIAppInstallManagerInternal7@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@EPEAUHSTRING__@@PEAU8@PEAUIAppUpdateOptions@34567@PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@7@$$Z_NPEAU8@AEAPEAU8@PEAVAppUpdateOptions@34567@@wil@@YA?A_PPEAUIAppInstallManagerInternal7@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@P81234567@EAAJEPEAUHSTRING__@@1PEAUIAppUpdateOptions@34567@PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@7@@Z$$QEA_N$$QEAPEAU8@AEAPEAU8@$$QEAPEAVAppUpdateOptions@34567@@Z
0x180020bb7  nop
0x180020bb8  lea     rcx, [rsp+148h+var_B8]; this
0x180020bc0  call    ??1CorrelationVector@@QEAA@XZ; CorrelationVector::~CorrelationVector(void)
0x180020bc5  lea     rax, aAutoupdatestat_0; "AutoUpdateState_Disabled"
0x180020bcc  mov     [rsp+148h+var_118], rax; char *
0x180020bd1  call    ?StateTransition@CommonTelemetry@WindowsUpdate@@YAXPEBG0000PEBD1EJ1@Z; WindowsUpdate::CommonTelemetry::StateTransition(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,char const *,char const *,uchar,long,char const *)
0x180020bd6  nop
0x180020bd7  lea     rcx, [rsp+148h+var_E8]
0x180020bdc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020be1  nop
0x180020be2  lea     rcx, [rsp+148h+string]
0x180020be7  call    ??1?$com_ptr_t@UITaskSchedulerEx2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(void)
0x180020bec  nop
0x180020bed  test    rbx, rbx
0x180020bf0  jz      loc_180020D25
0x180020bf6  mov     rax, [rbx]
0x180020bf9  mov     rax, [rax+10h]
0x180020bfd  jmp     loc_180020D1C
0x180020c02  lea     rax, aReEnablingAuto; "Re-enabling auto update, as it should n"...
0x180020c09  mov     [rsp+148h+var_120], rax; unsigned __int16 *
0x180020c0e  mov     dword ptr [rsp+148h+ppv], 0FFFFFFFFh; int
0x180020c16  mov     r8d, 0E35h; unsigned int
0x180020c1c  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x180020c21  mov     ecx, 1
0x180020c26  call    ?SetAutoUpdateState@@YAJW4AutoUpdateState@Internal@WindowsUpdate@@@Z; SetAutoUpdateState(WindowsUpdate::Internal::AutoUpdateState)
0x180020c2b  mov     [rsp+148h+var_E8], rdi
0x180020c30  lea     rcx, [rsp+148h+var_E8]
0x180020c35  call    ?GetAutoUpdatePauseEndTime@@YA_NAEAV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; GetAutoUpdatePauseEndTime(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> &)
0x180020c3a  lea     rcx, [rsp+148h+var_E8]
0x180020c3f  call    ??$Make@VAppUpdateOptions@InstallControl@Preview@Store@ApplicationModel@Windows@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VAppUpdateOptions@InstallControl@Preview@Store@ApplicationModel@Windows@@@12@XZ; Microsoft::WRL::Details::Make<Windows::ApplicationModel::Store::Preview::InstallControl::AppUpdateOptions,>(void)
0x180020c44  nop
0x180020c45  mov     rbx, [rsp+148h+var_E8]
0x180020c4a  lea     rcx, [rbx+10h]
0x180020c4e  mov     rax, [rcx]
0x180020c51  mov     dl, 1
0x180020c53  mov     rax, [rax+38h]
0x180020c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c5c  mov     rcx, [rsp+148h]; this
0x180020c64  test    eax, eax
0x180020c66  js      loc_180020E8A
0x180020c6c  lea     rcx, [rsp+148h+string]
0x180020c71  call    ??$ActivateInstance@UIAppInstallManagerInternal7@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@wil@@YA?AV?$com_ptr_t@UIAppInstallManagerInternal7@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::ActivateInstance<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppInstallManagerInternal7>(ushort const *)
0x180020c76  nop
0x180020c77  mov     qword ptr [rsp+148h+var_C0], rbx
0x180020c7f  lea     rcx, [rsp+148h+var_B8]; this
0x180020c87  call    ??0CorrelationVector@@QEAA@XZ; CorrelationVector::CorrelationVector(void)
0x180020c8c  nop
0x180020c8d  mov     rcx, rax; this
0x180020c90  call    ?hstring@CorrelationVector@@QEAAPEAUHSTRING__@@XZ; CorrelationVector::hstring(void)
0x180020c95  mov     qword ptr [rsp+148h+var_C8], rax
0x180020c9d  mov     byte ptr [rsp+148h+var_F8], dil; char *
0x180020ca2  lea     rax, [rsp+148h+var_C0]
0x180020caa  mov     [rsp+148h+var_118], rax
0x180020caf  lea     rax, [rsp+148h+var_D8]
0x180020cb4  mov     [rsp+148h+var_120], rax; unsigned __int16 *
0x180020cb9  lea     rax, [rsp+148h+var_C8]
0x180020cc1  mov     [rsp+148h+ppv], rax; unsigned __int16 *
0x180020cc6  lea     r9, [rsp+148h+var_F8]
0x180020ccb  mov     rdx, [rsp+148h+string]
0x180020cd0  lea     rcx, [rsp+148h+var_D0]
0x180020cd5  call    ??$CallAndWaitForCompletion@UIAppInstallManagerInternal7@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@EPEAUHSTRING__@@PEAU8@PEAUIAppUpdateOptions@34567@PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@7@$$Z_NPEAU8@AEAPEAU8@PEAVAppUpdateOptions@34567@@wil@@YA?A_PPEAUIAppInstallManagerInternal7@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@P81234567@EAAJEPEAUHSTRING__@@1PEAUIAppUpdateOptions@34567@PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@7@@Z$$QEA_N$$QEAPEAU8@AEAPEAU8@$$QEAPEAVAppUpdateOptions@34567@@Z
0x180020cda  nop
0x180020cdb  lea     rcx, [rsp+148h+var_B8]; this
0x180020ce3  call    ??1CorrelationVector@@QEAA@XZ; CorrelationVector::~CorrelationVector(void)
0x180020ce8  lea     rax, aAutoupdatestat; "AutoUpdateState_Enabled"
0x180020cef  mov     [rsp+148h+var_118], rax; char *
0x180020cf4  call    ?StateTransition@CommonTelemetry@WindowsUpdate@@YAXPEBG0000PEBD1EJ1@Z; WindowsUpdate::CommonTelemetry::StateTransition(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,char const *,char const *,uchar,long,char const *)
0x180020cf9  nop
0x180020cfa  lea     rcx, [rsp+148h+var_D0]
0x180020cff  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020d04  nop
0x180020d05  lea     rcx, [rsp+148h+string]
0x180020d0a  call    ??1?$com_ptr_t@UITaskSchedulerEx2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(void)
0x180020d0f  nop
0x180020d10  test    rbx, rbx
0x180020d13  jz      short loc_180020D25
0x180020d15  mov     rdx, [rbx]
0x180020d18  mov     rax, [rdx+10h]
0x180020d1c  mov     rcx, rbx
0x180020d1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d24  nop
0x180020d25  call    ?RecordSuccessUpdatesSearch@@YAXXZ; RecordSuccessUpdatesSearch(void)
0x180020d2a  mov     al, 1
0x180020d2c  jmp     loc_180020E3F
0x180020d31  mov     [rsp+148h+var_E8], rdi
0x180020d36  lea     rcx, [rsp+148h+var_E8]
0x180020d3b  call    ?GetAutoUpdatePauseEndTime@@YA_NAEAV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; GetAutoUpdatePauseEndTime(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> &)
0x180020d40  jmp     short loc_180020D47
0x180020d42  call    ?DeleteAutoUpdatePauseEndTimeKey@@YAXXZ; DeleteAutoUpdatePauseEndTimeKey(void)
0x180020d47  call    ?GetDisableUsoStoreProviderFromOneSettings@@YA_NXZ; GetDisableUsoStoreProviderFromOneSettings(void)
0x180020d4c  test    al, al
0x180020d4e  jz      short loc_180020D93
0x180020d50  mov     [rsp+148h+var_110], rdi; unsigned __int16 *
0x180020d55  mov     [rsp+148h+var_118], rdi; char *
0x180020d5a  lea     rax, aUsoStoreProvid_0; "USO store provider is disabled by OneSe"...
0x180020d61  mov     [rsp+148h+var_120], rax; unsigned __int16 *
0x180020d66  mov     dword ptr [rsp+148h+ppv], 0FFFFFFFFh; int
0x180020d6e  lea     r9, aCanuseusostore; "CanUseUsoStoreProvider"
0x180020d75  mov     r8d, 0E69h; unsigned int
0x180020d7b  lea     rdx, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x180020d82  mov     ecx, 3; unsigned int
0x180020d87  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x180020d8c  xor     al, al
0x180020d8e  jmp     loc_180020E3F
0x180020d93  mov     [rsp+148h+var_E0], rdi
0x180020d98  lea     rax, [rsp+148h+var_E0]
0x180020d9d  mov     [rsp+148h+ppv], rax; ppv
0x180020da2  lea     r9, _GUID_39cdd716_77a8_4031_93bb_bd7492d52b4d; riid
0x180020da9  xor     edx, edx; pUnkOuter
0x180020dab  lea     r8d, [rdx+4]; dwClsContext
0x180020daf  lea     rcx, _GUID_46687f54_2097_4fc1_9173_3863021dc370; rclsid
0x180020db6  call    cs:__imp_CoCreateInstance
0x180020dbc  test    eax, eax
0x180020dbe  js      short loc_180020E2F
0x180020dc0  mov     dword ptr [rsp+148h+string], edi
0x180020dc4  mov     rcx, [rsp+148h+var_E0]
0x180020dc9  mov     rax, [rcx]
0x180020dcc  lea     rdx, [rsp+148h+string]
0x180020dd1  mov     rax, [rax+18h]
0x180020dd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020dda  test    eax, eax
0x180020ddc  js      short loc_180020E2F
0x180020dde  cmp     dword ptr [rsp+148h+string], edi
0x180020de2  jz      short loc_180020E2F
0x180020de4  mov     [rsp+148h+var_110], rdi; unsigned __int16 *
0x180020de9  mov     [rsp+148h+var_118], rdi; char *
0x180020dee  lea     rax, aUsoStoreProvid_1; "USO store provider is enabled."
0x180020df5  mov     [rsp+148h+var_120], rax; unsigned __int16 *
0x180020dfa  mov     dword ptr [rsp+148h+ppv], 0FFFFFFFFh; int
0x180020e02  lea     r9, aCanuseusostore; "CanUseUsoStoreProvider"
0x180020e09  mov     r8d, 0E78h; unsigned int
0x180020e0f  lea     rdx, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x180020e16  mov     ecx, 3; unsigned int
0x180020e1b  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x180020e20  nop
0x180020e21  lea     rcx, [rsp+148h+var_E0]
0x180020e26  call    ??1?$com_ptr_t@UITaskSchedulerEx2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(void)
0x180020e2b  mov     al, 1
0x180020e2d  jmp     short loc_180020E3F
0x180020e2f  lea     rcx, [rsp+148h+var_E0]
0x180020e34  call    ??1?$com_ptr_t@UITaskSchedulerEx2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(void)
0x180020e39  xor     al, al
0x180020e3b  jmp     short loc_180020E3F
0x180020e3d  xor     al, al
0x180020e3f  mov     rcx, [rsp+148h+var_18]
0x180020e47  xor     rcx, rsp; StackCookie
0x180020e4a  call    __security_check_cookie
0x180020e4f  mov     rbx, [rsp+148h+arg_8]
0x180020e57  add     rsp, 140h
0x180020e5e  pop     rdi
0x180020e5f  retn
0x180020e60  mov     r9d, eax; char *
0x180020e63  lea     r8, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x180020e6a  mov     edx, 0E0Fh; void *
0x180020e6f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180020e75  mov     r9d, eax; char *
0x180020e78  lea     r8, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x180020e7f  mov     edx, 0E1Dh; void *
0x180020e84  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180020e8a  mov     r9d, eax; char *
0x180020e8d  lea     r8, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x180020e94  mov     edx, 0E3Ch; void *
0x180020e99  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
