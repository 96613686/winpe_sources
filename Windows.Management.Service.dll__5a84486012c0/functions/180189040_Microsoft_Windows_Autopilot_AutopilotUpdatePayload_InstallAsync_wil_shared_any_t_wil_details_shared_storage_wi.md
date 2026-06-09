# Microsoft::Windows::Autopilot::AutopilotUpdatePayload::InstallAsync(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>)

- ea: `0x180189040`
- end: `0x1801894c7`
- name: `?InstallAsync@AutopilotUpdatePayload@Autopilot@Windows@Microsoft@@UEAA?AV?$task@V?$shared_ptr@VIAutopilotUpdateInstallResult@Autopilot@Windows@Microsoft@@@std@@@Concurrency@@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z`
- size: `1159`
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
- `0x1801815d0`
- `0x18018202c`
- `0x180183104`
- `0x1801837fc`
- `0x1801842bc`
- `0x180184468`
- `0x180184528`
- `0x180184bfc`
- `0x180185264`
- `0x180185354`
- `0x180185f58`
- `0x180188ffc`
- `0x180189040`
- `0x18018a89c`
- `0x18018bf0c`
- `0x18018bf58`
- `0x1801fa010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1801891f1`
- `OLEAUT32!__imp_VariantInit` at `0x1801891f1`
- `OLEAUT32!__imp_VariantClear` at `0x18018942f`
- `OLEAUT32!__imp_VariantClear` at `0x18018942f`

## string_xrefs

