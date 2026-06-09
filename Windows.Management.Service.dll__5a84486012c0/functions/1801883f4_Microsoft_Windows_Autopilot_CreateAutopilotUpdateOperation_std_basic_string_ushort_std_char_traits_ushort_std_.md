# Microsoft::Windows::Autopilot::CreateAutopilotUpdateOperation(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Microsoft::WRL::ComPtr<IUnknown> const &,Microsoft::WRL::ComPtr<IUpdateSession> const &)

- ea: `0x1801883f4`
- end: `0x1801888f2`
- name: `?CreateAutopilotUpdateOperation@Autopilot@Windows@Microsoft@@YA?AV?$ComPtr@U?$IAsyncOperationWithProgress@W4AutopilotUpdateStatus@AutoPilot@Service@EnterpriseDeviceManagement@@UAutopilotUpdateProgress@234@@Foundation@Windows@@@WRL@3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIUnknown@@@53@AEBV?$ComPtr@UIUpdateSession@@@53@@Z`
- size: `1278`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180188344`

## callees

- `0x18000b820`
- `0x18000bd0c`
- `0x18000c414`
- `0x180067008`
- `0x18006dfb8`
- `0x18006e89c`
- `0x180077384`
- `0x18007748c`
- `0x18008019c`
- `0x1800841e8`
- `0x1800853a0`
- `0x1800868d4`
- `0x18008939c`
- `0x180093060`
- `0x180093a28`
- `0x1800b7498`
- `0x1801817b8`
- `0x180183f9c`
- `0x180184528`
- `0x180184c50`
- `0x18018528c`
- `0x180185fb0`
- `0x1801883f4`
- `0x18018aa00`
- `0x18018bf58`
- `0x18018ded0`
- `0x18018e424`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1801886d6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1801886d6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18018850c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18018850c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801884f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801884f9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801885f2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801885f2`

## string_xrefs

