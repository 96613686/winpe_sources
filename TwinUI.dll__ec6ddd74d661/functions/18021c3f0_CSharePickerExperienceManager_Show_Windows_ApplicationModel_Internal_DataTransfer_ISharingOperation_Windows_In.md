# CSharePickerExperienceManager::Show(Windows::ApplicationModel::Internal::DataTransfer::ISharingOperation *,Windows::Internal::Shell::Share::IShareExperienceCallbacks *,HSTRING__ *)

- ea: `0x18021c3f0`
- end: `0x18021cb26`
- name: `?Show@CSharePickerExperienceManager@@UEAAJPEAUISharingOperation@DataTransfer@Internal@ApplicationModel@Windows@@PEAUIShareExperienceCallbacks@Share@Shell@46@PEAUHSTRING__@@@Z`
- size: `1846`
- prototype: `__int64 __fastcall(CSharePickerExperienceManager *__hidden this, struct Windows::ApplicationModel::Internal::DataTransfer::ISharingOperation *, struct Windows::Internal::Shell::Share::IShareExperienceCallbacks *, HSTRING)`
- caller_count: `0`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800378dc`
- `0x180064b18`
- `0x1800a5ab8`
- `0x1800ed104`
- `0x18010b88c`
- `0x180142e10`
- `0x1801674ac`
- `0x1801704b0`
- `0x180173150`
- `0x18021413c`
- `0x180214ae0`
- `0x1802155e4`
- `0x180215710`
- `0x180215770`
- `0x180215a44`
- `0x180215ae0`
- `0x180215bb4`
- `0x180218278`
- `0x1802186dc`
- `0x1802198b8`
- `0x18021c128`
- `0x18021c3f0`
- `0x18021d2e8`
- `0x18021d338`
- `0x18021d388`
- `0x18021da2c`
- `0x18021db6c`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18021c6d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18021cac4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18021c6d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18021cac4`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18021c484`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18021c5dd`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18021c74f`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18021c8a4`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18021c484`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18021c5dd`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18021c74f`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18021c8a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18021c443`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18021c4db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18021ca03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18021c443`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18021c4db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18021ca03`
- `USER32!GetPropA` at `0x18021c54e`
- `USER32!GetPropA` at `0x18021c54e`
- `api-ms-win-rtcore-ntuser-shell-l1-1-0!GetShellWindow` at `0x18021c55f`
- `api-ms-win-rtcore-ntuser-shell-l1-1-0!GetShellWindow` at `0x18021c55f`

## string_xrefs