- `0x18018907d`: `Install`
- `0x1801890fa`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotupdate.cpp`
- `0x1801890eb`: `Unable to create installer`
- `0x18018912d`: `put_Updates`
- `0x1801891c8`: `Unable to create installCompletionEvent callbacks`
- `0x180189254`: `Cancel invoked during install`
- `0x1801892cc`: `BeginInstall failed`

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
0x180189040  push    rbp
0x180189042  push    rbx
0x180189043  push    rsi
0x180189044  push    rdi
0x180189045  push    r12
0x180189047  push    r14
0x180189049  push    r15
0x18018904b  lea     rbp, [rsp-3B0h]
0x180189053  sub     rsp, 4B0h
0x18018905a  mov     rax, cs:__security_cookie
0x180189061  xor     rax, rsp
0x180189064  mov     [rbp+3E0h+var_40], rax
0x18018906b  mov     r14, r8
0x18018906e  mov     rsi, rdx
0x180189071  mov     r15, rcx
0x180189074  mov     [rsp+4E0h+var_4A0], rdx
0x180189079  mov     [rbp+3E0h+var_418], r8
0x18018907d  lea     rdx, aInstall; "Install"
0x180189084  lea     rcx, [rbp+3E0h+var_190]; struct wil::details::IFailureCallback *
0x18018908b  call    ??0?$ActivityBase@VAutopilotUpdateLoggingProvider@Logging@Autopilot@Management@Windows@Microsoft@@$00$0IAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180189090  lea     rax, ??_7Install@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@6B@; const Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Install::`vftable'
0x180189097  mov     [rbp+3E0h+var_190], rax
0x18018909e  lea     rcx, [rbp+3E0h+var_190]; this
0x1801890a5  call    ?StartActivity@Install@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@QEAAXXZ; Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Install::StartActivity(void)
0x1801890aa  nop
0x1801890ab  lea     rcx, [rsp+4E0h+var_480]
0x1801890b0  call    ??0?$task_completion_event@E@Concurrency@@QEAA@XZ; Concurrency::task_completion_event<uchar>::task_completion_event<uchar>(void)
0x1801890b5  nop
0x1801890b6  mov     [rsp+4E0h+var_4B0], 0; char *
0x1801890bf  mov     rdi, [r15+8]
0x1801890c3  mov     rax, [rdi]
0x1801890c6  mov     rbx, [rax+70h]
0x1801890ca  lea     rcx, [rsp+4E0h+var_4B0]
0x1801890cf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801890d4  lea     rdx, [rsp+4E0h+var_4B0]
0x1801890d9  mov     rcx, rdi
0x1801890dc  mov     rax, rbx
0x1801890df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801890e4  mov     rcx, [rbp+3E8h]; this
0x1801890eb  lea     rdx, aUnableToCreate_5; "Unable to create installer"
0x1801890f2  mov     qword ptr [rsp+4E0h+var_4C0], rdx; int
0x1801890f7  mov     r9d, eax; char *
0x1801890fa  lea     r12, aOnecoreuapAdmi_110; "onecoreuap\\admin\\moderndeployment\\au"...
0x180189101  mov     r8, r12; unsigned int
0x180189104  mov     edx, 0A9h; void *
0x180189109  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18018910e  mov     rcx, [rsp+4E0h+var_4B0]
0x180189113  mov     rax, [rcx]
0x180189116  mov     rdx, [r15+10h]
0x18018911a  mov     rax, [rax+80h]
0x180189121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180189126  mov     rcx, [rbp+3E8h]; this
0x18018912d  lea     rdx, aPutUpdates; "put_Updates"
0x180189134  mov     qword ptr [rsp+4E0h+var_4C0], rdx; int
0x180189139  mov     r9d, eax; char *
0x18018913c  mov     r8, r12; unsigned int
0x18018913f  mov     edx, 0ACh; void *
0x180189144  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180189149  mov     [rsp+4E0h+var_4A0], 0
0x180189152  mov     rax, [rbp+3E0h+var_80]
0x180189159  cmp     dword ptr [rax], 1
0x18018915c  jnz     loc_1801894AC
0x180189162  lea     rcx, [rbp+3E0h+var_190]
0x180189169  call    ?IncrementExpectedStopCount@?$ActivityBase@VAutopilotUpdateLoggingProvider@Logging@Autopilot@Management@Windows@Microsoft@@$00$0IAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::IncrementExpectedStopCount(void)
0x18018916e  lea     rdx, [rbp+3E0h+var_190]
0x180189175  lea     rcx, [rbp+3E0h+var_310]
0x18018917c  call    ??0?$ActivityBase@VAutopilotUpdateLoggingProvider@Logging@Autopilot@Management@Windows@Microsoft@@$00$0IAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x180189181  lea     rax, ??_7Install@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@6B@; const Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Install::`vftable'
0x180189188  mov     [rbp+3E0h+var_310], rax
0x18018918f  lea     rcx, [rsp+4E0h+var_4A0]
0x180189194  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180189199  lea     r9, [rbp+3E0h+var_310]
0x1801891a0  lea     r8, [rsp+4E0h+var_480]
0x1801891a5  lea     rdx, [r15+18h]
0x1801891a9  lea     rcx, [rsp+4E0h+var_4A0]
0x1801891ae  call    ??$MakeAndInitialize@VWUInstallCallback@Autopilot@Windows@Microsoft@@V1234@AEAV?$shared_ptr@VIAutopilotUpdateContext@Autopilot@Windows@Microsoft@@@std@@AEAV?$task_completion_event@X@Concurrency@@VInstall@UpdateOperations@Logging@2Management@34@@Details@WRL@Microsoft@@YAJPEAPEAVWUInstallCallback@Autopilot@Windows@2@AEAV?$shared_ptr@VIAutopilotUpdateContext@Autopilot@Windows@Microsoft@@@std@@AEAV?$task_completion_event@X@Concurrency@@$$QEAVInstall@UpdateOperations@Logging@4Management@52@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::Windows::Autopilot::WUInstallCallback,Microsoft::Windows::Autopilot::WUInstallCallback,std::shared_ptr<Microsoft::Windows::Autopilot::IAutopilotUpdateContext> &,Concurrency::task_completion_event<void> &,Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Install>(Microsoft::Windows::Autopilot::WUInstallCallback * *,std::shared_ptr<Microsoft::Windows::Autopilot::IAutopilotUpdateContext> &,Concurrency::task_completion_event<void> &,Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Install &&)
0x1801891b3  mov     ebx, eax
0x1801891b5  lea     rcx, [rbp+3E0h+var_310]; this
0x1801891bc  call    ??1Install@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Install::~Install(void)
0x1801891c1  mov     rcx, [rbp+3E8h]; this
0x1801891c8  lea     rax, aUnableToCreate_4; "Unable to create installCompletionEvent"...
0x1801891cf  mov     qword ptr [rsp+4E0h+var_4C0], rax; int
0x1801891d4  mov     r9d, ebx; char *
0x1801891d7  mov     r8, r12; unsigned int
0x1801891da  mov     edx, 0B0h; void *
0x1801891df  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1801891e4  mov     [rsp+4E0h+var_4A8], 0
0x1801891ed  lea     rcx, [rbp+3E0h+pvarg]; pvarg
0x1801891f1  call    cs:__imp_VariantInit
0x1801891f7  nop
0x1801891f8  mov     [rsp+4E0h+var_498], 0
0x180189201  mov     rbx, [rsp+4E0h+var_4A0]
0x180189206  mov     rax, [rbx]
0x180189209  mov     rdi, [rax]
0x18018920c  lea     rcx, [rsp+4E0h+var_498]
0x180189211  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180189216  lea     r8, [rsp+4E0h+var_498]
0x18018921b  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180189222  mov     rcx, rbx
0x180189225  mov     rax, rdi
0x180189228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018922d  nop
0x18018922e  mov     rcx, [rbp+3E8h]; this
0x180189235  test    eax, eax
0x180189237  js      loc_18018949B
0x18018923d  mov     rcx, [r15+18h]
0x180189241  mov     rax, [rcx]
0x180189244  mov     rax, [rax+28h]
0x180189248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018924d  mov     rcx, [rbp+3E8h]; this
0x180189254  lea     rdx, aCancelInvokedD_0; "Cancel invoked during install"
0x18018925b  mov     [rsp+4E0h+var_4B8], rdx; char *
0x180189260  mov     [rsp+4E0h+var_4C0], al; char
0x180189264  mov     r9d, 80004004h; char *
0x18018926a  mov     r8, r12; unsigned int
0x18018926d  mov     edx, 0B9h; void *
0x180189272  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180189277  mov     rdi, [rsp+4E0h+var_4B0]
0x18018927c  mov     rax, [rdi]
0x18018927f  mov     rbx, [rax+88h]
0x180189286  lea     rcx, [rsp+4E0h+var_4A8]
0x18018928b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180189290  movups  xmm0, xmmword ptr [rbp+3E0h+pvarg]
0x180189294  movsd   xmm1, qword ptr [rbp+3E0h+pvarg+10h]
0x180189299  mov     rdx, [rsp+4E0h+var_498]
0x18018929e  movaps  [rsp+4E0h+var_470], xmm0
0x1801892a3  movsd   [rbp+3E0h+var_460], xmm1
0x1801892a8  lea     rax, [rsp+4E0h+var_4A8]
0x1801892ad  mov     qword ptr [rsp+4E0h+var_4C0], rax
0x1801892b2  lea     r9, [rsp+4E0h+var_470]
0x1801892b7  mov     r8, rdx
0x1801892ba  mov     rcx, rdi
0x1801892bd  mov     rax, rbx
0x1801892c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801892c5  mov     rcx, [rbp+3E8h]; this
0x1801892cc  lea     rdx, aBegininstallFa; "BeginInstall failed"
0x1801892d3  mov     qword ptr [rsp+4E0h+var_4C0], rdx; int
0x1801892d8  mov     r9d, eax; char *
0x1801892db  mov     r8, r12; unsigned int
0x1801892de  mov     edx, 0BCh; void *
0x1801892e3  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1801892e8  mov     rbx, [r15+18h]
0x1801892ec  mov     rax, [rbx]
0x1801892ef  mov     rdi, [rax+10h]
0x1801892f3  mov     rcx, [rsp+4E0h+var_4A8]
0x1801892f8  mov     [rbp+3E0h+var_310], rcx
0x1801892ff  test    rcx, rcx
0x180189302  jz      short loc_180189311
0x180189304  mov     rax, [rcx]
0x180189307  mov     rax, [rax+8]
0x18018930b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180189310  nop
0x180189311  lea     rdx, [rbp+3E0h+var_190]
0x180189318  lea     rcx, [rbp+3E0h+var_308]
0x18018931f  call    ??0?$ActivityBase@VAutopilotUpdateLoggingProvider@Logging@Autopilot@Management@Windows@Microsoft@@$00$0IAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x180189324  lea     rax, ??_7Install@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@6B@; const Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Install::`vftable'
0x18018932b  mov     [rbp+3E0h+var_308], rax
0x180189332  mov     [rbp+3E0h+var_338], 0
0x18018933d  lea     rcx, [rbp+3E0h+var_310]
0x180189344  call    ??$_Global_new@V?$_Func_impl_no_alloc@V_lambda_94e79490cbbf81312e51c64809d0d989_@@X$$V@std@@V_lambda_94e79490cbbf81312e51c64809d0d989_@@@std@@YAPEAV?$_Func_impl_no_alloc@V_lambda_94e79490cbbf81312e51c64809d0d989_@@X$$V@0@$$QEAV_lambda_94e79490cbbf81312e51c64809d0d989_@@@Z; std::_Global_new<std::_Func_impl_no_alloc<_lambda_94e79490cbbf81312e51c64809d0d989_,void,>,_lambda_94e79490cbbf81312e51c64809d0d989_>(_lambda_94e79490cbbf81312e51c64809d0d989_ &&)
0x180189349  mov     [rbp+3E0h+var_338], rax
0x180189350  lea     rdx, [rbp+3E0h+var_370]
0x180189354  mov     rcx, rbx
0x180189357  mov     rax, rdi
0x18018935a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018935f  nop
0x180189360  lea     rcx, [rbp+3E0h+var_370]
0x180189364  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x180189369  nop
0x18018936a  lea     rcx, [rbp+3E0h+var_310]; this
0x180189371  call    ??1_lambda_94e79490cbbf81312e51c64809d0d989_@@QEAA@XZ; _lambda_94e79490cbbf81312e51c64809d0d989_::~_lambda_94e79490cbbf81312e51c64809d0d989_(void)
0x180189376  lea     rdx, [r15+18h]
0x18018937a  lea     rcx, [rbp+3E0h+var_440]
0x18018937e  call    ??0?$shared_ptr@VAutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager> const &)
0x180189383  nop
0x180189384  lea     rcx, [rbp+3E0h+var_370]; this
0x180189388  call    ??0task_options@Concurrency@@QEAA@XZ; Concurrency::task_options::task_options(void)
0x18018938d  mov     r8, rax
0x180189390  lea     rdx, [rsp+4E0h+var_480]
0x180189395  lea     rcx, [rbp+3E0h+var_450]
0x180189399  call    ??0?$shared_ptr@VAutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager> const &)
0x18018939e  lea     rdx, [rbp+3E0h+var_450]
0x1801893a2  lea     rcx, [rsp+4E0h+var_470]
0x1801893a7  call    ??$create_task@V?$task_completion_event@X@Concurrency@@@Concurrency@@YA?AV?$task@X@0@V?$task_completion_event@X@0@Vtask_options@0@@Z; Concurrency::create_task<Concurrency::task_completion_event<void>>(Concurrency::task_completion_event<void>,Concurrency::task_options)
0x1801893ac  mov     rdi, rax
0x1801893af  lea     rcx, [rbp+3E0h+var_410]; this
0x1801893b3  call    ??0task_options@Concurrency@@QEAA@XZ; Concurrency::task_options::task_options(void)
0x1801893b8  mov     rbx, rax
0x1801893bb  mov     [rsp+4E0h+var_4B8], r14
0x1801893c0  lea     rax, [rbp+3E0h+var_440]
0x1801893c4  mov     qword ptr [rsp+4E0h+var_4C0], rax
0x1801893c9  lea     r9, [rbp+3E0h+var_190]
0x1801893d0  lea     r8, [rsp+4E0h+var_4A8]
0x1801893d5  lea     rdx, [rsp+4E0h+var_4B0]
0x1801893da  lea     rcx, [rbp+3E0h+var_310]
0x1801893e1  call    ??0_lambda_eb2477cd02ab199a1356e51038d987f6_@@QEAA@AEBV?$ComPtr@UIUpdateInstaller@@@WRL@Microsoft@@AEBV?$ComPtr@UIInstallationJob@@@23@AEBVInstall@UpdateOperations@Logging@Autopilot@Management@Windows@3@AEBV?$shared_ptr@VIAutopilotUpdateContext@Autopilot@Windows@Microsoft@@@std@@AEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; _lambda_eb2477cd02ab199a1356e51038d987f6_::_lambda_eb2477cd02ab199a1356e51038d987f6_(Microsoft::WRL::ComPtr<IUpdateInstaller> const &,Microsoft::WRL::ComPtr<IInstallationJob> const &,Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Install const &,std::shared_ptr<Microsoft::Windows::Autopilot::IAutopilotUpdateContext> const &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> const &)
0x1801893e6  nop
0x1801893e7  mov     r9, rbx
0x1801893ea  mov     r8, rax
0x1801893ed  mov     rdx, rsi
0x1801893f0  mov     rcx, rdi
0x1801893f3  call    ??$then@V_lambda_eb2477cd02ab199a1356e51038d987f6_@@@?$task@X@Concurrency@@QEBA?AV?$task@V?$shared_ptr@VIAutopilotUpdateInstallResult@Autopilot@Windows@Microsoft@@@std@@@1@AEBV_lambda_eb2477cd02ab199a1356e51038d987f6_@@Vtask_options@1@@Z; Concurrency::task<void>::then<_lambda_eb2477cd02ab199a1356e51038d987f6_>(_lambda_eb2477cd02ab199a1356e51038d987f6_ const &,Concurrency::task_options)
0x1801893f8  nop
0x1801893f9  lea     rcx, [rbp+3E0h+var_310]; this
0x180189400  call    ??1_lambda_eb2477cd02ab199a1356e51038d987f6_@@QEAA@XZ; _lambda_eb2477cd02ab199a1356e51038d987f6_::~_lambda_eb2477cd02ab199a1356e51038d987f6_(void)
0x180189405  nop
0x180189406  lea     rcx, [rsp+4E0h+var_470]
0x18018940b  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x180189410  nop
0x180189411  mov     rcx, [rbp+3E0h+var_438]; this
0x180189415  test    rcx, rcx
0x180189418  jz      short loc_180189420
0x18018941a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18018941f  nop
0x180189420  lea     rcx, [rsp+4E0h+var_498]
0x180189425  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018942a  nop
0x18018942b  lea     rcx, [rbp+3E0h+pvarg]; pvarg
0x18018942f  call    cs:__imp_VariantClear
0x180189435  nop
0x180189436  lea     rcx, [rsp+4E0h+var_4A8]
0x18018943b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180189440  nop
0x180189441  lea     rcx, [rsp+4E0h+var_4A0]
0x180189446  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018944b  nop
0x18018944c  lea     rcx, [rsp+4E0h+var_4B0]
0x180189451  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180189456  nop
0x180189457  lea     rcx, [rsp+4E0h+var_480]
0x18018945c  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x180189461  nop
0x180189462  lea     rcx, [rbp+3E0h+var_190]; this
0x180189469  call    ??1Install@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Install::~Install(void)
0x18018946e  nop
0x18018946f  mov     rcx, r14
0x180189472  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x180189477  mov     rax, rsi
0x18018947a  mov     rcx, [rbp+3E0h+var_40]
0x180189481  xor     rcx, rsp; StackCookie
0x180189484  call    __security_check_cookie
0x180189489  add     rsp, 4B0h
0x180189490  pop     r15
0x180189492  pop     r14
0x180189494  pop     r12
0x180189496  pop     rdi
0x180189497  pop     rsi
0x180189498  pop     rbx
0x180189499  pop     rbp
0x18018949a  retn
0x18018949b  mov     r9d, eax; char *
0x18018949e  mov     r8, r12; unsigned int
0x1801894a1  mov     edx, 0B7h; void *
0x1801894a6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801894ac  xor     edx, edx; Val
0x1801894ae  mov     r8d, 98h; Size
0x1801894b4  lea     rcx, [rbp+3E0h+var_410]; void *
0x1801894b8  call    memset_0
0x1801894bd  lea     rcx, [rbp+3E0h+var_410]; this
0x1801894c1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
