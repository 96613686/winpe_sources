# Microsoft::Windows::Autopilot::AutopilotUpdateSearchResult::DownloadAsync(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>)

- ea: `0x180188a80`
- end: `0x180188fa0`
- name: `?DownloadAsync@AutopilotUpdateSearchResult@Autopilot@Windows@Microsoft@@UEAA?AV?$task@V?$shared_ptr@VIAutopilotUpdatePayload@Autopilot@Windows@Microsoft@@@std@@@Concurrency@@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z`
- size: `1312`
- prototype: ``
- caller_count: `0`
- callee_count: `27`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b820`
- `0x18000c414`
- `0x180067008`
- `0x180068628`
- `0x18006dfb8`
- `0x180077384`
- `0x180093060`
- `0x180093a28`
- `0x1800d84e0`
- `0x180114714`
- `0x1801814d8`
- `0x180181ed4`
- `0x180183104`
- `0x1801835a4`
- `0x180183da0`
- `0x180184468`
- `0x180184528`
- `0x180184bfc`
- `0x1801851dc`
- `0x180185204`
- `0x180185f2c`
- `0x180188a80`
- `0x180188ffc`
- `0x18018a7f0`
- `0x18018bf0c`
- `0x18018bf58`
- `0x1801fa010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180188c61`
- `OLEAUT32!__imp_VariantInit` at `0x180188c61`
- `OLEAUT32!__imp_VariantClear` at `0x180188f05`
- `OLEAUT32!__imp_VariantClear` at `0x180188f05`

## string_xrefs

- `0x180188b2a`: `Unable to create downloader`
- `0x180188c38`: `Unable to create download callbacks`
- `0x180188cc3`: `Cancel invoked during download`
- `0x180188b39`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotupdate.cpp`
- `0x180188cd9`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotupdate.cpp`
- `0x180188d49`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotupdate.cpp`
- `0x180188f73`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotupdate.cpp`
- `0x180188b69`: `put_Updates`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall Microsoft::Windows::Autopilot::AutopilotUpdateSearchResult::DownloadAsync(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64 *); // rbx
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  _QWORD *v11; // r14
  unsigned int v12; // ebx
  __int64 (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v14)(_QWORD, GUID *, __int64 *); // rdi
  int v15; // eax
  char v16; // al
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64, __int64, VARIANTARG *, void ***); // rbx
  unsigned int v19; // eax
  __int64 v20; // rbx
  void (__fastcall *v21)(__int64, _BYTE *); // rdi
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rdi
  __int64 v25; // rbx
  __int64 v26; // rax
  const struct wil::FailureInfo *v28; // rdx
  int v29; // [rsp+20h] [rbp-E0h]
  char *v30; // [rsp+28h] [rbp-D8h]
  char *v31; // [rsp+28h] [rbp-D8h]
  char *v32; // [rsp+28h] [rbp-D8h]
  char *v33; // [rsp+28h] [rbp-D8h]
  char *v34; // [rsp+28h] [rbp-D8h]
  const char *v35; // [rsp+30h] [rbp-D0h]
  __int64 v36; // [rsp+40h] [rbp-C0h] BYREF
  void **v37; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v38; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v39)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v41[3]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v42[16]; // [rsp+80h] [rbp-80h] BYREF
  VARIANTARG v43; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v44[16]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v45[8]; // [rsp+C0h] [rbp-40h] BYREF
  std::_Ref_count_base *v46; // [rsp+C8h] [rbp-38h]
  VARIANTARG pvarg; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v48; // [rsp+E8h] [rbp-18h]
  _BYTE v49[160]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v50[56]; // [rsp+190h] [rbp+90h] BYREF
  __int64 v51; // [rsp+1C8h] [rbp+C8h]
  void **v52; // [rsp+1F0h] [rbp+F0h] BYREF
  void **v53; // [rsp+1F8h] [rbp+F8h] BYREF
  _QWORD v54[42]; // [rsp+380h] [rbp+280h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+518h] [rbp+418h]

  v40 = a2;
  v48 = a3;
  wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v54);
  v54[0] = &Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Download::`vftable';
  Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Download::StartActivity((Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Download *)v54);
  Concurrency::task_completion_event<unsigned char>::task_completion_event<unsigned char>(v42);
  v36 = 0;
  v6 = a1[1];
  v7 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v6 + 104LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
  v8 = v7(v6, &v36);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x165,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
    (const char *)v8,
    (int)"Unable to create downloader",
    v30);
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v36 + 112LL))(v36, a1[2]);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x168,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
    (const char *)v9,
    (int)"put_Updates",
    v31);
  v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v36 + 96LL))(v36, 3);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x16C,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
    (const char *)v10,
    (int)"put_Priority",
    v32);
  v39 = 0;
  if ( *(_DWORD *)v54[34] != 1 )
  {
    memset_0(v49, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v49, v28);
  }
  wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::IncrementExpectedStopCount(v54);
  wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>(
    &v52,
    v54);
  v52 = &Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Download::`vftable';
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
  v11 = a1 + 3;
  v12 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::Windows::Autopilot::WUDownloadCallback,Microsoft::Windows::Autopilot::WUDownloadCallback,std::shared_ptr<Microsoft::Windows::Autopilot::IAutopilotUpdateContext> &,Concurrency::task_completion_event<void> &,Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Download>(
          &v39,
          a1 + 3,
          v42,
          &v52);
  Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Download::~Download((Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Download *)&v52);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x170,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
    (const char *)v12,
    (int)"Unable to create download callbacks",
    v33);
  v37 = 0;
  VariantInit(&pvarg);
  v38 = 0;
  v13 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v39;
  v14 = **v39;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
  v15 = v14(v13, &GUID_00000000_0000_0000_c000_000000000046, &v38);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
      (const char *)(unsigned int)v15,
      v29);
  v16 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 40LL))(*v11);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x179,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
    (const char *)0x80004004LL,
    v16,
    (bool)"Cancel invoked during download",
    v35);
  v17 = v36;
  v18 = *(__int64 (__fastcall **)(__int64, __int64, __int64, VARIANTARG *, void ***))(*(_QWORD *)v36 + 120LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  v43 = pvarg;
  v19 = v18(v17, v38, v38, &v43, &v37);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x17C,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
    (const char *)v19,
    (int)"BeginDownload failed",
    v34);
  v20 = *v11;
  v21 = *(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)*v11 + 16LL);
  v52 = v37;
  if ( v37 )
    (*((void (__fastcall **)(void **))*v37 + 1))(v37);
  wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>(
    &v53,
    v54);
  v53 = &Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Download::`vftable';
  v51 = 0;
  v51 = std::_Global_new<std::_Func_impl_no_alloc<_lambda_734f4998f4de1a2fb4596d979aecf192_,void,>,_lambda_734f4998f4de1a2fb4596d979aecf192_>(&v52);
  v21(v20, v50);
  std::_Func_class<bool,std::wstring const &>::_Tidy(v50);
  _lambda_734f4998f4de1a2fb4596d979aecf192_::~_lambda_734f4998f4de1a2fb4596d979aecf192_((_lambda_734f4998f4de1a2fb4596d979aecf192_ *)&v52);
  v22 = a1[1];
  v40 = v22;
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
  v23 = a1[2];
  v41[0] = v23;
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23);
  std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(
    v45,
    a1 + 3);
  Concurrency::task_options::task_options((Concurrency::task_options *)v50);
  std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(
    v44,
    v42);
  v24 = Concurrency::create_task<Concurrency::task_completion_event<void>>(&v43, v44);
  v25 = Concurrency::task_options::task_options((Concurrency::task_options *)v49);
  v26 = _lambda_76a63f6372620a881c4c4ab6f024e098_::_lambda_76a63f6372620a881c4c4ab6f024e098_(
          (unsigned int)&v52,
          (unsigned int)&v40,
          (unsigned int)&v36,
          (unsigned int)v41,
          (__int64)&v37,
          (__int64)v54,
          (__int64)v45,
          a3);
  Concurrency::task<void>::then<_lambda_76a63f6372620a881c4c4ab6f024e098_>(v24, a2, v26, v25);
  _lambda_76a63f6372620a881c4c4ab6f024e098_::~_lambda_76a63f6372620a881c4c4ab6f024e098_((_lambda_76a63f6372620a881c4c4ab6f024e098_ *)&v52);
  std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(&v43);
  if ( v46 )
    std::_Ref_count_base::_Decref(v46);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v41);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
  VariantClear(&pvarg);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
  std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v42);
  Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Download::~Download((Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Download *)v54);
  std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(a3);
  return a2;
}

