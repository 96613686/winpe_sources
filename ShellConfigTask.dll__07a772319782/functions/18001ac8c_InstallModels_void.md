# InstallModels(void)

- ea: `0x18001ac8c`
- end: `0x18001b7f6`
- name: `?InstallModels@@YAXXZ`
- size: `2922`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001fd50`

## callees

- `0x18000163c`
- `0x180002590`
- `0x18000896c`
- `0x18000d4b0`
- `0x18000e8d4`
- `0x18000ea2c`
- `0x18000eadc`
- `0x180010a3c`
- `0x180010c84`
- `0x180010da8`
- `0x180010ecc`
- `0x180010ff0`
- `0x180011618`
- `0x180011838`
- `0x180011948`
- `0x180011a58`
- `0x180011b68`
- `0x180014efc`
- `0x180015130`
- `0x18001ac8c`
- `0x18001c1b0`
- `0x18001c784`
- `0x18001d388`
- `0x18001d52c`
- `0x180020dfc`
- `0x180022f08`
- `0x180023024`
- `0x180024b4c`
- `0x180024f28`
- `0x180033010`

## pseudocode

```c
void InstallModels(void)
{
  const struct _tlgProvider_t *v0; // rax
  int v1; // eax
  wil *v2; // rcx
  char v3; // al
  int v4; // eax
  __int64 IsCachedAsync; // rax
  int v6; // eax
  wil *v7; // rcx
  char v8; // al
  int v9; // eax
  __int64 v10; // rax
  int v11; // eax
  wil *v12; // rcx
  char v13; // al
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  wil *v17; // rcx
  char v18; // al
  int v19; // eax
  __int64 v20; // rax
  int v21; // eax
  wil *v22; // rcx
  char v23; // al
  int v24; // eax
  __int64 v25; // rax
  AIXPolicyHelper *v26; // rcx
  wil *v27; // rcx
  __int64 AvailableAsync; // rax
  __int64 v29; // rax
  const struct _tlgProvider_t *v30; // rax
  wil *v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rax
  bool v34[8]; // [rsp+30h] [rbp-58h] BYREF
  __int64 *v35; // [rsp+38h] [rbp-50h] BYREF
  __int64 *v36; // [rsp+40h] [rbp-48h] BYREF
  __int64 *v37; // [rsp+48h] [rbp-40h] BYREF
  __int64 *v38; // [rsp+50h] [rbp-38h] BYREF
  int v39; // [rsp+58h] [rbp-30h] BYREF
  __int128 v40; // [rsp+60h] [rbp-28h]

  v0 = AIXTelemetryLogging::Provider();
  if ( *(_DWORD *)v0 > 5u )
    tlgWriteTransfer_EventWriteTransfer(v0, byte_180039033, 0, 0, 2, &v39);
  try
  {
    v37 = &qword_180041E08;
    _InterlockedIncrement64(&qword_180041E08);
    if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Vision::TextRecognizer,winrt::Microsoft::Windows::Vision::ITextRecognizerStatics> )
    {
      v34[0] = 0;
      v39 = 0;
      v40 = 0;
      v1 = (*(__int64 (__fastcall **)(__int64, bool *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Vision::TextRecognizer,winrt::Microsoft::Windows::Vision::ITextRecognizerStatics>
                                                      + 48LL))(
             winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Vision::TextRecognizer,winrt::Microsoft::Windows::Vision::ITextRecognizerStatics>,
             v34);
      if ( v1 < 0 )
        winrt::throw_hresult((unsigned int)v1, &v39);
      v3 = v34[0];
      _InterlockedDecrement64(&qword_180041E08);
    }
    else
    {
      _InterlockedDecrement64(&qword_180041E08);
      v37 = (__int64 *)_lambda_0379b32abc0657f54a544af3521b1cb2_::_lambda_invoker_cdecl_;
      v3 = winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::Vision::TextRecognizer,winrt::Microsoft::Windows::Vision::ITextRecognizerStatics>::call<bool (*)(winrt::Microsoft::Windows::Vision::ITextRecognizerStatics const &)>(
             0,
             &v37);
    }
    if ( !v3 )
    {
      v35 = &qword_180041E08;
      _InterlockedIncrement64(&qword_180041E08);
      if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Vision::TextRecognizer,winrt::Microsoft::Windows::Vision::ITextRecognizerStatics> )
      {
        v37 = 0;
        v39 = 0;
        v40 = 0;
        v4 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Vision::TextRecognizer,winrt::Microsoft::Windows::Vision::ITextRecognizerStatics>
                                                            + 56LL))(
               winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Vision::TextRecognizer,winrt::Microsoft::Windows::Vision::ITextRecognizerStatics>,
               &v37);
        if ( v4 < 0 )
          winrt::throw_hresult((unsigned int)v4, &v39);
        v36 = v37;
        _InterlockedDecrement64(&qword_180041E08);
      }
      else
      {
        _InterlockedDecrement64(&qword_180041E08);
        v37 = (__int64 *)_lambda_05cb80ee2c167c13088eab7ae81a7071_::_lambda_invoker_cdecl_;
        winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::Vision::TextRecognizer,winrt::Microsoft::Windows::Vision::ITextRecognizerStatics>::call<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> (*)(winrt::Microsoft::Windows::Vision::ITextRecognizerStatics const &)>(
          0,
          &v36,
          &v37);
      }
      winrt::impl::consume_Windows_Foundation_IAsyncOperationWithProgress<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::get(
        &v36,
        &v38);
      if ( v36 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v36);
      if ( (unsigned int)winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::Status(&v38) == 1 )
      {
        LODWORD(v35) = 13;
        IsCachedAsync = winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal::EnsureModelIsCachedAsync((const enum winrt::Microsoft::Windows::Workloads::Internal::ModelKind *)&v37);
        winrt::impl::consume_Windows_Foundation_IAsyncAction<winrt::Windows::Foundation::IAsyncAction>::get(IsCachedAsync);
        if ( v37 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v37);
        LODWORD(v35) = 0;
        AIXTelemetry::ModelInstallation_Succeeded<enum ModelName>(&v35);
      }
      else
      {
        LODWORD(v36) = *(_DWORD *)winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::Error(
                                    &v38,
                                    &v35);
        LODWORD(v35) = 0;
        AIXTelemetry::ModelInstallation_Failed<enum ModelName,long &>(&v35, &v36);
      }
      if ( v38 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v38);
    }
  }
  catch ( ... )
  {
    LODWORD(v35) = wil::ResultFromCaughtException(v2);
    LODWORD(v36) = 0;
    AIXTelemetry::ModelInstallation_Failed<enum ModelName,long const &>(&v36, &v35);
  }
  try
  {
    v37 = &qword_180041E28;
    _InterlockedIncrement64(&qword_180041E28);
    if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Vision::ScreenRegionDetector,winrt::Microsoft::Windows::Vision::IScreenRegionDetectorStatics> )
    {
      v34[0] = 0;
      v39 = 0;
      v40 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, bool *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Vision::ScreenRegionDetector,winrt::Microsoft::Windows::Vision::IScreenRegionDetectorStatics>
                                                      + 48LL))(
             winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Vision::ScreenRegionDetector,winrt::Microsoft::Windows::Vision::IScreenRegionDetectorStatics>,
             v34);
      if ( v6 < 0 )
        winrt::throw_hresult((unsigned int)v6, &v39);
      v8 = v34[0];
      _InterlockedDecrement64(&qword_180041E28);
    }
    else
    {
      _InterlockedDecrement64(&qword_180041E28);
      v37 = (__int64 *)_lambda_0379b32abc0657f54a544af3521b1cb2_::_lambda_invoker_cdecl_;
      v8 = winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::Vision::ScreenRegionDetector,winrt::Microsoft::Windows::Vision::IScreenRegionDetectorStatics>::call<bool (*)(winrt::Microsoft::Windows::Vision::IScreenRegionDetectorStatics const &)>(
             0,
             &v37);
    }
    if ( !v8 )
    {
      v36 = &qword_180041E28;
      _InterlockedIncrement64(&qword_180041E28);
      if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Vision::ScreenRegionDetector,winrt::Microsoft::Windows::Vision::IScreenRegionDetectorStatics> )
      {
        v35 = 0;
        v39 = 0;
        v40 = 0;
        v9 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Vision::ScreenRegionDetector,winrt::Microsoft::Windows::Vision::IScreenRegionDetectorStatics>
                                                            + 56LL))(
               winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Vision::ScreenRegionDetector,winrt::Microsoft::Windows::Vision::IScreenRegionDetectorStatics>,
               &v35);
        if ( v9 < 0 )
          winrt::throw_hresult((unsigned int)v9, &v39);
        v38 = v35;
        _InterlockedDecrement64(&qword_180041E28);
      }
      else
      {
        _InterlockedDecrement64(&qword_180041E28);
        v35 = (__int64 *)_lambda_05cb80ee2c167c13088eab7ae81a7071_::_lambda_invoker_cdecl_;
        winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::Vision::ScreenRegionDetector,winrt::Microsoft::Windows::Vision::IScreenRegionDetectorStatics>::call<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> (*)(winrt::Microsoft::Windows::Vision::IScreenRegionDetectorStatics const &)>(
          0,
          &v38,
          &v35);
      }
      winrt::impl::consume_Windows_Foundation_IAsyncOperationWithProgress<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::get(
        &v38,
        &v37);
      if ( v38 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v38);
      if ( (unsigned int)winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::Status(&v37) == 1 )
      {
        LODWORD(v35) = 12;
        v10 = winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal::EnsureModelIsCachedAsync((const enum winrt::Microsoft::Windows::Workloads::Internal::ModelKind *)&v36);
        winrt::impl::consume_Windows_Foundation_IAsyncAction<winrt::Windows::Foundation::IAsyncAction>::get(v10);
        if ( v36 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v36);
        LODWORD(v35) = 1;
        AIXTelemetry::ModelInstallation_Succeeded<enum ModelName>(&v35);
      }
      else
      {
        LODWORD(v35) = *(_DWORD *)winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::Error(
                                    &v37,
                                    &v35);
        LODWORD(v36) = 1;
        AIXTelemetry::ModelInstallation_Failed<enum ModelName,long &>(&v36, &v35);
      }
      if ( v37 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v37);
    }
  }
  catch ( ... )
  {
    LODWORD(v35) = wil::ResultFromCaughtException(v7);
    LODWORD(v36) = 1;
    AIXTelemetry::ModelInstallation_Failed<enum ModelName,long const &>(&v36, &v35);
  }
  try
  {
    v37 = &qword_180041E48;
    _InterlockedIncrement64(&qword_180041E48);
    if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::ImageSearchEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearch::IImageSearchEmbeddingsCreatorStatics> )
    {
      v34[0] = 0;
      v39 = 0;
      v40 = 0;
      v11 = (*(__int64 (__fastcall **)(__int64, bool *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::ImageSearchEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearch::IImageSearchEmbeddingsCreatorStatics>
                                                       + 48LL))(
              winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::ImageSearchEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearch::IImageSearchEmbeddingsCreatorStatics>,
              v34);
      if ( v11 < 0 )
        winrt::throw_hresult((unsigned int)v11, &v39);
      v13 = v34[0];
      _InterlockedDecrement64(&qword_180041E48);
    }
    else
    {
      _InterlockedDecrement64(&qword_180041E48);
      v37 = (__int64 *)_lambda_0379b32abc0657f54a544af3521b1cb2_::_lambda_invoker_cdecl_;
      v13 = winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::ImageSearchEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearch::IImageSearchEmbeddingsCreatorStatics>::call<bool (*)(winrt::Microsoft::Windows::SemanticSearch::IImageSearchEmbeddingsCreatorStatics const &)>(
              0,
              &v37);
    }
    if ( !v13 )
    {
      v36 = &qword_180041E48;
      _InterlockedIncrement64(&qword_180041E48);
      if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::ImageSearchEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearch::IImageSearchEmbeddingsCreatorStatics> )
      {
        v35 = 0;
        v39 = 0;
        v40 = 0;
        v14 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::ImageSearchEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearch::IImageSearchEmbeddingsCreatorStatics>
                                                             + 56LL))(
                winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::ImageSearchEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearch::IImageSearchEmbeddingsCreatorStatics>,
                &v35);
        if ( v14 < 0 )
          winrt::throw_hresult((unsigned int)v14, &v39);
        v37 = v35;
        _InterlockedDecrement64(&qword_180041E48);
      }
      else
      {
        _InterlockedDecrement64(&qword_180041E48);
        v35 = (__int64 *)_lambda_05cb80ee2c167c13088eab7ae81a7071_::_lambda_invoker_cdecl_;
        winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::ImageSearchEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearch::IImageSearchEmbeddingsCreatorStatics>::call<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> (*)(winrt::Microsoft::Windows::SemanticSearch::IImageSearchEmbeddingsCreatorStatics const &)>(
          0,
          &v37,
          &v35);
      }
      winrt::impl::consume_Windows_Foundation_IAsyncOperationWithProgress<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::get(
        &v37,
        &v38);
      if ( v37 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v37);
      if ( (unsigned int)winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::Status(&v38) == 1 )
      {
        LODWORD(v35) = 6;
        v15 = winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal::EnsureModelIsCachedAsync((const enum winrt::Microsoft::Windows::Workloads::Internal::ModelKind *)&v36);
        winrt::impl::consume_Windows_Foundation_IAsyncAction<winrt::Windows::Foundation::IAsyncAction>::get(v15);
        if ( v36 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v36);
        LODWORD(v35) = 2;
        AIXTelemetry::ModelInstallation_Succeeded<enum ModelName>(&v35);
      }
      else
      {
        LODWORD(v35) = *(_DWORD *)winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::Error(
                                    &v38,
                                    &v35);
        LODWORD(v36) = 2;
        AIXTelemetry::ModelInstallation_Failed<enum ModelName,long &>(&v36, &v35);
      }
      if ( v38 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v38);
    }
  }
  catch ( ... )
  {
    LODWORD(v35) = wil::ResultFromCaughtException(v12);
    LODWORD(v36) = 2;
    AIXTelemetry::ModelInstallation_Failed<enum ModelName,long const &>(&v36, &v35);
  }
  try
  {
    v37 = &qword_180041E68;
    _InterlockedIncrement64(&qword_180041E68);
    if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextEmbeddingsCreatorStatics> )
    {
      v34[0] = 0;
      v39 = 0;
      v40 = 0;
      v16 = (*(__int64 (__fastcall **)(__int64, bool *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextEmbeddingsCreatorStatics>
                                                       + 48LL))(
              winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextEmbeddingsCreatorStatics>,
              v34);
      if ( v16 < 0 )
        winrt::throw_hresult((unsigned int)v16, &v39);
      v18 = v34[0];
      _InterlockedDecrement64(&qword_180041E68);
    }
    else
    {
      _InterlockedDecrement64(&qword_180041E68);
      v37 = (__int64 *)_lambda_0379b32abc0657f54a544af3521b1cb2_::_lambda_invoker_cdecl_;
      v18 = winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextEmbeddingsCreatorStatics>::call<bool (*)(winrt::Microsoft::Windows::SemanticSearch::ISemanticTextEmbeddingsCreatorStatics const &)>(
              0,
              &v37);
    }
    if ( !v18 )
    {
      v36 = &qword_180041E68;
      _InterlockedIncrement64(&qword_180041E68);
      if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextEmbeddingsCreatorStatics> )
      {
        v35 = 0;
        v39 = 0;
        v40 = 0;
        v19 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextEmbeddingsCreatorStatics>
                                                             + 56LL))(
                winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextEmbeddingsCreatorStatics>,
                &v35);
        if ( v19 < 0 )
          winrt::throw_hresult((unsigned int)v19, &v39);
        v37 = v35;
        _InterlockedDecrement64(&qword_180041E68);
      }
      else
      {
        _InterlockedDecrement64(&qword_180041E68);
        v35 = (__int64 *)_lambda_05cb80ee2c167c13088eab7ae81a7071_::_lambda_invoker_cdecl_;
        winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextEmbeddingsCreatorStatics>::call<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> (*)(winrt::Microsoft::Windows::SemanticSearch::ISemanticTextEmbeddingsCreatorStatics const &)>(
          0,
          &v37,
          &v35);
      }
      winrt::impl::consume_Windows_Foundation_IAsyncOperationWithProgress<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::get(
        &v37,
        &v38);
      if ( v37 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v37);
      if ( (unsigned int)winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::Status(&v38) == 1 )
      {
        LODWORD(v35) = 11;
        v20 = winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal::EnsureModelIsCachedAsync((const enum winrt::Microsoft::Windows::Workloads::Internal::ModelKind *)&v36);
        winrt::impl::consume_Windows_Foundation_IAsyncAction<winrt::Windows::Foundation::IAsyncAction>::get(v20);
        if ( v36 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v36);
        LODWORD(v35) = 3;
        AIXTelemetry::ModelInstallation_Succeeded<enum ModelName>(&v35);
      }
      else
      {
        LODWORD(v35) = *(_DWORD *)winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::Error(
                                    &v38,
                                    &v35);
        LODWORD(v36) = 3;
        AIXTelemetry::ModelInstallation_Failed<enum ModelName,long &>(&v36, &v35);
      }
      if ( v38 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v38);
    }
  }
  catch ( ... )
  {
    LODWORD(v35) = wil::ResultFromCaughtException(v17);
    LODWORD(v36) = 3;
    AIXTelemetry::ModelInstallation_Failed<enum ModelName,long const &>(&v36, &v35);
  }
  try
  {
    v37 = &qword_180041E88;
    _InterlockedIncrement64(&qword_180041E88);
    if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::QueryProcessor,winrt::Microsoft::Windows::SemanticSearch::IQueryProcessorStatics> )
    {
      v34[0] = 0;
      v39 = 0;
      v40 = 0;
      v21 = (*(__int64 (__fastcall **)(__int64, bool *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::QueryProcessor,winrt::Microsoft::Windows::SemanticSearch::IQueryProcessorStatics>
                                                       + 48LL))(
              winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::QueryProcessor,winrt::Microsoft::Windows::SemanticSearch::IQueryProcessorStatics>,
              v34);
      if ( v21 < 0 )
        winrt::throw_hresult((unsigned int)v21, &v39);
      v23 = v34[0];
      _InterlockedDecrement64(&qword_180041E88);
    }
    else
    {
      _InterlockedDecrement64(&qword_180041E88);
      v37 = (__int64 *)_lambda_0379b32abc0657f54a544af3521b1cb2_::_lambda_invoker_cdecl_;
      v23 = winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::QueryProcessor,winrt::Microsoft::Windows::SemanticSearch::IQueryProcessorStatics>::call<bool (*)(winrt::Microsoft::Windows::SemanticSearch::IQueryProcessorStatics const &)>(
              0,
              &v37);
    }
    if ( !v23 )
    {
      v36 = &qword_180041E88;
      _InterlockedIncrement64(&qword_180041E88);
      if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::QueryProcessor,winrt::Microsoft::Windows::SemanticSearch::IQueryProcessorStatics> )
      {
        v35 = 0;
        v39 = 0;
        v40 = 0;
        v24 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::QueryProcessor,winrt::Microsoft::Windows::SemanticSearch::IQueryProcessorStatics>
                                                             + 56LL))(
                winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::QueryProcessor,winrt::Microsoft::Windows::SemanticSearch::IQueryProcessorStatics>,
                &v35);
        if ( v24 < 0 )
          winrt::throw_hresult((unsigned int)v24, &v39);
        v37 = v35;
        _InterlockedDecrement64(&qword_180041E88);
      }
      else
      {
        _InterlockedDecrement64(&qword_180041E88);
        v35 = (__int64 *)_lambda_05cb80ee2c167c13088eab7ae81a7071_::_lambda_invoker_cdecl_;
        winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::QueryProcessor,winrt::Microsoft::Windows::SemanticSearch::IQueryProcessorStatics>::call<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> (*)(winrt::Microsoft::Windows::SemanticSearch::IQueryProcessorStatics const &)>(
          0,
          &v37,
          &v35);
      }
      winrt::impl::consume_Windows_Foundation_IAsyncOperationWithProgress<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::get(
        &v37,
        &v38);
      if ( v37 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v37);
      if ( (unsigned int)winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::Status(&v38) == 1 )
      {
        LODWORD(v35) = 9;
        v25 = winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal::EnsureModelIsCachedAsync((const enum winrt::Microsoft::Windows::Workloads::Internal::ModelKind *)&v36);
        winrt::impl::consume_Windows_Foundation_IAsyncAction<winrt::Windows::Foundation::IAsyncAction>::get(v25);
        if ( v36 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v36);
        LODWORD(v35) = 4;
        AIXTelemetry::ModelInstallation_Succeeded<enum ModelName>(&v35);
      }
      else
      {
        LODWORD(v35) = *(_DWORD *)winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::Error(
                                    &v38,
                                    &v35);
        LODWORD(v36) = 4;
        AIXTelemetry::ModelInstallation_Failed<enum ModelName,long &>(&v36, &v35);
      }
      if ( v38 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v38);
    }
  }
  catch ( ... )
  {
    LODWORD(v35) = wil::ResultFromCaughtException(v22);
    LODWORD(v36) = 4;
    AIXTelemetry::ModelInstallation_Failed<enum ModelName,long const &>(&v36, &v35);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56659309>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56659309>::GetImpl'::`2'::impl) )
  {
    if ( !AIXPolicyHelper::MeetsPhiDriverRequirements(v26) )
      goto LABEL_108;
    v34[0] = IsCTAMachine();
    if ( !v34[0] )
    {
      try
      {
        if ( !(unsigned __int8)winrt::Microsoft::Windows::AI::Generative::LanguageModel::IsAvailable() )
        {
          AvailableAsync = winrt::Microsoft::Windows::AI::Generative::LanguageModel::MakeAvailableAsync();
          winrt::impl::consume_Windows_Foundation_IAsyncOperationWithProgress<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::get(
            AvailableAsync,
            &v37);
          if ( v38 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v38);
          if ( (unsigned int)winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::Status(&v37) == 1 )
          {
            LODWORD(v35) = 16;
            v29 = winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal::EnsureModelIsCachedAsync((const enum winrt::Microsoft::Windows::Workloads::Internal::ModelKind *)&v36);
            winrt::impl::consume_Windows_Foundation_IAsyncAction<winrt::Windows::Foundation::IAsyncAction>::get(v29);
            if ( v36 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v36);
            LODWORD(v35) = 6;
            AIXTelemetry::ModelInstallation_Succeeded<enum ModelName>(&v35);
          }
          else
          {
            LODWORD(v35) = *(_DWORD *)winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::Error(
                                        &v37,
                                        &v35);
            LODWORD(v36) = 6;
            AIXTelemetry::ModelInstallation_Failed<enum ModelName,long &>(&v36, &v35);
          }
          if ( v37 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v37);
        }
      }
      catch ( ... )
      {
        LODWORD(v35) = wil::ResultFromCaughtException(v27);
        LODWORD(v36) = 6;
        AIXTelemetry::ModelInstallation_Failed<enum ModelName,long const &>(&v36, &v35);
      }
    }
  }
  else
  {
    v34[0] = IsCTAMachine();
    if ( !v34[0] )
    {
      try
      {
        if ( !(unsigned __int8)winrt::Microsoft::Windows::AI::Generative::LanguageModel::IsAvailable() )
        {
          v32 = winrt::Microsoft::Windows::AI::Generative::LanguageModel::MakeAvailableAsync();
          winrt::impl::consume_Windows_Foundation_IAsyncOperationWithProgress<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::get(
            v32,
            &v37);
          if ( v38 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v38);
          if ( (unsigned int)winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::Status(&v37) == 1 )
          {
            LODWORD(v35) = 16;
            v33 = winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal::EnsureModelIsCachedAsync((const enum winrt::Microsoft::Windows::Workloads::Internal::ModelKind *)&v36);
            winrt::impl::consume_Windows_Foundation_IAsyncAction<winrt::Windows::Foundation::IAsyncAction>::get(v33);
            if ( v36 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v36);
            LODWORD(v35) = 6;
            AIXTelemetry::ModelInstallation_Succeeded<enum ModelName>(&v35);
          }
          else
          {
            LODWORD(v35) = *(_DWORD *)winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::Error(
                                        &v37,
                                        &v35);
            LODWORD(v36) = 6;
            AIXTelemetry::ModelInstallation_Failed<enum ModelName,long &>(&v36, &v35);
          }
          if ( v37 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v37);
        }
      }
      catch ( ... )
      {
        LODWORD(v35) = wil::ResultFromCaughtException(v31);
        LODWORD(v36) = 6;
        AIXTelemetry::ModelInstallation_Failed<enum ModelName,long const &>(&v36, &v35);
      }
    }
  }
  LODWORD(v35) = 6;
  AIXTelemetry::ModelInstallation_IsCTAMachine<enum ModelName,bool &>(&v35, v34);
