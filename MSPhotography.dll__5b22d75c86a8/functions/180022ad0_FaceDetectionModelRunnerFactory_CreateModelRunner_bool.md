# FaceDetectionModelRunnerFactory::CreateModelRunner(bool)

- ea: `0x180022ad0`
- end: `0x180023146`
- name: `?CreateModelRunner@FaceDetectionModelRunnerFactory@@SAPEAVFaceDetectionModelRunner@@_N@Z`
- size: `1654`
- prototype: `struct FaceDetectionModelRunner *__fastcall(char)`
- caller_count: `1`
- callee_count: `36`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800153b0`

## callees

- `0x180002da0`
- `0x180003094`
- `0x18000e834`
- `0x18000ef60`
- `0x18001cba4`
- `0x18001cc30`
- `0x18001ccd0`
- `0x18001d764`
- `0x18001d7d8`
- `0x18001d860`
- `0x1800207f0`
- `0x180020e84`
- `0x180020ea4`
- `0x1800216a4`
- `0x180021708`
- `0x180021de0`
- `0x180021e54`
- `0x180021ed0`
- `0x180021f98`
- `0x1800222e0`
- `0x180022408`
- `0x1800225cc`
- `0x180022a58`
- `0x180022ad0`
- `0x180023604`
- `0x1800252e4`
- `0x180025a38`
- `0x180025afc`
- `0x180027438`
- `0x180027f40`
- `0x1800280e4`
- `0x180028188`
- `0x1800281c8`
- `0x180028360`
- `0x180028554`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180022b0d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180022b0d`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180022bd4`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180022bd4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180022bac`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180022bac`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180022bdf`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180022bdf`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x180022b84`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x180022b84`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180022c0d`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180022c0d`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOverStream` at `0x180022c5f`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOverStream` at `0x180022c5f`

## pseudocode

```c
struct FaceDetectionModelRunner *__fastcall FaceDetectionModelRunnerFactory::CreateModelRunner(char a1)
{
  unsigned int ModuleHandle; // eax
  __int64 v3; // rdx
  HRSRC ResourceW; // rdi
  HGLOBAL Resource; // rbx
  UINT v6; // esi
  const BYTE *v7; // rbx
  IStream *v8; // rax
  __int64 v9; // rdi
  struct IUnknown *v10; // rdx
  void **v11; // rax
  unsigned int RandomAccessStreamOverStream; // eax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 (__fastcall ***v15)(_QWORD, __int64 *, __int64 *); // rcx
  unsigned int v16; // eax
  __int128 *v17; // rax
  __int64 v18; // rdx
  __int128 *v19; // rbx
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 (__fastcall ***v22)(_QWORD, __int64 *, __int64 *); // rcx
  unsigned int v23; // eax
  _OWORD *v24; // rax
  __int64 v25; // rdx
  _OWORD *v26; // rbx
  __int64 v27; // rcx
  __int64 (__fastcall ***v28)(_QWORD, __int64 *, __int64 *); // rcx
  __int64 v29; // rbx
  __int64 v30; // r8
  __int64 v31; // rsi
  unsigned int v32; // eax
  const struct winrt::Windows::AI::MachineLearning::LearningModelDevice *v33; // rax
  void *v34; // rsi
  const struct FaceDetectionModelRunner::FaceDetectionModelConstants *v35; // rax
  __int64 v36; // rsi
  const struct winrt::impl::slim_source_location *v38; // rax
  __int64 v39; // [rsp+20h] [rbp-79h] BYREF
  int pExceptionObject; // [rsp+28h] [rbp-71h] BYREF
  __int128 v41; // [rsp+30h] [rbp-69h]
  __int64 v42; // [rsp+40h] [rbp-59h] BYREF
  void (__fastcall ***v43)(_QWORD, __int64 *, __int64 *); // [rsp+48h] [rbp-51h] BYREF
  __int64 *v44; // [rsp+50h] [rbp-49h] BYREF
  __int64 v45; // [rsp+58h] [rbp-41h] BYREF
  __int64 v46; // [rsp+60h] [rbp-39h] BYREF
  __int64 v47; // [rsp+68h] [rbp-31h] BYREF
  __int64 v48; // [rsp+70h] [rbp-29h] BYREF
  __int64 v49; // [rsp+78h] [rbp-21h] BYREF
  __int128 v50; // [rsp+80h] [rbp-19h] BYREF
  __int128 v51; // [rsp+90h] [rbp-9h] BYREF
  char v52[8]; // [rsp+A0h] [rbp+7h] BYREF
  _BYTE v53[72]; // [rsp+A8h] [rbp+Fh] BYREF
  __int64 v54; // [rsp+108h] [rbp+6Fh] BYREF
  HMODULE phModule; // [rsp+110h] [rbp+77h] BYREF
  char v56; // [rsp+118h] [rbp+7Fh] BYREF

