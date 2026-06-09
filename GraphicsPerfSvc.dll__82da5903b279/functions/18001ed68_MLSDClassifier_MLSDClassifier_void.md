# MLSDClassifier::MLSDClassifier(void)

- ea: `0x18001ed68`
- end: `0x18001f2a5`
- name: `??0MLSDClassifier@@AEAA@XZ`
- size: `1341`
- prototype: `MLSDClassifier *__fastcall(MLSDClassifier *__hidden this)`
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000f5c8`

## callees

- `0x180001754`
- `0x1800047fc`
- `0x18000d67c`
- `0x18001e628`
- `0x18001e694`
- `0x18001e7c8`
- `0x18001eb90`
- `0x18001ec04`
- `0x18001ec7c`
- `0x18001ecf0`
- `0x18001ed68`
- `0x18001f340`
- `0x18001f864`
- `0x18001f90c`
- `0x18001f9f4`
- `0x180020454`
- `0x180020710`
- `0x1800207c4`
- `0x180020c70`
- `0x180020d5c`
- `0x180020dd0`
- `0x1800211a8`
- `0x180021674`
- `0x180021730`
- `0x1800217c4`
- `0x180021880`
- `0x180021954`
- `0x1800219e4`
- `0x180022a38`
- `0x180031010`

## import_xrefs

- `msvcp_win!_Thrd_hardware_concurrency` at `0x18001edbb`
- `msvcp_win!_Thrd_hardware_concurrency` at `0x18001edbb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18001eefc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18001eefc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef41`

## string_xrefs

- `0x18001eef5`: `onnxruntime.dll`
- `0x18001ef1a`: `OnnxRuntime.dll not detected during startup. MLSD will not be initalized.`

## pseudocode

```c
MLSDClassifier *__fastcall MLSDClassifier::MLSDClassifier(MLSDClassifier *this)
{
  __int64 *v1; // rbx
  int v2; // eax
  __int64 v3; // rcx
  unsigned int v4; // eax
  signed int LastError; // eax
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 *AsVectorView; // rax
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 *v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rbx
  __int64 v16; // rcx
  unsigned int v17; // eax
  __int64 v18; // rax
  __int64 *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rdx
  std::_Ref_count_base *v22; // rcx
  __int64 *v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rdx
  std::_Ref_count_base *v26; // rcx
  const struct winrt::impl::slim_source_location *v28; // rax
  const winrt::hresult_error *v29; // rbx
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 *v32; // [rsp+20h] [rbp-98h] BYREF
  __int64 v33; // [rsp+28h] [rbp-90h]
  HMODULE Library; // [rsp+30h] [rbp-88h] BYREF
  void (__fastcall ***v35)(_QWORD, __int64 *, MLSDClassifier **); // [rsp+38h] [rbp-80h] BYREF
  __int64 (__fastcall ***v36)(_QWORD, __int64 *, __int64 *); // [rsp+40h] [rbp-78h] BYREF
  _BYTE v37[8]; // [rsp+48h] [rbp-70h] BYREF
  int v38; // [rsp+50h] [rbp-68h] BYREF
  __int128 v39; // [rsp+58h] [rbp-60h]
  int *v40; // [rsp+68h] [rbp-50h]
  const winrt::hresult_error *v41; // [rsp+70h] [rbp-48h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+78h] [rbp-40h] BYREF
  MLSDClassifier *v43; // [rsp+C0h] [rbp+8h] BYREF
  __int64 v44; // [rsp+C8h] [rbp+10h] BYREF
  char v45; // [rsp+D0h] [rbp+18h] BYREF
  char v46; // [rsp+D8h] [rbp+20h] BYREF

  v43 = this;
  v40 = &`MLSDClassifier::GetInstance'::`2'::instance;
  `MLSDClassifier::GetInstance'::`2'::instance = 0;
  xmmword_180042D18 = 0;
  xmmword_180042D28 = 0;
  qword_180042D38 = 0;
  qword_180042D40 = 0;
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_180042080);
  if ( _Thrd_hardware_concurrency() >= 4 )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      winrt::Windows::Storage::Streams::InMemoryRandomAccessStream::InMemoryRandomAccessStream((struct IUnknown *)&v35);
      if ( v35 )
      {
        v43 = 0;
        (**v35)(v35, winrt::impl::guid_v<winrt::Windows::Storage::Streams::IOutputStream>, &v43);
        Library = (HMODULE)v43;
      }
      else
      {
        Library = 0;
      }
      winrt::Windows::Storage::Streams::DataWriter::DataWriter(
        (winrt::Windows::Storage::Streams::DataWriter *)&v46,
        (const struct winrt::Windows::Storage::Streams::IOutputStream *)&Library);
      winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel((winrt::Windows::AI::MachineLearning::ILearningModel *)&Library);
      v32 = qword_1800351E0;
      LODWORD(v33) = 12549;
      HIDWORD(v33) = DWORD1(v39);
      winrt::impl::consume_Windows_Storage_Streams_IDataWriter<winrt::Windows::Storage::Streams::IDataWriter>::WriteBytes(
        &v46,
        &v32);
      v1 = (__int64 *)winrt::impl::consume_Windows_Storage_Streams_IDataWriter<winrt::Windows::Storage::Streams::IDataWriter>::StoreAsync(
                        &v46,
                        &v32);
      v2 = winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperation<unsigned int>>::Status(v1);
      if ( !v2 )
        v2 = ((__int64 (__fastcall *)(__int64 *))winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<unsigned int>>)(v1);
      if ( v2 == 2 )
      {
        v28 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(&v38);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)pExceptionObject, v28);
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      LODWORD(v43) = 0;
      v3 = *v1;
      v38 = 0;
      v39 = 0;
      v4 = (*(__int64 (__fastcall **)(__int64, MLSDClassifier **))(*(_QWORD *)v3 + 64LL))(v3, &v43);
      winrt::check_hresult(&v44, v4, &v38);
      winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel((winrt::Windows::AI::MachineLearning::ILearningModel *)&v32);
      winrt::Windows::Storage::Streams::RandomAccessStreamReference::CreateFromStream((const struct winrt::Windows::Storage::Streams::IRandomAccessStream *)v37);
      Library = LoadLibraryExA("onnxruntime.dll", 0, 0x800u);
      if ( Library )
      {
        winrt::Windows::AI::MachineLearning::LearningModel::LoadFromStream((const struct winrt::Windows::Storage::Streams::IRandomAccessStreamReference *)&v45);
        v7 = winrt::impl::consume_Windows_AI_MachineLearning_ILearningModel<winrt::Windows::AI::MachineLearning::ILearningModel>::InputFeatures(
               &v45,
               &v32);
        v8 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::AI::MachineLearning::ILearningModelFeatureDescriptor>,winrt::Windows::AI::MachineLearning::ILearningModelFeatureDescriptor>::GetAt(
               v7,
               &v44);
        AsVectorView = (__int64 *)winrt::impl::consume_Windows_AI_MachineLearning_ITensorFloat<winrt::Windows::AI::MachineLearning::ITensorFloat>::GetAsVectorView(
                                    v8,
                                    &v43);
        if ( &qword_180042D38 != AsVectorView )
        {
          v10 = *AsVectorView;
          *AsVectorView = 0;
          winrt::handle_type<winrt::impl::hstring_traits>::close(&qword_180042D38);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&qword_180042D38);
          qword_180042D38 = v10;
        }
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v43);
        winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel((winrt::Windows::AI::MachineLearning::ILearningModel *)&v44);
        winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel((winrt::Windows::AI::MachineLearning::ILearningModel *)&v32);
        v11 = winrt::impl::consume_Windows_AI_MachineLearning_ILearningModel<winrt::Windows::AI::MachineLearning::ILearningModel>::OutputFeatures(
                &v45,
                &v32);
        v12 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::AI::MachineLearning::ILearningModelFeatureDescriptor>,winrt::Windows::AI::MachineLearning::ILearningModelFeatureDescriptor>::GetAt(
                v11,
                &v44);
        v13 = (__int64 *)winrt::impl::consume_Windows_AI_MachineLearning_ITensorFloat<winrt::Windows::AI::MachineLearning::ITensorFloat>::GetAsVectorView(
                           v12,
                           &v43);
        if ( &qword_180042D40 != v13 )
        {
          v14 = *v13;
          *v13 = 0;
          winrt::handle_type<winrt::impl::hstring_traits>::close(&qword_180042D40);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&qword_180042D40);
          qword_180042D40 = v14;
        }
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v43);
        winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel((winrt::Windows::AI::MachineLearning::ILearningModel *)&v44);
        winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel((winrt::Windows::AI::MachineLearning::ILearningModel *)&v32);
        winrt::Windows::AI::MachineLearning::LearningModelSessionOptions::LearningModelSessionOptions((winrt::Windows::AI::MachineLearning::LearningModelSessionOptions *)&v36);
        if ( v36 )
        {
          v44 = 0;
          v38 = 0;
          v39 = 0;
          v17 = (**v36)(v36, winrt::impl::guid_v<ILearningModelSessionOptionsNative>, &v44);
          winrt::check_hresult(&v43, v17, &v38);
          v15 = v44;
          v16 = v44;
        }
        else
        {
          v15 = 0;
          v16 = 0;
        }
        v44 = v15;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 24LL))(v16, 1);
        LODWORD(v43) = 0;
        v18 = winrt::Windows::AI::MachineLearning::LearningModelDevice::LearningModelDevice(
                (winrt::Windows::AI::MachineLearning::LearningModelDevice *)&v32,
                (const enum winrt::Windows::AI::MachineLearning::LearningModelDeviceKind *)&v43);
        v19 = (__int64 *)std::make_shared<winrt::Windows::AI::MachineLearning::LearningModelSession,winrt::Windows::AI::MachineLearning::LearningModel &,winrt::Windows::AI::MachineLearning::LearningModelDevice,winrt::Windows::AI::MachineLearning::LearningModelSessionOptions &>(
                           &v38,
                           &v45,
                           v18,
                           &v36,
                           v32,
                           v33,
                           Library);
        v20 = *v19;
        v21 = v19[1];
        *v19 = 0;
        v19[1] = 0;
        *(_QWORD *)&xmmword_180042D18 = v20;
        v22 = (std::_Ref_count_base *)*((_QWORD *)&xmmword_180042D18 + 1);
        *((_QWORD *)&xmmword_180042D18 + 1) = v21;
        if ( v22 )
          std::_Ref_count_base::_Decref(v22);
        if ( (_QWORD)v39 )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)v39);
        winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel((winrt::Windows::AI::MachineLearning::ILearningModel *)&v32);
        v23 = (__int64 *)std::make_shared<winrt::Windows::AI::MachineLearning::LearningModelBinding,winrt::Windows::AI::MachineLearning::LearningModelSession &>(
                           &v38,
                           xmmword_180042D18);
        v24 = *v23;
        v25 = v23[1];
        *v23 = 0;
        v23[1] = 0;
        *(_QWORD *)&xmmword_180042D28 = v24;
        v26 = (std::_Ref_count_base *)*((_QWORD *)&xmmword_180042D28 + 1);
        *((_QWORD *)&xmmword_180042D28 + 1) = v25;
        if ( v26 )
          std::_Ref_count_base::_Decref(v26);
        if ( (_QWORD)v39 )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)v39);
        `MLSDClassifier::GetInstance'::`2'::instance = 1;
        if ( v15 )
          winrt::com_ptr<ILearningModelSessionOptionsNative>::unconditional_release_ref(&v44);
        winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel((winrt::Windows::AI::MachineLearning::ILearningModel *)&v36);
        winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel((winrt::Windows::AI::MachineLearning::ILearningModel *)&v45);
        wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&Library);
        winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel((winrt::Windows::AI::MachineLearning::ILearningModel *)v37);
        winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel((winrt::Windows::AI::MachineLearning::ILearningModel *)&v46);
        winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel((winrt::Windows::AI::MachineLearning::ILearningModel *)&v35);
      }
      else
      {
        `MLSDClassifier::GetInstance'::`2'::instance = -1;
        v32 = (__int64 *)L"OnnxRuntime.dll not detected during startup. MLSD will not be initalized.";
        v33 = 73;
        winrt::hstring::hstring(&v43, &v32);
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        MLSDClassifier::LogDiagnostic(v6, (unsigned int)LastError, &v43);
        wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&Library);
        winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel((winrt::Windows::AI::MachineLearning::ILearningModel *)v37);
        winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel((winrt::Windows::AI::MachineLearning::ILearningModel *)&v46);
        winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel((winrt::Windows::AI::MachineLearning::ILearningModel *)&v35);
      }
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &winrt::hresult_error `RTTI Type Descriptor', &v41) )
      {
        `MLSDClassifier::GetInstance'::`2'::instance = -1;
        v29 = v41;
        v30 = winrt::hresult_error::message(v41, &v43);
        MLSDClassifier::LogDiagnostic(v31, *((unsigned int *)v29 + 3), v30);
        __eh34_try_continuation(0, &winrt::hresult_error `RTTI Type Descriptor', &loc_18001F264);
      }
    }
  }
  return (MLSDClassifier *)&`MLSDClassifier::GetInstance'::`2'::instance;
}

