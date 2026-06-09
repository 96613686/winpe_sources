# InstallModels(void)

- ea: `0x18001871c`
- end: `0x180018b49`
- name: `?InstallModels@@YAXXZ`
- size: `1069`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001c380`

## callees

- `0x18000c1d0`
- `0x18000d6b0`
- `0x18000d770`
- `0x18000ef74`
- `0x18000f0c0`
- `0x18000f910`
- `0x18000f9a8`
- `0x1800116b4`
- `0x1800117a4`
- `0x180012514`
- `0x1800125b0`
- `0x1800127e8`
- `0x180012880`
- `0x180012e64`
- `0x180012f04`
- `0x180013334`
- `0x1800139b0`
- `0x18001871c`
- `0x180019368`
- `0x1800193e0`
- `0x18001962c`
- `0x18001bd60`
- `0x18001d2e8`
- `0x18001d310`
- `0x18001d718`
- `0x18001ecd8`
- `0x1800211c4`
- `0x180024010`

## pseudocode

```c
void InstallModels(void)
{
  __int64 v0; // rcx
  __int64 AvailableAsync; // rax
  wil *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rax
  unsigned int v5; // eax
  enum AsyncStatus v6; // edx
  unsigned int v7; // eax
  wil *v8; // rcx
  _QWORD v9[2]; // [rsp+20h] [rbp-B8h] BYREF
  int v10; // [rsp+30h] [rbp-A8h] BYREF
  __int128 v11; // [rsp+38h] [rbp-A0h]
  _BYTE v12[64]; // [rsp+50h] [rbp-88h] BYREF
  _BYTE v13[72]; // [rsp+90h] [rbp-48h] BYREF
  int v14; // [rsp+E0h] [rbp+8h] BYREF
  __int64 *v15; // [rsp+E8h] [rbp+10h] BYREF
  __int64 v16; // [rsp+F0h] [rbp+18h] BYREF
  __int64 v17; // [rsp+F8h] [rbp+20h] BYREF

  SettingsDownloadTelemetry::ModelInstallation_Started();
  v17 = 0;
  *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::operator->(
                           &v17,
                           &v14)
            + 276LL) = 0;
  tip2::test_data_control<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>(&v14);
  tip2::tip_test<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::start_and_watch_errors(
    &v17,
    v13);
  try
  {
    if ( !(unsigned __int8)winrt::impl::call_factory_cast<bool (*)(winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics const &),winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel,winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics,_lambda_92b19b62d8502e19e704d065a5482035_>() )
    {
      AvailableAsync = winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel::MakeAvailableAsync();
      winrt::impl::consume_Windows_Foundation_IAsyncOperationWithProgress<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::get(
        AvailableAsync,
        v9);
      winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(&v15);
      if ( (unsigned int)winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::Status(v9) == 1 )
      {
        v14 = 0;
        SettingsDownloadTelemetry::ModelInstallation_Succeeded<enum ModelName>(&v14);
      }
      else
      {
        v14 = *(_DWORD *)winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::Error(
                           v9,
                           &v14);
        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::operator->(
                                 &v17,
                                 &v15)
                  + 272LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>(&v15);
        LODWORD(v15) = 0;
        SettingsDownloadTelemetry::ModelInstallation_Failed<enum ModelName,long &>(&v15, &v14);
      }
      winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(v9);
    }
    v15 = &qword_18002ED68;
    _InterlockedIncrement64(&qword_18002ED68);
    if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel,winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics> )
    {
      _lambda_09a2d7c47ef10c93b6f90465b8259541_::operator()(
        v0,
        &v14,
        &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel,winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics>);
      _InterlockedDecrement64(&qword_18002ED68);
    }
    else
    {
      _InterlockedDecrement64(&qword_18002ED68);
      v15 = (__int64 *)_lambda_09a2d7c47ef10c93b6f90465b8259541_::_lambda_invoker_cdecl_;
      winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel,winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics>::call<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> (*)(winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics const &)>(
        v0,
        &v14,
        &v15);
    }
    winrt::impl::wait_get<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::AI::Generative::LanguageModel>>((winrt *)v9);
    winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(v9);
    winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(&v14);
  }
  catch ( ... )
  {
    v14 = wil::ResultFromCaughtException(v2);
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::operator->(
                             &v17,
                             &v15)
              + 272LL) = 2;
    tip2::test_data_control<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>(&v15);
    LODWORD(v15) = 0;
    SettingsDownloadTelemetry::ModelInstallation_Failed<enum ModelName,long const &>(&v15, &v14);
  }
  if ( v17 )
    tip2::details::shared_data<0,0,0>::complete_without_lock(v17 + 8);
  v16 = 0;
  *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::operator->(
                           &v16,
                           &v14)
            + 276LL) = 1;
  tip2::test_data_control<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>(&v14);
  tip2::tip_test<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::start_and_watch_errors(
    &v16,
    v12);
  try
  {
    if ( !(unsigned __int8)winrt::impl::call_factory_cast<bool (*)(winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics const &),winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics,_lambda_8a0cfe8d315f60f66c33c2531ac951bf_>() )
    {
      v4 = winrt::Microsoft::Windows::SemanticSearch::QueryBlockList::MakeAvailableAsync();
      winrt::impl::consume_Windows_Foundation_IAsyncOperationWithProgress<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::get(
        v4,
        v9);
      winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(&v15);
      if ( (unsigned int)winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::Status(v9) == 1 )
      {
        v14 = 1;
        SettingsDownloadTelemetry::ModelInstallation_Succeeded<enum ModelName>(&v14);
      }
      else
      {
        v14 = *(_DWORD *)winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::Error(
                           v9,
                           &v14);
        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::operator->(
                                 &v16,
                                 &v15)
                  + 272LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>(&v15);
        LODWORD(v15) = 1;
        SettingsDownloadTelemetry::ModelInstallation_Failed<enum ModelName,long &>(&v15, &v14);
      }
      winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(v9);
    }
    v14 = 8;
    v15 = (__int64 *)&v14;
    v9[1] = &qword_18002ED28;
    _InterlockedIncrement64(&qword_18002ED28);
    if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics> )
    {
      _lambda_f0867a2080869fb329157b990d30dd01_::operator()(
        &v15,
        v9,
        &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics>);
      _InterlockedDecrement64(&qword_18002ED28);
    }
    else
    {
      _InterlockedDecrement64(&qword_18002ED28);
      winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics>::call<_lambda_f0867a2080869fb329157b990d30dd01_ &>(
        v3,
        v9,
        &v15);
    }
    v5 = winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>>::Status(v9);
    if ( !v5 )
      v5 = winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncAction>(v9);
    winrt::impl::check_status_canceled((winrt::impl *)v5, v6);
    v10 = 0;
    v11 = 0;
    v7 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v9[0] + 64LL))(v9[0]);
    winrt::check_hresult(&v15, v7, &v10);
    winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(v9);
  }
  catch ( ... )
  {
    v14 = wil::ResultFromCaughtException(v8);
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::operator->(
                             &v16,
                             &v15)
              + 272LL) = 2;
    tip2::test_data_control<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>(&v15);
    LODWORD(v15) = 1;
    SettingsDownloadTelemetry::ModelInstallation_Failed<enum ModelName,long const &>(&v15, &v14);
  }
  if ( v16 )
    tip2::details::shared_data<0,0,0>::complete_without_lock(v16 + 8);
  tip2::test_watcher<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::~test_watcher<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>(v12);
  wil::com_ptr_t<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>,wil::err_returncode_policy>(&v16);
  tip2::test_watcher<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::~test_watcher<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>(v13);
  wil::com_ptr_t<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>,wil::err_returncode_policy>(&v17);
}