- `0x18021c7d6`: `%S(%d) SharePicker in state=%d, returning retry to let current operation complete. ThreadId=%u`
- `0x18021c7b3`: `%S(%d) State changed to Hiding during dismiss. ThreadId=%u`
- `0x18021c791`: `%S(%d) Failed to re-acquire lock after dismiss. ThreadId=%u`
- `0x18021c661`: `%S(%d) State=Hiding. ThreadId=%u`
- `0x18021c61d`: `%S(%d) Failed to acquire frame lock. ThreadId=%u`
- `0x18021c4f6`: `%S(%d) Acquired m_shareLaunchLock. ThreadId=%u`
- `0x18021c45f`: `%S(%d) Rapid click detected - already launching, returning retry immediately. ThreadId=%u`
- `0x18021ca29`: `%S(%d) PersistentShareShow failed hr=0x%08X State=%d ThreadId=%u`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CSharePickerExperienceManager::Show(
        CSharePickerExperienceManager *this,
        struct Windows::ApplicationModel::Internal::DataTransfer::ISharingOperation *a2,
        struct Windows::Internal::Shell::Share::IShareExperienceCallbacks *a3,
        HSTRING a4)
{
  DWORD CurrentThreadId; // eax
  DWORD v8; // r14d
  int v9; // eax
  int v10; // ebx
  HWND ShellWindow; // r12
  HWND v12; // rdx
  int ShouldWindowBeAllowedToPerformPrivilegedOperation; // eax
  int v14; // r15d
  int v15; // r9d
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rax
  _QWORD *v22; // rdx
  __int64 v23; // rbx
  DWORD v24; // eax
  int v25; // eax
  FARPROC v26; // rax
  HMODULE v27; // rax
  int v28; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v29; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v30; // [rsp+38h] [rbp-C8h] BYREF
  char *v31; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v32; // [rsp+48h] [rbp-B8h] BYREF
  HWND hWnd; // [rsp+50h] [rbp-B0h] BYREF
  struct Windows::Internal::Shell::Share::IShareExperienceCallbacks *v34; // [rsp+58h] [rbp-A8h]
  HSTRING v35; // [rsp+60h] [rbp-A0h]
  _BYTE v36[64]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v37[4]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v38[32]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v35 = a4;
  v34 = a3;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IVCFTest>::GetImpl'::`2'::impl)
    && *((_DWORD *)this + 171) == 1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    NearbyShareUXTraceLogging::TraceLoggingInfo(
      "%S(%d) Rapid click detected - already launching, returning retry immediately. ThreadId=%u",
      (const wchar_t *)"CSharePickerExperienceManager::Show",
      389,
      CurrentThreadId);
    return 2147549450LL;
  }
  v32 = 0;
  v29 = ((unsigned __int64)this + 832) & -(__int64)(TryAcquireSRWLockExclusive((PSRWLOCK)this + 104) != 0);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::operator=(
    &v32,
    &v29);
  CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock((CAutoSRWExclusiveLock *)&v29);
  if ( !v32 )
    goto LABEL_18;
  v8 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IVCFTest>::GetImpl'::`2'::impl) )
  {
    v8 = GetCurrentThreadId();
    NearbyShareUXTraceLogging::TraceLoggingInfo(
      "%S(%d) Acquired m_shareLaunchLock. ThreadId=%u",
      (const wchar_t *)"CSharePickerExperienceManager::Show",
      405,
      v8);
  }
  hWnd = 0;
  v9 = (*(__int64 (__fastcall **)(struct Windows::ApplicationModel::Internal::DataTransfer::ISharingOperation *, HWND *))(*(_QWORD *)a2 + 72LL))(
         a2,
         &hWnd);
  v10 = v9;
  if ( v9 >= 0 )
  {
    ShellWindow = hWnd;
    if ( GetPropA(hWnd, "AttachToDesktop") )
    {
      ShellWindow = GetShellWindow();
    }
    else
    {
      ShouldWindowBeAllowedToPerformPrivilegedOperation = DesktopApiPolicyChecker::ShouldWindowBeAllowedToPerformPrivilegedOperation(
                                                            ShellWindow,
                                                            v12);
      v14 = ShouldWindowBeAllowedToPerformPrivilegedOperation;
      v10 = -2147019873;
      if ( ShouldWindowBeAllowedToPerformPrivilegedOperation == -2147019873 )
        goto LABEL_68;
      if ( ShouldWindowBeAllowedToPerformPrivilegedOperation < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1AA,
          (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\sharepickerexperiencemanager.cpp",
          (const char *)(unsigned int)ShouldWindowBeAllowedToPerformPrivilegedOperation,
          v28);
        v10 = v14;
        goto LABEL_68;
      }
    }
    tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>>((struct wil::details::IFailureCallback *)v36);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IVCFTest>::GetImpl'::`2'::impl) )
    {
      v30 = 0;
      v29 = ((unsigned __int64)this + 840) & -(__int64)(TryAcquireSRWLockExclusive((PSRWLOCK)this + 105) != 0);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::operator=(
        &v30,
        &v29);
      CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock((CAutoSRWExclusiveLock *)&v29);
      if ( !v30 )
      {
        NearbyShareUXTraceLogging::TraceLoggingInfo(
          "%S(%d) Failed to acquire frame lock. ThreadId=%u",
          "CSharePickerExperienceManager::Show",
          437,
          v8);
LABEL_17:
        CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock((CAutoSRWExclusiveLock *)&v30);
        tip2::test_watcher<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::~test_watcher<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>(v36);
LABEL_18:
        v10 = -2147417846;
        goto LABEL_68;
      }
      if ( CSharePickerExperienceManager::IsDestroyInProgress(this) )
      {
        NearbyShareUXTraceLogging::TraceLoggingInfo(
          "%S(%d) State=Hiding. ThreadId=%u",
          "CSharePickerExperienceManager::Show",
          442,
          v8);
        goto LABEL_17;
      }
      v15 = *((_DWORD *)this + 171);
      if ( v15 == 2 )
      {
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
          &v30,
          0);
        v10 = CSharePickerExperienceManager::TryDismissShareExperience(this);
        if ( v10 < 0 )
        {
          tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>>(&v29);
          if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_TwinuiGuidedTourAnchorValidationTest,_tip_TwinuiGuidedTourAnchorValidationTest>>::operator bool(&v29) )
          {
            tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::complete(&v29);
            ProcAddress = (FARPROC)`TestControlReporting'::`2'::s_pfnTestControlReporting;
            if ( `TestControlReporting'::`2'::s_pfnTestControlReporting
              || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
                  ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestControlReporting"),
                  (`TestControlReporting'::`2'::s_pfnTestControlReporting = (__int64)ProcAddress) != 0) )
            {
              ((void (__fastcall *)(_QWORD))ProcAddress)(0);
            }
          }
          wil::com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>(&v29);
          CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock((CAutoSRWExclusiveLock *)&v30);
          goto LABEL_67;
        }
        tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>>(&v29);
        if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_TwinuiGuidedTourAnchorValidationTest,_tip_TwinuiGuidedTourAnchorValidationTest>>::operator bool(&v29) )
        {
          *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::operator->(
                                  &v29,
                                  &v31)
                   + 272LL) = 1;
          tip2::test_data_control<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::~test_data_control<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>(&v31);
        }
        wil::com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>(&v29);
        v29 = ((unsigned __int64)this + 840) & -(__int64)(TryAcquireSRWLockExclusive((PSRWLOCK)this + 105) != 0);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::operator=(
          &v30,
          &v29);
        CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock((CAutoSRWExclusiveLock *)&v29);
        if ( !v30 )
        {
          NearbyShareUXTraceLogging::TraceLoggingInfo(
            "%S(%d) Failed to re-acquire lock after dismiss. ThreadId=%u",
            "CSharePickerExperienceManager::Show",
            474,
            v8);
          goto LABEL_17;
        }
        if ( CSharePickerExperienceManager::IsDestroyInProgress(this) )
        {
          NearbyShareUXTraceLogging::TraceLoggingInfo(
            "%S(%d) State changed to Hiding during dismiss. ThreadId=%u",
            "CSharePickerExperienceManager::Show",
            481,
            v8);
          goto LABEL_17;
        }
      }
      else
      {
        if ( (v15 & 0xFFFFFFFB) != 0 )
        {
          NearbyShareUXTraceLogging::TraceLoggingInfo(
            "%S(%d) SharePicker in state=%d, returning retry to let current operation complete. ThreadId=%u",
            (const wchar_t *)"CSharePickerExperienceManager::Show",
            488,
            v15,
            v8);
          goto LABEL_17;
        }
        tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>>(&v29);
        if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_TwinuiGuidedTourAnchorValidationTest,_tip_TwinuiGuidedTourAnchorValidationTest>>::operator bool(&v29) )
        {
          *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::operator->(
                                  &v29,
                                  &v31)
                   + 272LL) = 1;
          tip2::test_data_control<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::~test_data_control<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>(&v31);
        }
        wil::com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>(&v29);
      }
      *((_DWORD *)this + 171) = 1;
    }
    else
    {
      v10 = CSharePickerExperienceManager::TryDismissShareExperience(this);
      if ( v10 < 0 )
      {
        tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>>(&v29);
        if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_TwinuiGuidedTourAnchorValidationTest,_tip_TwinuiGuidedTourAnchorValidationTest>>::operator bool(&v29) )
        {
          tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::complete(&v29);
          v26 = (FARPROC)`TestControlReporting'::`2'::s_pfnTestControlReporting;
          if ( `TestControlReporting'::`2'::s_pfnTestControlReporting
            || (v27 = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
                v26 = GetProcAddress(v27, "TestControlReporting"),
                (`TestControlReporting'::`2'::s_pfnTestControlReporting = (__int64)v26) != 0) )
          {
            ((void (__fastcall *)(_QWORD))v26)(0);
          }
        }
        wil::com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>(&v29);
        goto LABEL_67;
      }
      tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>>(&v29);
      if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_TwinuiGuidedTourAnchorValidationTest,_tip_TwinuiGuidedTourAnchorValidationTest>>::operator bool(&v29) )
      {
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::operator->(
                                &v29,
                                &v31)
                 + 272LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::~test_data_control<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>(&v31);
      }
      wil::com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>(&v29);
      v30 = 0;
      v29 = ((unsigned __int64)this + 840) & -(__int64)(TryAcquireSRWLockExclusive((PSRWLOCK)this + 105) != 0);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::operator=(
        &v30,
        &v29);
      CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock((CAutoSRWExclusiveLock *)&v29);
      if ( !v30 )
        goto LABEL_17;
    }
    CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock((CAutoSRWExclusiveLock *)&v30);
    v31 = (char *)this + 592;
    v18 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v31);
    v19 = Microsoft::WRL::AsWeak<IFileSavePickerEventSink>(a2, v18);
    v10 = v19;
    if ( v19 < 0 )
    {
      v20 = 535;
LABEL_46:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\sharepickerexperiencemanager.cpp",
        (const char *)(unsigned int)v19,
        v28);