```

## disassembly

```asm
0x18001ed68  mov     [rsp+arg_0], rcx
0x18001ed6d  push    rbx
0x18001ed6e  push    rsi
0x18001ed6f  push    rdi
0x18001ed70  push    r14
0x18001ed72  sub     rsp, 98h
0x18001ed79  xor     esi, esi
0x18001ed7b  lea     rdi, ?instance@?1??GetInstance@MLSDClassifier@@SAAEAV2@XZ@4V2@A; MLSDClassifier `MLSDClassifier::GetInstance(void)'::`2'::instance
0x18001ed82  mov     [rsp+0B8h+var_50], rdi
0x18001ed87  mov     cs:?instance@?1??GetInstance@MLSDClassifier@@SAAEAV2@XZ@4V2@A, esi; MLSDClassifier `MLSDClassifier::GetInstance(void)'::`2'::instance
0x18001ed8d  xorps   xmm0, xmm0
0x18001ed90  movdqu  cs:xmmword_180042D18, xmm0
0x18001ed98  movdqu  cs:xmmword_180042D28, xmm0
0x18001eda0  mov     cs:qword_180042D38, rsi
0x18001eda7  mov     cs:qword_180042D40, rsi
0x18001edae  lea     rcx, dword_180042080; CallbackContext
0x18001edb5  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001edba  nop
0x18001edbb  call    cs:__imp__Thrd_hardware_concurrency
0x18001edc1  cmp     eax, 4
0x18001edc4  jnb     short loc_18001EDCB
0x18001edc6  jmp     loc_18001F26B
0x18001edcb  lea     rcx, [rsp+0B8h+var_80]; this
0x18001edd0  call    ??0InMemoryRandomAccessStream@Streams@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::Streams::InMemoryRandomAccessStream::InMemoryRandomAccessStream(void)
0x18001edd5  nop
0x18001edd6  mov     rcx, [rsp+0B8h+var_80]
0x18001eddb  test    rcx, rcx
0x18001edde  jnz     short loc_18001EDE7
0x18001ede0  mov     [rsp+0B8h+var_88], rsi
0x18001ede5  jmp     short loc_18001EE16
0x18001ede7  mov     [rsp+0B8h+arg_0], rsi
0x18001edef  mov     rax, [rcx]
0x18001edf2  lea     r8, [rsp+0B8h+arg_0]
0x18001edfa  lea     rdx, ??$guid_v@UIOutputStream@Streams@Storage@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Storage::Streams::IOutputStream>
0x18001ee01  mov     rax, [rax]
0x18001ee04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee09  mov     rax, [rsp+0B8h+arg_0]
0x18001ee11  mov     [rsp+0B8h+var_88], rax
0x18001ee16  lea     rdx, [rsp+0B8h+var_88]; struct winrt::Windows::Storage::Streams::IOutputStream *
0x18001ee1b  lea     rcx, [rsp+0B8h+arg_18]; this
0x18001ee23  call    ??0DataWriter@Streams@Storage@Windows@winrt@@QEAA@AEBUIOutputStream@1234@@Z; winrt::Windows::Storage::Streams::DataWriter::DataWriter(winrt::Windows::Storage::Streams::IOutputStream const &)
0x18001ee28  nop
0x18001ee29  lea     rcx, [rsp+0B8h+var_88]; this
0x18001ee2e  call    ??1ILearningModel@MachineLearning@AI@Windows@winrt@@QEAA@XZ; winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel(void)
0x18001ee33  lea     rax, qword_1800351E0
0x18001ee3a  mov     [rsp+0B8h+var_98], rax
0x18001ee3f  mov     dword ptr [rsp+0B8h+var_90], 3105h
0x18001ee47  mov     eax, [rsp+0B8h+var_5C]
0x18001ee4b  mov     dword ptr [rsp+0B8h+var_90+4], eax
0x18001ee4f  lea     rdx, [rsp+0B8h+var_98]
0x18001ee54  lea     rcx, [rsp+0B8h+arg_18]
0x18001ee5c  call    ?WriteBytes@?$consume_Windows_Storage_Streams_IDataWriter@UIDataWriter@Streams@Storage@Windows@winrt@@@impl@winrt@@QEBA@U?$array_view@$$CBE@3@@Z; winrt::impl::consume_Windows_Storage_Streams_IDataWriter<winrt::Windows::Storage::Streams::IDataWriter>::WriteBytes(winrt::array_view<uchar const>)
0x18001ee61  lea     rdx, [rsp+0B8h+var_98]
0x18001ee66  lea     rcx, [rsp+0B8h+arg_18]
0x18001ee6e  call    ?StoreAsync@?$consume_Windows_Storage_Streams_IDataWriter@UIDataWriter@Streams@Storage@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Storage_Streams_IDataWriter<winrt::Windows::Storage::Streams::IDataWriter>::StoreAsync(void)
0x18001ee73  mov     rbx, rax
0x18001ee76  mov     rcx, rax
0x18001ee79  call    ?Status@?$consume_Windows_Foundation_IAsyncInfo@U?$IAsyncOperation@I@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperation<uint>>::Status(void)
0x18001ee7e  test    eax, eax
0x18001ee80  jnz     short loc_18001EE8A
0x18001ee82  mov     rcx, rbx
0x18001ee85  call    ??$wait_for_completed@U?$IAsyncOperation@I@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@I@Foundation@Windows@1@I@Z
0x18001ee8a  cmp     eax, 2
0x18001ee8d  jz      loc_18001F27B
0x18001ee93  mov     dword ptr [rsp+0B8h+arg_0], esi
0x18001ee9a  mov     rcx, [rbx]
0x18001ee9d  mov     [rsp+0B8h+var_68], esi
0x18001eea1  xorps   xmm0, xmm0
0x18001eea4  movdqu  xmmword ptr [rsp+58h], xmm0
0x18001eeaa  mov     rax, [rcx]
0x18001eead  lea     rdx, [rsp+0B8h+arg_0]
0x18001eeb5  mov     rax, [rax+40h]
0x18001eeb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eebe  lea     r8, [rsp+0B8h+var_68]
0x18001eec3  mov     edx, eax
0x18001eec5  lea     rcx, [rsp+0B8h+arg_8]
0x18001eecd  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001eed2  nop
0x18001eed3  lea     rcx, [rsp+0B8h+var_98]; this
0x18001eed8  call    ??1ILearningModel@MachineLearning@AI@Windows@winrt@@QEAA@XZ; winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel(void)
0x18001eedd  lea     rdx, [rsp+0B8h+var_80]
0x18001eee2  lea     rcx, [rsp+0B8h+var_70]; struct winrt::Windows::Storage::Streams::IRandomAccessStream *
0x18001eee7  call    ?CreateFromStream@RandomAccessStreamReference@Streams@Storage@Windows@winrt@@SA@AEBUIRandomAccessStream@2345@@Z; winrt::Windows::Storage::Streams::RandomAccessStreamReference::CreateFromStream(winrt::Windows::Storage::Streams::IRandomAccessStream const &)
0x18001eeec  nop
0x18001eeed  xor     edx, edx; hFile
0x18001eeef  mov     r8d, 800h; dwFlags
0x18001eef5  lea     rcx, aOnnxruntimeDll; "onnxruntime.dll"
0x18001eefc  call    cs:__imp_LoadLibraryExA
0x18001ef02  mov     [rsp+0B8h+var_88], rax
0x18001ef07  test    rax, rax
0x18001ef0a  jnz     loc_18001EF97
0x18001ef10  mov     cs:?instance@?1??GetInstance@MLSDClassifier@@SAAEAV2@XZ@4V2@A, 0FFFFFFFFh; MLSDClassifier `MLSDClassifier::GetInstance(void)'::`2'::instance
0x18001ef1a  lea     rax, aOnnxruntimeDll_0; "OnnxRuntime.dll not detected during sta"...
0x18001ef21  mov     [rsp+0B8h+var_98], rax
0x18001ef26  mov     [rsp+0B8h+var_90], 49h ; 'I'
0x18001ef2f  lea     rdx, [rsp+0B8h+var_98]
0x18001ef34  lea     rcx, [rsp+0B8h+arg_0]
0x18001ef3c  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001ef41  call    cs:__imp_GetLastError
0x18001ef47  test    eax, eax
0x18001ef49  jle     short loc_18001EF53
0x18001ef4b  movzx   eax, ax
0x18001ef4e  or      eax, 80070000h
0x18001ef53  lea     r8, [rsp+0B8h+arg_0]
0x18001ef5b  mov     edx, eax
0x18001ef5d  call    ?LogDiagnostic@MLSDClassifier@@AEAAXJUhstring@winrt@@@Z; MLSDClassifier::LogDiagnostic(long,winrt::hstring)
0x18001ef62  nop
0x18001ef63  lea     rcx, [rsp+0B8h+var_88]
0x18001ef68  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18001ef6d  nop
0x18001ef6e  lea     rcx, [rsp+0B8h+var_70]; this
0x18001ef73  call    ??1ILearningModel@MachineLearning@AI@Windows@winrt@@QEAA@XZ; winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel(void)
0x18001ef78  nop
0x18001ef79  lea     rcx, [rsp+0B8h+arg_18]; this
0x18001ef81  call    ??1ILearningModel@MachineLearning@AI@Windows@winrt@@QEAA@XZ; winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel(void)
0x18001ef86  nop
0x18001ef87  lea     rcx, [rsp+0B8h+var_80]; this
0x18001ef8c  call    ??1ILearningModel@MachineLearning@AI@Windows@winrt@@QEAA@XZ; winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel(void)
0x18001ef91  nop
0x18001ef92  jmp     loc_18001F26B
0x18001ef97  lea     rdx, [rsp+0B8h+var_70]
0x18001ef9c  lea     rcx, [rsp+0B8h+arg_10]; struct winrt::Windows::Storage::Streams::IRandomAccessStreamReference *
0x18001efa4  call    ?LoadFromStream@LearningModel@MachineLearning@AI@Windows@winrt@@SA@AEBUIRandomAccessStreamReference@Streams@Storage@45@@Z; winrt::Windows::AI::MachineLearning::LearningModel::LoadFromStream(winrt::Windows::Storage::Streams::IRandomAccessStreamReference const &)
0x18001efa9  nop
0x18001efaa  lea     rdx, [rsp+0B8h+var_98]
0x18001efaf  lea     rcx, [rsp+0B8h+arg_10]
0x18001efb7  call    ?InputFeatures@?$consume_Windows_AI_MachineLearning_ILearningModel@UILearningModel@MachineLearning@AI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_AI_MachineLearning_ILearningModel<winrt::Windows::AI::MachineLearning::ILearningModel>::InputFeatures(void)
0x18001efbc  nop
0x18001efbd  lea     rdx, [rsp+0B8h+arg_8]
0x18001efc5  mov     rcx, rax
0x18001efc8  call    ?GetAt@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@UILearningModelFeatureDescriptor@MachineLearning@AI@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UILearningModelFeatureDescriptor@MachineLearning@AI@45@@impl@winrt@@QEBA@I@Z; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::AI::MachineLearning::ILearningModelFeatureDescriptor>,winrt::Windows::AI::MachineLearning::ILearningModelFeatureDescriptor>::GetAt(uint)
0x18001efcd  nop
0x18001efce  lea     rdx, [rsp+0B8h+arg_0]
0x18001efd6  mov     rcx, rax
0x18001efd9  call    ?GetAsVectorView@?$consume_Windows_AI_MachineLearning_ITensorFloat@UITensorFloat@MachineLearning@AI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_AI_MachineLearning_ITensorFloat<winrt::Windows::AI::MachineLearning::ITensorFloat>::GetAsVectorView(void)
0x18001efde  lea     r14, qword_180042D38
0x18001efe5  cmp     r14, rax
0x18001efe8  jz      short loc_18001F007
0x18001efea  mov     rbx, [rax]
0x18001efed  mov     [rax], rsi
0x18001eff0  mov     rcx, r14
0x18001eff3  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18001eff8  mov     rcx, r14
0x18001effb  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18001f000  mov     cs:qword_180042D38, rbx
0x18001f007  lea     rcx, [rsp+0B8h+arg_0]
0x18001f00f  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18001f014  nop
0x18001f015  lea     rcx, [rsp+0B8h+arg_8]; this
0x18001f01d  call    ??1ILearningModel@MachineLearning@AI@Windows@winrt@@QEAA@XZ; winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel(void)
0x18001f022  nop
0x18001f023  lea     rcx, [rsp+0B8h+var_98]; this
0x18001f028  call    ??1ILearningModel@MachineLearning@AI@Windows@winrt@@QEAA@XZ; winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel(void)
0x18001f02d  lea     rdx, [rsp+0B8h+var_98]
0x18001f032  lea     rcx, [rsp+0B8h+arg_10]
0x18001f03a  call    ?OutputFeatures@?$consume_Windows_AI_MachineLearning_ILearningModel@UILearningModel@MachineLearning@AI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_AI_MachineLearning_ILearningModel<winrt::Windows::AI::MachineLearning::ILearningModel>::OutputFeatures(void)
0x18001f03f  nop
0x18001f040  lea     rdx, [rsp+0B8h+arg_8]
0x18001f048  mov     rcx, rax
0x18001f04b  call    ?GetAt@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@UILearningModelFeatureDescriptor@MachineLearning@AI@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UILearningModelFeatureDescriptor@MachineLearning@AI@45@@impl@winrt@@QEBA@I@Z; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::AI::MachineLearning::ILearningModelFeatureDescriptor>,winrt::Windows::AI::MachineLearning::ILearningModelFeatureDescriptor>::GetAt(uint)
0x18001f050  nop
0x18001f051  lea     rdx, [rsp+0B8h+arg_0]
0x18001f059  mov     rcx, rax
0x18001f05c  call    ?GetAsVectorView@?$consume_Windows_AI_MachineLearning_ITensorFloat@UITensorFloat@MachineLearning@AI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_AI_MachineLearning_ITensorFloat<winrt::Windows::AI::MachineLearning::ITensorFloat>::GetAsVectorView(void)
0x18001f061  lea     r14, qword_180042D40
0x18001f068  cmp     r14, rax
0x18001f06b  jz      short loc_18001F08A
0x18001f06d  mov     rbx, [rax]
0x18001f070  mov     [rax], rsi
0x18001f073  mov     rcx, r14
0x18001f076  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18001f07b  mov     rcx, r14
0x18001f07e  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18001f083  mov     cs:qword_180042D40, rbx
0x18001f08a  lea     rcx, [rsp+0B8h+arg_0]
0x18001f092  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18001f097  nop
0x18001f098  lea     rcx, [rsp+0B8h+arg_8]; this
0x18001f0a0  call    ??1ILearningModel@MachineLearning@AI@Windows@winrt@@QEAA@XZ; winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel(void)
0x18001f0a5  nop
0x18001f0a6  lea     rcx, [rsp+0B8h+var_98]; this
0x18001f0ab  call    ??1ILearningModel@MachineLearning@AI@Windows@winrt@@QEAA@XZ; winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel(void)
0x18001f0b0  lea     rcx, [rsp+0B8h+var_78]; this
0x18001f0b5  call    ??0LearningModelSessionOptions@MachineLearning@AI@Windows@winrt@@QEAA@XZ; winrt::Windows::AI::MachineLearning::LearningModelSessionOptions::LearningModelSessionOptions(void)
0x18001f0ba  nop
0x18001f0bb  mov     rcx, [rsp+0B8h+var_78]
0x18001f0c0  test    rcx, rcx
0x18001f0c3  jnz     short loc_18001F0CD
0x18001f0c5  mov     rbx, rsi
0x18001f0c8  mov     rcx, rsi
0x18001f0cb  jmp     short loc_18001F11B
0x18001f0cd  mov     [rsp+0B8h+arg_8], rsi
0x18001f0d5  mov     [rsp+0B8h+var_68], esi
0x18001f0d9  xorps   xmm0, xmm0
0x18001f0dc  movdqu  xmmword ptr [rsp+58h], xmm0
0x18001f0e2  mov     rax, [rcx]
0x18001f0e5  lea     r8, [rsp+0B8h+arg_8]
0x18001f0ed  lea     rdx, ??$guid_v@UILearningModelSessionOptionsNative@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<ILearningModelSessionOptionsNative>
0x18001f0f4  mov     rax, [rax]
0x18001f0f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0fc  lea     r8, [rsp+0B8h+var_68]
0x18001f101  mov     edx, eax
0x18001f103  lea     rcx, [rsp+0B8h+arg_0]
0x18001f10b  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001f110  mov     rbx, [rsp+0B8h+arg_8]
0x18001f118  mov     rcx, rbx
0x18001f11b  mov     [rsp+0B8h+arg_8], rbx
0x18001f123  mov     rax, [rcx]
0x18001f126  mov     r14d, 1
0x18001f12c  mov     edx, r14d
0x18001f12f  mov     rax, [rax+18h]
0x18001f133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f138  mov     dword ptr [rsp+0B8h+arg_0], esi
0x18001f13f  lea     rdx, [rsp+0B8h+arg_0]; enum winrt::Windows::AI::MachineLearning::LearningModelDeviceKind *
0x18001f147  lea     rcx, [rsp+0B8h+var_98]; this
0x18001f14c  call    ??0LearningModelDevice@MachineLearning@AI@Windows@winrt@@QEAA@AEBW4LearningModelDeviceKind@1234@@Z; winrt::Windows::AI::MachineLearning::LearningModelDevice::LearningModelDevice(winrt::Windows::AI::MachineLearning::LearningModelDeviceKind const &)
0x18001f151  nop
0x18001f152  lea     r9, [rsp+0B8h+var_78]
0x18001f157  mov     r8, rax
0x18001f15a  lea     rdx, [rsp+0B8h+arg_10]
0x18001f162  lea     rcx, [rsp+0B8h+var_68]
0x18001f167  call    ??$make_shared@ULearningModelSession@MachineLearning@AI@Windows@winrt@@AEAULearningModel@2345@ULearningModelDevice@2345@AEAULearningModelSessionOptions@2345@@std@@YA?AV?$shared_ptr@ULearningModelSession@MachineLearning@AI@Windows@winrt@@@0@AEAULearningModel@MachineLearning@AI@Windows@winrt@@$$QEAULearningModelDevice@3456@AEAULearningModelSessionOptions@3456@@Z; std::make_shared<winrt::Windows::AI::MachineLearning::LearningModelSession,winrt::Windows::AI::MachineLearning::LearningModel &,winrt::Windows::AI::MachineLearning::LearningModelDevice,winrt::Windows::AI::MachineLearning::LearningModelSessionOptions &>(winrt::Windows::AI::MachineLearning::LearningModel &,winrt::Windows::AI::MachineLearning::LearningModelDevice &&,winrt::Windows::AI::MachineLearning::LearningModelSessionOptions &)
0x18001f16c  mov     rcx, [rax]
0x18001f16f  mov     rdx, [rax+8]
0x18001f173  mov     [rax], rsi
0x18001f176  mov     [rax+8], rsi
0x18001f17a  mov     qword ptr cs:xmmword_180042D18, rcx
0x18001f181  mov     rcx, qword ptr cs:xmmword_180042D18+8; this
0x18001f188  mov     qword ptr cs:xmmword_180042D18+8, rdx
0x18001f18f  test    rcx, rcx
0x18001f192  jz      short loc_18001F199
0x18001f194  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f199  mov     rcx, [rsp+58h]; this
0x18001f19e  test    rcx, rcx
0x18001f1a1  jz      short loc_18001F1A9
0x18001f1a3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f1a8  nop
0x18001f1a9  lea     rcx, [rsp+0B8h+var_98]; this
0x18001f1ae  call    ??1ILearningModel@MachineLearning@AI@Windows@winrt@@QEAA@XZ; winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel(void)
0x18001f1b3  mov     rdx, qword ptr cs:xmmword_180042D18
0x18001f1ba  lea     rcx, [rsp+0B8h+var_68]
0x18001f1bf  call    ??$make_shared@ULearningModelBinding@MachineLearning@AI@Windows@winrt@@AEAULearningModelSession@2345@@std@@YA?AV?$shared_ptr@ULearningModelBinding@MachineLearning@AI@Windows@winrt@@@0@AEAULearningModelSession@MachineLearning@AI@Windows@winrt@@@Z; std::make_shared<winrt::Windows::AI::MachineLearning::LearningModelBinding,winrt::Windows::AI::MachineLearning::LearningModelSession &>(winrt::Windows::AI::MachineLearning::LearningModelSession &)
0x18001f1c4  mov     rcx, [rax]
0x18001f1c7  mov     rdx, [rax+8]
0x18001f1cb  mov     [rax], rsi
0x18001f1ce  mov     [rax+8], rsi
0x18001f1d2  mov     qword ptr cs:xmmword_180042D28, rcx
0x18001f1d9  mov     rcx, qword ptr cs:xmmword_180042D28+8; this
0x18001f1e0  mov     qword ptr cs:xmmword_180042D28+8, rdx
0x18001f1e7  test    rcx, rcx
0x18001f1ea  jz      short loc_18001F1F1
0x18001f1ec  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f1f1  mov     rcx, [rsp+58h]; this
0x18001f1f6  test    rcx, rcx
0x18001f1f9  jz      short loc_18001F200
0x18001f1fb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f200  mov     cs:?instance@?1??GetInstance@MLSDClassifier@@SAAEAV2@XZ@4V2@A, r14d; MLSDClassifier `MLSDClassifier::GetInstance(void)'::`2'::instance
0x18001f207  test    rbx, rbx
0x18001f20a  jz      short loc_18001F21A
0x18001f20c  lea     rcx, [rsp+0B8h+arg_8]
0x18001f214  call    ?unconditional_release_ref@?$com_ptr@UILearningModelSessionOptionsNative@@@winrt@@AEAAXXZ; winrt::com_ptr<ILearningModelSessionOptionsNative>::unconditional_release_ref(void)
0x18001f219  nop
0x18001f21a  lea     rcx, [rsp+0B8h+var_78]; this
0x18001f21f  call    ??1ILearningModel@MachineLearning@AI@Windows@winrt@@QEAA@XZ; winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel(void)
0x18001f224  nop
0x18001f225  lea     rcx, [rsp+0B8h+arg_10]; this
0x18001f22d  call    ??1ILearningModel@MachineLearning@AI@Windows@winrt@@QEAA@XZ; winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel(void)
0x18001f232  nop
0x18001f233  lea     rcx, [rsp+0B8h+var_88]
0x18001f238  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18001f23d  nop
0x18001f23e  lea     rcx, [rsp+0B8h+var_70]; this
0x18001f243  call    ??1ILearningModel@MachineLearning@AI@Windows@winrt@@QEAA@XZ; winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel(void)
0x18001f248  nop
0x18001f249  lea     rcx, [rsp+0B8h+arg_18]; this
0x18001f251  call    ??1ILearningModel@MachineLearning@AI@Windows@winrt@@QEAA@XZ; winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel(void)
0x18001f256  nop
0x18001f257  lea     rcx, [rsp+0B8h+var_80]; this
0x18001f25c  call    ??1ILearningModel@MachineLearning@AI@Windows@winrt@@QEAA@XZ; winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel(void)
0x18001f261  nop
0x18001f262  jmp     short loc_18001F26B
0x18001f264  lea     rdi, ?instance@?1??GetInstance@MLSDClassifier@@SAAEAV2@XZ@4V2@A; MLSDClassifier `MLSDClassifier::GetInstance(void)'::`2'::instance
0x18001f26b  mov     rax, rdi
0x18001f26e  add     rsp, 98h
0x18001f275  pop     r14
0x18001f277  pop     rdi
0x18001f278  pop     rsi
0x18001f279  pop     rbx
0x18001f27a  retn
0x18001f27b  lea     rcx, [rsp+0B8h+var_68]
0x18001f280  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001f285  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001f288  lea     rcx, [rsp+0B8h+pExceptionObject]; this
0x18001f28d  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18001f292  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18001f299  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x18001f29e  call    _CxxThrowException_0
```