```

## disassembly

```asm
0x18001871c  sub     rsp, 0D8h
0x180018723  call    ?ModelInstallation_Started@SettingsDownloadTelemetry@@SAXXZ; SettingsDownloadTelemetry::ModelInstallation_Started(void)
0x180018728  mov     [rsp+0D8h+arg_18], 0
0x180018734  lea     rdx, [rsp+0D8h+arg_0]
0x18001873c  lea     rcx, [rsp+0D8h+arg_18]
0x180018744  call    ??C?$tip_test@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::operator->(void)
0x180018749  mov     rcx, [rax]
0x18001874c  mov     dword ptr [rcx+114h], 0
0x180018756  lea     rcx, [rsp+0D8h+arg_0]
0x18001875e  call    ??1?$test_data_control@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>(void)
0x180018763  lea     rdx, [rsp+0D8h+var_48]
0x18001876b  lea     rcx, [rsp+0D8h+arg_18]
0x180018773  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::start_and_watch_errors(void)
0x180018778  nop
0x180018779  call    ??$call_factory_cast@P6A_NAEBUISettingsModelStatics@Internal@Generative@AI@Windows@Microsoft@winrt@@@ZUSettingsModel@234567@U1234567@V_lambda_92b19b62d8502e19e704d065a5482035_@@@impl@winrt@@YA?A_P$$QEAV_lambda_92b19b62d8502e19e704d065a5482035_@@@Z
0x18001877e  test    al, al
0x180018780  jnz     loc_18001884D
0x180018786  lea     rcx, [rsp+0D8h+arg_8]
0x18001878e  call    ?MakeAvailableAsync@SettingsModel@Internal@Generative@AI@Windows@Microsoft@winrt@@SA@XZ; winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel::MakeAvailableAsync(void)
0x180018793  nop
0x180018794  lea     rdx, [rsp+0D8h+var_B8]
0x180018799  mov     rcx, rax
0x18001879c  call    ?get@?$consume_Windows_Foundation_IAsyncOperationWithProgress@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@UPackageDeploymentResult@Deployment@Management@3Microsoft@4@UPackageDeploymentProgress@67384@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperationWithProgress<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::get(void)
0x1800187a1  nop
0x1800187a2  lea     rcx, [rsp+0D8h+arg_8]
0x1800187aa  call    ??1?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(void)
0x1800187af  lea     rcx, [rsp+0D8h+var_B8]
0x1800187b4  call    ?Status@?$consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult@UIPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::Status(void)
0x1800187b9  cmp     eax, 1
0x1800187bc  jz      short loc_18001882A
0x1800187be  lea     rdx, [rsp+0D8h+arg_0]
0x1800187c6  lea     rcx, [rsp+0D8h+var_B8]
0x1800187cb  call    ?Error@?$consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult@UIPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::Error(void)
0x1800187d0  mov     eax, [rax]
0x1800187d2  mov     [rsp+0D8h+arg_0], eax
0x1800187d9  lea     rdx, [rsp+0D8h+arg_8]
0x1800187e1  lea     rcx, [rsp+0D8h+arg_18]
0x1800187e9  call    ??C?$tip_test@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::operator->(void)
0x1800187ee  mov     rcx, [rax]
0x1800187f1  mov     dword ptr [rcx+110h], 1
0x1800187fb  lea     rcx, [rsp+0D8h+arg_8]
0x180018803  call    ??1?$test_data_control@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>(void)
0x180018808  mov     dword ptr [rsp+0D8h+arg_8], 0
0x180018813  lea     rdx, [rsp+0D8h+arg_0]
0x18001881b  lea     rcx, [rsp+0D8h+arg_8]
0x180018823  call    ??$ModelInstallation_Failed@W4ModelName@@AEAJ@SettingsDownloadTelemetry@@SAX$$QEAW4ModelName@@AEAJ@Z; SettingsDownloadTelemetry::ModelInstallation_Failed<ModelName,long &>(ModelName &&,long &)
0x180018828  jmp     short loc_180018843
0x18001882a  mov     [rsp+0D8h+arg_0], 0
0x180018835  lea     rcx, [rsp+0D8h+arg_0]
0x18001883d  call    ??$ModelInstallation_Succeeded@W4ModelName@@@SettingsDownloadTelemetry@@SAX$$QEAW4ModelName@@@Z; SettingsDownloadTelemetry::ModelInstallation_Succeeded<ModelName>(ModelName &&)
0x180018842  nop
0x180018843  lea     rcx, [rsp+0D8h+var_B8]
0x180018848  call    ??1?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(void)
0x18001884d  lea     rax, qword_18002ED68
0x180018854  mov     [rsp+0D8h+arg_8], rax
0x18001885c  lock inc cs:qword_18002ED68
0x180018864  cmp     cs:??$factory_cache_entry_v@USettingsModel@Internal@Generative@AI@Windows@Microsoft@winrt@@UISettingsModelStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USettingsModel@Internal@Generative@AI@Windows@Microsoft@winrt@@UISettingsModelStatics@234567@@12@A, 0; factory_cache_entry<winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel,winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel,winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel,winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics>
0x18001886c  jz      short loc_18001888D
0x18001886e  lea     r8, ??$factory_cache_entry_v@USettingsModel@Internal@Generative@AI@Windows@Microsoft@winrt@@UISettingsModelStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USettingsModel@Internal@Generative@AI@Windows@Microsoft@winrt@@UISettingsModelStatics@234567@@12@A; factory_cache_entry<winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel,winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel,winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel,winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics>
0x180018875  lea     rdx, [rsp+0D8h+arg_0]
0x18001887d  call    ??R_lambda_09a2d7c47ef10c93b6f90465b8259541_@@QEBA@AEBUISettingsModelStatics@Internal@Generative@AI@Windows@Microsoft@winrt@@@Z; _lambda_09a2d7c47ef10c93b6f90465b8259541_::operator()(winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics const &)
0x180018882  nop
0x180018883  lock dec cs:qword_18002ED68
0x18001888b  jmp     short loc_1800188BA
0x18001888d  lock dec cs:qword_18002ED68
0x180018895  lea     rax, ?_lambda_invoker_cdecl_@_lambda_09a2d7c47ef10c93b6f90465b8259541_@@CA@AEBUISettingsModelStatics@Internal@Generative@AI@Windows@Microsoft@winrt@@@Z; _lambda_09a2d7c47ef10c93b6f90465b8259541_::_lambda_invoker_cdecl_(winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics const &)
0x18001889c  mov     [rsp+0D8h+arg_8], rax
0x1800188a4  lea     r8, [rsp+0D8h+arg_8]
0x1800188ac  lea     rdx, [rsp+0D8h+arg_0]
0x1800188b4  call    ??$call@P6A?AU?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@AEBUISettingsModelStatics@Internal@Generative@AI@3Microsoft@4@@Z@?$factory_cache_entry@USettingsModel@Internal@Generative@AI@Windows@Microsoft@winrt@@UISettingsModelStatics@234567@@impl@winrt@@QEAA?A_P$$QEAP6A?AU?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@2@AEBUISettingsModelStatics@Internal@Generative@AI@5Microsoft@2@@Z@Z
0x1800188b9  nop
0x1800188ba  lea     rdx, [rsp+0D8h+arg_0]
0x1800188c2  lea     rcx, [rsp+0D8h+var_B8]; this
0x1800188c7  call    ??$wait_get@U?$IAsyncOperation@ULanguageModel@Generative@AI@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@ULanguageModel@Generative@AI@Windows@Microsoft@winrt@@@Foundation@Windows@1@@Z
0x1800188cc  lea     rcx, [rsp+0D8h+var_B8]
0x1800188d1  call    ??1?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(void)
0x1800188d6  nop
0x1800188d7  lea     rcx, [rsp+0D8h+arg_0]
0x1800188df  call    ??1?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(void)
0x1800188e4  nop
0x1800188e5  mov     rcx, [rsp+0D8h+arg_18]
0x1800188ed  test    rcx, rcx
0x1800188f0  jz      short loc_1800188FB
0x1800188f2  add     rcx, 8
0x1800188f6  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x1800188fb  mov     [rsp+0D8h+arg_10], 0
0x180018907  lea     rdx, [rsp+0D8h+arg_0]
0x18001890f  lea     rcx, [rsp+0D8h+arg_10]
0x180018917  call    ??C?$tip_test@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::operator->(void)
0x18001891c  mov     rcx, [rax]
0x18001891f  mov     dword ptr [rcx+114h], 1
0x180018929  lea     rcx, [rsp+0D8h+arg_0]
0x180018931  call    ??1?$test_data_control@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>(void)
0x180018936  lea     rdx, [rsp+0D8h+var_88]
0x18001893b  lea     rcx, [rsp+0D8h+arg_10]
0x180018943  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::start_and_watch_errors(void)
0x180018948  nop
0x180018949  call    ??$call_factory_cast@P6A_NAEBUIQueryBlockListStatics@SemanticSearch@Windows@Microsoft@winrt@@@ZUQueryBlockList@2345@U12345@V_lambda_8a0cfe8d315f60f66c33c2531ac951bf_@@@impl@winrt@@YA?A_P$$QEAV_lambda_8a0cfe8d315f60f66c33c2531ac951bf_@@@Z
0x18001894e  test    al, al
0x180018950  jnz     loc_180018A1D
0x180018956  lea     rcx, [rsp+0D8h+arg_8]
0x18001895e  call    ?MakeAvailableAsync@QueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@SA@XZ; winrt::Microsoft::Windows::SemanticSearch::QueryBlockList::MakeAvailableAsync(void)
0x180018963  nop
0x180018964  lea     rdx, [rsp+0D8h+var_B8]
0x180018969  mov     rcx, rax
0x18001896c  call    ?get@?$consume_Windows_Foundation_IAsyncOperationWithProgress@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@UPackageDeploymentResult@Deployment@Management@3Microsoft@4@UPackageDeploymentProgress@67384@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperationWithProgress<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::get(void)
0x180018971  nop
0x180018972  lea     rcx, [rsp+0D8h+arg_8]
0x18001897a  call    ??1?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(void)
0x18001897f  lea     rcx, [rsp+0D8h+var_B8]
0x180018984  call    ?Status@?$consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult@UIPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::Status(void)
0x180018989  cmp     eax, 1
0x18001898c  jz      short loc_1800189FA
0x18001898e  lea     rdx, [rsp+0D8h+arg_0]
0x180018996  lea     rcx, [rsp+0D8h+var_B8]
0x18001899b  call    ?Error@?$consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult@UIPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::Error(void)
0x1800189a0  mov     eax, [rax]
0x1800189a2  mov     [rsp+0D8h+arg_0], eax
0x1800189a9  lea     rdx, [rsp+0D8h+arg_8]
0x1800189b1  lea     rcx, [rsp+0D8h+arg_10]
0x1800189b9  call    ??C?$tip_test@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::operator->(void)
0x1800189be  mov     rcx, [rax]
0x1800189c1  mov     dword ptr [rcx+110h], 1
0x1800189cb  lea     rcx, [rsp+0D8h+arg_8]
0x1800189d3  call    ??1?$test_data_control@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>(void)
0x1800189d8  mov     dword ptr [rsp+0D8h+arg_8], 1
0x1800189e3  lea     rdx, [rsp+0D8h+arg_0]
0x1800189eb  lea     rcx, [rsp+0D8h+arg_8]
0x1800189f3  call    ??$ModelInstallation_Failed@W4ModelName@@AEAJ@SettingsDownloadTelemetry@@SAX$$QEAW4ModelName@@AEAJ@Z; SettingsDownloadTelemetry::ModelInstallation_Failed<ModelName,long &>(ModelName &&,long &)
0x1800189f8  jmp     short loc_180018A13
0x1800189fa  mov     [rsp+0D8h+arg_0], 1
0x180018a05  lea     rcx, [rsp+0D8h+arg_0]
0x180018a0d  call    ??$ModelInstallation_Succeeded@W4ModelName@@@SettingsDownloadTelemetry@@SAX$$QEAW4ModelName@@@Z; SettingsDownloadTelemetry::ModelInstallation_Succeeded<ModelName>(ModelName &&)
0x180018a12  nop
0x180018a13  lea     rcx, [rsp+0D8h+var_B8]
0x180018a18  call    ??1?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(void)
0x180018a1d  mov     [rsp+0D8h+arg_0], 8
0x180018a28  lea     rax, [rsp+0D8h+arg_0]
0x180018a30  mov     [rsp+0D8h+arg_8], rax
0x180018a38  lea     rax, qword_18002ED28
0x180018a3f  mov     [rsp+0D8h+var_B0], rax
0x180018a44  lock inc cs:qword_18002ED28
0x180018a4c  cmp     cs:??$factory_cache_entry_v@UCacheManagerInternal@Internal@Workloads@Windows@Microsoft@winrt@@UICacheManagerInternalStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCacheManagerInternal@Internal@Workloads@Windows@Microsoft@winrt@@UICacheManagerInternalStatics@23456@@12@A, 0; factory_cache_entry<winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics>
0x180018a54  jz      short loc_180018A7A
0x180018a56  lea     r8, ??$factory_cache_entry_v@UCacheManagerInternal@Internal@Workloads@Windows@Microsoft@winrt@@UICacheManagerInternalStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCacheManagerInternal@Internal@Workloads@Windows@Microsoft@winrt@@UICacheManagerInternalStatics@23456@@12@A; factory_cache_entry<winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics>
0x180018a5d  lea     rdx, [rsp+0D8h+var_B8]
0x180018a62  lea     rcx, [rsp+0D8h+arg_8]
0x180018a6a  call    ??R_lambda_f0867a2080869fb329157b990d30dd01_@@QEBA@AEBUICacheManagerInternalStatics@Internal@Workloads@Windows@Microsoft@winrt@@@Z; _lambda_f0867a2080869fb329157b990d30dd01_::operator()(winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics const &)
0x180018a6f  nop
0x180018a70  lock dec cs:qword_18002ED28
0x180018a78  jmp     short loc_180018A95
0x180018a7a  lock dec cs:qword_18002ED28
0x180018a82  lea     r8, [rsp+0D8h+arg_8]
0x180018a8a  lea     rdx, [rsp+0D8h+var_B8]
0x180018a8f  call    ??$call@AEAV_lambda_f0867a2080869fb329157b990d30dd01_@@@?$factory_cache_entry@UCacheManagerInternal@Internal@Workloads@Windows@Microsoft@winrt@@UICacheManagerInternalStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_f0867a2080869fb329157b990d30dd01_@@@Z
0x180018a94  nop
0x180018a95  lea     rcx, [rsp+0D8h+var_B8]
0x180018a9a  call    ?Status@?$consume_Windows_Foundation_IAsyncInfo@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>>::Status(void)
0x180018a9f  test    eax, eax
0x180018aa1  jnz     short loc_180018AAD
0x180018aa3  lea     rcx, [rsp+0D8h+var_B8]
0x180018aa8  call    ??$wait_for_completed@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBUIAsyncAction@Foundation@Windows@1@I@Z
0x180018aad  mov     ecx, eax; this
0x180018aaf  call    ?check_status_canceled@impl@winrt@@YAXW4AsyncStatus@Foundation@Windows@2@@Z; winrt::impl::check_status_canceled(winrt::Windows::Foundation::AsyncStatus)
0x180018ab4  mov     rcx, [rsp+0D8h+var_B8]
0x180018ab9  mov     [rsp+0D8h+var_A8], 0
0x180018ac1  xorps   xmm0, xmm0
0x180018ac4  movdqu  [rsp+0D8h+var_A0], xmm0
0x180018aca  mov     rax, [rcx]
0x180018acd  mov     rax, [rax+40h]
0x180018ad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ad6  lea     r8, [rsp+0D8h+var_A8]
0x180018adb  mov     edx, eax
0x180018add  lea     rcx, [rsp+0D8h+arg_8]
0x180018ae5  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180018aea  nop
0x180018aeb  lea     rcx, [rsp+0D8h+var_B8]
0x180018af0  call    ??1?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(void)
0x180018af5  nop
0x180018af6  mov     rcx, [rsp+0D8h+arg_10]
0x180018afe  test    rcx, rcx
0x180018b01  jz      short loc_180018B0D
0x180018b03  add     rcx, 8
0x180018b07  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x180018b0c  nop
0x180018b0d  lea     rcx, [rsp+0D8h+var_88]
0x180018b12  call    ??1?$test_watcher@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::~test_watcher<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>(void)
0x180018b17  nop
0x180018b18  lea     rcx, [rsp+0D8h+arg_10]
0x180018b20  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>,wil::err_returncode_policy>(void)
0x180018b25  nop
0x180018b26  lea     rcx, [rsp+0D8h+var_48]
0x180018b2e  call    ??1?$test_watcher@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::~test_watcher<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>(void)
0x180018b33  nop
0x180018b34  lea     rcx, [rsp+0D8h+arg_18]
0x180018b3c  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>,wil::err_returncode_policy>(void)
0x180018b41  add     rsp, 0D8h
0x180018b48  retn
```
