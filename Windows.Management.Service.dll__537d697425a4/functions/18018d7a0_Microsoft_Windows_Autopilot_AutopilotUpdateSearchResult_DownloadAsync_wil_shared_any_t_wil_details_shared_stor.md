# Microsoft::Windows::Autopilot::AutopilotUpdateSearchResult::DownloadAsync(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>)

- ea: `0x18018d7a0`
- end: `0x18018dccd`
- name: `?DownloadAsync@AutopilotUpdateSearchResult@Autopilot@Windows@Microsoft@@UEAA?AV?$task@V?$shared_ptr@VIAutopilotUpdatePayload@Autopilot@Windows@Microsoft@@@std@@@Concurrency@@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z`
- size: `1325`
- prototype: ``
- caller_count: `0`
- callee_count: `27`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b8f0`
- `0x18000c504`
- `0x180067398`
- `0x180068aa0`
- `0x18006e508`
- `0x180077c04`
- `0x1800942e8`
- `0x180094ce0`
- `0x1800dabf0`
- `0x180117e18`
- `0x180186040`
- `0x180186a4c`
- `0x180187c78`
- `0x180188130`
- `0x18018894c`
- `0x180189018`
- `0x1801890d8`
- `0x180189800`
- `0x180189d3c`
- `0x180189d64`
- `0x18018aadc`
- `0x18018d7a0`
- `0x18018dd2c`
- `0x18018f564`
- `0x180190cd0`
- `0x180190d1c`
- `0x180200010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18018d981`
- `OLEAUT32!__imp_VariantInit` at `0x18018d981`
- `OLEAUT32!__imp_VariantClear` at `0x18018dc2b`
- `OLEAUT32!__imp_VariantClear` at `0x18018dc2b`

## string_xrefs

- `0x18018d859`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotupdate.cpp`
- `0x18018d9ff`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotupdate.cpp`
- `0x18018da6f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotupdate.cpp`
- `0x18018dca0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotupdate.cpp`
- `0x18018d889`: `put_Updates`
- `0x18018d9e9`: `Cancel invoked during download`
- `0x18018d84a`: `Unable to create downloader`
- `0x18018d958`: `Unable to create download callbacks`

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
0x18018d7a0  push    rbp
0x18018d7a2  push    rbx
0x18018d7a3  push    rsi
0x18018d7a4  push    rdi
0x18018d7a5  push    r12
0x18018d7a7  push    r14
0x18018d7a9  push    r15
0x18018d7ab  lea     rbp, [rsp-3E0h]
0x18018d7b3  sub     rsp, 4E0h
0x18018d7ba  mov     rax, cs:__security_cookie
0x18018d7c1  xor     rax, rsp
0x18018d7c4  mov     [rbp+410h+var_40], rax
0x18018d7cb  mov     r12, r8
0x18018d7ce  mov     r15, rdx
0x18018d7d1  mov     rsi, rcx
0x18018d7d4  mov     [rsp+510h+var_4B0], rdx
0x18018d7d9  mov     [rbp+410h+var_428], r8
0x18018d7dd  lea     rdx, aDownload; "Download"
0x18018d7e4  lea     rcx, [rbp+410h+var_190]; struct wil::details::IFailureCallback *
0x18018d7eb  call    ??0?$ActivityBase@VAutopilotUpdateLoggingProvider@Logging@Autopilot@Management@Windows@Microsoft@@$00$0IAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18018d7f0  lea     r14, ??_7Download@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@6B@; const Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Download::`vftable'
0x18018d7f7  mov     [rbp+410h+var_190], r14
0x18018d7fe  lea     rcx, [rbp+410h+var_190]; this
0x18018d805  call    ?StartActivity@Download@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@QEAAXXZ; Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Download::StartActivity(void)
0x18018d80a  nop
0x18018d80b  lea     rcx, [rbp+410h+var_490]
0x18018d80f  call    ??0?$task_completion_event@E@Concurrency@@QEAA@XZ; Concurrency::task_completion_event<uchar>::task_completion_event<uchar>(void)
0x18018d814  nop
0x18018d815  mov     [rsp+510h+var_4D0], 0
0x18018d81e  mov     rdi, [rsi+8]
0x18018d822  mov     rax, [rdi]
0x18018d825  mov     rbx, [rax+68h]
0x18018d829  lea     rcx, [rsp+510h+var_4D0]
0x18018d82e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018d833  lea     rdx, [rsp+510h+var_4D0]
0x18018d838  mov     rcx, rdi
0x18018d83b  mov     rax, rbx
0x18018d83e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018d843  mov     rcx, [rbp+418h]; this
0x18018d84a  lea     rdx, aUnableToCreate_3; "Unable to create downloader"
0x18018d851  mov     qword ptr [rsp+510h+var_4F0], rdx; int
0x18018d856  mov     r9d, eax; char *
0x18018d859  lea     rdi, aOnecoreuapAdmi_110; "onecoreuap\\admin\\moderndeployment\\au"...
0x18018d860  mov     r8, rdi; unsigned int
0x18018d863  mov     edx, 165h; void *
0x18018d868  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18018d86d  mov     rcx, [rsp+510h+var_4D0]
0x18018d872  mov     rax, [rcx]
0x18018d875  mov     rdx, [rsi+10h]
0x18018d879  mov     rax, [rax+70h]
0x18018d87d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018d882  mov     rcx, [rbp+418h]; this
0x18018d889  lea     rdx, aPutUpdates; "put_Updates"
0x18018d890  mov     qword ptr [rsp+510h+var_4F0], rdx; int
0x18018d895  mov     r9d, eax; char *
0x18018d898  mov     r8, rdi; unsigned int
0x18018d89b  mov     edx, 168h; void *
0x18018d8a0  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18018d8a5  mov     rcx, [rsp+510h+var_4D0]
0x18018d8aa  mov     rax, [rcx]
0x18018d8ad  mov     edx, 3
0x18018d8b2  mov     rax, [rax+60h]
0x18018d8b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018d8bb  mov     rcx, [rbp+418h]; this
0x18018d8c2  lea     rdx, aPutPriority; "put_Priority"
0x18018d8c9  mov     qword ptr [rsp+510h+var_4F0], rdx; int
0x18018d8ce  mov     r9d, eax; char *
0x18018d8d1  mov     r8, rdi; unsigned int
0x18018d8d4  mov     edx, 16Ch; void *
0x18018d8d9  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18018d8de  mov     [rsp+510h+var_4B8], 0
0x18018d8e7  mov     rax, [rbp+410h+var_80]
0x18018d8ee  cmp     dword ptr [rax], 1
0x18018d8f1  jnz     loc_18018DCB2
0x18018d8f7  lea     rcx, [rbp+410h+var_190]
0x18018d8fe  call    ?IncrementExpectedStopCount@?$ActivityBase@VAutopilotUpdateLoggingProvider@Logging@Autopilot@Management@Windows@Microsoft@@$00$0IAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::IncrementExpectedStopCount(void)
0x18018d903  lea     rdx, [rbp+410h+var_190]
0x18018d90a  lea     rcx, [rbp+410h+var_320]
0x18018d911  call    ??0?$ActivityBase@VAutopilotUpdateLoggingProvider@Logging@Autopilot@Management@Windows@Microsoft@@$00$0IAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x18018d916  mov     [rbp+410h+var_320], r14
0x18018d91d  lea     rcx, [rsp+510h+var_4B8]
0x18018d922  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018d927  lea     r14, [rsi+18h]
0x18018d92b  lea     r9, [rbp+410h+var_320]
0x18018d932  lea     r8, [rbp+410h+var_490]
0x18018d936  mov     rdx, r14
0x18018d939  lea     rcx, [rsp+510h+var_4B8]
0x18018d93e  call    ??$MakeAndInitialize@VWUDownloadCallback@Autopilot@Windows@Microsoft@@V1234@AEAV?$shared_ptr@VIAutopilotUpdateContext@Autopilot@Windows@Microsoft@@@std@@AEAV?$task_completion_event@X@Concurrency@@VDownload@UpdateOperations@Logging@2Management@34@@Details@WRL@Microsoft@@YAJPEAPEAVWUDownloadCallback@Autopilot@Windows@2@AEAV?$shared_ptr@VIAutopilotUpdateContext@Autopilot@Windows@Microsoft@@@std@@AEAV?$task_completion_event@X@Concurrency@@$$QEAVDownload@UpdateOperations@Logging@4Management@52@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::Windows::Autopilot::WUDownloadCallback,Microsoft::Windows::Autopilot::WUDownloadCallback,std::shared_ptr<Microsoft::Windows::Autopilot::IAutopilotUpdateContext> &,Concurrency::task_completion_event<void> &,Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Download>(Microsoft::Windows::Autopilot::WUDownloadCallback * *,std::shared_ptr<Microsoft::Windows::Autopilot::IAutopilotUpdateContext> &,Concurrency::task_completion_event<void> &,Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Download &&)
0x18018d943  mov     ebx, eax
0x18018d945  lea     rcx, [rbp+410h+var_320]; this
0x18018d94c  call    ??1Download@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Download::~Download(void)
0x18018d951  mov     rcx, [rbp+418h]; this
0x18018d958  lea     rax, aUnableToCreate_1; "Unable to create download callbacks"
0x18018d95f  mov     qword ptr [rsp+510h+var_4F0], rax; int
0x18018d964  mov     r9d, ebx; char *
0x18018d967  mov     r8, rdi; unsigned int
0x18018d96a  mov     edx, 170h; void *
0x18018d96f  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18018d974  mov     [rsp+510h+var_4C8], 0
0x18018d97d  lea     rcx, [rbp+410h+pvarg]; pvarg
0x18018d981  call    cs:__imp_VariantInit
0x18018d988  nop     dword ptr [rax+rax+00h]
0x18018d98d  nop
0x18018d98e  mov     [rsp+510h+var_4C0], 0
0x18018d997  mov     rbx, [rsp+510h+var_4B8]
0x18018d99c  mov     rax, [rbx]
0x18018d99f  mov     rdi, [rax]
0x18018d9a2  lea     rcx, [rsp+510h+var_4C0]
0x18018d9a7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018d9ac  lea     r8, [rsp+510h+var_4C0]
0x18018d9b1  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18018d9b8  mov     rcx, rbx
0x18018d9bb  mov     rax, rdi
0x18018d9be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018d9c3  nop
0x18018d9c4  mov     rcx, [rbp+418h]; this
0x18018d9cb  test    eax, eax
0x18018d9cd  js      loc_18018DC9D
0x18018d9d3  mov     rcx, [r14]
0x18018d9d6  mov     rax, [rcx]
0x18018d9d9  mov     rax, [rax+28h]
0x18018d9dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018d9e2  mov     rcx, [rbp+418h]; this
0x18018d9e9  lea     rdx, aCancelInvokedD_1; "Cancel invoked during download"
0x18018d9f0  mov     [rsp+510h+var_4E8], rdx; char *
0x18018d9f5  mov     [rsp+510h+var_4F0], al; char
0x18018d9f9  mov     r9d, 80004004h; char *
0x18018d9ff  lea     r8, aOnecoreuapAdmi_110; "onecoreuap\\admin\\moderndeployment\\au"...
0x18018da06  mov     edx, 179h; void *
0x18018da0b  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18018da10  mov     rdi, [rsp+510h+var_4D0]
0x18018da15  mov     rax, [rdi]
0x18018da18  mov     rbx, [rax+78h]
0x18018da1c  lea     rcx, [rsp+510h+var_4C8]
0x18018da21  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018da26  movups  xmm0, xmmword ptr [rbp+410h+pvarg]
0x18018da2a  movsd   xmm1, qword ptr [rbp+410h+pvarg+10h]
0x18018da2f  mov     rdx, [rsp+510h+var_4C0]
0x18018da34  movaps  [rbp+410h+var_480], xmm0
0x18018da38  movsd   [rbp+410h+var_470], xmm1
0x18018da3d  lea     rax, [rsp+510h+var_4C8]
0x18018da42  mov     qword ptr [rsp+510h+var_4F0], rax
0x18018da47  lea     r9, [rbp+410h+var_480]
0x18018da4b  mov     r8, rdx
0x18018da4e  mov     rcx, rdi
0x18018da51  mov     rax, rbx
0x18018da54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018da59  mov     rcx, [rbp+418h]; this
0x18018da60  lea     rdx, aBegindownloadF; "BeginDownload failed"
0x18018da67  mov     qword ptr [rsp+510h+var_4F0], rdx; int
0x18018da6c  mov     r9d, eax; char *
0x18018da6f  lea     r8, aOnecoreuapAdmi_110; "onecoreuap\\admin\\moderndeployment\\au"...
0x18018da76  mov     edx, 17Ch; void *
0x18018da7b  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18018da80  mov     rbx, [r14]
0x18018da83  mov     rax, [rbx]
0x18018da86  mov     rdi, [rax+10h]
0x18018da8a  mov     rcx, [rsp+510h+var_4C8]
0x18018da8f  mov     [rbp+410h+var_320], rcx
0x18018da96  test    rcx, rcx
0x18018da99  jz      short loc_18018DAA8
0x18018da9b  mov     rax, [rcx]
0x18018da9e  mov     rax, [rax+8]
0x18018daa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018daa7  nop
0x18018daa8  lea     rdx, [rbp+410h+var_190]
0x18018daaf  lea     rcx, [rbp+410h+var_318]
0x18018dab6  call    ??0?$ActivityBase@VAutopilotUpdateLoggingProvider@Logging@Autopilot@Management@Windows@Microsoft@@$00$0IAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x18018dabb  lea     rax, ??_7Download@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@6B@; const Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Download::`vftable'
0x18018dac2  mov     [rbp+410h+var_318], rax
0x18018dac9  mov     [rbp+410h+var_348], 0
0x18018dad4  lea     rcx, [rbp+410h+var_320]
0x18018dadb  call    ??$_Global_new@V?$_Func_impl_no_alloc@V_lambda_734f4998f4de1a2fb4596d979aecf192_@@X$$V@std@@V_lambda_734f4998f4de1a2fb4596d979aecf192_@@@std@@YAPEAV?$_Func_impl_no_alloc@V_lambda_734f4998f4de1a2fb4596d979aecf192_@@X$$V@0@$$QEAV_lambda_734f4998f4de1a2fb4596d979aecf192_@@@Z; std::_Global_new<std::_Func_impl_no_alloc<_lambda_734f4998f4de1a2fb4596d979aecf192_,void,>,_lambda_734f4998f4de1a2fb4596d979aecf192_>(_lambda_734f4998f4de1a2fb4596d979aecf192_ &&)
0x18018dae0  mov     [rbp+410h+var_348], rax
0x18018dae7  lea     rdx, [rbp+410h+var_380]
0x18018daee  mov     rcx, rbx
0x18018daf1  mov     rax, rdi
0x18018daf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018daf9  nop
0x18018dafa  lea     rcx, [rbp+410h+var_380]
0x18018db01  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x18018db06  nop
0x18018db07  lea     rcx, [rbp+410h+var_320]; this
0x18018db0e  call    ??1_lambda_734f4998f4de1a2fb4596d979aecf192_@@QEAA@XZ; _lambda_734f4998f4de1a2fb4596d979aecf192_::~_lambda_734f4998f4de1a2fb4596d979aecf192_(void)
0x18018db13  mov     rcx, [rsi+8]
0x18018db17  mov     [rsp+510h+var_4B0], rcx
0x18018db1c  test    rcx, rcx
0x18018db1f  jz      short loc_18018DB2E
0x18018db21  mov     rax, [rcx]
0x18018db24  mov     rax, [rax+8]
0x18018db28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018db2d  nop
0x18018db2e  mov     rcx, [rsi+10h]
0x18018db32  mov     [rsp+510h+var_4A8], rcx
0x18018db37  test    rcx, rcx
0x18018db3a  jz      short loc_18018DB49
0x18018db3c  mov     rax, [rcx]
0x18018db3f  mov     rax, [rax+8]
0x18018db43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018db48  nop
0x18018db49  mov     rdx, r14
0x18018db4c  lea     rcx, [rbp+410h+var_450]
0x18018db50  call    ??0?$shared_ptr@VAutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager> const &)
0x18018db55  nop
0x18018db56  lea     rcx, [rbp+410h+var_380]; this
0x18018db5d  call    ??0task_options@Concurrency@@QEAA@XZ; Concurrency::task_options::task_options(void)
0x18018db62  mov     r8, rax
0x18018db65  lea     rdx, [rbp+410h+var_490]
0x18018db69  lea     rcx, [rbp+410h+var_460]
0x18018db6d  call    ??0?$shared_ptr@VAutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager> const &)
0x18018db72  lea     rdx, [rbp+410h+var_460]
0x18018db76  lea     rcx, [rbp+410h+var_480]
0x18018db7a  call    ??$create_task@V?$task_completion_event@X@Concurrency@@@Concurrency@@YA?AV?$task@X@0@V?$task_completion_event@X@0@Vtask_options@0@@Z; Concurrency::create_task<Concurrency::task_completion_event<void>>(Concurrency::task_completion_event<void>,Concurrency::task_options)
0x18018db7f  mov     rdi, rax
0x18018db82  lea     rcx, [rbp+410h+var_420]; this
0x18018db86  call    ??0task_options@Concurrency@@QEAA@XZ; Concurrency::task_options::task_options(void)
0x18018db8b  mov     rbx, rax
0x18018db8e  mov     [rsp+510h+var_4D8], r12
0x18018db93  lea     rax, [rbp+410h+var_450]
0x18018db97  mov     [rsp+510h+var_4E0], rax
0x18018db9c  lea     rax, [rbp+410h+var_190]
0x18018dba3  mov     [rsp+510h+var_4E8], rax
0x18018dba8  lea     rax, [rsp+510h+var_4C8]
0x18018dbad  mov     qword ptr [rsp+510h+var_4F0], rax
0x18018dbb2  lea     r9, [rsp+510h+var_4A8]
0x18018dbb7  lea     r8, [rsp+510h+var_4D0]
0x18018dbbc  lea     rdx, [rsp+510h+var_4B0]
0x18018dbc1  lea     rcx, [rbp+410h+var_320]
0x18018dbc8  call    ??0_lambda_76a63f6372620a881c4c4ab6f024e098_@@QEAA@AEBV?$ComPtr@UIUpdateSession@@@WRL@Microsoft@@AEBV?$ComPtr@UIUpdateDownloader@@@23@AEBV?$ComPtr@UIUpdateCollection@@@23@AEBV?$ComPtr@UIDownloadJob@@@23@AEBVDownload@UpdateOperations@Logging@Autopilot@Management@Windows@3@AEBV?$shared_ptr@VIAutopilotUpdateContext@Autopilot@Windows@Microsoft@@@std@@AEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; _lambda_76a63f6372620a881c4c4ab6f024e098_::_lambda_76a63f6372620a881c4c4ab6f024e098_(Microsoft::WRL::ComPtr<IUpdateSession> const &,Microsoft::WRL::ComPtr<IUpdateDownloader> const &,Microsoft::WRL::ComPtr<IUpdateCollection> const &,Microsoft::WRL::ComPtr<IDownloadJob> const &,Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Download const &,std::shared_ptr<Microsoft::Windows::Autopilot::IAutopilotUpdateContext> const &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> const &)
0x18018dbcd  nop
0x18018dbce  mov     r9, rbx
0x18018dbd1  mov     r8, rax
0x18018dbd4  mov     rdx, r15
0x18018dbd7  mov     rcx, rdi
0x18018dbda  call    ??$then@V_lambda_76a63f6372620a881c4c4ab6f024e098_@@@?$task@X@Concurrency@@QEBA?AV?$task@V?$shared_ptr@VIAutopilotUpdatePayload@Autopilot@Windows@Microsoft@@@std@@@1@AEBV_lambda_76a63f6372620a881c4c4ab6f024e098_@@Vtask_options@1@@Z; Concurrency::task<void>::then<_lambda_76a63f6372620a881c4c4ab6f024e098_>(_lambda_76a63f6372620a881c4c4ab6f024e098_ const &,Concurrency::task_options)
0x18018dbdf  nop
0x18018dbe0  lea     rcx, [rbp+410h+var_320]; this
0x18018dbe7  call    ??1_lambda_76a63f6372620a881c4c4ab6f024e098_@@QEAA@XZ; _lambda_76a63f6372620a881c4c4ab6f024e098_::~_lambda_76a63f6372620a881c4c4ab6f024e098_(void)
0x18018dbec  nop
0x18018dbed  lea     rcx, [rbp+410h+var_480]
0x18018dbf1  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x18018dbf6  nop
0x18018dbf7  mov     rcx, [rbp+410h+var_448]; this
0x18018dbfb  test    rcx, rcx
0x18018dbfe  jz      short loc_18018DC06
0x18018dc00  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18018dc05  nop
0x18018dc06  lea     rcx, [rsp+510h+var_4A8]
0x18018dc0b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018dc10  nop
0x18018dc11  lea     rcx, [rsp+510h+var_4B0]
0x18018dc16  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018dc1b  nop
0x18018dc1c  lea     rcx, [rsp+510h+var_4C0]
0x18018dc21  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018dc26  nop
0x18018dc27  lea     rcx, [rbp+410h+pvarg]; pvarg
0x18018dc2b  call    cs:__imp_VariantClear
0x18018dc32  nop     dword ptr [rax+rax+00h]
0x18018dc37  nop
0x18018dc38  lea     rcx, [rsp+510h+var_4C8]
0x18018dc3d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018dc42  nop
0x18018dc43  lea     rcx, [rsp+510h+var_4B8]
0x18018dc48  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018dc4d  nop
0x18018dc4e  lea     rcx, [rsp+510h+var_4D0]
0x18018dc53  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018dc58  nop
0x18018dc59  lea     rcx, [rbp+410h+var_490]
0x18018dc5d  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x18018dc62  nop
0x18018dc63  lea     rcx, [rbp+410h+var_190]; this
0x18018dc6a  call    ??1Download@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Download::~Download(void)
0x18018dc6f  nop
0x18018dc70  mov     rcx, r12
0x18018dc73  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x18018dc78  mov     rax, r15
0x18018dc7b  mov     rcx, [rbp+410h+var_40]
0x18018dc82  xor     rcx, rsp; StackCookie
0x18018dc85  call    __security_check_cookie
0x18018dc8a  add     rsp, 4E0h
0x18018dc91  pop     r15
0x18018dc93  pop     r14
0x18018dc95  pop     r12
0x18018dc97  pop     rdi
0x18018dc98  pop     rsi
0x18018dc99  pop     rbx
0x18018dc9a  pop     rbp
0x18018dc9b  retn
0x18018dc9d  mov     r9d, eax; char *
0x18018dca0  lea     r8, aOnecoreuapAdmi_110; "onecoreuap\\admin\\moderndeployment\\au"...
0x18018dca7  mov     edx, 177h; void *
0x18018dcac  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18018dcb2  xor     edx, edx; Val
0x18018dcb4  mov     r8d, 98h; Size
0x18018dcba  lea     rcx, [rbp+410h+var_420]; void *
0x18018dcbe  call    memset_0
0x18018dcc3  lea     rcx, [rbp+410h+var_420]; this
0x18018dcc7  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
  ... truncated ...
```