  phModule = 0;
  pExceptionObject = 0;
  v41 = 0;
  ModuleHandle = GetModuleHandleExW(6u, (LPCWSTR)FaceDetectionModelRunnerFactory::CreateModelRunner, &phModule);
  winrt::check_bool<int>(ModuleHandle, &pExceptionObject);
  pExceptionObject = 0;
  v41 = 0;
  winrt::check_pointer<HRSRC__>(phModule, &pExceptionObject);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Camera_FaceDetectionModelUpdate_55609719>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Camera_FaceDetectionModelUpdate_55609719>::GetImpl'::`2'::impl) )
  {
    if ( (unsigned __int8)byte_180160805 >= 0x20u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 10, &WPP_3819cc37a64338403add9ef0c33489c9_Traceguids);
    v3 = 102;
  }
  else
  {
    v3 = 101;
  }
  ResourceW = FindResourceW(phModule, (LPCWSTR)v3, (LPCWSTR)0xA);
  pExceptionObject = 0;
  v41 = 0;
  winrt::check_pointer<HRSRC__>(ResourceW, &pExceptionObject);
  Resource = LoadResource(phModule, ResourceW);
  pExceptionObject = 0;
  v41 = 0;
  winrt::check_pointer<HRSRC__>(Resource, &pExceptionObject);
  v6 = SizeofResource(phModule, ResourceW);
  v7 = (const BYTE *)LockResource(Resource);
  pExceptionObject = 0;
  v41 = 0;
  winrt::check_pointer<HRSRC__>(v7, &pExceptionObject);
  v49 = 0;
  v48 = 0;
  v8 = SHCreateMemStream(v7, v6);
  winrt::com_ptr<IStream>::attach(&v49, v8);
  pExceptionObject = 0;
  v41 = 0;
  v9 = v49;
  winrt::check_pointer<HRSRC__>(v49, &pExceptionObject);
  pExceptionObject = 0;
  v41 = 0;
  v11 = winrt::put_abi((winrt *)&v48, v10);
  RandomAccessStreamOverStream = CreateRandomAccessStreamOverStream(
                                   v9,
                                   0,
                                   winrt::impl::guid_v<winrt::Windows::Storage::Streams::IRandomAccessStream>,
                                   v11);
  winrt::check_hresult(&v54, RandomAccessStreamOverStream, &pExceptionObject);
  if ( (unsigned __int8)byte_180160805 >= 0x20u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 11, &WPP_3819cc37a64338403add9ef0c33489c9_Traceguids, v6);
  v54 = winrt::Windows::Storage::Streams::RandomAccessStreamReference::CreateFromStream((const struct winrt::Windows::Storage::Streams::IRandomAccessStream *)&v42);
  v44 = &qword_18015F9E8;
  _InterlockedIncrement64(&qword_18015F9E8);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::AI::MachineLearning::LearningModel,winrt::Windows::AI::MachineLearning::ILearningModelStatics> )
  {
    _lambda_a97271d0ed239d0f5a7f0c77aad64038_::operator()(
      &v54,
      &v56,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::AI::MachineLearning::LearningModel,winrt::Windows::AI::MachineLearning::ILearningModelStatics>);
    _InterlockedDecrement64(&qword_18015F9E8);
  }
  else
  {
    _InterlockedDecrement64(&qword_18015F9E8);
    winrt::impl::factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModel,winrt::Windows::AI::MachineLearning::ILearningModelStatics>::call<_lambda_a97271d0ed239d0f5a7f0c77aad64038_ &>(
      v13,
      &v56,
      &v54);
  }
  winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>::~IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>(&v42);
  v54 = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v56, &v54) )
  {
    v38 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v53);
    winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)&pExceptionObject, v38);
    throw (winrt::hresult_not_implemented *)&pExceptionObject;
  }
  v50 = 0;
  v51 = 0;
  v14 = winrt::impl::consume_Windows_AI_MachineLearning_ILearningModel<winrt::Windows::AI::MachineLearning::ILearningModel>::InputFeatures(
          &v56,
          &v47);
  v15 = *(__int64 (__fastcall ****)(_QWORD, __int64 *, __int64 *))winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::AI::MachineLearning::ILearningModelFeatureDescriptor>,winrt::Windows::AI::MachineLearning::ILearningModelFeatureDescriptor>::GetAt(
                                                                    v14,
                                                                    &v42);
  if ( v15 )
  {
    v39 = 0;
    pExceptionObject = 0;
    v41 = 0;
    v16 = (**v15)(v15, winrt::impl::guid_v<winrt::Windows::AI::MachineLearning::ITensorFeatureDescriptor>, &v39);
    winrt::check_hresult(&v54, v16, &pExceptionObject);
    v46 = v39;
  }
  else
  {
    v46 = 0;
  }
  winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>::~IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>(&v42);
  winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>::~IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>(&v47);
  v17 = (__int128 *)winrt::impl::consume_Windows_AI_MachineLearning_ILearningModelFeatureDescriptor<winrt::Windows::AI::MachineLearning::TensorFeatureDescriptor>::Name(
                      &v46,
                      &v54);
  if ( &v50 != v17 )
  {
    v18 = *(_QWORD *)v17;
    *(_QWORD *)v17 = 0;
    winrt::handle_type<winrt::impl::hstring_traits>::attach(&v50, v18);
  }
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v54);
  v19 = (__int128 *)winrt::impl::consume_Windows_AI_MachineLearning_ITensorFeatureDescriptor<winrt::Windows::AI::MachineLearning::ITensorFeatureDescriptor>::Shape(
                      &v46,
                      &v54);
  if ( &v51 != v19 )
  {
    if ( (_QWORD)v51 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v51);
    v20 = *(_QWORD *)v19;
    *(_QWORD *)v19 = 0;
    *(_QWORD *)&v51 = v20;
  }
  winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>::~IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>(&v54);
  v21 = winrt::impl::consume_Windows_AI_MachineLearning_ILearningModel<winrt::Windows::AI::MachineLearning::ILearningModel>::OutputFeatures(
          &v56,
          &v44);
  v22 = *(__int64 (__fastcall ****)(_QWORD, __int64 *, __int64 *))winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::AI::MachineLearning::ILearningModelFeatureDescriptor>,winrt::Windows::AI::MachineLearning::ILearningModelFeatureDescriptor>::GetAt(
                                                                    v21,
                                                                    v52);
  if ( v22 )
  {
    v39 = 0;
    pExceptionObject = 0;
    v41 = 0;
    v23 = (**v22)(v22, winrt::impl::guid_v<winrt::Windows::AI::MachineLearning::ITensorFeatureDescriptor>, &v39);
    winrt::check_hresult(&v54, v23, &pExceptionObject);
    v45 = v39;
  }
  else
  {
    v45 = 0;
  }
  winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>::~IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>(v52);
  winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>::~IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>(&v44);
  v24 = (_OWORD *)winrt::impl::consume_Windows_AI_MachineLearning_ILearningModelFeatureDescriptor<winrt::Windows::AI::MachineLearning::TensorFeatureDescriptor>::Name(
                    &v45,
                    &v54);
  if ( (__int128 *)((char *)&v50 + 8) != v24 )
  {
    v25 = *(_QWORD *)v24;
    *(_QWORD *)v24 = 0;
    winrt::handle_type<winrt::impl::hstring_traits>::attach((char *)&v50 + 8, v25);
  }
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v54);
  v26 = (_OWORD *)winrt::impl::consume_Windows_AI_MachineLearning_ITensorFeatureDescriptor<winrt::Windows::AI::MachineLearning::ITensorFeatureDescriptor>::Shape(
                    &v45,
                    &v54);
  if ( (__int128 *)((char *)&v51 + 8) != v26 )
  {
    if ( *((_QWORD *)&v51 + 1) )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((char *)&v51 + 8);
    v27 = *(_QWORD *)v26;
    *(_QWORD *)v26 = 0;
    *((_QWORD *)&v51 + 1) = v27;
  }
  winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>::~IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>(&v54);
  winrt::Windows::AI::MachineLearning::LearningModelSessionOptions::LearningModelSessionOptions((winrt::Windows::AI::MachineLearning::LearningModelSessionOptions *)&v43);
  winrt::impl::consume_Windows_AI_MachineLearning_ILearningModelSessionOptions2<winrt::Windows::AI::MachineLearning::LearningModelSessionOptions>::CloseModelOnSessionCreation(&v43);
  v28 = (__int64 (__fastcall ***)(_QWORD, __int64 *, __int64 *))v43;
  if ( v43 )
  {
    v54 = 0;
    (**v43)(v43, winrt::impl::guid_v<ILearningModelSessionOptionsNative1>, &v54);
    v29 = v54;
    v30 = v54;
    v28 = (__int64 (__fastcall ***)(_QWORD, __int64 *, __int64 *))v43;
  }
  else
  {
    v29 = 0;
    v30 = 0;
  }
  v42 = v29;
  if ( v30 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v30 + 24LL))(v30, 0);
    if ( (unsigned __int8)byte_180160805 >= 0x20u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 12, &WPP_3819cc37a64338403add9ef0c33489c9_Traceguids);
  }
  else
  {
    if ( v28 )
    {
      v39 = 0;
      pExceptionObject = 0;
      v41 = 0;
      v32 = (**v28)(v28, winrt::impl::guid_v<ILearningModelSessionOptionsNative>, &v39);
      winrt::check_hresult(&v54, v32, &pExceptionObject);
      v31 = v39;
      v54 = v39;
    }
    else
    {
      v54 = 0;
      v31 = 0;
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v31 + 24LL))(v31, 1);
    if ( (unsigned __int8)byte_180160805 >= 0x20u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 13, &WPP_3819cc37a64338403add9ef0c33489c9_Traceguids);
    if ( v31 )
      winrt::com_ptr<ITensorNative>::unconditional_release_ref(&v54);
  }
  LODWORD(v54) = 1;
  v33 = (const struct winrt::Windows::AI::MachineLearning::LearningModelDevice *)winrt::Windows::AI::MachineLearning::LearningModelDevice::LearningModelDevice(
                                                                                   (winrt::Windows::AI::MachineLearning::LearningModelDevice *)&v44,
                                                                                   (const enum winrt::Windows::AI::MachineLearning::LearningModelDeviceKind *)&v54);
  winrt::Windows::AI::MachineLearning::LearningModelSession::LearningModelSession(
    (winrt::Windows::AI::MachineLearning::LearningModelSession *)&v47,
    (const struct winrt::Windows::AI::MachineLearning::LearningModel *)&v56,
    v33,
    (const struct winrt::Windows::AI::MachineLearning::LearningModelSessionOptions *)&v43);
  winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>::~IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>(&v44);
  v34 = operator new(0xB0u);
  v54 = (__int64)v34;
  v44 = &v39;
  v39 = v47;
  Microsoft::WRL::ComPtr<IAsyncInfo>::InternalAddRef(&v39);
  v35 = (const struct FaceDetectionModelRunner::FaceDetectionModelConstants *)FaceDetectionModelRunner::FaceDetectionModelConstants::FaceDetectionModelConstants(
                                                                                (FaceDetectionModelRunner::FaceDetectionModelConstants *)v53,
                                                                                (const struct FaceDetectionModelRunner::FaceDetectionModelConstants *)&v50);
  v36 = FaceDetectionModelRunner::FaceDetectionModelRunner((__int64)v34, v35, &v39, a1);
  winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>::~IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>(&v47);
  if ( v29 )
    winrt::com_ptr<ITensorNative>::unconditional_release_ref(&v42);
  winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>::~IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>(&v43);
  winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>::~IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>(&v45);
  winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>::~IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>(&v46);
  FaceDetectionModelRunner::FaceDetectionModelConstants::~FaceDetectionModelConstants((FaceDetectionModelRunner::FaceDetectionModelConstants *)&v50);
  winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>::~IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>(&v56);
  winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>::~IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>(&v48);
  if ( v9 )
    winrt::com_ptr<ITensorNative>::unconditional_release_ref(&v49);
  return (struct FaceDetectionModelRunner *)v36;
}

