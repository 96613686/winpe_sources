# Microsoft::Windows::Autopilot::AutopilotUpdatePayload::InstallAsync(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>)

- ea: `0x18018dd70`
- end: `0x18018e204`
- name: `?InstallAsync@AutopilotUpdatePayload@Autopilot@Windows@Microsoft@@UEAA?AV?$task@V?$shared_ptr@VIAutopilotUpdateInstallResult@Autopilot@Windows@Microsoft@@@std@@@Concurrency@@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z`
- size: `1172`
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
- `0x180186138`
- `0x180186ba4`
- `0x180187c78`
- `0x180188398`
- `0x180188e6c`
- `0x180189018`
- `0x1801890d8`
- `0x180189800`
- `0x180189dc4`
- `0x180189eb4`
- `0x18018ab08`
- `0x18018dd2c`
- `0x18018dd70`
- `0x18018f618`
- `0x180190cd0`
- `0x180190d1c`
- `0x180200010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18018df21`
- `OLEAUT32!__imp_VariantInit` at `0x18018df21`
- `OLEAUT32!__imp_VariantClear` at `0x18018e165`
- `OLEAUT32!__imp_VariantClear` at `0x18018e165`

## string_xrefs

- `0x18018de2a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotupdate.cpp`
- `0x18018de1b`: `Unable to create installer`
- `0x18018de5d`: `put_Updates`
- `0x18018def8`: `Unable to create installCompletionEvent callbacks`
- `0x18018ddad`: `Install`
- `0x18018df8a`: `Cancel invoked during install`
- `0x18018e002`: `BeginInstall failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 (__fastcall ***__fastcall Microsoft::Windows::Autopilot::AutopilotUpdatePayload::InstallAsync(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, _QWORD *),
        __int64 a3))(_QWORD, GUID *, _QWORD *)
{
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, char **); // rbx
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // ebx
  __int64 (__fastcall ***v11)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v12)(_QWORD, GUID *, _QWORD *); // rdi
  int v13; // eax
  char v14; // al
  char *v15; // rdi
  __int64 (__fastcall *v16)(char *, _QWORD, _QWORD, VARIANTARG *, void ***); // rbx
  unsigned int v17; // eax
  __int64 v18; // rbx
  void (__fastcall *v19)(__int64, _BYTE *); // rdi
  __int64 v20; // rdi
  __int64 v21; // rbx
  __int64 v22; // rax
  const struct wil::FailureInfo *v24; // rdx
  int v25; // [rsp+20h] [rbp-E0h]
  char *v26; // [rsp+28h] [rbp-D8h]
  char *v27; // [rsp+28h] [rbp-D8h]
  char *v28; // [rsp+28h] [rbp-D8h]
  char *v29; // [rsp+28h] [rbp-D8h]
  char *v30; // [rsp+30h] [rbp-D0h] BYREF
  void **v31; // [rsp+38h] [rbp-C8h] BYREF
  __int64 (__fastcall ***v32)(_QWORD, GUID *, _QWORD *); // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v33[3]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v34[16]; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG v35; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v36[16]; // [rsp+90h] [rbp-70h] BYREF
  char v37[8]; // [rsp+A0h] [rbp-60h] BYREF
  std::_Ref_count_base *v38; // [rsp+A8h] [rbp-58h]
  VARIANTARG pvarg; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v40; // [rsp+C8h] [rbp-38h]
  _BYTE v41[160]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v42[56]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v43; // [rsp+1A8h] [rbp+A8h]
  void **v44; // [rsp+1D0h] [rbp+D0h] BYREF
  void **v45; // [rsp+1D8h] [rbp+D8h] BYREF
  _QWORD v46[42]; // [rsp+350h] [rbp+250h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4E8h] [rbp+3E8h]

  v32 = a2;
  v40 = a3;
  wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v46);
  v46[0] = &Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Install::`vftable';
  Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Install::StartActivity((Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Install *)v46);
  Concurrency::task_completion_event<unsigned char>::task_completion_event<unsigned char>(v34);
  v30 = 0;
  v6 = *(_QWORD *)(a1 + 8);
  v7 = *(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v6 + 112LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
  v8 = v7(v6, &v30);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xA9,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
    (const char *)v8,
    (int)"Unable to create installer",
    v26);
  v9 = (*(__int64 (__fastcall **)(char *, _QWORD))(*(_QWORD *)v30 + 128LL))(v30, *(_QWORD *)(a1 + 16));
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xAC,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
    (const char *)v9,
    (int)"put_Updates",
    v27);
  v32 = 0;
  if ( *(_DWORD *)v46[34] != 1 )
  {
    memset_0(v41, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v41, v24);
  }
  wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::IncrementExpectedStopCount(v46);
  wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>(
    &v44,
    v46);
  v44 = &Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Install::`vftable';
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  v10 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::Windows::Autopilot::WUInstallCallback,Microsoft::Windows::Autopilot::WUInstallCallback,std::shared_ptr<Microsoft::Windows::Autopilot::IAutopilotUpdateContext> &,Concurrency::task_completion_event<void> &,Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Install>(
          &v32,
          a1 + 24,
          v34,
          &v44);
  Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Install::~Install((Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Install *)&v44);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xB0,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
    (const char *)v10,
    (int)"Unable to create installCompletionEvent callbacks",
    v28);
  v31 = 0;
  VariantInit(&pvarg);
  v33[0] = 0;
  v11 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v32;
  v12 = **v32;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v33);
  v13 = v12(v11, &GUID_00000000_0000_0000_c000_000000000046, v33);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
      (const char *)(unsigned int)v13,
      v25);
  v14 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 40LL))(*(_QWORD *)(a1 + 24));
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xB9,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
    (const char *)0x80004004LL,
    v14,
    (bool)"Cancel invoked during install",
    v30);
  v15 = v30;
  v16 = *(__int64 (__fastcall **)(char *, _QWORD, _QWORD, VARIANTARG *, void ***))(*(_QWORD *)v30 + 136LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  v35 = pvarg;
  v17 = v16(v15, v33[0], v33[0], &v35, &v31);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xBC,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
    (const char *)v17,
    (int)"BeginInstall failed",
    v29);
  v18 = *(_QWORD *)(a1 + 24);
  v19 = *(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v18 + 16LL);
  v44 = v31;
  if ( v31 )
    (*((void (__fastcall **)(void **))*v31 + 1))(v31);
  wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>(
    &v45,
    v46);
  v45 = &Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Install::`vftable';
  v43 = 0;
  v43 = std::_Global_new<std::_Func_impl_no_alloc<_lambda_94e79490cbbf81312e51c64809d0d989_,void,>,_lambda_94e79490cbbf81312e51c64809d0d989_>(&v44);
  v19(v18, v42);
  std::_Func_class<bool,std::wstring const &>::_Tidy(v42);
  _lambda_94e79490cbbf81312e51c64809d0d989_::~_lambda_94e79490cbbf81312e51c64809d0d989_((_lambda_94e79490cbbf81312e51c64809d0d989_ *)&v44);
  std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(
    v37,
    a1 + 24);
  Concurrency::task_options::task_options((Concurrency::task_options *)v42);
  std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(
    v36,
    v34);
  v20 = Concurrency::create_task<Concurrency::task_completion_event<void>>(&v35, v36);
  v21 = Concurrency::task_options::task_options((Concurrency::task_options *)v41);
  v22 = _lambda_eb2477cd02ab199a1356e51038d987f6_::_lambda_eb2477cd02ab199a1356e51038d987f6_(
          (unsigned int)&v44,
          (unsigned int)&v30,
          (unsigned int)&v31,
          (unsigned int)v46,
          (__int64)v37,
          a3);
  Concurrency::task<void>::then<_lambda_eb2477cd02ab199a1356e51038d987f6_>(v20, a2, v22, v21);
  _lambda_eb2477cd02ab199a1356e51038d987f6_::~_lambda_eb2477cd02ab199a1356e51038d987f6_((_lambda_eb2477cd02ab199a1356e51038d987f6_ *)&v44);
  std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(&v35);
  if ( v38 )
    std::_Ref_count_base::_Decref(v38);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v33);
  VariantClear(&pvarg);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
  std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v34);
  Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Install::~Install((Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Install *)v46);
  std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(a3);
  return a2;
}