- `0x180188451`: `Update`
- `0x18018859d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotupdate.cpp`
- `0x1801888e0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotupdate.cpp`
- `0x18018882a`: `Failed to make Autopilot update operation`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
_QWORD *__fastcall Microsoft::Windows::Autopilot::CreateAutopilotUpdateOperation(
        _QWORD *a1,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4)
{
  const unsigned __int16 *v6; // rbx
  std::_Ref_count_base *v7; // rcx
  HANDLE CurrentProcess; // rax
  const char *v9; // r9
  _DWORD *v10; // rdi
  unsigned int v11; // eax
  __int64 v12; // rbx
  int ActivationFactory; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64, _QWORD, __int64 *); // rbx
  int v16; // eax
  char *v17; // rdi
  _DWORD *v18; // r15
  __int64 v19; // rcx
  __int64 v20; // rbx
  __int64 updated; // rax
  __int64 v22; // r8
  int v24; // [rsp+20h] [rbp-E0h]
  char *v25; // [rsp+28h] [rbp-D8h]
  char *v26; // [rsp+28h] [rbp-D8h]
  __int64 v27; // [rsp+48h] [rbp-B8h] BYREF
  std::_Ref_count_base *v28; // [rsp+50h] [rbp-B0h]
  char v29[8]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v31; // [rsp+68h] [rbp-98h] BYREF
  PHANDLE TokenHandle[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v33; // [rsp+80h] [rbp-80h] BYREF
  std::_Ref_count_base *v34; // [rsp+88h] [rbp-78h]
  _QWORD *v35; // [rsp+90h] [rbp-70h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  _QWORD v37[2]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v38[3]; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v40; // [rsp+E0h] [rbp-20h]
  _QWORD v41[42]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v42[448]; // [rsp+240h] [rbp+140h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+448h] [rbp+348h]

  *(_QWORD *)v29 = a4;
  v35 = a3;
  v36 = a2;
  v38[2] = a1;
  v6 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v41);
  v41[0] = &Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Update::`vftable';
  Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Update::StartActivity(
    (Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Update *)v41,
    v6);
  *(_OWORD *)TokenHandle = 0;
  wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::reset(
    TokenHandle,
    0);
  if ( !TokenHandle[0] )
  {
    v7 = (std::_Ref_count_base *)operator new(0x18u);
    v34 = v7;
    *(_OWORD *)v7 = 0;
    *((_DWORD *)v7 + 2) = 1;
    *((_DWORD *)v7 + 3) = 1;
    *(_QWORD *)v7 = &std::_Ref_count_obj2<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::`vftable';
    *((_QWORD *)v7 + 2) = 0;
    v27 = (__int64)v7 + 16;
    v28 = v7;
    std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry>::operator=(TokenHandle, &v27);
    if ( v28 )
      std::_Ref_count_base::_Decref(v28);
  }
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0xEu, TokenHandle[0]) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x30A,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
      v9);
  v10 = operator new(0x18u);
  v34 = (std::_Ref_count_base *)v10;
  *(_OWORD *)v10 = 0;
  v10[2] = 1;
  v10[3] = 1;
  *(_QWORD *)v10 = &std::_Ref_count_obj2<Microsoft::Windows::Autopilot::AutopilotUpdateCtacRegistryKeyManager>::`vftable';
  Microsoft::Windows::Autopilot::AutopilotUpdateCtacRegistryKeyManager::AutopilotUpdateCtacRegistryKeyManager((Microsoft::Windows::Autopilot::AutopilotUpdateCtacRegistryKeyManager *)(v10 + 4));
  v37[0] = v10 + 4;
  v37[1] = v10;
  wil::make_bstr(&v33, L"ManagementOOBE");
  v11 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a4 + 64LL))(*a4, v33);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x311,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
    (const char *)v11,
    (int)"Failed to put_ClientApplicationID",
    v25);
  v30 = 0;
  v40 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Flighting.OneSettings.OneSettingsManager",
    0x3Au,
    0x39u);
  v12 = v40;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
  ActivationFactory = RoGetActivationFactory(v12, &GUID_6ebfc469_e65b_45eb_9863_b3f57e2a5017, &v30);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x314,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v24);
  v31 = 0;
  v14 = v30;
  v15 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 *))(*(_QWORD *)v30 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  v40 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"CTAC", 5u, 4u);
  v16 = v15(v14, v40, 0, &v31);
  if ( v16 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x319,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
      (const char *)(unsigned int)v16,
      v24);
  *a1 = 0;
  v17 = (char *)operator new(0xA8u);
  v27 = (__int64)v17;
  *(_OWORD *)v17 = 0;
  *((_DWORD *)v17 + 2) = 1;
  *((_DWORD *)v17 + 3) = 1;
  *(_QWORD *)v17 = &std::_Ref_count_obj2<Microsoft::Windows::Autopilot::AutopilotUpdateOperationContext>::`vftable';
  memset_0(v17 + 26, 0, 0x8Eu);
  *((_QWORD *)v17 + 2) = &Microsoft::Windows::Autopilot::AutopilotUpdateOperationContext::`vftable';
  *((_WORD *)v17 + 12) = 0;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v17 + 32), 0, 0);
  *((_QWORD *)v17 + 9) = 0;
  *((_QWORD *)v17 + 10) = 0;
  *((_QWORD *)v17 + 11) = 0;
  *((_QWORD *)v17 + 12) = 0;
  *((_QWORD *)v17 + 20) = 0;
  v38[0] = v17 + 16;
  v38[1] = v17;
  v18 = operator new(0x30u);
  v27 = (__int64)v18;
  *(_OWORD *)v18 = 0;
  v18[2] = 1;
  v18[3] = 1;
  *(_QWORD *)v18 = &std::_Ref_count_obj2<Microsoft::Windows::Autopilot::AutopilotUpdateSearcher>::`vftable';
  _InterlockedIncrement((volatile signed __int32 *)v17 + 2);
  v27 = (__int64)(v17 + 16);
  v28 = (std::_Ref_count_base *)v17;
  *((_QWORD *)v18 + 2) = &Microsoft::Windows::Autopilot::AutopilotUpdateSearcher::`vftable';
  v19 = **(_QWORD **)v29;
  *((_QWORD *)v18 + 3) = **(_QWORD **)v29;
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
  std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(
    v18 + 8,
    &v27);
  std::_Ref_count_base::_Decref((std::_Ref_count_base *)v17);
  hstringHeader.Reserved.Reserved1 = v18 + 4;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = v18;
  *(_QWORD *)v29 = *v35;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<ModernDeployment::Autopilot::Core::IDiscoveryUrlRequestInfo *>>::InternalAddRef(v29);
  v20 = lambda_a19a8da35514efa0f6ca678ab46fa2c8_::_lambda_a19a8da35514efa0f6ca678ab46fa2c8__0(
          (unsigned int)v42,
          (unsigned int)&hstringHeader,
          (unsigned int)v38,
          (unsigned int)v41,
          v36,
          (__int64)v29,
          (__int64)v37,
          (__int64)TokenHandle);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1);
  v27 = 4;
  LODWORD(v28) = 0;
  updated = Windows::Internal::MakeOpLambda_1_Windows::Internal::ProgressResult_Windows::Internal::CBasicResult_enum_EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUpdateStatus_1__EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUpdateProgress___lambda_a19a8da35514efa0f6ca678ab46fa2c8___(v20);
  LODWORD(v20) = Windows::Internal::MakeAsyncOperationWithProgressHelper<Windows::Internal::ProgressResult<Windows::Internal::CBasicResult<enum EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUpdateStatus,1>,EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUpdateProgress>,enum EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUpdateStatus,EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUpdateProgress,Windows::Internal::ComTaskPoolHandler>(
                   &v27,
                   a1,
                   v22,
                   updated);
  lambda_a19a8da35514efa0f6ca678ab46fa2c8_::__lambda_a19a8da35514efa0f6ca678ab46fa2c8_(v42);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x3A4,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
    (const char *)(unsigned int)v20,
    (int)"Failed to make Autopilot update operation",
    v26);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v29);
  std::_Ref_count_base::_Decref((std::_Ref_count_base *)v18);
  std::_Ref_count_base::_Decref((std::_Ref_count_base *)v17);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
  std::_Ref_count_base::_Decref(v34);
  std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(TokenHandle);
  Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Update::~Update((Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Update *)v41);
  return a1;
}

```