LABEL_108:
  v30 = AIXTelemetryLogging::Provider();
  if ( *(_DWORD *)v30 > 5u )
    tlgWriteTransfer_EventWriteTransfer(v30, byte_180039209, 0, 0, 2, &v39);
}

```

## disassembly

```asm
0x18001ac8c  mov     [rsp+arg_0], rbx
0x18001ac91  push    rdi
0x18001ac92  sub     rsp, 80h
0x18001ac99  mov     rax, cs:__security_cookie
0x18001aca0  xor     rax, rsp
0x18001aca3  mov     [rsp+88h+var_10], rax
0x18001aca8  xor     ebx, ebx
0x18001acaa  call    ?Provider@AIXTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; AIXTelemetryLogging::Provider(void)
0x18001acaf  mov     ecx, [rax]
0x18001acb1  cmp     ecx, 5
0x18001acb4  jbe     short loc_18001ACDE
0x18001acb6  lea     rcx, [rsp+88h+var_30]
0x18001acbb  mov     [rsp+88h+var_60], rcx
0x18001acc0  mov     [rsp+88h+var_68], 2
0x18001acc8  xor     r9d, r9d
0x18001accb  xor     r8d, r8d
0x18001acce  lea     rdx, byte_180039033
0x18001acd5  mov     rcx, rax
0x18001acd8  call    _tlgWriteTransfer_EventWriteTransfer
0x18001acdd  nop
0x18001acde  lea     rdi, qword_180041E08
0x18001ace5  mov     [rsp+88h+var_40], rdi
0x18001acea  lock inc cs:qword_180041E08
0x18001acf2  mov     rcx, cs:??$factory_cache_entry_v@UTextRecognizer@Vision@Windows@Microsoft@winrt@@UITextRecognizerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UTextRecognizer@Vision@Windows@Microsoft@winrt@@UITextRecognizerStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::Vision::TextRecognizer,winrt::Microsoft::Windows::Vision::ITextRecognizerStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Vision::TextRecognizer,winrt::Microsoft::Windows::Vision::ITextRecognizerStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Vision::TextRecognizer,winrt::Microsoft::Windows::Vision::ITextRecognizerStatics>
0x18001acf9  test    rcx, rcx
0x18001acfc  jz      short loc_18001AD36
0x18001acfe  mov     [rsp+88h+var_58], bl
0x18001ad02  mov     [rsp+88h+var_30], ebx
0x18001ad06  xorps   xmm0, xmm0
0x18001ad09  movdqu  [rsp+88h+var_28], xmm0
0x18001ad0f  mov     rax, [rcx]
0x18001ad12  lea     rdx, [rsp+88h+var_58]
0x18001ad17  mov     rax, [rax+30h]
0x18001ad1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad20  test    eax, eax
0x18001ad22  js      loc_18001B773
0x18001ad28  mov     al, [rsp+88h+var_58]
0x18001ad2c  lock dec cs:qword_180041E08
0x18001ad34  jmp     short loc_18001AD54
0x18001ad36  lock dec cs:qword_180041E08
0x18001ad3e  lea     rax, ?_lambda_invoker_cdecl_@_lambda_0379b32abc0657f54a544af3521b1cb2_@@CA@AEBUIEducationSettingsStatics@Profile@System@Windows@winrt@@@Z; _lambda_0379b32abc0657f54a544af3521b1cb2_::_lambda_invoker_cdecl_(winrt::Windows::System::Profile::IEducationSettingsStatics const &)
0x18001ad45  mov     [rsp+88h+var_40], rax
0x18001ad4a  lea     rdx, [rsp+88h+var_40]
0x18001ad4f  call    ??$call@P6A_NAEBUITextRecognizerStatics@Vision@Windows@Microsoft@winrt@@@Z@?$factory_cache_entry@UTextRecognizer@Vision@Windows@Microsoft@winrt@@UITextRecognizerStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A_NAEBUITextRecognizerStatics@Vision@Windows@Microsoft@2@@Z@Z
0x18001ad54  test    al, al
0x18001ad56  jnz     loc_18001AE80
0x18001ad5c  mov     [rsp+88h+var_50], rdi
0x18001ad61  lock inc cs:qword_180041E08
0x18001ad69  mov     rcx, cs:??$factory_cache_entry_v@UTextRecognizer@Vision@Windows@Microsoft@winrt@@UITextRecognizerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UTextRecognizer@Vision@Windows@Microsoft@winrt@@UITextRecognizerStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::Vision::TextRecognizer,winrt::Microsoft::Windows::Vision::ITextRecognizerStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Vision::TextRecognizer,winrt::Microsoft::Windows::Vision::ITextRecognizerStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Vision::TextRecognizer,winrt::Microsoft::Windows::Vision::ITextRecognizerStatics>
0x18001ad70  test    rcx, rcx
0x18001ad73  jz      short loc_18001ADB4
0x18001ad75  mov     [rsp+88h+var_40], rbx
0x18001ad7a  mov     [rsp+88h+var_30], ebx
0x18001ad7e  xorps   xmm0, xmm0
0x18001ad81  movdqu  [rsp+88h+var_28], xmm0
0x18001ad87  mov     rax, [rcx]
0x18001ad8a  lea     rdx, [rsp+88h+var_40]
0x18001ad8f  mov     rax, [rax+38h]
0x18001ad93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad98  test    eax, eax
0x18001ad9a  js      loc_18001B780
0x18001ada0  mov     rax, [rsp+88h+var_40]
0x18001ada5  mov     [rsp+88h+var_48], rax
0x18001adaa  lock dec cs:qword_180041E08
0x18001adb2  jmp     short loc_18001ADD8
0x18001adb4  lock dec cs:qword_180041E08
0x18001adbc  lea     rax, ?_lambda_invoker_cdecl_@_lambda_05cb80ee2c167c13088eab7ae81a7071_@@CA@AEBUITextRecognizerStatics@Vision@Windows@Microsoft@winrt@@@Z; _lambda_05cb80ee2c167c13088eab7ae81a7071_::_lambda_invoker_cdecl_(winrt::Microsoft::Windows::Vision::ITextRecognizerStatics const &)
0x18001adc3  mov     [rsp+88h+var_40], rax
0x18001adc8  lea     r8, [rsp+88h+var_40]
0x18001adcd  lea     rdx, [rsp+88h+var_48]
0x18001add2  call    ??$call@P6A?AU?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@AEBUITextRecognizerStatics@Vision@3Microsoft@4@@Z@?$factory_cache_entry@UTextRecognizer@Vision@Windows@Microsoft@winrt@@UITextRecognizerStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AU?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@2@AEBUITextRecognizerStatics@Vision@5Microsoft@2@@Z@Z
0x18001add7  nop
0x18001add8  lea     rdx, [rsp+88h+var_38]
0x18001addd  lea     rcx, [rsp+88h+var_48]
0x18001ade2  call    ?get@?$consume_Windows_Foundation_IAsyncOperationWithProgress@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@UPackageDeploymentResult@Deployment@Management@3Microsoft@4@UPackageDeploymentProgress@67384@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperationWithProgress<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::get(void)
0x18001ade7  nop
0x18001ade8  cmp     [rsp+88h+var_48], rbx
0x18001aded  jz      short loc_18001ADF9
0x18001adef  lea     rcx, [rsp+88h+var_48]
0x18001adf4  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001adf9  lea     rcx, [rsp+88h+var_38]
0x18001adfe  call    ?Status@?$consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult@UIPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::Status(void)
0x18001ae03  lea     rdx, [rsp+88h+var_50]
0x18001ae08  cmp     eax, 1
0x18001ae0b  jz      short loc_18001AE32
0x18001ae0d  lea     rcx, [rsp+88h+var_38]
0x18001ae12  call    ?Error@?$consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult@UIPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::Error(void)
0x18001ae17  mov     eax, [rax]
0x18001ae19  mov     dword ptr [rsp+88h+var_48], eax
0x18001ae1d  mov     dword ptr [rsp+88h+var_50], ebx
0x18001ae21  lea     rdx, [rsp+88h+var_48]
0x18001ae26  lea     rcx, [rsp+88h+var_50]
0x18001ae2b  call    ??$ModelInstallation_Failed@W4ModelName@@AEAJ@AIXTelemetry@@SAX$$QEAW4ModelName@@AEAJ@Z; AIXTelemetry::ModelInstallation_Failed<ModelName,long &>(ModelName &&,long &)
0x18001ae30  jmp     short loc_18001AE6E
0x18001ae32  mov     dword ptr [rsp+88h+var_50], 0Dh
0x18001ae3a  lea     rcx, [rsp+88h+var_40]; enum winrt::Microsoft::Windows::Workloads::Internal::ModelKind *
0x18001ae3f  call    ?EnsureModelIsCachedAsync@CacheManagerInternal@Internal@Workloads@Windows@Microsoft@winrt@@SA@AEBW4ModelKind@23456@@Z; winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal::EnsureModelIsCachedAsync(winrt::Microsoft::Windows::Workloads::Internal::ModelKind const &)
0x18001ae44  nop
0x18001ae45  mov     rcx, rax
0x18001ae48  call    ?get@?$consume_Windows_Foundation_IAsyncAction@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncAction<winrt::Windows::Foundation::IAsyncAction>::get(void)
0x18001ae4d  nop
0x18001ae4e  cmp     [rsp+88h+var_40], rbx
0x18001ae53  jz      short loc_18001AE5F
0x18001ae55  lea     rcx, [rsp+88h+var_40]
0x18001ae5a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001ae5f  mov     dword ptr [rsp+88h+var_50], ebx
0x18001ae63  lea     rcx, [rsp+88h+var_50]
0x18001ae68  call    ??$ModelInstallation_Succeeded@W4ModelName@@@AIXTelemetry@@SAX$$QEAW4ModelName@@@Z; AIXTelemetry::ModelInstallation_Succeeded<ModelName>(ModelName &&)
0x18001ae6d  nop
0x18001ae6e  cmp     [rsp+88h+var_38], rbx
0x18001ae73  jz      short loc_18001AE80
0x18001ae75  lea     rcx, [rsp+88h+var_38]
0x18001ae7a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001ae7f  nop
0x18001ae80  jmp     short loc_18001AE84
0x18001ae82  xor     ebx, ebx
0x18001ae84  lea     rdi, qword_180041E28
0x18001ae8b  mov     [rsp+88h+var_40], rdi
0x18001ae90  lock inc cs:qword_180041E28
0x18001ae98  mov     rcx, cs:??$factory_cache_entry_v@UScreenRegionDetector@Vision@Windows@Microsoft@winrt@@UIScreenRegionDetectorStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UScreenRegionDetector@Vision@Windows@Microsoft@winrt@@UIScreenRegionDetectorStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::Vision::ScreenRegionDetector,winrt::Microsoft::Windows::Vision::IScreenRegionDetectorStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Vision::ScreenRegionDetector,winrt::Microsoft::Windows::Vision::IScreenRegionDetectorStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Vision::ScreenRegionDetector,winrt::Microsoft::Windows::Vision::IScreenRegionDetectorStatics>
0x18001ae9f  test    rcx, rcx
0x18001aea2  jz      short loc_18001AEDC
0x18001aea4  mov     [rsp+88h+var_58], bl
0x18001aea8  mov     [rsp+88h+var_30], ebx
0x18001aeac  xorps   xmm0, xmm0
0x18001aeaf  movdqu  [rsp+88h+var_28], xmm0
0x18001aeb5  mov     rax, [rcx]
0x18001aeb8  lea     rdx, [rsp+88h+var_58]
0x18001aebd  mov     rax, [rax+30h]
0x18001aec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aec6  test    eax, eax
0x18001aec8  js      loc_18001B78D
0x18001aece  mov     al, [rsp+88h+var_58]
0x18001aed2  lock dec cs:qword_180041E28
0x18001aeda  jmp     short loc_18001AEFA
0x18001aedc  lock dec cs:qword_180041E28
0x18001aee4  lea     rax, ?_lambda_invoker_cdecl_@_lambda_0379b32abc0657f54a544af3521b1cb2_@@CA@AEBUIEducationSettingsStatics@Profile@System@Windows@winrt@@@Z; _lambda_0379b32abc0657f54a544af3521b1cb2_::_lambda_invoker_cdecl_(winrt::Windows::System::Profile::IEducationSettingsStatics const &)
0x18001aeeb  mov     [rsp+88h+var_40], rax
0x18001aef0  lea     rdx, [rsp+88h+var_40]
0x18001aef5  call    ??$call@P6A_NAEBUIScreenRegionDetectorStatics@Vision@Windows@Microsoft@winrt@@@Z@?$factory_cache_entry@UScreenRegionDetector@Vision@Windows@Microsoft@winrt@@UIScreenRegionDetectorStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A_NAEBUIScreenRegionDetectorStatics@Vision@Windows@Microsoft@2@@Z@Z
0x18001aefa  test    al, al
0x18001aefc  jnz     loc_18001B02E
0x18001af02  mov     [rsp+88h+var_48], rdi
0x18001af07  lock inc cs:qword_180041E28
0x18001af0f  mov     rcx, cs:??$factory_cache_entry_v@UScreenRegionDetector@Vision@Windows@Microsoft@winrt@@UIScreenRegionDetectorStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UScreenRegionDetector@Vision@Windows@Microsoft@winrt@@UIScreenRegionDetectorStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::Vision::ScreenRegionDetector,winrt::Microsoft::Windows::Vision::IScreenRegionDetectorStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Vision::ScreenRegionDetector,winrt::Microsoft::Windows::Vision::IScreenRegionDetectorStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Vision::ScreenRegionDetector,winrt::Microsoft::Windows::Vision::IScreenRegionDetectorStatics>
0x18001af16  test    rcx, rcx
0x18001af19  jz      short loc_18001AF5A
0x18001af1b  mov     [rsp+88h+var_50], rbx
0x18001af20  mov     [rsp+88h+var_30], ebx
0x18001af24  xorps   xmm0, xmm0
0x18001af27  movdqu  [rsp+88h+var_28], xmm0
0x18001af2d  mov     rax, [rcx]
0x18001af30  lea     rdx, [rsp+88h+var_50]
0x18001af35  mov     rax, [rax+38h]
0x18001af39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af3e  test    eax, eax
0x18001af40  js      loc_18001B79A
0x18001af46  mov     rax, [rsp+88h+var_50]
0x18001af4b  mov     [rsp+88h+var_38], rax
0x18001af50  lock dec cs:qword_180041E28
0x18001af58  jmp     short loc_18001AF7E
0x18001af5a  lock dec cs:qword_180041E28
0x18001af62  lea     rax, ?_lambda_invoker_cdecl_@_lambda_05cb80ee2c167c13088eab7ae81a7071_@@CA@AEBUITextRecognizerStatics@Vision@Windows@Microsoft@winrt@@@Z; _lambda_05cb80ee2c167c13088eab7ae81a7071_::_lambda_invoker_cdecl_(winrt::Microsoft::Windows::Vision::ITextRecognizerStatics const &)
0x18001af69  mov     [rsp+88h+var_50], rax
0x18001af6e  lea     r8, [rsp+88h+var_50]
0x18001af73  lea     rdx, [rsp+88h+var_38]
0x18001af78  call    ??$call@P6A?AU?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@AEBUIScreenRegionDetectorStatics@Vision@3Microsoft@4@@Z@?$factory_cache_entry@UScreenRegionDetector@Vision@Windows@Microsoft@winrt@@UIScreenRegionDetectorStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AU?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@2@AEBUIScreenRegionDetectorStatics@Vision@5Microsoft@2@@Z@Z
0x18001af7d  nop
0x18001af7e  lea     rdx, [rsp+88h+var_40]
0x18001af83  lea     rcx, [rsp+88h+var_38]
0x18001af88  call    ?get@?$consume_Windows_Foundation_IAsyncOperationWithProgress@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@UPackageDeploymentResult@Deployment@Management@3Microsoft@4@UPackageDeploymentProgress@67384@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperationWithProgress<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::get(void)
0x18001af8d  nop
0x18001af8e  cmp     [rsp+88h+var_38], rbx
0x18001af93  jz      short loc_18001AF9F
0x18001af95  lea     rcx, [rsp+88h+var_38]
0x18001af9a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001af9f  lea     rcx, [rsp+88h+var_40]
0x18001afa4  call    ?Status@?$consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult@UIPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::Status(void)
0x18001afa9  lea     rdx, [rsp+88h+var_50]
0x18001afae  cmp     eax, 1
0x18001afb1  jz      short loc_18001AFDC
0x18001afb3  lea     rcx, [rsp+88h+var_40]
0x18001afb8  call    ?Error@?$consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult@UIPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::Error(void)
0x18001afbd  mov     eax, [rax]
0x18001afbf  mov     dword ptr [rsp+88h+var_50], eax
0x18001afc3  mov     dword ptr [rsp+88h+var_48], 1
0x18001afcb  lea     rdx, [rsp+88h+var_50]
0x18001afd0  lea     rcx, [rsp+88h+var_48]
0x18001afd5  call    ??$ModelInstallation_Failed@W4ModelName@@AEAJ@AIXTelemetry@@SAX$$QEAW4ModelName@@AEAJ@Z; AIXTelemetry::ModelInstallation_Failed<ModelName,long &>(ModelName &&,long &)
0x18001afda  jmp     short loc_18001B01C
0x18001afdc  mov     dword ptr [rsp+88h+var_50], 0Ch
0x18001afe4  lea     rcx, [rsp+88h+var_48]; enum winrt::Microsoft::Windows::Workloads::Internal::ModelKind *
0x18001afe9  call    ?EnsureModelIsCachedAsync@CacheManagerInternal@Internal@Workloads@Windows@Microsoft@winrt@@SA@AEBW4ModelKind@23456@@Z; winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal::EnsureModelIsCachedAsync(winrt::Microsoft::Windows::Workloads::Internal::ModelKind const &)
0x18001afee  nop
0x18001afef  mov     rcx, rax
0x18001aff2  call    ?get@?$consume_Windows_Foundation_IAsyncAction@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncAction<winrt::Windows::Foundation::IAsyncAction>::get(void)
0x18001aff7  nop
0x18001aff8  cmp     [rsp+88h+var_48], rbx
0x18001affd  jz      short loc_18001B009
0x18001afff  lea     rcx, [rsp+88h+var_48]
0x18001b004  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001b009  mov     dword ptr [rsp+88h+var_50], 1
0x18001b011  lea     rcx, [rsp+88h+var_50]
0x18001b016  call    ??$ModelInstallation_Succeeded@W4ModelName@@@AIXTelemetry@@SAX$$QEAW4ModelName@@@Z; AIXTelemetry::ModelInstallation_Succeeded<ModelName>(ModelName &&)
0x18001b01b  nop
0x18001b01c  cmp     [rsp+88h+var_40], rbx
0x18001b021  jz      short loc_18001B02E
0x18001b023  lea     rcx, [rsp+88h+var_40]
0x18001b028  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001b02d  nop
0x18001b02e  jmp     short loc_18001B032
0x18001b030  xor     ebx, ebx
0x18001b032  lea     rdi, qword_180041E48
0x18001b039  mov     [rsp+88h+var_40], rdi
0x18001b03e  lock inc cs:qword_180041E48
0x18001b046  mov     rcx, cs:??$factory_cache_entry_v@UImageSearchEmbeddingsCreator@SemanticSearch@Windows@Microsoft@winrt@@UIImageSearchEmbeddingsCreatorStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UImageSearchEmbeddingsCreator@SemanticSearch@Windows@Microsoft@winrt@@UIImageSearchEmbeddingsCreatorStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::ImageSearchEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearch::IImageSearchEmbeddingsCreatorStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::ImageSearchEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearch::IImageSearchEmbeddingsCreatorStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::ImageSearchEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearch::IImageSearchEmbeddingsCreatorStatics>
0x18001b04d  test    rcx, rcx
0x18001b050  jz      short loc_18001B08A
0x18001b052  mov     [rsp+88h+var_58], bl
0x18001b056  mov     [rsp+88h+var_30], ebx
0x18001b05a  xorps   xmm0, xmm0
0x18001b05d  movdqu  [rsp+88h+var_28], xmm0
0x18001b063  mov     rax, [rcx]
0x18001b066  lea     rdx, [rsp+88h+var_58]
0x18001b06b  mov     rax, [rax+30h]
0x18001b06f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b074  test    eax, eax
0x18001b076  js      loc_18001B7A7
0x18001b07c  mov     al, [rsp+88h+var_58]
0x18001b080  lock dec cs:qword_180041E48
0x18001b088  jmp     short loc_18001B0A8
0x18001b08a  lock dec cs:qword_180041E48
0x18001b092  lea     rax, ?_lambda_invoker_cdecl_@_lambda_0379b32abc0657f54a544af3521b1cb2_@@CA@AEBUIEducationSettingsStatics@Profile@System@Windows@winrt@@@Z; _lambda_0379b32abc0657f54a544af3521b1cb2_::_lambda_invoker_cdecl_(winrt::Windows::System::Profile::IEducationSettingsStatics const &)
0x18001b099  mov     [rsp+88h+var_40], rax
0x18001b09e  lea     rdx, [rsp+88h+var_40]
0x18001b0a3  call    ??$call@P6A_NAEBUIImageSearchEmbeddingsCreatorStatics@SemanticSearch@Windows@Microsoft@winrt@@@Z@?$factory_cache_entry@UImageSearchEmbeddingsCreator@SemanticSearch@Windows@Microsoft@winrt@@UIImageSearchEmbeddingsCreatorStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A_NAEBUIImageSearchEmbeddingsCreatorStatics@SemanticSearch@Windows@Microsoft@2@@Z@Z
0x18001b0a8  test    al, al
0x18001b0aa  jnz     loc_18001B1DC
0x18001b0b0  mov     [rsp+88h+var_48], rdi
0x18001b0b5  lock inc cs:qword_180041E48
0x18001b0bd  mov     rcx, cs:??$factory_cache_entry_v@UImageSearchEmbeddingsCreator@SemanticSearch@Windows@Microsoft@winrt@@UIImageSearchEmbeddingsCreatorStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UImageSearchEmbeddingsCreator@SemanticSearch@Windows@Microsoft@winrt@@UIImageSearchEmbeddingsCreatorStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::ImageSearchEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearch::IImageSearchEmbeddingsCreatorStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::ImageSearchEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearch::IImageSearchEmbeddingsCreatorStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::ImageSearchEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearch::IImageSearchEmbeddingsCreatorStatics>
0x18001b0c4  test    rcx, rcx
0x18001b0c7  jz      short loc_18001B108
0x18001b0c9  mov     [rsp+88h+var_50], rbx
0x18001b0ce  mov     [rsp+88h+var_30], ebx
0x18001b0d2  xorps   xmm0, xmm0
0x18001b0d5  movdqu  [rsp+88h+var_28], xmm0
0x18001b0db  mov     rax, [rcx]
0x18001b0de  lea     rdx, [rsp+88h+var_50]
0x18001b0e3  mov     rax, [rax+38h]
0x18001b0e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0ec  test    eax, eax
0x18001b0ee  js      loc_18001B7B4
0x18001b0f4  mov     rax, [rsp+88h+var_50]
0x18001b0f9  mov     [rsp+88h+var_40], rax
0x18001b0fe  lock dec cs:qword_180041E48
0x18001b106  jmp     short loc_18001B12C
0x18001b108  lock dec cs:qword_180041E48
0x18001b110  lea     rax, ?_lambda_invoker_cdecl_@_lambda_05cb80ee2c167c13088eab7ae81a7071_@@CA@AEBUITextRecognizerStatics@Vision@Windows@Microsoft@winrt@@@Z; _lambda_05cb80ee2c167c13088eab7ae81a7071_::_lambda_invoker_cdecl_(winrt::Microsoft::Windows::Vision::ITextRecognizerStatics const &)
0x18001b117  mov     [rsp+88h+var_50], rax
0x18001b11c  lea     r8, [rsp+88h+var_50]
0x18001b121  lea     rdx, [rsp+88h+var_40]
0x18001b126  call    ??$call@P6A?AU?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@AEBUIImageSearchEmbeddingsCreatorStatics@SemanticSearch@3Microsoft@4@@Z@?$factory_cache_entry@UImageSearchEmbeddingsCreator@SemanticSearch@Windows@Microsoft@winrt@@UIImageSearchEmbeddingsCreatorStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AU?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@2@AEBUIImageSearchEmbeddingsCreatorStatics@SemanticSearch@5Microsoft@2@@Z@Z
0x18001b12b  nop
0x18001b12c  lea     rdx, [rsp+88h+var_38]
0x18001b131  lea     rcx, [rsp+88h+var_40]
0x18001b136  call    ?get@?$consume_Windows_Foundation_IAsyncOperationWithProgress@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@UPackageDeploymentResult@Deployment@Management@3Microsoft@4@UPackageDeploymentProgress@67384@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperationWithProgress<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::get(void)
0x18001b13b  nop
0x18001b13c  cmp     [rsp+88h+var_40], rbx
0x18001b141  jz      short loc_18001B14D
0x18001b143  lea     rcx, [rsp+88h+var_40]
0x18001b148  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001b14d  lea     rcx, [rsp+88h+var_38]
0x18001b152  call    ?Status@?$consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult@UIPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::Status(void)
0x18001b157  lea     rdx, [rsp+88h+var_50]
0x18001b15c  cmp     eax, 1
0x18001b15f  jz      short loc_18001B18A
0x18001b161  lea     rcx, [rsp+88h+var_38]
0x18001b166  call    ?Error@?$consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult@UIPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::Error(void)
0x18001b16b  mov     eax, [rax]
0x18001b16d  mov     dword ptr [rsp+88h+var_50], eax
0x18001b171  mov     dword ptr [rsp+88h+var_48], 2
0x18001b179  lea     rdx, [rsp+88h+var_50]
0x18001b17e  lea     rcx, [rsp+88h+var_48]
0x18001b183  call    ??$ModelInstallation_Failed@W4ModelName@@AEAJ@AIXTelemetry@@SAX$$QEAW4ModelName@@AEAJ@Z; AIXTelemetry::ModelInstallation_Failed<ModelName,long &>(ModelName &&,long &)
0x18001b188  jmp     short loc_18001B1CA
0x18001b18a  mov     dword ptr [rsp+88h+var_50], 6
0x18001b192  lea     rcx, [rsp+88h+var_48]; enum winrt::Microsoft::Windows::Workloads::Internal::ModelKind *
0x18001b197  call    ?EnsureModelIsCachedAsync@CacheManagerInternal@Internal@Workloads@Windows@Microsoft@winrt@@SA@AEBW4ModelKind@23456@@Z; winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal::EnsureModelIsCachedAsync(winrt::Microsoft::Windows::Workloads::Internal::ModelKind const &)
0x18001b19c  nop
0x18001b19d  mov     rcx, rax
0x18001b1a0  call    ?get@?$consume_Windows_Foundation_IAsyncAction@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncAction<winrt::Windows::Foundation::IAsyncAction>::get(void)
0x18001b1a5  nop
0x18001b1a6  cmp     [rsp+88h+var_48], rbx
0x18001b1ab  jz      short loc_18001B1B7
0x18001b1ad  lea     rcx, [rsp+88h+var_48]
0x18001b1b2  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001b1b7  mov     dword ptr [rsp+88h+var_50], 2
0x18001b1bf  lea     rcx, [rsp+88h+var_50]
0x18001b1c4  call    ??$ModelInstallation_Succeeded@W4ModelName@@@AIXTelemetry@@SAX$$QEAW4ModelName@@@Z; AIXTelemetry::ModelInstallation_Succeeded<ModelName>(ModelName &&)
  ... truncated ...
```