```

## disassembly

```asm
0x18018dd70  push    rbp
0x18018dd72  push    rbx
0x18018dd73  push    rsi
0x18018dd74  push    rdi
0x18018dd75  push    r12
0x18018dd77  push    r14
0x18018dd79  push    r15
0x18018dd7b  lea     rbp, [rsp-3B0h]
0x18018dd83  sub     rsp, 4B0h
0x18018dd8a  mov     rax, cs:__security_cookie
0x18018dd91  xor     rax, rsp
0x18018dd94  mov     [rbp+3E0h+var_40], rax
0x18018dd9b  mov     r14, r8
0x18018dd9e  mov     rsi, rdx
0x18018dda1  mov     r15, rcx
0x18018dda4  mov     [rsp+4E0h+var_4A0], rdx
0x18018dda9  mov     [rbp+3E0h+var_418], r8
0x18018ddad  lea     rdx, aInstall; "Install"
0x18018ddb4  lea     rcx, [rbp+3E0h+var_190]; struct wil::details::IFailureCallback *
0x18018ddbb  call    ??0?$ActivityBase@VAutopilotUpdateLoggingProvider@Logging@Autopilot@Management@Windows@Microsoft@@$00$0IAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18018ddc0  lea     rax, ??_7Install@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@6B@; const Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Install::`vftable'
0x18018ddc7  mov     [rbp+3E0h+var_190], rax
0x18018ddce  lea     rcx, [rbp+3E0h+var_190]; this
0x18018ddd5  call    ?StartActivity@Install@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@QEAAXXZ; Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Install::StartActivity(void)
0x18018ddda  nop
0x18018dddb  lea     rcx, [rsp+4E0h+var_480]
0x18018dde0  call    ??0?$task_completion_event@E@Concurrency@@QEAA@XZ; Concurrency::task_completion_event<uchar>::task_completion_event<uchar>(void)
0x18018dde5  nop
0x18018dde6  mov     [rsp+4E0h+var_4B0], 0; char *
0x18018ddef  mov     rdi, [r15+8]
0x18018ddf3  mov     rax, [rdi]
0x18018ddf6  mov     rbx, [rax+70h]
0x18018ddfa  lea     rcx, [rsp+4E0h+var_4B0]
0x18018ddff  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018de04  lea     rdx, [rsp+4E0h+var_4B0]
0x18018de09  mov     rcx, rdi
0x18018de0c  mov     rax, rbx
0x18018de0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018de14  mov     rcx, [rbp+3E8h]; this
0x18018de1b  lea     rdx, aUnableToCreate_5; "Unable to create installer"
0x18018de22  mov     qword ptr [rsp+4E0h+var_4C0], rdx; int
0x18018de27  mov     r9d, eax; char *
0x18018de2a  lea     r12, aOnecoreuapAdmi_110; "onecoreuap\\admin\\moderndeployment\\au"...
0x18018de31  mov     r8, r12; unsigned int
0x18018de34  mov     edx, 0A9h; void *
0x18018de39  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18018de3e  mov     rcx, [rsp+4E0h+var_4B0]
0x18018de43  mov     rax, [rcx]
0x18018de46  mov     rdx, [r15+10h]
0x18018de4a  mov     rax, [rax+80h]
0x18018de51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018de56  mov     rcx, [rbp+3E8h]; this
0x18018de5d  lea     rdx, aPutUpdates; "put_Updates"
0x18018de64  mov     qword ptr [rsp+4E0h+var_4C0], rdx; int
0x18018de69  mov     r9d, eax; char *
0x18018de6c  mov     r8, r12; unsigned int
0x18018de6f  mov     edx, 0ACh; void *
0x18018de74  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18018de79  mov     [rsp+4E0h+var_4A0], 0
0x18018de82  mov     rax, [rbp+3E0h+var_80]
0x18018de89  cmp     dword ptr [rax], 1
0x18018de8c  jnz     loc_18018E1E9
0x18018de92  lea     rcx, [rbp+3E0h+var_190]
0x18018de99  call    ?IncrementExpectedStopCount@?$ActivityBase@VAutopilotUpdateLoggingProvider@Logging@Autopilot@Management@Windows@Microsoft@@$00$0IAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::IncrementExpectedStopCount(void)
0x18018de9e  lea     rdx, [rbp+3E0h+var_190]
0x18018dea5  lea     rcx, [rbp+3E0h+var_310]
0x18018deac  call    ??0?$ActivityBase@VAutopilotUpdateLoggingProvider@Logging@Autopilot@Management@Windows@Microsoft@@$00$0IAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x18018deb1  lea     rax, ??_7Install@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@6B@; const Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Install::`vftable'
0x18018deb8  mov     [rbp+3E0h+var_310], rax
0x18018debf  lea     rcx, [rsp+4E0h+var_4A0]
0x18018dec4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018dec9  lea     r9, [rbp+3E0h+var_310]
0x18018ded0  lea     r8, [rsp+4E0h+var_480]
0x18018ded5  lea     rdx, [r15+18h]
0x18018ded9  lea     rcx, [rsp+4E0h+var_4A0]
0x18018dede  call    ??$MakeAndInitialize@VWUInstallCallback@Autopilot@Windows@Microsoft@@V1234@AEAV?$shared_ptr@VIAutopilotUpdateContext@Autopilot@Windows@Microsoft@@@std@@AEAV?$task_completion_event@X@Concurrency@@VInstall@UpdateOperations@Logging@2Management@34@@Details@WRL@Microsoft@@YAJPEAPEAVWUInstallCallback@Autopilot@Windows@2@AEAV?$shared_ptr@VIAutopilotUpdateContext@Autopilot@Windows@Microsoft@@@std@@AEAV?$task_completion_event@X@Concurrency@@$$QEAVInstall@UpdateOperations@Logging@4Management@52@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::Windows::Autopilot::WUInstallCallback,Microsoft::Windows::Autopilot::WUInstallCallback,std::shared_ptr<Microsoft::Windows::Autopilot::IAutopilotUpdateContext> &,Concurrency::task_completion_event<void> &,Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Install>(Microsoft::Windows::Autopilot::WUInstallCallback * *,std::shared_ptr<Microsoft::Windows::Autopilot::IAutopilotUpdateContext> &,Concurrency::task_completion_event<void> &,Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Install &&)
0x18018dee3  mov     ebx, eax
0x18018dee5  lea     rcx, [rbp+3E0h+var_310]; this
0x18018deec  call    ??1Install@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Install::~Install(void)
0x18018def1  mov     rcx, [rbp+3E8h]; this
0x18018def8  lea     rax, aUnableToCreate_4; "Unable to create installCompletionEvent"...
0x18018deff  mov     qword ptr [rsp+4E0h+var_4C0], rax; int
0x18018df04  mov     r9d, ebx; char *
0x18018df07  mov     r8, r12; unsigned int
0x18018df0a  mov     edx, 0B0h; void *
0x18018df0f  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18018df14  mov     [rsp+4E0h+var_4A8], 0
0x18018df1d  lea     rcx, [rbp+3E0h+pvarg]; pvarg
0x18018df21  call    cs:__imp_VariantInit
0x18018df28  nop     dword ptr [rax+rax+00h]
0x18018df2d  nop
0x18018df2e  mov     [rsp+4E0h+var_498], 0
0x18018df37  mov     rbx, [rsp+4E0h+var_4A0]
0x18018df3c  mov     rax, [rbx]
0x18018df3f  mov     rdi, [rax]
0x18018df42  lea     rcx, [rsp+4E0h+var_498]
0x18018df47  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018df4c  lea     r8, [rsp+4E0h+var_498]
0x18018df51  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18018df58  mov     rcx, rbx
0x18018df5b  mov     rax, rdi
0x18018df5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018df63  nop
0x18018df64  mov     rcx, [rbp+3E8h]; this
0x18018df6b  test    eax, eax
0x18018df6d  js      loc_18018E1D8
0x18018df73  mov     rcx, [r15+18h]
0x18018df77  mov     rax, [rcx]
0x18018df7a  mov     rax, [rax+28h]
0x18018df7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018df83  mov     rcx, [rbp+3E8h]; this
0x18018df8a  lea     rdx, aCancelInvokedD_0; "Cancel invoked during install"
0x18018df91  mov     [rsp+4E0h+var_4B8], rdx; char *
0x18018df96  mov     [rsp+4E0h+var_4C0], al; char
0x18018df9a  mov     r9d, 80004004h; char *
0x18018dfa0  mov     r8, r12; unsigned int
0x18018dfa3  mov     edx, 0B9h; void *
0x18018dfa8  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18018dfad  mov     rdi, [rsp+4E0h+var_4B0]
0x18018dfb2  mov     rax, [rdi]
0x18018dfb5  mov     rbx, [rax+88h]
0x18018dfbc  lea     rcx, [rsp+4E0h+var_4A8]
0x18018dfc1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018dfc6  movups  xmm0, xmmword ptr [rbp+3E0h+pvarg]
0x18018dfca  movsd   xmm1, qword ptr [rbp+3E0h+pvarg+10h]
0x18018dfcf  mov     rdx, [rsp+4E0h+var_498]
0x18018dfd4  movaps  [rsp+4E0h+var_470], xmm0
0x18018dfd9  movsd   [rbp+3E0h+var_460], xmm1
0x18018dfde  lea     rax, [rsp+4E0h+var_4A8]
0x18018dfe3  mov     qword ptr [rsp+4E0h+var_4C0], rax
0x18018dfe8  lea     r9, [rsp+4E0h+var_470]
0x18018dfed  mov     r8, rdx
0x18018dff0  mov     rcx, rdi
0x18018dff3  mov     rax, rbx
0x18018dff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018dffb  mov     rcx, [rbp+3E8h]; this
0x18018e002  lea     rdx, aBegininstallFa; "BeginInstall failed"
0x18018e009  mov     qword ptr [rsp+4E0h+var_4C0], rdx; int
0x18018e00e  mov     r9d, eax; char *
0x18018e011  mov     r8, r12; unsigned int
0x18018e014  mov     edx, 0BCh; void *
0x18018e019  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18018e01e  mov     rbx, [r15+18h]
0x18018e022  mov     rax, [rbx]
0x18018e025  mov     rdi, [rax+10h]
0x18018e029  mov     rcx, [rsp+4E0h+var_4A8]
0x18018e02e  mov     [rbp+3E0h+var_310], rcx
0x18018e035  test    rcx, rcx
0x18018e038  jz      short loc_18018E047
0x18018e03a  mov     rax, [rcx]
0x18018e03d  mov     rax, [rax+8]
0x18018e041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e046  nop
0x18018e047  lea     rdx, [rbp+3E0h+var_190]
0x18018e04e  lea     rcx, [rbp+3E0h+var_308]
0x18018e055  call    ??0?$ActivityBase@VAutopilotUpdateLoggingProvider@Logging@Autopilot@Management@Windows@Microsoft@@$00$0IAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x18018e05a  lea     rax, ??_7Install@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@6B@; const Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Install::`vftable'
0x18018e061  mov     [rbp+3E0h+var_308], rax
0x18018e068  mov     [rbp+3E0h+var_338], 0
0x18018e073  lea     rcx, [rbp+3E0h+var_310]
0x18018e07a  call    ??$_Global_new@V?$_Func_impl_no_alloc@V_lambda_94e79490cbbf81312e51c64809d0d989_@@X$$V@std@@V_lambda_94e79490cbbf81312e51c64809d0d989_@@@std@@YAPEAV?$_Func_impl_no_alloc@V_lambda_94e79490cbbf81312e51c64809d0d989_@@X$$V@0@$$QEAV_lambda_94e79490cbbf81312e51c64809d0d989_@@@Z; std::_Global_new<std::_Func_impl_no_alloc<_lambda_94e79490cbbf81312e51c64809d0d989_,void,>,_lambda_94e79490cbbf81312e51c64809d0d989_>(_lambda_94e79490cbbf81312e51c64809d0d989_ &&)
0x18018e07f  mov     [rbp+3E0h+var_338], rax
0x18018e086  lea     rdx, [rbp+3E0h+var_370]
0x18018e08a  mov     rcx, rbx
0x18018e08d  mov     rax, rdi
0x18018e090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e095  nop
0x18018e096  lea     rcx, [rbp+3E0h+var_370]
0x18018e09a  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x18018e09f  nop
0x18018e0a0  lea     rcx, [rbp+3E0h+var_310]; this
0x18018e0a7  call    ??1_lambda_94e79490cbbf81312e51c64809d0d989_@@QEAA@XZ; _lambda_94e79490cbbf81312e51c64809d0d989_::~_lambda_94e79490cbbf81312e51c64809d0d989_(void)
0x18018e0ac  lea     rdx, [r15+18h]
0x18018e0b0  lea     rcx, [rbp+3E0h+var_440]
0x18018e0b4  call    ??0?$shared_ptr@VAutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager> const &)
0x18018e0b9  nop
0x18018e0ba  lea     rcx, [rbp+3E0h+var_370]; this
0x18018e0be  call    ??0task_options@Concurrency@@QEAA@XZ; Concurrency::task_options::task_options(void)
0x18018e0c3  mov     r8, rax
0x18018e0c6  lea     rdx, [rsp+4E0h+var_480]
0x18018e0cb  lea     rcx, [rbp+3E0h+var_450]
0x18018e0cf  call    ??0?$shared_ptr@VAutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager> const &)
0x18018e0d4  lea     rdx, [rbp+3E0h+var_450]
0x18018e0d8  lea     rcx, [rsp+4E0h+var_470]
0x18018e0dd  call    ??$create_task@V?$task_completion_event@X@Concurrency@@@Concurrency@@YA?AV?$task@X@0@V?$task_completion_event@X@0@Vtask_options@0@@Z; Concurrency::create_task<Concurrency::task_completion_event<void>>(Concurrency::task_completion_event<void>,Concurrency::task_options)
0x18018e0e2  mov     rdi, rax
0x18018e0e5  lea     rcx, [rbp+3E0h+var_410]; this
0x18018e0e9  call    ??0task_options@Concurrency@@QEAA@XZ; Concurrency::task_options::task_options(void)
0x18018e0ee  mov     rbx, rax
0x18018e0f1  mov     [rsp+4E0h+var_4B8], r14
0x18018e0f6  lea     rax, [rbp+3E0h+var_440]
0x18018e0fa  mov     qword ptr [rsp+4E0h+var_4C0], rax
0x18018e0ff  lea     r9, [rbp+3E0h+var_190]
0x18018e106  lea     r8, [rsp+4E0h+var_4A8]
0x18018e10b  lea     rdx, [rsp+4E0h+var_4B0]
0x18018e110  lea     rcx, [rbp+3E0h+var_310]
0x18018e117  call    ??0_lambda_eb2477cd02ab199a1356e51038d987f6_@@QEAA@AEBV?$ComPtr@UIUpdateInstaller@@@WRL@Microsoft@@AEBV?$ComPtr@UIInstallationJob@@@23@AEBVInstall@UpdateOperations@Logging@Autopilot@Management@Windows@3@AEBV?$shared_ptr@VIAutopilotUpdateContext@Autopilot@Windows@Microsoft@@@std@@AEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; _lambda_eb2477cd02ab199a1356e51038d987f6_::_lambda_eb2477cd02ab199a1356e51038d987f6_(Microsoft::WRL::ComPtr<IUpdateInstaller> const &,Microsoft::WRL::ComPtr<IInstallationJob> const &,Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Install const &,std::shared_ptr<Microsoft::Windows::Autopilot::IAutopilotUpdateContext> const &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> const &)
0x18018e11c  nop
0x18018e11d  mov     r9, rbx
0x18018e120  mov     r8, rax
0x18018e123  mov     rdx, rsi
0x18018e126  mov     rcx, rdi
0x18018e129  call    ??$then@V_lambda_eb2477cd02ab199a1356e51038d987f6_@@@?$task@X@Concurrency@@QEBA?AV?$task@V?$shared_ptr@VIAutopilotUpdateInstallResult@Autopilot@Windows@Microsoft@@@std@@@1@AEBV_lambda_eb2477cd02ab199a1356e51038d987f6_@@Vtask_options@1@@Z; Concurrency::task<void>::then<_lambda_eb2477cd02ab199a1356e51038d987f6_>(_lambda_eb2477cd02ab199a1356e51038d987f6_ const &,Concurrency::task_options)
0x18018e12e  nop
0x18018e12f  lea     rcx, [rbp+3E0h+var_310]; this
0x18018e136  call    ??1_lambda_eb2477cd02ab199a1356e51038d987f6_@@QEAA@XZ; _lambda_eb2477cd02ab199a1356e51038d987f6_::~_lambda_eb2477cd02ab199a1356e51038d987f6_(void)
0x18018e13b  nop
0x18018e13c  lea     rcx, [rsp+4E0h+var_470]
0x18018e141  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x18018e146  nop
0x18018e147  mov     rcx, [rbp+3E0h+var_438]; this
0x18018e14b  test    rcx, rcx
0x18018e14e  jz      short loc_18018E156
0x18018e150  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18018e155  nop
0x18018e156  lea     rcx, [rsp+4E0h+var_498]
0x18018e15b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018e160  nop
0x18018e161  lea     rcx, [rbp+3E0h+pvarg]; pvarg
0x18018e165  call    cs:__imp_VariantClear
0x18018e16c  nop     dword ptr [rax+rax+00h]
0x18018e171  nop
0x18018e172  lea     rcx, [rsp+4E0h+var_4A8]
0x18018e177  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018e17c  nop
0x18018e17d  lea     rcx, [rsp+4E0h+var_4A0]
0x18018e182  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018e187  nop
0x18018e188  lea     rcx, [rsp+4E0h+var_4B0]
0x18018e18d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018e192  nop
0x18018e193  lea     rcx, [rsp+4E0h+var_480]
0x18018e198  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x18018e19d  nop
0x18018e19e  lea     rcx, [rbp+3E0h+var_190]; this
0x18018e1a5  call    ??1Install@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Install::~Install(void)
0x18018e1aa  nop
0x18018e1ab  mov     rcx, r14
0x18018e1ae  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x18018e1b3  mov     rax, rsi
0x18018e1b6  mov     rcx, [rbp+3E0h+var_40]
0x18018e1bd  xor     rcx, rsp; StackCookie
0x18018e1c0  call    __security_check_cookie
0x18018e1c5  add     rsp, 4B0h
0x18018e1cc  pop     r15
0x18018e1ce  pop     r14
0x18018e1d0  pop     r12
0x18018e1d2  pop     rdi
0x18018e1d3  pop     rsi
0x18018e1d4  pop     rbx
0x18018e1d5  pop     rbp
0x18018e1d6  retn
0x18018e1d8  mov     r9d, eax; char *
0x18018e1db  mov     r8, r12; unsigned int
0x18018e1de  mov     edx, 0B7h; void *
0x18018e1e3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18018e1e9  xor     edx, edx; Val
0x18018e1eb  mov     r8d, 98h; Size
0x18018e1f1  lea     rcx, [rbp+3E0h+var_410]; void *
0x18018e1f5  call    memset_0
0x18018e1fa  lea     rcx, [rbp+3E0h+var_410]; this
0x18018e1fe  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