## disassembly

```asm
0x1801883f4  mov     [rsp-8+arg_10], rbx
0x1801883f9  push    rbp
0x1801883fa  push    rsi
0x1801883fb  push    rdi
0x1801883fc  push    r12
0x1801883fe  push    r13
0x180188400  push    r14
0x180188402  push    r15
0x180188404  lea     rbp, [rsp-310h]
0x18018840c  sub     rsp, 410h
0x180188413  mov     rax, cs:__security_cookie
0x18018841a  xor     rax, rsp
0x18018841d  mov     [rbp+340h+var_40], rax
0x180188424  mov     r14, r9
0x180188427  mov     qword ptr [rsp+440h+var_3E8], r9
0x18018842c  mov     [rbp+340h+var_3B0], r8
0x180188430  mov     [rbp+340h+var_3A8], rdx
0x180188434  mov     r12, rcx
0x180188437  mov     [rbp+340h+var_380], rcx
0x18018843b  xor     r15d, r15d
0x18018843e  mov     esi, r15d
0x180188441  mov     [rsp+440h+var_400], r15d
0x180188446  mov     rcx, rdx
0x180188449  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18018844e  mov     rbx, rax
0x180188451  lea     rdx, aUpdate; "Update"
0x180188458  lea     rcx, [rbp+340h+var_350]; struct wil::details::IFailureCallback *
0x18018845c  call    ??0?$ActivityBase@VAutopilotUpdateLoggingProvider@Logging@Autopilot@Management@Windows@Microsoft@@$00$0IAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180188461  lea     rax, ??_7Update@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@6B@; const Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Update::`vftable'
0x180188468  mov     [rbp+340h+var_350], rax
0x18018846c  mov     rdx, rbx; unsigned __int16 *
0x18018846f  lea     rcx, [rbp+340h+var_350]; this
0x180188473  call    ?StartActivity@Update@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@QEAAXPEBG@Z; Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Update::StartActivity(ushort const *)
0x180188478  nop
0x180188479  xorps   xmm1, xmm1
0x18018847c  movdqu  xmmword ptr [rsp+440h+TokenHandle], xmm1
0x180188482  xor     edx, edx
0x180188484  lea     rcx, [rsp+440h+TokenHandle]
0x180188489  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::reset(void *)
0x18018848e  lea     ebx, [r15+18h]
0x180188492  lea     r13d, [r15+1]
0x180188496  cmp     [rsp+440h+TokenHandle], r15
0x18018849b  jnz     short loc_1801884F9
0x18018849d  mov     ecx, ebx; Size
0x18018849f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801884a4  mov     rcx, rax
0x1801884a7  mov     [rbp+340h+var_3B8], rax
0x1801884ab  xorps   xmm0, xmm0
0x1801884ae  movups  xmmword ptr [rax], xmm0
0x1801884b1  mov     [rax+8], r13d
0x1801884b5  mov     [rax+0Ch], r13d
0x1801884b9  lea     rax, ??_7?$_Ref_count_obj2@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@6B@; const std::_Ref_count_obj2<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::`vftable'
0x1801884c0  mov     [rcx], rax
0x1801884c3  lea     rax, [rcx+10h]
0x1801884c7  mov     [rax], r15
0x1801884ca  lea     esi, [rbx-16h]
0x1801884cd  mov     [rsp+440h+var_400], esi
0x1801884d1  mov     [rsp+440h+var_3F8], rax
0x1801884d6  mov     [rsp+440h+var_3F0], rcx
0x1801884db  lea     rdx, [rsp+440h+var_3F8]
0x1801884e0  lea     rcx, [rsp+440h+TokenHandle]
0x1801884e5  call    ??4?$shared_ptr@VEtwProcessingDataEntry@Diagnostics@Autopilot@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry>::operator=(std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry> &&)
0x1801884ea  mov     rcx, [rsp+440h+var_3F0]; this
0x1801884ef  test    rcx, rcx
0x1801884f2  jz      short loc_1801884F9
0x1801884f4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801884f9  call    cs:__imp_GetCurrentProcess
0x1801884ff  mov     r8, [rsp+440h+TokenHandle]; TokenHandle
0x180188504  mov     edx, 0Eh; DesiredAccess
0x180188509  mov     rcx, rax; ProcessHandle
0x18018850c  call    cs:__imp_OpenProcessToken
0x180188512  mov     rcx, [rbp+348h]; this
0x180188519  test    eax, eax
0x18018851b  jz      loc_1801888E0
0x180188521  mov     rcx, rbx; Size
0x180188524  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180188529  mov     rdi, rax
0x18018852c  mov     [rbp+340h+var_3B8], rax
0x180188530  xorps   xmm0, xmm0
0x180188533  movups  xmmword ptr [rax], xmm0
0x180188536  mov     [rax+8], r13d
0x18018853a  mov     [rax+0Ch], r13d
0x18018853e  lea     rax, ??_7?$_Ref_count_obj2@VAutopilotUpdateCtacRegistryKeyManager@Autopilot@Windows@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Windows::Autopilot::AutopilotUpdateCtacRegistryKeyManager>::`vftable'
0x180188545  mov     [rdi], rax
0x180188548  lea     rbx, [rdi+10h]
0x18018854c  mov     rcx, rbx; this
0x18018854f  call    ??0AutopilotUpdateCtacRegistryKeyManager@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::AutopilotUpdateCtacRegistryKeyManager::AutopilotUpdateCtacRegistryKeyManager(void)
0x180188554  or      esi, 4
0x180188557  mov     [rsp+440h+var_400], esi
0x18018855b  mov     [rbp+340h+var_3A0], rbx
0x18018855f  mov     [rbp+340h+var_398], rdi
0x180188563  lea     rdx, aManagementoobe; "ManagementOOBE"
0x18018856a  lea     rcx, [rbp+340h+var_3C0]
0x18018856e  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180188573  nop
0x180188574  mov     rcx, [r14]
0x180188577  mov     rax, [rcx]
0x18018857a  mov     rdx, [rbp+340h+var_3C0]
0x18018857e  mov     rax, [rax+40h]
0x180188582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188587  mov     rcx, [rbp+348h]; this
0x18018858e  lea     rdx, aFailedToPutCli; "Failed to put_ClientApplicationID"
0x180188595  mov     qword ptr [rsp+440h+var_420], rdx; int
0x18018859a  mov     r9d, eax; char *
0x18018859d  lea     r14, aOnecoreuapAdmi_110; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801885a4  mov     r8, r14; unsigned int
0x1801885a7  mov     edx, 311h; void *
0x1801885ac  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1801885b1  mov     [rsp+440h+var_3E0], r15
0x1801885b6  mov     [rbp+340h+var_360], r15
0x1801885ba  mov     r9d, 39h ; '9'; unsigned int
0x1801885c0  lea     r8d, [r9+1]; unsigned int
0x1801885c4  lea     rdx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsManager@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x1801885cb  lea     rcx, [rbp+340h+hstringHeader]; hstringHeader
0x1801885cf  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801885d4  nop
0x1801885d5  mov     rbx, [rbp+340h+var_360]
0x1801885d9  lea     rcx, [rsp+440h+var_3E0]
0x1801885de  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801885e3  lea     r8, [rsp+440h+var_3E0]
0x1801885e8  lea     rdx, _GUID_6ebfc469_e65b_45eb_9863_b3f57e2a5017
0x1801885ef  mov     rcx, rbx
0x1801885f2  call    cs:__imp_RoGetActivationFactory
0x1801885f8  mov     rcx, [rbp+348h]; this
0x1801885ff  test    eax, eax
0x180188601  js      loc_1801888CF
0x180188607  mov     [rsp+440h+var_3D8], r15
0x18018860c  mov     rdi, [rsp+440h+var_3E0]
0x180188611  mov     rax, [rdi]
0x180188614  mov     rbx, [rax+38h]
0x180188618  lea     rcx, [rsp+440h+var_3D8]
0x18018861d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180188622  mov     [rbp+340h+var_360], r15
0x180188626  mov     r9d, 4; unsigned int
0x18018862c  lea     r8d, [r9+1]; unsigned int
0x180188630  lea     rdx, aCtac; "CTAC"
0x180188637  lea     rcx, [rbp+340h+hstringHeader]; hstringHeader
0x18018863b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180188640  nop
0x180188641  lea     r9, [rsp+440h+var_3D8]
0x180188646  xor     r8d, r8d
0x180188649  mov     rdx, [rbp+340h+var_360]
0x18018864d  mov     rcx, rdi
0x180188650  mov     rax, rbx
0x180188653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188658  mov     rcx, [rbp+348h]; this
0x18018865f  test    eax, eax
0x180188661  jns     short loc_180188674
0x180188663  mov     r9d, eax; char *
0x180188666  mov     r8, r14; unsigned int
0x180188669  mov     edx, 319h; void *
0x18018866e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180188673  nop
0x180188674  mov     [r12], r15
0x180188678  or      esi, r13d
0x18018867b  mov     [rsp+440h+var_400], esi
0x18018867f  mov     ecx, 0A8h; Size
0x180188684  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180188689  mov     rdi, rax
0x18018868c  mov     [rsp+440h+var_3F8], rax
0x180188691  xorps   xmm0, xmm0
0x180188694  movups  xmmword ptr [rax], xmm0
0x180188697  mov     [rax+8], r13d
0x18018869b  mov     [rax+0Ch], r13d
0x18018869f  lea     rax, ??_7?$_Ref_count_obj2@VAutopilotUpdateOperationContext@Autopilot@Windows@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Windows::Autopilot::AutopilotUpdateOperationContext>::`vftable'
0x1801886a6  mov     [rdi], rax
0x1801886a9  lea     rbx, [rdi+10h]
0x1801886ad  lea     rcx, [rbx+0Ah]; void *
0x1801886b1  xor     edx, edx; Val
0x1801886b3  mov     r8d, 8Eh; Size
0x1801886b9  call    memset_0
0x1801886be  lea     rax, ??_7AutopilotUpdateOperationContext@Autopilot@Windows@Microsoft@@6B@; const Microsoft::Windows::Autopilot::AutopilotUpdateOperationContext::`vftable'
0x1801886c5  mov     [rbx], rax
0x1801886c8  mov     [rbx+8], r15w
0x1801886cd  lea     rcx, [rbx+10h]; lpCriticalSection
0x1801886d1  xor     r8d, r8d; Flags
0x1801886d4  xor     edx, edx; dwSpinCount
0x1801886d6  call    cs:__imp_InitializeCriticalSectionEx
0x1801886dc  mov     [rbx+38h], r15
0x1801886e0  mov     [rbx+40h], r15
0x1801886e4  mov     [rbx+48h], r15
0x1801886e8  mov     [rbx+50h], r15
0x1801886ec  mov     [rbx+90h], r15
0x1801886f3  or      esi, 8
0x1801886f6  mov     [rsp+440h+var_400], esi
0x1801886fa  mov     [rbp+340h+var_390], rbx
0x1801886fe  mov     [rbp+340h+var_388], rdi
0x180188702  mov     ecx, 30h ; '0'; Size
0x180188707  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18018870c  mov     r15, rax
0x18018870f  mov     [rsp+440h+var_3F8], rax
0x180188714  xorps   xmm0, xmm0
0x180188717  movups  xmmword ptr [rax], xmm0
0x18018871a  mov     [rax+8], r13d
0x18018871e  mov     [rax+0Ch], r13d
0x180188722  lea     rax, ??_7?$_Ref_count_obj2@VAutopilotUpdateSearcher@Autopilot@Windows@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Windows::Autopilot::AutopilotUpdateSearcher>::`vftable'
0x180188729  mov     [r15], rax
0x18018872c  lea     r13, [r15+10h]
0x180188730  lock inc dword ptr [rdi+8]
0x180188734  mov     [rsp+440h+var_3F8], rbx
0x180188739  mov     [rsp+440h+var_3F0], rdi
0x18018873e  lea     rax, ??_7AutopilotUpdateSearcher@Autopilot@Windows@Microsoft@@6B@; const Microsoft::Windows::Autopilot::AutopilotUpdateSearcher::`vftable'
0x180188745  mov     [r13+0], rax
0x180188749  mov     rcx, qword ptr [rsp+440h+var_3E8]
0x18018874e  mov     rcx, [rcx]
0x180188751  mov     [r13+8], rcx
0x180188755  test    rcx, rcx
0x180188758  jz      short loc_180188767
0x18018875a  mov     rax, [rcx]
0x18018875d  mov     rax, [rax+8]
0x180188761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188766  nop
0x180188767  lea     rcx, [r13+10h]
0x18018876b  lea     rdx, [rsp+440h+var_3F8]
0x180188770  call    ??0?$shared_ptr@VAutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager> const &)
0x180188775  mov     rcx, rdi; this
0x180188778  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18018877d  or      esi, 10h
0x180188780  mov     [rsp+440h+var_400], esi
0x180188784  mov     qword ptr [rbp+340h+hstringHeader.Reserved], r13
0x180188788  mov     qword ptr [rbp+340h+hstringHeader.Reserved+8], r15
0x18018878c  mov     rax, [rbp+340h+var_3B0]
0x180188790  mov     rax, [rax]
0x180188793  mov     qword ptr [rsp+440h+var_3E8], rax
0x180188798  lea     rcx, [rsp+440h+var_3E8]
0x18018879d  call    ?InternalAddRef@?$ComPtr@U?$IAsyncOperationCompletedHandler@PEAUIDiscoveryUrlRequestInfo@Core@Autopilot@ModernDeployment@@@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<ModernDeployment::Autopilot::Core::IDiscoveryUrlRequestInfo *>>::InternalAddRef(void)
0x1801887a2  nop
0x1801887a3  lea     rax, [rsp+440h+TokenHandle]
0x1801887a8  mov     [rsp+440h+var_408], rax
0x1801887ad  lea     rax, [rbp+340h+var_3A0]
0x1801887b1  mov     [rsp+440h+var_410], rax
0x1801887b6  lea     rax, [rsp+440h+var_3E8]
0x1801887bb  mov     [rsp+440h+var_418], rax; char *
0x1801887c0  mov     rax, [rbp+340h+var_3A8]
0x1801887c4  mov     qword ptr [rsp+440h+var_420], rax
0x1801887c9  lea     r9, [rbp+340h+var_350]
0x1801887cd  lea     r8, [rbp+340h+var_390]
0x1801887d1  lea     rdx, [rbp+340h+hstringHeader]
0x1801887d5  lea     rcx, [rbp+340h+var_200]
0x1801887dc  call    _lambda_a19a8da35514efa0f6ca678ab46fa2c8____lambda_a19a8da35514efa0f6ca678ab46fa2c8__0
0x1801887e1  mov     rbx, rax
0x1801887e4  mov     rcx, r12
0x1801887e7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801887ec  mov     [rsp+440h+var_3F8], 4
0x1801887f5  mov     dword ptr [rsp+440h+var_3F0], 0
0x1801887fd  mov     rcx, rbx
0x180188800  call    Windows__Internal__MakeOpLambda_1_Windows__Internal__ProgressResult_Windows__Internal__CBasicResult_enum_EnterpriseDeviceManagement__Service__AutoPilot__AutopilotUpdateStatus_1__EnterpriseDeviceManagement__Service__AutoPilot__AutopilotUpdateProgress___lambda_a19a8da35514efa0f6ca678ab46fa2c8___
0x180188805  mov     r9, rax
0x180188808  mov     rdx, r12
0x18018880b  lea     rcx, [rsp+440h+var_3F8]
0x180188810  call    ??$MakeAsyncOperationWithProgressHelper@V?$ProgressResult@V?$CBasicResult@W4AutopilotUpdateStatus@AutoPilot@Service@EnterpriseDeviceManagement@@$00@Internal@Windows@@UAutopilotUpdateProgress@AutoPilot@Service@EnterpriseDeviceManagement@@@Internal@Windows@@W4AutopilotUpdateStatus@AutoPilot@Service@EnterpriseDeviceManagement@@UAutopilotUpdateProgress@567@VComTaskPoolHandler@23@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperationWithProgress@W4AutopilotUpdateStatus@AutoPilot@Service@EnterpriseDeviceManagement@@UAutopilotUpdateProgress@234@@Foundation@1@W4TrustLevel@@PEAV?$AsyncCallbackBase@V?$ProgressResult@V?$CBasicResult@W4AutopilotUpdateStatus@AutoPilot@Service@EnterpriseDeviceManagement@@$00@Internal@Windows@@UAutopilotUpdateProgress@AutoPilot@Service@EnterpriseDeviceManagement@@@Internal@Windows@@@01@@Z; Windows::Internal::MakeAsyncOperationWithProgressHelper<Windows::Internal::ProgressResult<Windows::Internal::CBasicResult<EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUpdateStatus,1>,EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUpdateProgress>,EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUpdateStatus,EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUpdateProgress,Windows::Internal::ComTaskPoolHandler>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperationWithProgress<EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUpdateStatus,EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUpdateProgress> * *,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::ProgressResult<Windows::Internal::CBasicResult<EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUpdateStatus,1>,EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUpdateProgress>> *)
0x180188815  mov     ebx, eax
0x180188817  lea     rcx, [rbp+340h+var_200]
0x18018881e  call    _lambda_a19a8da35514efa0f6ca678ab46fa2c8_____lambda_a19a8da35514efa0f6ca678ab46fa2c8_
0x180188823  mov     rcx, [rbp+348h]; this
0x18018882a  lea     rax, aFailedToMakeAu; "Failed to make Autopilot update operati"...
0x180188831  mov     qword ptr [rsp+440h+var_420], rax; int
0x180188836  mov     r9d, ebx; char *
0x180188839  mov     r8, r14; unsigned int
0x18018883c  mov     edx, 3A4h; void *
0x180188841  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180188846  nop
0x180188847  lea     rcx, [rsp+440h+var_3E8]
0x18018884c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180188851  nop
0x180188852  mov     rcx, r15; this
0x180188855  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18018885a  nop
0x18018885b  mov     rcx, rdi; this
0x18018885e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180188863  nop
0x180188864  lea     rcx, [rsp+440h+var_3D8]
0x180188869  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018886e  nop
0x18018886f  lea     rcx, [rsp+440h+var_3E0]
0x180188874  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180188879  nop
0x18018887a  lea     rcx, [rbp+340h+var_3C0]
0x18018887e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180188883  nop
0x180188884  mov     rcx, [rbp+340h+var_3B8]; this
0x180188888  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18018888d  nop
0x18018888e  lea     rcx, [rsp+440h+TokenHandle]
0x180188893  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x180188898  nop
0x180188899  lea     rcx, [rbp+340h+var_350]; this
0x18018889d  call    ??1Update@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Update::~Update(void)
0x1801888a2  mov     rax, r12
0x1801888a5  mov     rcx, [rbp+340h+var_40]
0x1801888ac  xor     rcx, rsp; StackCookie
0x1801888af  call    __security_check_cookie
0x1801888b4  mov     rbx, [rsp+440h+arg_10]
0x1801888bc  add     rsp, 410h
0x1801888c3  pop     r15
0x1801888c5  pop     r14
0x1801888c7  pop     r13
0x1801888c9  pop     r12
0x1801888cb  pop     rdi
0x1801888cc  pop     rsi
  ... truncated ...
```