LABEL_67:
      tip2::test_watcher<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::~test_watcher<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>(v36);
      goto LABEL_68;
    }
    v31 = (char *)this + 600;
    v21 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v31);
    v19 = Microsoft::WRL::AsWeak<IFileSavePickerEventSink>(v34, v21);
    v10 = v19;
    if ( v19 < 0 )
    {
      v20 = 536;
      goto LABEL_46;
    }
    HSTRINGtoUTF8(v37, v35);
    v22 = v37;
    if ( v37[3] > 0xFu )
      v22 = (_QWORD *)v37[0];
    v23 = ExtendCorrelationVector(v38, v22);
    if ( (CSharePickerExperienceManager *)((char *)this + 608) != (CSharePickerExperienceManager *)v23 )
    {
      std::string::_Tidy_deallocate((char *)this + 608);
      *((_OWORD *)this + 38) = *(_OWORD *)v23;
      *((_OWORD *)this + 39) = *(_OWORD *)(v23 + 16);
      *(_QWORD *)(v23 + 16) = 0;
      *(_QWORD *)(v23 + 24) = 15;
      *(_BYTE *)v23 = 0;
    }
    std::string::_Tidy_deallocate(v38);
    *((_QWORD *)this + 12) = ShellWindow;
    *((_BYTE *)this + 120) = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IVCFTest>::GetImpl'::`2'::impl) )
    {
      v10 = CSharePickerExperienceManager::PersistentShareShow(this, a2, ShellWindow);
      if ( v10 < 0 )
      {
        if ( *((_DWORD *)this + 171) == 1 )
          *((_DWORD *)this + 171) = 4;
        v24 = GetCurrentThreadId();
        NearbyShareUXTraceLogging::TraceLoggingError(
          "%S(%d) PersistentShareShow failed hr=0x%08X State=%d ThreadId=%u",
          (const wchar_t *)"CSharePickerExperienceManager::Show",
          554,
          v10,
          *((_DWORD *)this + 171),
          v24);
        goto LABEL_60;
      }
    }
    else
    {
      v25 = CSharePickerExperienceManager::PersistentShareShow(this, a2, ShellWindow);
      v10 = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x230,
          (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\sharepickerexperiencemanager.cpp",
          (const char *)(unsigned int)v25,
          v28);
LABEL_60:
        std::string::_Tidy_deallocate(v37);
        goto LABEL_67;
      }
    }
    std::string::_Tidy_deallocate(v37);
    tip2::test_watcher<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::~test_watcher<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>(v36);
    CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock((CAutoSRWExclusiveLock *)&v32);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x199,
    (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\sharepickerexperiencemanager.cpp",
    (const char *)(unsigned int)v9,
    v28);