```

## disassembly

```asm
0x180022ad0  mov     [rsp-8+arg_0], rbx
0x180022ad5  push    rbp
0x180022ad6  push    rsi
0x180022ad7  push    rdi
0x180022ad8  push    r14
0x180022ada  push    r15
0x180022adc  lea     rbp, [rsp-37h]
0x180022ae1  sub     rsp, 0D0h
0x180022ae8  mov     r14b, cl
0x180022aeb  xor     r15d, r15d
0x180022aee  mov     [rbp+57h+phModule], r15
0x180022af2  mov     [rbp+57h+pExceptionObject], r15d
0x180022af6  xorps   xmm0, xmm0
0x180022af9  movdqu  [rbp+57h+var_C0], xmm0
0x180022afe  lea     r8, [rbp+57h+phModule]; phModule
0x180022b02  lea     rdx, ?CreateModelRunner@FaceDetectionModelRunnerFactory@@SAPEAVFaceDetectionModelRunner@@_N@Z; lpModuleName
0x180022b09  lea     ecx, [r15+6]; dwFlags
0x180022b0d  call    cs:__imp_GetModuleHandleExW
0x180022b13  lea     rdx, [rbp+57h+pExceptionObject]
0x180022b17  mov     ecx, eax
0x180022b19  call    ??$check_bool@H@winrt@@YAHHAEBUslim_source_location@impl@0@@Z; winrt::check_bool<int>(int,winrt::impl::slim_source_location const &)
0x180022b1e  mov     [rbp+57h+pExceptionObject], r15d
0x180022b22  xorps   xmm0, xmm0
0x180022b25  movdqu  [rbp+57h+var_C0], xmm0
0x180022b2a  lea     rdx, [rbp+57h+pExceptionObject]
0x180022b2e  mov     rcx, [rbp+57h+phModule]
0x180022b32  call    ??$check_pointer@UHRSRC__@@@winrt@@YAPEAUHRSRC__@@PEAU1@AEBUslim_source_location@impl@0@@Z; winrt::check_pointer<HRSRC__>(HRSRC__ *,winrt::impl::slim_source_location const &)
0x180022b37  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Camera_FaceDetectionModelUpdate_55609719@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Camera_FaceDetectionModelUpdate_55609719@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Camera_FaceDetectionModelUpdate_55609719> `wil::Feature<__WilFeatureTraits_Feature_Camera_FaceDetectionModelUpdate_55609719>::GetImpl(void)'::`2'::impl
0x180022b3e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Camera_FaceDetectionModelUpdate_55609719@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Camera_FaceDetectionModelUpdate_55609719>::__private_IsEnabled(void)
0x180022b43  test    al, al
0x180022b45  jz      short loc_180022B75
0x180022b47  cmp     cs:byte_180160805, 20h ; ' '
0x180022b4e  jb      short loc_180022B6E
0x180022b50  lea     edx, [r15+0Ah]
0x180022b54  lea     r8, WPP_3819cc37a64338403add9ef0c33489c9_Traceguids
0x180022b5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b62  mov     rcx, [rcx+0D8h]
0x180022b69  call    WPP_SF_
0x180022b6e  mov     edx, 66h ; 'f'
0x180022b73  jmp     short loc_180022B7A
0x180022b75  mov     edx, 65h ; 'e'; lpName
0x180022b7a  mov     r8d, 0Ah; lpType
0x180022b80  mov     rcx, [rbp+57h+phModule]; hModule
0x180022b84  call    cs:__imp_FindResourceW
0x180022b8a  xorps   xmm0, xmm0
0x180022b8d  mov     rdi, rax
0x180022b90  mov     [rbp+57h+pExceptionObject], r15d
0x180022b94  movdqu  [rbp+57h+var_C0], xmm0
0x180022b99  lea     rdx, [rbp+57h+pExceptionObject]
0x180022b9d  mov     rcx, rax
0x180022ba0  call    ??$check_pointer@UHRSRC__@@@winrt@@YAPEAUHRSRC__@@PEAU1@AEBUslim_source_location@impl@0@@Z; winrt::check_pointer<HRSRC__>(HRSRC__ *,winrt::impl::slim_source_location const &)
0x180022ba5  mov     rdx, rdi; hResInfo
0x180022ba8  mov     rcx, [rbp+57h+phModule]; hModule
0x180022bac  call    cs:__imp_LoadResource
0x180022bb2  mov     rbx, rax
0x180022bb5  mov     [rbp+57h+pExceptionObject], r15d
0x180022bb9  xorps   xmm0, xmm0
0x180022bbc  movdqu  [rbp+57h+var_C0], xmm0
0x180022bc1  lea     rdx, [rbp+57h+pExceptionObject]
0x180022bc5  mov     rcx, rax
0x180022bc8  call    ??$check_pointer@UHRSRC__@@@winrt@@YAPEAUHRSRC__@@PEAU1@AEBUslim_source_location@impl@0@@Z; winrt::check_pointer<HRSRC__>(HRSRC__ *,winrt::impl::slim_source_location const &)
0x180022bcd  mov     rdx, rdi; hResInfo
0x180022bd0  mov     rcx, [rbp+57h+phModule]; hModule
0x180022bd4  call    cs:__imp_SizeofResource
0x180022bda  mov     esi, eax
0x180022bdc  mov     rcx, rbx; hResData
0x180022bdf  call    cs:__imp_LockResource
0x180022be5  mov     rbx, rax
0x180022be8  mov     [rbp+57h+pExceptionObject], r15d
0x180022bec  xorps   xmm0, xmm0
0x180022bef  movdqu  [rbp+57h+var_C0], xmm0
0x180022bf4  lea     rdx, [rbp+57h+pExceptionObject]
0x180022bf8  mov     rcx, rax
0x180022bfb  call    ??$check_pointer@UHRSRC__@@@winrt@@YAPEAUHRSRC__@@PEAU1@AEBUslim_source_location@impl@0@@Z; winrt::check_pointer<HRSRC__>(HRSRC__ *,winrt::impl::slim_source_location const &)
0x180022c00  mov     [rbp+57h+var_78], r15
0x180022c04  mov     [rbp+57h+var_80], r15
0x180022c08  mov     edx, esi; cbInit
0x180022c0a  mov     rcx, rbx; pInit
0x180022c0d  call    cs:__imp_SHCreateMemStream
0x180022c13  mov     rdx, rax
0x180022c16  lea     rcx, [rbp+57h+var_78]
0x180022c1a  call    ?attach@?$com_ptr@UIStream@@@winrt@@QEAAXPEAUIStream@@@Z; winrt::com_ptr<IStream>::attach(IStream *)
0x180022c1f  mov     [rbp+57h+pExceptionObject], r15d
0x180022c23  xorps   xmm0, xmm0
0x180022c26  movdqu  [rbp+57h+var_C0], xmm0
0x180022c2b  lea     rdx, [rbp+57h+pExceptionObject]
0x180022c2f  mov     rdi, [rbp+57h+var_78]
0x180022c33  mov     rcx, rdi
0x180022c36  call    ??$check_pointer@UHRSRC__@@@winrt@@YAPEAUHRSRC__@@PEAU1@AEBUslim_source_location@impl@0@@Z; winrt::check_pointer<HRSRC__>(HRSRC__ *,winrt::impl::slim_source_location const &)
0x180022c3b  mov     [rbp+57h+pExceptionObject], r15d
0x180022c3f  xorps   xmm0, xmm0
0x180022c42  movdqu  [rbp+57h+var_C0], xmm0
0x180022c47  lea     rcx, [rbp+57h+var_80]; this
0x180022c4b  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x180022c50  mov     r9, rax
0x180022c53  lea     r8, ??$guid_v@UIRandomAccessStream@Streams@Storage@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Storage::Streams::IRandomAccessStream>
0x180022c5a  xor     edx, edx
0x180022c5c  mov     rcx, rdi
0x180022c5f  call    cs:__imp_CreateRandomAccessStreamOverStream
0x180022c65  lea     r8, [rbp+57h+pExceptionObject]
0x180022c69  mov     edx, eax
0x180022c6b  lea     rcx, [rbp+57h+arg_8]
0x180022c6f  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180022c74  cmp     cs:byte_180160805, 20h ; ' '
0x180022c7b  jb      short loc_180022C9F
0x180022c7d  mov     edx, 0Bh
0x180022c82  mov     r9d, esi
0x180022c85  lea     r8, WPP_3819cc37a64338403add9ef0c33489c9_Traceguids
0x180022c8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c93  mov     rcx, [rcx+0D8h]
0x180022c9a  call    WPP_SF_d
0x180022c9f  lea     rdx, [rbp+57h+var_80]
0x180022ca3  lea     rcx, [rbp+57h+var_B0]; struct winrt::Windows::Storage::Streams::IRandomAccessStream *
0x180022ca7  call    ?CreateFromStream@RandomAccessStreamReference@Streams@Storage@Windows@winrt@@SA@AEBUIRandomAccessStream@2345@@Z; winrt::Windows::Storage::Streams::RandomAccessStreamReference::CreateFromStream(winrt::Windows::Storage::Streams::IRandomAccessStream const &)
0x180022cac  nop
0x180022cad  mov     [rbp+57h+arg_8], rax
0x180022cb1  lea     rax, qword_18015F9E8
0x180022cb8  mov     [rbp+57h+var_A0], rax
0x180022cbc  lock inc cs:qword_18015F9E8
0x180022cc4  cmp     cs:??$factory_cache_entry_v@ULearningModel@MachineLearning@AI@Windows@winrt@@UILearningModelStatics@2345@@impl@winrt@@3U?$factory_cache_entry@ULearningModel@MachineLearning@AI@Windows@winrt@@UILearningModelStatics@2345@@12@A, r15; factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModel,winrt::Windows::AI::MachineLearning::ILearningModelStatics>::winrt::factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModel,winrt::Windows::AI::MachineLearning::ILearningModelStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::AI::MachineLearning::LearningModel,winrt::Windows::AI::MachineLearning::ILearningModelStatics>
0x180022ccb  jz      short loc_180022CEC
0x180022ccd  lea     r8, ??$factory_cache_entry_v@ULearningModel@MachineLearning@AI@Windows@winrt@@UILearningModelStatics@2345@@impl@winrt@@3U?$factory_cache_entry@ULearningModel@MachineLearning@AI@Windows@winrt@@UILearningModelStatics@2345@@12@A; factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModel,winrt::Windows::AI::MachineLearning::ILearningModelStatics>::winrt::factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModel,winrt::Windows::AI::MachineLearning::ILearningModelStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::AI::MachineLearning::LearningModel,winrt::Windows::AI::MachineLearning::ILearningModelStatics>
0x180022cd4  lea     rdx, [rbp+57h+arg_18]
0x180022cd8  lea     rcx, [rbp+57h+arg_8]
0x180022cdc  call    ??R_lambda_a97271d0ed239d0f5a7f0c77aad64038_@@QEBA@AEBUILearningModelStatics@MachineLearning@AI@Windows@winrt@@@Z; _lambda_a97271d0ed239d0f5a7f0c77aad64038_::operator()(winrt::Windows::AI::MachineLearning::ILearningModelStatics const &)
0x180022ce1  nop
0x180022ce2  lock dec cs:qword_18015F9E8
0x180022cea  jmp     short loc_180022D02
0x180022cec  lock dec cs:qword_18015F9E8
0x180022cf4  lea     r8, [rbp+57h+arg_8]
0x180022cf8  lea     rdx, [rbp+57h+arg_18]
0x180022cfc  call    ??$call@AEAV_lambda_a97271d0ed239d0f5a7f0c77aad64038_@@@?$factory_cache_entry@ULearningModel@MachineLearning@AI@Windows@winrt@@UILearningModelStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_a97271d0ed239d0f5a7f0c77aad64038_@@@Z
0x180022d01  nop
0x180022d02  lea     rcx, [rbp+57h+var_B0]
0x180022d06  call    ??1?$IAsyncOperation@ULearningModel@MachineLearning@AI@Windows@winrt@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>::~IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>(void)
0x180022d0b  mov     [rbp+57h+arg_8], r15
0x180022d0f  lea     rdx, [rbp+57h+arg_8]
0x180022d13  lea     rcx, [rbp+57h+arg_18]
0x180022d17  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180022d1c  test    al, al
0x180022d1e  jnz     loc_180023120
0x180022d24  xorps   xmm0, xmm0
0x180022d27  movdqu  [rbp+57h+var_70], xmm0
0x180022d2c  xorps   xmm1, xmm1
0x180022d2f  movdqu  [rbp+57h+var_60], xmm1
0x180022d34  lea     rdx, [rbp+57h+var_88]
0x180022d38  lea     rcx, [rbp+57h+arg_18]
0x180022d3c  call    ?InputFeatures@?$consume_Windows_AI_MachineLearning_ILearningModel@UILearningModel@MachineLearning@AI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_AI_MachineLearning_ILearningModel<winrt::Windows::AI::MachineLearning::ILearningModel>::InputFeatures(void)
0x180022d41  nop
0x180022d42  lea     rdx, [rbp+57h+var_B0]
0x180022d46  mov     rcx, rax
0x180022d49  call    ?GetAt@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@UILearningModelFeatureDescriptor@MachineLearning@AI@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UILearningModelFeatureDescriptor@MachineLearning@AI@45@@impl@winrt@@QEBA@I@Z; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::AI::MachineLearning::ILearningModelFeatureDescriptor>,winrt::Windows::AI::MachineLearning::ILearningModelFeatureDescriptor>::GetAt(uint)
0x180022d4e  nop
0x180022d4f  mov     rcx, [rax]
0x180022d52  test    rcx, rcx
0x180022d55  jnz     short loc_180022D5D
0x180022d57  mov     [rbp+57h+var_90], r15
0x180022d5b  jmp     short loc_180022D9A
0x180022d5d  mov     [rbp+57h+var_D0], r15
0x180022d61  mov     [rbp+57h+pExceptionObject], r15d
0x180022d65  xorps   xmm0, xmm0
0x180022d68  movdqu  [rbp+57h+var_C0], xmm0
0x180022d6d  mov     rax, [rcx]
0x180022d70  lea     r8, [rbp+57h+var_D0]
0x180022d74  lea     rdx, ??$guid_v@UITensorFeatureDescriptor@MachineLearning@AI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::AI::MachineLearning::ITensorFeatureDescriptor>
0x180022d7b  mov     rax, [rax]
0x180022d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d83  lea     r8, [rbp+57h+pExceptionObject]
0x180022d87  mov     edx, eax
0x180022d89  lea     rcx, [rbp+57h+arg_8]
0x180022d8d  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180022d92  mov     rax, [rbp+57h+var_D0]
0x180022d96  mov     [rbp+57h+var_90], rax
0x180022d9a  lea     rcx, [rbp+57h+var_B0]
0x180022d9e  call    ??1?$IAsyncOperation@ULearningModel@MachineLearning@AI@Windows@winrt@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>::~IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>(void)
0x180022da3  nop
0x180022da4  lea     rcx, [rbp+57h+var_88]
0x180022da8  call    ??1?$IAsyncOperation@ULearningModel@MachineLearning@AI@Windows@winrt@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>::~IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>(void)
0x180022dad  lea     rdx, [rbp+57h+arg_8]
0x180022db1  lea     rcx, [rbp+57h+var_90]
0x180022db5  call    ?Name@?$consume_Windows_AI_MachineLearning_ILearningModelFeatureDescriptor@UTensorFeatureDescriptor@MachineLearning@AI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_AI_MachineLearning_ILearningModelFeatureDescriptor<winrt::Windows::AI::MachineLearning::TensorFeatureDescriptor>::Name(void)
0x180022dba  lea     rcx, [rbp+57h+var_70]
0x180022dbe  cmp     rcx, rax
0x180022dc1  jz      short loc_180022DD2
0x180022dc3  mov     rdx, [rax]
0x180022dc6  mov     [rax], r15
0x180022dc9  lea     rcx, [rbp+57h+var_70]
0x180022dcd  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x180022dd2  lea     rcx, [rbp+57h+arg_8]
0x180022dd6  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180022ddb  lea     rdx, [rbp+57h+arg_8]
0x180022ddf  lea     rcx, [rbp+57h+var_90]
0x180022de3  call    ?Shape@?$consume_Windows_AI_MachineLearning_ITensorFeatureDescriptor@UITensorFeatureDescriptor@MachineLearning@AI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_AI_MachineLearning_ITensorFeatureDescriptor<winrt::Windows::AI::MachineLearning::ITensorFeatureDescriptor>::Shape(void)
0x180022de8  mov     rbx, rax
0x180022deb  lea     rax, [rbp+57h+var_60]
0x180022def  cmp     rax, rbx
0x180022df2  jz      short loc_180022E0D
0x180022df4  cmp     qword ptr [rbp+57h+var_60], r15
0x180022df8  jz      short loc_180022E03
0x180022dfa  lea     rcx, [rbp+57h+var_60]
0x180022dfe  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180022e03  mov     rcx, [rbx]
0x180022e06  mov     [rbx], r15
0x180022e09  mov     qword ptr [rbp+57h+var_60], rcx
0x180022e0d  lea     rcx, [rbp+57h+arg_8]
0x180022e11  call    ??1?$IAsyncOperation@ULearningModel@MachineLearning@AI@Windows@winrt@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>::~IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>(void)
0x180022e16  lea     rdx, [rbp+57h+var_A0]
0x180022e1a  lea     rcx, [rbp+57h+arg_18]
0x180022e1e  call    ?OutputFeatures@?$consume_Windows_AI_MachineLearning_ILearningModel@UILearningModel@MachineLearning@AI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_AI_MachineLearning_ILearningModel<winrt::Windows::AI::MachineLearning::ILearningModel>::OutputFeatures(void)
0x180022e23  nop
0x180022e24  lea     rdx, [rbp+57h+var_50]
0x180022e28  mov     rcx, rax
0x180022e2b  call    ?GetAt@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@UILearningModelFeatureDescriptor@MachineLearning@AI@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UILearningModelFeatureDescriptor@MachineLearning@AI@45@@impl@winrt@@QEBA@I@Z; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::AI::MachineLearning::ILearningModelFeatureDescriptor>,winrt::Windows::AI::MachineLearning::ILearningModelFeatureDescriptor>::GetAt(uint)
0x180022e30  nop
0x180022e31  mov     rcx, [rax]
0x180022e34  test    rcx, rcx
0x180022e37  jnz     short loc_180022E3F
0x180022e39  mov     [rbp+57h+var_98], r15
0x180022e3d  jmp     short loc_180022E7C
0x180022e3f  mov     [rbp+57h+var_D0], r15
0x180022e43  mov     [rbp+57h+pExceptionObject], r15d
0x180022e47  xorps   xmm0, xmm0
0x180022e4a  movdqu  [rbp+57h+var_C0], xmm0
0x180022e4f  mov     rax, [rcx]
0x180022e52  lea     r8, [rbp+57h+var_D0]
0x180022e56  lea     rdx, ??$guid_v@UITensorFeatureDescriptor@MachineLearning@AI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::AI::MachineLearning::ITensorFeatureDescriptor>
0x180022e5d  mov     rax, [rax]
0x180022e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e65  lea     r8, [rbp+57h+pExceptionObject]
0x180022e69  mov     edx, eax
0x180022e6b  lea     rcx, [rbp+57h+arg_8]
0x180022e6f  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180022e74  mov     rax, [rbp+57h+var_D0]
0x180022e78  mov     [rbp+57h+var_98], rax
0x180022e7c  lea     rcx, [rbp+57h+var_50]
0x180022e80  call    ??1?$IAsyncOperation@ULearningModel@MachineLearning@AI@Windows@winrt@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>::~IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>(void)
0x180022e85  nop
0x180022e86  lea     rcx, [rbp+57h+var_A0]
0x180022e8a  call    ??1?$IAsyncOperation@ULearningModel@MachineLearning@AI@Windows@winrt@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>::~IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>(void)
0x180022e8f  lea     rdx, [rbp+57h+arg_8]
0x180022e93  lea     rcx, [rbp+57h+var_98]
0x180022e97  call    ?Name@?$consume_Windows_AI_MachineLearning_ILearningModelFeatureDescriptor@UTensorFeatureDescriptor@MachineLearning@AI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_AI_MachineLearning_ILearningModelFeatureDescriptor<winrt::Windows::AI::MachineLearning::TensorFeatureDescriptor>::Name(void)
0x180022e9c  lea     rcx, [rbp+57h+var_70+8]
0x180022ea0  cmp     rcx, rax
0x180022ea3  jz      short loc_180022EB4
0x180022ea5  mov     rdx, [rax]
0x180022ea8  mov     [rax], r15
0x180022eab  lea     rcx, [rbp+57h+var_70+8]
0x180022eaf  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x180022eb4  lea     rcx, [rbp+57h+arg_8]
0x180022eb8  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180022ebd  lea     rdx, [rbp+57h+arg_8]
0x180022ec1  lea     rcx, [rbp+57h+var_98]
0x180022ec5  call    ?Shape@?$consume_Windows_AI_MachineLearning_ITensorFeatureDescriptor@UITensorFeatureDescriptor@MachineLearning@AI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_AI_MachineLearning_ITensorFeatureDescriptor<winrt::Windows::AI::MachineLearning::ITensorFeatureDescriptor>::Shape(void)
0x180022eca  mov     rbx, rax
0x180022ecd  lea     rax, [rbp+57h+var_60+8]
0x180022ed1  cmp     rax, rbx
0x180022ed4  jz      short loc_180022EEF
0x180022ed6  cmp     qword ptr [rbp+57h+var_60+8], r15
0x180022eda  jz      short loc_180022EE5
0x180022edc  lea     rcx, [rbp+57h+var_60+8]
0x180022ee0  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180022ee5  mov     rcx, [rbx]
0x180022ee8  mov     [rbx], r15
0x180022eeb  mov     qword ptr [rbp+57h+var_60+8], rcx
0x180022eef  lea     rcx, [rbp+57h+arg_8]
0x180022ef3  call    ??1?$IAsyncOperation@ULearningModel@MachineLearning@AI@Windows@winrt@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>::~IAsyncOperation<winrt::Windows::AI::MachineLearning::LearningModel>(void)
0x180022ef8  lea     rcx, [rbp+57h+var_A8]; this
0x180022efc  call    ??0LearningModelSessionOptions@MachineLearning@AI@Windows@winrt@@QEAA@XZ; winrt::Windows::AI::MachineLearning::LearningModelSessionOptions::LearningModelSessionOptions(void)
0x180022f01  nop
0x180022f02  lea     rcx, [rbp+57h+var_A8]
0x180022f06  call    ?CloseModelOnSessionCreation@?$consume_Windows_AI_MachineLearning_ILearningModelSessionOptions2@ULearningModelSessionOptions@MachineLearning@AI@Windows@winrt@@@impl@winrt@@QEBA@_N@Z; winrt::impl::consume_Windows_AI_MachineLearning_ILearningModelSessionOptions2<winrt::Windows::AI::MachineLearning::LearningModelSessionOptions>::CloseModelOnSessionCreation(bool)
0x180022f0b  mov     rcx, [rbp+57h+var_A8]
0x180022f0f  test    rcx, rcx
0x180022f12  jnz     short loc_180022F1C
0x180022f14  mov     rbx, r15
0x180022f17  mov     r8, r15
0x180022f1a  jmp     short loc_180022F41
0x180022f1c  mov     [rbp+57h+arg_8], r15
0x180022f20  mov     rax, [rcx]
0x180022f23  lea     r8, [rbp+57h+arg_8]
0x180022f27  lea     rdx, ??$guid_v@UILearningModelSessionOptionsNative1@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<ILearningModelSessionOptionsNative1>
0x180022f2e  mov     rax, [rax]
0x180022f31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f36  mov     rbx, [rbp+57h+arg_8]
0x180022f3a  mov     r8, rbx
0x180022f3d  mov     rcx, [rbp+57h+var_A8]
0x180022f41  mov     [rbp+57h+var_B0], rbx
0x180022f45  test    r8, r8
0x180022f48  jz      short loc_180022F8C
0x180022f4a  mov     rax, [r8]
0x180022f4d  xor     edx, edx
0x180022f4f  mov     rcx, r8
0x180022f52  mov     rax, [rax+18h]
0x180022f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f5b  cmp     cs:byte_180160805, 20h ; ' '
0x180022f62  jb      loc_180023022
0x180022f68  mov     edx, 0Ch
0x180022f6d  lea     r8, WPP_3819cc37a64338403add9ef0c33489c9_Traceguids
0x180022f74  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