```

## disassembly

```asm
0x180188a80  push    rbp
0x180188a82  push    rbx
0x180188a83  push    rsi
0x180188a84  push    rdi
0x180188a85  push    r12
0x180188a87  push    r14
0x180188a89  push    r15
0x180188a8b  lea     rbp, [rsp-3E0h]
0x180188a93  sub     rsp, 4E0h
0x180188a9a  mov     rax, cs:__security_cookie
0x180188aa1  xor     rax, rsp
0x180188aa4  mov     [rbp+410h+var_40], rax
0x180188aab  mov     r12, r8
0x180188aae  mov     r15, rdx
0x180188ab1  mov     rsi, rcx
0x180188ab4  mov     [rsp+510h+var_4B0], rdx
0x180188ab9  mov     [rbp+410h+var_428], r8
0x180188abd  lea     rdx, aDownload; "Download"
0x180188ac4  lea     rcx, [rbp+410h+var_190]; struct wil::details::IFailureCallback *
0x180188acb  call    ??0?$ActivityBase@VAutopilotUpdateLoggingProvider@Logging@Autopilot@Management@Windows@Microsoft@@$00$0IAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180188ad0  lea     r14, ??_7Download@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@6B@; const Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Download::`vftable'
0x180188ad7  mov     [rbp+410h+var_190], r14
0x180188ade  lea     rcx, [rbp+410h+var_190]; this
0x180188ae5  call    ?StartActivity@Download@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@QEAAXXZ; Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Download::StartActivity(void)
0x180188aea  nop
0x180188aeb  lea     rcx, [rbp+410h+var_490]
0x180188aef  call    ??0?$task_completion_event@E@Concurrency@@QEAA@XZ; Concurrency::task_completion_event<uchar>::task_completion_event<uchar>(void)
0x180188af4  nop
0x180188af5  mov     [rsp+510h+var_4D0], 0
0x180188afe  mov     rdi, [rsi+8]
0x180188b02  mov     rax, [rdi]
0x180188b05  mov     rbx, [rax+68h]
0x180188b09  lea     rcx, [rsp+510h+var_4D0]
0x180188b0e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180188b13  lea     rdx, [rsp+510h+var_4D0]
0x180188b18  mov     rcx, rdi
0x180188b1b  mov     rax, rbx
0x180188b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188b23  mov     rcx, [rbp+418h]; this
0x180188b2a  lea     rdx, aUnableToCreate_3; "Unable to create downloader"
0x180188b31  mov     qword ptr [rsp+510h+var_4F0], rdx; int
0x180188b36  mov     r9d, eax; char *
0x180188b39  lea     rdi, aOnecoreuapAdmi_110; "onecoreuap\\admin\\moderndeployment\\au"...
0x180188b40  mov     r8, rdi; unsigned int
0x180188b43  mov     edx, 165h; void *
0x180188b48  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180188b4d  mov     rcx, [rsp+510h+var_4D0]
0x180188b52  mov     rax, [rcx]
0x180188b55  mov     rdx, [rsi+10h]
0x180188b59  mov     rax, [rax+70h]
0x180188b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188b62  mov     rcx, [rbp+418h]; this
0x180188b69  lea     rdx, aPutUpdates; "put_Updates"
0x180188b70  mov     qword ptr [rsp+510h+var_4F0], rdx; int
0x180188b75  mov     r9d, eax; char *
0x180188b78  mov     r8, rdi; unsigned int
0x180188b7b  mov     edx, 168h; void *
0x180188b80  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180188b85  mov     rcx, [rsp+510h+var_4D0]
0x180188b8a  mov     rax, [rcx]
0x180188b8d  mov     edx, 3
0x180188b92  mov     rax, [rax+60h]
0x180188b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188b9b  mov     rcx, [rbp+418h]; this
0x180188ba2  lea     rdx, aPutPriority; "put_Priority"
0x180188ba9  mov     qword ptr [rsp+510h+var_4F0], rdx; int
0x180188bae  mov     r9d, eax; char *
0x180188bb1  mov     r8, rdi; unsigned int
0x180188bb4  mov     edx, 16Ch; void *
0x180188bb9  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180188bbe  mov     [rsp+510h+var_4B8], 0
0x180188bc7  mov     rax, [rbp+410h+var_80]
0x180188bce  cmp     dword ptr [rax], 1
0x180188bd1  jnz     loc_180188F85
0x180188bd7  lea     rcx, [rbp+410h+var_190]
0x180188bde  call    ?IncrementExpectedStopCount@?$ActivityBase@VAutopilotUpdateLoggingProvider@Logging@Autopilot@Management@Windows@Microsoft@@$00$0IAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::IncrementExpectedStopCount(void)
0x180188be3  lea     rdx, [rbp+410h+var_190]
0x180188bea  lea     rcx, [rbp+410h+var_320]
0x180188bf1  call    ??0?$ActivityBase@VAutopilotUpdateLoggingProvider@Logging@Autopilot@Management@Windows@Microsoft@@$00$0IAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x180188bf6  mov     [rbp+410h+var_320], r14
0x180188bfd  lea     rcx, [rsp+510h+var_4B8]
0x180188c02  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180188c07  lea     r14, [rsi+18h]
0x180188c0b  lea     r9, [rbp+410h+var_320]
0x180188c12  lea     r8, [rbp+410h+var_490]
0x180188c16  mov     rdx, r14
0x180188c19  lea     rcx, [rsp+510h+var_4B8]
0x180188c1e  call    ??$MakeAndInitialize@VWUDownloadCallback@Autopilot@Windows@Microsoft@@V1234@AEAV?$shared_ptr@VIAutopilotUpdateContext@Autopilot@Windows@Microsoft@@@std@@AEAV?$task_completion_event@X@Concurrency@@VDownload@UpdateOperations@Logging@2Management@34@@Details@WRL@Microsoft@@YAJPEAPEAVWUDownloadCallback@Autopilot@Windows@2@AEAV?$shared_ptr@VIAutopilotUpdateContext@Autopilot@Windows@Microsoft@@@std@@AEAV?$task_completion_event@X@Concurrency@@$$QEAVDownload@UpdateOperations@Logging@4Management@52@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::Windows::Autopilot::WUDownloadCallback,Microsoft::Windows::Autopilot::WUDownloadCallback,std::shared_ptr<Microsoft::Windows::Autopilot::IAutopilotUpdateContext> &,Concurrency::task_completion_event<void> &,Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Download>(Microsoft::Windows::Autopilot::WUDownloadCallback * *,std::shared_ptr<Microsoft::Windows::Autopilot::IAutopilotUpdateContext> &,Concurrency::task_completion_event<void> &,Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Download &&)
0x180188c23  mov     ebx, eax
0x180188c25  lea     rcx, [rbp+410h+var_320]; this
0x180188c2c  call    ??1Download@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Download::~Download(void)
0x180188c31  mov     rcx, [rbp+418h]; this
0x180188c38  lea     rax, aUnableToCreate_1; "Unable to create download callbacks"
0x180188c3f  mov     qword ptr [rsp+510h+var_4F0], rax; int
0x180188c44  mov     r9d, ebx; char *
0x180188c47  mov     r8, rdi; unsigned int
0x180188c4a  mov     edx, 170h; void *
0x180188c4f  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180188c54  mov     [rsp+510h+var_4C8], 0
0x180188c5d  lea     rcx, [rbp+410h+pvarg]; pvarg
0x180188c61  call    cs:__imp_VariantInit
0x180188c67  nop
0x180188c68  mov     [rsp+510h+var_4C0], 0
0x180188c71  mov     rbx, [rsp+510h+var_4B8]
0x180188c76  mov     rax, [rbx]
0x180188c79  mov     rdi, [rax]
0x180188c7c  lea     rcx, [rsp+510h+var_4C0]
0x180188c81  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180188c86  lea     r8, [rsp+510h+var_4C0]
0x180188c8b  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180188c92  mov     rcx, rbx
0x180188c95  mov     rax, rdi
0x180188c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188c9d  nop
0x180188c9e  mov     rcx, [rbp+418h]; this
0x180188ca5  test    eax, eax
0x180188ca7  js      loc_180188F70
0x180188cad  mov     rcx, [r14]
0x180188cb0  mov     rax, [rcx]
0x180188cb3  mov     rax, [rax+28h]
0x180188cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188cbc  mov     rcx, [rbp+418h]; this
0x180188cc3  lea     rdx, aCancelInvokedD_1; "Cancel invoked during download"
0x180188cca  mov     [rsp+510h+var_4E8], rdx; char *
0x180188ccf  mov     [rsp+510h+var_4F0], al; char
0x180188cd3  mov     r9d, 80004004h; char *
0x180188cd9  lea     r8, aOnecoreuapAdmi_110; "onecoreuap\\admin\\moderndeployment\\au"...
0x180188ce0  mov     edx, 179h; void *
0x180188ce5  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180188cea  mov     rdi, [rsp+510h+var_4D0]
0x180188cef  mov     rax, [rdi]
0x180188cf2  mov     rbx, [rax+78h]
0x180188cf6  lea     rcx, [rsp+510h+var_4C8]
0x180188cfb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180188d00  movups  xmm0, xmmword ptr [rbp+410h+pvarg]
0x180188d04  movsd   xmm1, qword ptr [rbp+410h+pvarg+10h]
0x180188d09  mov     rdx, [rsp+510h+var_4C0]
0x180188d0e  movaps  [rbp+410h+var_480], xmm0
0x180188d12  movsd   [rbp+410h+var_470], xmm1
0x180188d17  lea     rax, [rsp+510h+var_4C8]
0x180188d1c  mov     qword ptr [rsp+510h+var_4F0], rax
0x180188d21  lea     r9, [rbp+410h+var_480]
0x180188d25  mov     r8, rdx
0x180188d28  mov     rcx, rdi
0x180188d2b  mov     rax, rbx
0x180188d2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188d33  mov     rcx, [rbp+418h]; this
0x180188d3a  lea     rdx, aBegindownloadF; "BeginDownload failed"
0x180188d41  mov     qword ptr [rsp+510h+var_4F0], rdx; int
0x180188d46  mov     r9d, eax; char *
0x180188d49  lea     r8, aOnecoreuapAdmi_110; "onecoreuap\\admin\\moderndeployment\\au"...
0x180188d50  mov     edx, 17Ch; void *
0x180188d55  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180188d5a  mov     rbx, [r14]
0x180188d5d  mov     rax, [rbx]
0x180188d60  mov     rdi, [rax+10h]
0x180188d64  mov     rcx, [rsp+510h+var_4C8]
0x180188d69  mov     [rbp+410h+var_320], rcx
0x180188d70  test    rcx, rcx
0x180188d73  jz      short loc_180188D82
0x180188d75  mov     rax, [rcx]
0x180188d78  mov     rax, [rax+8]
0x180188d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188d81  nop
0x180188d82  lea     rdx, [rbp+410h+var_190]
0x180188d89  lea     rcx, [rbp+410h+var_318]
0x180188d90  call    ??0?$ActivityBase@VAutopilotUpdateLoggingProvider@Logging@Autopilot@Management@Windows@Microsoft@@$00$0IAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x180188d95  lea     rax, ??_7Download@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@6B@; const Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Download::`vftable'
0x180188d9c  mov     [rbp+410h+var_318], rax
0x180188da3  mov     [rbp+410h+var_348], 0
0x180188dae  lea     rcx, [rbp+410h+var_320]
0x180188db5  call    ??$_Global_new@V?$_Func_impl_no_alloc@V_lambda_734f4998f4de1a2fb4596d979aecf192_@@X$$V@std@@V_lambda_734f4998f4de1a2fb4596d979aecf192_@@@std@@YAPEAV?$_Func_impl_no_alloc@V_lambda_734f4998f4de1a2fb4596d979aecf192_@@X$$V@0@$$QEAV_lambda_734f4998f4de1a2fb4596d979aecf192_@@@Z; std::_Global_new<std::_Func_impl_no_alloc<_lambda_734f4998f4de1a2fb4596d979aecf192_,void,>,_lambda_734f4998f4de1a2fb4596d979aecf192_>(_lambda_734f4998f4de1a2fb4596d979aecf192_ &&)
0x180188dba  mov     [rbp+410h+var_348], rax
0x180188dc1  lea     rdx, [rbp+410h+var_380]
0x180188dc8  mov     rcx, rbx
0x180188dcb  mov     rax, rdi
0x180188dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188dd3  nop
0x180188dd4  lea     rcx, [rbp+410h+var_380]
0x180188ddb  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x180188de0  nop
0x180188de1  lea     rcx, [rbp+410h+var_320]; this
0x180188de8  call    ??1_lambda_734f4998f4de1a2fb4596d979aecf192_@@QEAA@XZ; _lambda_734f4998f4de1a2fb4596d979aecf192_::~_lambda_734f4998f4de1a2fb4596d979aecf192_(void)
0x180188ded  mov     rcx, [rsi+8]
0x180188df1  mov     [rsp+510h+var_4B0], rcx
0x180188df6  test    rcx, rcx
0x180188df9  jz      short loc_180188E08
0x180188dfb  mov     rax, [rcx]
0x180188dfe  mov     rax, [rax+8]
0x180188e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188e07  nop
0x180188e08  mov     rcx, [rsi+10h]
0x180188e0c  mov     [rsp+510h+var_4A8], rcx
0x180188e11  test    rcx, rcx
0x180188e14  jz      short loc_180188E23
0x180188e16  mov     rax, [rcx]
0x180188e19  mov     rax, [rax+8]
0x180188e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188e22  nop
0x180188e23  mov     rdx, r14
0x180188e26  lea     rcx, [rbp+410h+var_450]
0x180188e2a  call    ??0?$shared_ptr@VAutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager> const &)
0x180188e2f  nop
0x180188e30  lea     rcx, [rbp+410h+var_380]; this
0x180188e37  call    ??0task_options@Concurrency@@QEAA@XZ; Concurrency::task_options::task_options(void)
0x180188e3c  mov     r8, rax
0x180188e3f  lea     rdx, [rbp+410h+var_490]
0x180188e43  lea     rcx, [rbp+410h+var_460]
0x180188e47  call    ??0?$shared_ptr@VAutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager> const &)
0x180188e4c  lea     rdx, [rbp+410h+var_460]
0x180188e50  lea     rcx, [rbp+410h+var_480]
0x180188e54  call    ??$create_task@V?$task_completion_event@X@Concurrency@@@Concurrency@@YA?AV?$task@X@0@V?$task_completion_event@X@0@Vtask_options@0@@Z; Concurrency::create_task<Concurrency::task_completion_event<void>>(Concurrency::task_completion_event<void>,Concurrency::task_options)
0x180188e59  mov     rdi, rax
0x180188e5c  lea     rcx, [rbp+410h+var_420]; this
0x180188e60  call    ??0task_options@Concurrency@@QEAA@XZ; Concurrency::task_options::task_options(void)
0x180188e65  mov     rbx, rax
0x180188e68  mov     [rsp+510h+var_4D8], r12
0x180188e6d  lea     rax, [rbp+410h+var_450]
0x180188e71  mov     [rsp+510h+var_4E0], rax
0x180188e76  lea     rax, [rbp+410h+var_190]
0x180188e7d  mov     [rsp+510h+var_4E8], rax
0x180188e82  lea     rax, [rsp+510h+var_4C8]
0x180188e87  mov     qword ptr [rsp+510h+var_4F0], rax
0x180188e8c  lea     r9, [rsp+510h+var_4A8]
0x180188e91  lea     r8, [rsp+510h+var_4D0]
0x180188e96  lea     rdx, [rsp+510h+var_4B0]
0x180188e9b  lea     rcx, [rbp+410h+var_320]
0x180188ea2  call    ??0_lambda_76a63f6372620a881c4c4ab6f024e098_@@QEAA@AEBV?$ComPtr@UIUpdateSession@@@WRL@Microsoft@@AEBV?$ComPtr@UIUpdateDownloader@@@23@AEBV?$ComPtr@UIUpdateCollection@@@23@AEBV?$ComPtr@UIDownloadJob@@@23@AEBVDownload@UpdateOperations@Logging@Autopilot@Management@Windows@3@AEBV?$shared_ptr@VIAutopilotUpdateContext@Autopilot@Windows@Microsoft@@@std@@AEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; _lambda_76a63f6372620a881c4c4ab6f024e098_::_lambda_76a63f6372620a881c4c4ab6f024e098_(Microsoft::WRL::ComPtr<IUpdateSession> const &,Microsoft::WRL::ComPtr<IUpdateDownloader> const &,Microsoft::WRL::ComPtr<IUpdateCollection> const &,Microsoft::WRL::ComPtr<IDownloadJob> const &,Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Download const &,std::shared_ptr<Microsoft::Windows::Autopilot::IAutopilotUpdateContext> const &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> const &)
0x180188ea7  nop
0x180188ea8  mov     r9, rbx
0x180188eab  mov     r8, rax
0x180188eae  mov     rdx, r15
0x180188eb1  mov     rcx, rdi
0x180188eb4  call    ??$then@V_lambda_76a63f6372620a881c4c4ab6f024e098_@@@?$task@X@Concurrency@@QEBA?AV?$task@V?$shared_ptr@VIAutopilotUpdatePayload@Autopilot@Windows@Microsoft@@@std@@@1@AEBV_lambda_76a63f6372620a881c4c4ab6f024e098_@@Vtask_options@1@@Z; Concurrency::task<void>::then<_lambda_76a63f6372620a881c4c4ab6f024e098_>(_lambda_76a63f6372620a881c4c4ab6f024e098_ const &,Concurrency::task_options)
0x180188eb9  nop
0x180188eba  lea     rcx, [rbp+410h+var_320]; this
0x180188ec1  call    ??1_lambda_76a63f6372620a881c4c4ab6f024e098_@@QEAA@XZ; _lambda_76a63f6372620a881c4c4ab6f024e098_::~_lambda_76a63f6372620a881c4c4ab6f024e098_(void)
0x180188ec6  nop
0x180188ec7  lea     rcx, [rbp+410h+var_480]
0x180188ecb  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x180188ed0  nop
0x180188ed1  mov     rcx, [rbp+410h+var_448]; this
0x180188ed5  test    rcx, rcx
0x180188ed8  jz      short loc_180188EE0
0x180188eda  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180188edf  nop
0x180188ee0  lea     rcx, [rsp+510h+var_4A8]
0x180188ee5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180188eea  nop
0x180188eeb  lea     rcx, [rsp+510h+var_4B0]
0x180188ef0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180188ef5  nop
0x180188ef6  lea     rcx, [rsp+510h+var_4C0]
0x180188efb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180188f00  nop
0x180188f01  lea     rcx, [rbp+410h+pvarg]; pvarg
0x180188f05  call    cs:__imp_VariantClear
0x180188f0b  nop
0x180188f0c  lea     rcx, [rsp+510h+var_4C8]
0x180188f11  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180188f16  nop
0x180188f17  lea     rcx, [rsp+510h+var_4B8]
0x180188f1c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180188f21  nop
0x180188f22  lea     rcx, [rsp+510h+var_4D0]
0x180188f27  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180188f2c  nop
0x180188f2d  lea     rcx, [rbp+410h+var_490]
0x180188f31  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x180188f36  nop
0x180188f37  lea     rcx, [rbp+410h+var_190]; this
0x180188f3e  call    ??1Download@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Download::~Download(void)
0x180188f43  nop
0x180188f44  mov     rcx, r12
0x180188f47  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x180188f4c  mov     rax, r15
0x180188f4f  mov     rcx, [rbp+410h+var_40]
0x180188f56  xor     rcx, rsp; StackCookie
0x180188f59  call    __security_check_cookie
0x180188f5e  add     rsp, 4E0h
0x180188f65  pop     r15
0x180188f67  pop     r14
0x180188f69  pop     r12
0x180188f6b  pop     rdi
0x180188f6c  pop     rsi
0x180188f6d  pop     rbx
0x180188f6e  pop     rbp
0x180188f6f  retn
0x180188f70  mov     r9d, eax; char *
0x180188f73  lea     r8, aOnecoreuapAdmi_110; "onecoreuap\\admin\\moderndeployment\\au"...
0x180188f7a  mov     edx, 177h; void *
0x180188f7f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180188f85  xor     edx, edx; Val
0x180188f87  mov     r8d, 98h; Size
0x180188f8d  lea     rcx, [rbp+410h+var_420]; void *
0x180188f91  call    memset_0
0x180188f96  lea     rcx, [rbp+410h+var_420]; this
0x180188f9a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