LABEL_68:
  CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock((CAutoSRWExclusiveLock *)&v32);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18021c3f0  push    rbp
0x18021c3f2  push    rbx
0x18021c3f3  push    rsi
0x18021c3f4  push    rdi
0x18021c3f5  push    r12
0x18021c3f7  push    r13
0x18021c3f9  push    r14
0x18021c3fb  push    r15
0x18021c3fd  lea     rbp, [rsp-8]
0x18021c402  sub     rsp, 108h
0x18021c409  mov     rax, cs:__security_cookie
0x18021c410  xor     rax, rsp
0x18021c413  mov     [rbp+40h+var_50], rax
0x18021c417  mov     [rsp+140h+var_E0], r9
0x18021c41c  mov     [rsp+140h+var_E8], r8
0x18021c421  mov     r13, rdx
0x18021c424  mov     rdi, rcx
0x18021c427  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IVCFTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IVCFTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest> `wil::Feature<__WilFeatureTraits_Feature_IVCFTest>::GetImpl(void)'::`2'::impl
0x18021c42e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IVCFTest@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest>::__private_IsEnabled(void)
0x18021c433  xor     r15d, r15d
0x18021c436  test    al, al
0x18021c438  jz      short loc_18021C475
0x18021c43a  cmp     dword ptr [rdi+2ACh], 1
0x18021c441  jnz     short loc_18021C475
0x18021c443  call    cs:__imp_GetCurrentThreadId
0x18021c44a  nop     dword ptr [rax+rax+00h]
0x18021c44f  mov     r9d, eax
0x18021c452  mov     r8d, 185h
0x18021c458  lea     rdx, aCsharepickerex_9; "CSharePickerExperienceManager::Show"
0x18021c45f  lea     rcx, aSDRapidClickDe; "%S(%d) Rapid click detected - already l"...
0x18021c466  call    ?TraceLoggingInfo@NearbyShareUXTraceLogging@@SAXPEBDZZ; NearbyShareUXTraceLogging::TraceLoggingInfo(char const *,...)
0x18021c46b  mov     eax, 8001010Ah
0x18021c470  jmp     loc_18021CB05
0x18021c475  mov     [rsp+140h+var_F8], r15
0x18021c47a  lea     rbx, [rdi+340h]
0x18021c481  mov     rcx, rbx; SRWLock
0x18021c484  call    cs:__imp_TryAcquireSRWLockExclusive
0x18021c48b  nop     dword ptr [rax+rax+00h]
0x18021c490  neg     al
0x18021c492  sbb     rcx, rcx
0x18021c495  and     rcx, rbx
0x18021c498  mov     [rsp+140h+var_110], rcx
0x18021c49d  lea     rdx, [rsp+140h+var_110]
0x18021c4a2  lea     rcx, [rsp+140h+var_F8]
0x18021c4a7  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> &&)
0x18021c4ac  lea     rcx, [rsp+140h+var_110]; this
0x18021c4b1  call    ??1CAutoSRWExclusiveLock@@QEAA@XZ; CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock(void)
0x18021c4b6  cmp     [rsp+140h+var_F8], r15
0x18021c4bb  jz      loc_18021C645
0x18021c4c1  mov     r14d, r15d
0x18021c4c4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IVCFTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IVCFTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest> `wil::Feature<__WilFeatureTraits_Feature_IVCFTest>::GetImpl(void)'::`2'::impl
0x18021c4cb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IVCFTest@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest>::__private_IsEnabled(void)
0x18021c4d0  lea     rsi, aCsharepickerex_9; "CSharePickerExperienceManager::Show"
0x18021c4d7  test    al, al
0x18021c4d9  jz      short loc_18021C502
0x18021c4db  call    cs:__imp_GetCurrentThreadId
0x18021c4e2  nop     dword ptr [rax+rax+00h]
0x18021c4e7  mov     r14d, eax
0x18021c4ea  mov     r9d, eax
0x18021c4ed  mov     r8d, 195h
0x18021c4f3  mov     rdx, rsi
0x18021c4f6  lea     rcx, aSDAcquiredMSha; "%S(%d) Acquired m_shareLaunchLock. Thre"...
0x18021c4fd  call    ?TraceLoggingInfo@NearbyShareUXTraceLogging@@SAXPEBDZZ; NearbyShareUXTraceLogging::TraceLoggingInfo(char const *,...)
0x18021c502  mov     [rsp+140h+hWnd], r15
0x18021c507  mov     rcx, [r13+0]
0x18021c50b  mov     rax, [rcx+48h]
0x18021c50f  lea     rdx, [rsp+140h+hWnd]
0x18021c514  mov     rcx, r13
0x18021c517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021c51c  mov     ebx, eax
0x18021c51e  test    eax, eax
0x18021c520  jns     short loc_18021C53F
0x18021c522  mov     rcx, [rbp+48h]; this
0x18021c526  mov     r9d, eax; char *
0x18021c529  lea     r8, aShellTwinuiExp_4; "shell\\twinui\\experiencemanagers\\lib"...
0x18021c530  mov     edx, 199h; void *
0x18021c535  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021c53a  jmp     loc_18021CAF9
0x18021c53f  mov     r12, [rsp+140h+hWnd]
0x18021c544  lea     rdx, aAttachtodeskto; "AttachToDesktop"
0x18021c54b  mov     rcx, r12; hWnd
0x18021c54e  call    cs:__imp_GetPropA
0x18021c555  nop     dword ptr [rax+rax+00h]
0x18021c55a  test    rax, rax
0x18021c55d  jz      short loc_18021C570
0x18021c55f  call    cs:__imp_GetShellWindow
0x18021c566  nop     dword ptr [rax+rax+00h]
0x18021c56b  mov     r12, rax
0x18021c56e  jmp     short loc_18021C5AF
0x18021c570  mov     rcx, r12; hWnd
0x18021c573  call    ?ShouldWindowBeAllowedToPerformPrivilegedOperation@DesktopApiPolicyChecker@@YAJPEAUHWND__@@@Z; DesktopApiPolicyChecker::ShouldWindowBeAllowedToPerformPrivilegedOperation(HWND__ *)
0x18021c578  mov     r15d, eax
0x18021c57b  mov     ebx, 8007139Fh
0x18021c580  cmp     eax, ebx
0x18021c582  jz      loc_18021CAF9
0x18021c588  test    eax, eax
0x18021c58a  jns     short loc_18021C5AC
0x18021c58c  mov     rcx, [rbp+48h]; this
0x18021c590  mov     r9d, eax; char *
0x18021c593  lea     r8, aShellTwinuiExp_4; "shell\\twinui\\experiencemanagers\\lib"...
0x18021c59a  mov     edx, 1AAh; void *
0x18021c59f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021c5a4  mov     ebx, r15d
0x18021c5a7  jmp     loc_18021CAF9
0x18021c5ac  xor     r15d, r15d
0x18021c5af  lea     rcx, [rsp+140h+var_D0]; struct wil::details::IFailureCallback *
0x18021c5b4  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18021c5b9  nop
0x18021c5ba  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IVCFTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IVCFTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest> `wil::Feature<__WilFeatureTraits_Feature_IVCFTest>::GetImpl(void)'::`2'::impl
0x18021c5c1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IVCFTest@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest>::__private_IsEnabled(void)
0x18021c5c6  test    al, al
0x18021c5c8  jz      loc_18021C83E
0x18021c5ce  mov     [rsp+140h+var_108], r15
0x18021c5d3  lea     r15, [rdi+348h]
0x18021c5da  mov     rcx, r15; SRWLock
0x18021c5dd  call    cs:__imp_TryAcquireSRWLockExclusive
0x18021c5e4  nop     dword ptr [rax+rax+00h]
0x18021c5e9  neg     al
0x18021c5eb  sbb     rcx, rcx
0x18021c5ee  and     rcx, r15
0x18021c5f1  mov     [rsp+140h+var_110], rcx
0x18021c5f6  lea     rdx, [rsp+140h+var_110]
0x18021c5fb  lea     rcx, [rsp+140h+var_108]
0x18021c600  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> &&)
0x18021c605  lea     rcx, [rsp+140h+var_110]; this
0x18021c60a  call    ??1CAutoSRWExclusiveLock@@QEAA@XZ; CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock(void)
0x18021c60f  cmp     [rsp+140h+var_108], 0
0x18021c615  jnz     short loc_18021C64F
0x18021c617  mov     r8d, 1B5h
0x18021c61d  lea     rcx, aSDFailedToAcqu; "%S(%d) Failed to acquire frame lock. Th"...
0x18021c624  mov     rdx, rsi
0x18021c627  mov     r9d, r14d
0x18021c62a  call    ?TraceLoggingInfo@NearbyShareUXTraceLogging@@SAXPEBDZZ; NearbyShareUXTraceLogging::TraceLoggingInfo(char const *,...)
0x18021c62f  nop
0x18021c630  lea     rcx, [rsp+140h+var_108]; this
0x18021c635  call    ??1CAutoSRWExclusiveLock@@QEAA@XZ; CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock(void)
0x18021c63a  nop
0x18021c63b  lea     rcx, [rsp+140h+var_D0]
0x18021c640  call    ??1?$test_watcher@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::~test_watcher<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>(void)
0x18021c645  mov     ebx, 8001010Ah
0x18021c64a  jmp     loc_18021CAF9
0x18021c64f  mov     rcx, rdi; this
0x18021c652  call    ?IsDestroyInProgress@CSharePickerExperienceManager@@AEBA_NXZ; CSharePickerExperienceManager::IsDestroyInProgress(void)
0x18021c657  test    al, al
0x18021c659  jz      short loc_18021C66A
0x18021c65b  mov     r8d, 1BAh
0x18021c661  lea     rcx, aSDStateHidingT; "%S(%d) State=Hiding. ThreadId=%u"
0x18021c668  jmp     short loc_18021C624
0x18021c66a  mov     r9d, [rdi+2ACh]
0x18021c671  cmp     r9d, 2
0x18021c675  jnz     loc_18021C7BF
0x18021c67b  xor     edx, edx
0x18021c67d  lea     rcx, [rsp+140h+var_108]
0x18021c682  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x18021c687  mov     rcx, rdi; this
0x18021c68a  call    ?TryDismissShareExperience@CSharePickerExperienceManager@@AEAAJXZ; CSharePickerExperienceManager::TryDismissShareExperience(void)
0x18021c68f  mov     ebx, eax
0x18021c691  lea     rcx, [rsp+140h+var_110]
0x18021c696  test    eax, eax
0x18021c698  jns     short loc_18021C70B
0x18021c69a  call    ??$open@V?$tip_test@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@0@XZ; tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>>(void)
0x18021c69f  lea     rcx, [rsp+140h+var_110]
0x18021c6a4  call    ??B?$tip_test@V?$merged_data@U_tip_TwinuiGuidedTourAnchorValidationTest@@U1@@details@tip2@@@tip2@@QEBA_NXZ; tip2::tip_test<tip2::details::merged_data<_tip_TwinuiGuidedTourAnchorValidationTest,_tip_TwinuiGuidedTourAnchorValidationTest>>::operator bool(void)
0x18021c6a9  test    al, al
0x18021c6ab  jz      short loc_18021C6F1
0x18021c6ad  lea     rcx, [rsp+140h+var_110]
0x18021c6b2  call    ?complete@?$tip_test@V?$merged_data@U_tip_ShareSheetResizeTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::complete(void)
0x18021c6b7  mov     rax, cs:?s_pfnTestControlReporting@?1??TestControlReporting@@9@4P6AXW4TestReportingRequest@@@ZEA; void (*`TestControlReporting'::`2'::s_pfnTestControlReporting)(TestReportingRequest)
0x18021c6be  test    rax, rax
0x18021c6c1  jnz     short loc_18021C6EA
0x18021c6c3  call    tip_details_GetKernelBaseModuleHandle
0x18021c6c8  mov     rcx, rax; hModule
0x18021c6cb  lea     rdx, aTestcontrolrep; "TestControlReporting"
0x18021c6d2  call    cs:__imp_GetProcAddress
0x18021c6d9  nop     dword ptr [rax+rax+00h]
0x18021c6de  mov     cs:?s_pfnTestControlReporting@?1??TestControlReporting@@9@4P6AXW4TestReportingRequest@@@ZEA, rax; void (*`TestControlReporting'::`2'::s_pfnTestControlReporting)(TestReportingRequest)
0x18021c6e5  test    rax, rax
0x18021c6e8  jz      short loc_18021C6F1
0x18021c6ea  xor     ecx, ecx
0x18021c6ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021c6f1  lea     rcx, [rsp+140h+var_110]
0x18021c6f6  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>(void)
0x18021c6fb  nop
0x18021c6fc  lea     rcx, [rsp+140h+var_108]; this
0x18021c701  call    ??1CAutoSRWExclusiveLock@@QEAA@XZ; CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock(void)
0x18021c706  jmp     loc_18021CAEE
0x18021c70b  call    ??$open@V?$tip_test@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@0@XZ; tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>>(void)
0x18021c710  lea     rcx, [rsp+140h+var_110]
0x18021c715  call    ??B?$tip_test@V?$merged_data@U_tip_TwinuiGuidedTourAnchorValidationTest@@U1@@details@tip2@@@tip2@@QEBA_NXZ; tip2::tip_test<tip2::details::merged_data<_tip_TwinuiGuidedTourAnchorValidationTest,_tip_TwinuiGuidedTourAnchorValidationTest>>::operator bool(void)
0x18021c71a  test    al, al
0x18021c71c  jz      short loc_18021C741
0x18021c71e  lea     rdx, [rsp+140h+var_100]
0x18021c723  lea     rcx, [rsp+140h+var_110]
0x18021c728  call    ??C?$tip_test@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::operator->(void)
0x18021c72d  mov     rcx, [rax]
0x18021c730  mov     byte ptr [rcx+110h], 1
0x18021c737  lea     rcx, [rsp+140h+var_100]
0x18021c73c  call    ??1?$test_data_control@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::~test_data_control<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>(void)
0x18021c741  lea     rcx, [rsp+140h+var_110]
0x18021c746  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>(void)
0x18021c74b  nop
0x18021c74c  mov     rcx, r15; SRWLock
0x18021c74f  call    cs:__imp_TryAcquireSRWLockExclusive
0x18021c756  nop     dword ptr [rax+rax+00h]
0x18021c75b  neg     al
0x18021c75d  sbb     rcx, rcx
0x18021c760  and     rcx, r15
0x18021c763  mov     [rsp+140h+var_110], rcx
0x18021c768  lea     rdx, [rsp+140h+var_110]
0x18021c76d  lea     rcx, [rsp+140h+var_108]
0x18021c772  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> &&)
0x18021c777  lea     rcx, [rsp+140h+var_110]; this
0x18021c77c  call    ??1CAutoSRWExclusiveLock@@QEAA@XZ; CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock(void)
0x18021c781  xor     r15d, r15d
0x18021c784  cmp     [rsp+140h+var_108], r15
0x18021c789  jnz     short loc_18021C79D
0x18021c78b  mov     r8d, 1DAh
0x18021c791  lea     rcx, aSDFailedToReAc; "%S(%d) Failed to re-acquire lock after "...
0x18021c798  jmp     loc_18021C624
0x18021c79d  mov     rcx, rdi; this
0x18021c7a0  call    ?IsDestroyInProgress@CSharePickerExperienceManager@@AEBA_NXZ; CSharePickerExperienceManager::IsDestroyInProgress(void)
0x18021c7a5  test    al, al
0x18021c7a7  jz      loc_18021C82F
0x18021c7ad  mov     r8d, 1E1h
0x18021c7b3  lea     rcx, aSDStateChanged; "%S(%d) State changed to Hiding during d"...
0x18021c7ba  jmp     loc_18021C624
0x18021c7bf  test    r9d, 0FFFFFFFBh
0x18021c7c6  jz      short loc_18021C7E7
0x18021c7c8  mov     [rsp+140h+var_120], r14d
0x18021c7cd  mov     r8d, 1E8h
0x18021c7d3  mov     rdx, rsi
0x18021c7d6  lea     rcx, aSDSharepickerI; "%S(%d) SharePicker in state=%d, returni"...
0x18021c7dd  call    ?TraceLoggingInfo@NearbyShareUXTraceLogging@@SAXPEBDZZ; NearbyShareUXTraceLogging::TraceLoggingInfo(char const *,...)
0x18021c7e2  jmp     loc_18021C630
0x18021c7e7  lea     rcx, [rsp+140h+var_110]
0x18021c7ec  call    ??$open@V?$tip_test@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@0@XZ; tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>>(void)
0x18021c7f1  lea     rcx, [rsp+140h+var_110]
0x18021c7f6  call    ??B?$tip_test@V?$merged_data@U_tip_TwinuiGuidedTourAnchorValidationTest@@U1@@details@tip2@@@tip2@@QEBA_NXZ; tip2::tip_test<tip2::details::merged_data<_tip_TwinuiGuidedTourAnchorValidationTest,_tip_TwinuiGuidedTourAnchorValidationTest>>::operator bool(void)
0x18021c7fb  xor     r15d, r15d
0x18021c7fe  test    al, al
0x18021c800  jz      short loc_18021C825
0x18021c802  lea     rdx, [rsp+140h+var_100]
0x18021c807  lea     rcx, [rsp+140h+var_110]
0x18021c80c  call    ??C?$tip_test@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::operator->(void)
0x18021c811  mov     rcx, [rax]
0x18021c814  mov     byte ptr [rcx+110h], 1
0x18021c81b  lea     rcx, [rsp+140h+var_100]
0x18021c820  call    ??1?$test_data_control@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::~test_data_control<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>(void)
0x18021c825  lea     rcx, [rsp+140h+var_110]
0x18021c82a  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>(void)
0x18021c82f  mov     dword ptr [rdi+2ACh], 1
0x18021c839  jmp     loc_18021C8E1
0x18021c83e  mov     rcx, rdi; this
0x18021c841  call    ?TryDismissShareExperience@CSharePickerExperienceManager@@AEAAJXZ; CSharePickerExperienceManager::TryDismissShareExperience(void)
0x18021c846  mov     ebx, eax
0x18021c848  lea     rcx, [rsp+140h+var_110]
0x18021c84d  test    eax, eax
0x18021c84f  js      loc_18021CA8C
0x18021c855  call    ??$open@V?$tip_test@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@0@XZ; tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>>(void)
0x18021c85a  lea     rcx, [rsp+140h+var_110]
0x18021c85f  call    ??B?$tip_test@V?$merged_data@U_tip_TwinuiGuidedTourAnchorValidationTest@@U1@@details@tip2@@@tip2@@QEBA_NXZ; tip2::tip_test<tip2::details::merged_data<_tip_TwinuiGuidedTourAnchorValidationTest,_tip_TwinuiGuidedTourAnchorValidationTest>>::operator bool(void)
0x18021c864  test    al, al
0x18021c866  jz      short loc_18021C88B
0x18021c868  lea     rdx, [rsp+140h+var_100]
0x18021c86d  lea     rcx, [rsp+140h+var_110]
0x18021c872  call    ??C?$tip_test@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::operator->(void)
0x18021c877  mov     rcx, [rax]
0x18021c87a  mov     byte ptr [rcx+110h], 1
0x18021c881  lea     rcx, [rsp+140h+var_100]
0x18021c886  call    ??1?$test_data_control@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::~test_data_control<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>(void)
0x18021c88b  lea     rcx, [rsp+140h+var_110]
0x18021c890  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>(void)
0x18021c895  mov     [rsp+140h+var_108], r15
0x18021c89a  lea     rbx, [rdi+348h]
0x18021c8a1  mov     rcx, rbx; SRWLock
0x18021c8a4  call    cs:__imp_TryAcquireSRWLockExclusive
0x18021c8ab  nop     dword ptr [rax+rax+00h]
0x18021c8b0  neg     al
0x18021c8b2  sbb     rcx, rcx
0x18021c8b5  and     rcx, rbx
0x18021c8b8  mov     [rsp+140h+var_110], rcx
0x18021c8bd  lea     rdx, [rsp+140h+var_110]
0x18021c8c2  lea     rcx, [rsp+140h+var_108]
0x18021c8c7  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> &&)
0x18021c8cc  lea     rcx, [rsp+140h+var_110]; this
0x18021c8d1  call    ??1CAutoSRWExclusiveLock@@QEAA@XZ; CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock(void)
0x18021c8d6  cmp     [rsp+140h+var_108], r15
0x18021c8db  jz      loc_18021C630
0x18021c8e1  lea     rcx, [rsp+140h+var_108]; this
0x18021c8e6  call    ??1CAutoSRWExclusiveLock@@QEAA@XZ; CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock(void)
0x18021c8eb  lea     rax, [rdi+250h]
0x18021c8f2  mov     [rsp+140h+var_100], rax
0x18021c8f7  lea     rcx, [rsp+140h+var_100]
0x18021c8fc  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18021c901  mov     rdx, rax
0x18021c904  mov     rcx, r13
0x18021c907  call    ??$AsWeak@UIFileSavePickerEventSink@@@WRL@Microsoft@@YAJPEAUIFileSavePickerEventSink@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<IFileSavePickerEventSink>(IFileSavePickerEventSink *,Microsoft::WRL::WeakRef *)
0x18021c90c  mov     ebx, eax
0x18021c90e  test    eax, eax
0x18021c910  jns     short loc_18021C92F
  ... truncated ...
```
