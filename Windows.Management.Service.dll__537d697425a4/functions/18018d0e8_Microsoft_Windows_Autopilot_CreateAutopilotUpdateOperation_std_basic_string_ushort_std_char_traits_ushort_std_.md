# Microsoft::Windows::Autopilot::CreateAutopilotUpdateOperation(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Microsoft::WRL::ComPtr<IUnknown> const &,Microsoft::WRL::ComPtr<IUpdateSession> const &)

- ea: `0x18018d0e8`
- end: `0x18018d5ff`
- name: `?CreateAutopilotUpdateOperation@Autopilot@Windows@Microsoft@@YA?AV?$ComPtr@U?$IAsyncOperationWithProgress@W4AutopilotUpdateStatus@AutoPilot@Service@EnterpriseDeviceManagement@@UAutopilotUpdateProgress@234@@Foundation@Windows@@@WRL@3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIUnknown@@@53@AEBV?$ComPtr@UIUpdateSession@@@53@@Z`
- size: `1303`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18018d030`

## callees

- `0x18000b8f0`
- `0x18000bddc`
- `0x18000c504`
- `0x180067398`
- `0x18006e508`
- `0x18006ee48`
- `0x180077c04`
- `0x180077d0c`
- `0x180080bac`
- `0x180084d5c`
- `0x180086044`
- `0x180087634`
- `0x18008a26c`
- `0x1800942e8`
- `0x180094ce0`
- `0x1800b9178`
- `0x180186320`
- `0x180188b4c`
- `0x1801890d8`
- `0x180189854`
- `0x180189dec`
- `0x18018ab60`
- `0x18018d0e8`
- `0x18018f790`
- `0x180190d1c`
- `0x180192d90`
- `0x180193368`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18018d3dc`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18018d3dc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18018d206`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18018d206`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18018d1ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18018d1ed`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18018d2f2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18018d2f2`

## string_xrefs

- `0x18018d145`: `Update`
- `0x18018d29d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotupdate.cpp`
- `0x18018d5ed`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotupdate.cpp`
- `0x18018d536`: `Failed to make Autopilot update operation`

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
0x18018d0e8  mov     [rsp-8+arg_10], rbx
0x18018d0ed  push    rbp
0x18018d0ee  push    rsi
0x18018d0ef  push    rdi
0x18018d0f0  push    r12
0x18018d0f2  push    r13
0x18018d0f4  push    r14
0x18018d0f6  push    r15
0x18018d0f8  lea     rbp, [rsp-310h]
0x18018d100  sub     rsp, 410h
0x18018d107  mov     rax, cs:__security_cookie
0x18018d10e  xor     rax, rsp
0x18018d111  mov     [rbp+340h+var_40], rax
0x18018d118  mov     r14, r9
0x18018d11b  mov     qword ptr [rsp+440h+var_3E8], r9
0x18018d120  mov     [rbp+340h+var_3B0], r8
0x18018d124  mov     [rbp+340h+var_3A8], rdx
0x18018d128  mov     r12, rcx
0x18018d12b  mov     [rbp+340h+var_380], rcx
0x18018d12f  xor     r15d, r15d
0x18018d132  mov     esi, r15d
0x18018d135  mov     [rsp+440h+var_400], r15d
0x18018d13a  mov     rcx, rdx
0x18018d13d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18018d142  mov     rbx, rax
0x18018d145  lea     rdx, aUpdate; "Update"
0x18018d14c  lea     rcx, [rbp+340h+var_350]; struct wil::details::IFailureCallback *
0x18018d150  call    ??0?$ActivityBase@VAutopilotUpdateLoggingProvider@Logging@Autopilot@Management@Windows@Microsoft@@$00$0IAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18018d155  lea     rax, ??_7Update@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@6B@; const Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Update::`vftable'
0x18018d15c  mov     [rbp+340h+var_350], rax
0x18018d160  mov     rdx, rbx; unsigned __int16 *
0x18018d163  lea     rcx, [rbp+340h+var_350]; this
0x18018d167  call    ?StartActivity@Update@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@QEAAXPEBG@Z; Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Update::StartActivity(ushort const *)
0x18018d16c  nop
0x18018d16d  xorps   xmm1, xmm1
0x18018d170  movdqu  xmmword ptr [rsp+440h+TokenHandle], xmm1
0x18018d176  xor     edx, edx
0x18018d178  lea     rcx, [rsp+440h+TokenHandle]
0x18018d17d  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::reset(void *)
0x18018d182  lea     ebx, [r15+18h]
0x18018d186  lea     r13d, [r15+1]
0x18018d18a  cmp     [rsp+440h+TokenHandle], r15
0x18018d18f  jnz     short loc_18018D1ED
0x18018d191  mov     ecx, ebx; Size
0x18018d193  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18018d198  mov     rcx, rax
0x18018d19b  mov     [rbp+340h+var_3B8], rax
0x18018d19f  xorps   xmm0, xmm0
0x18018d1a2  movups  xmmword ptr [rax], xmm0
0x18018d1a5  mov     [rax+8], r13d
0x18018d1a9  mov     [rax+0Ch], r13d
0x18018d1ad  lea     rax, ??_7?$_Ref_count_obj2@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@6B@; const std::_Ref_count_obj2<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::`vftable'
0x18018d1b4  mov     [rcx], rax
0x18018d1b7  lea     rax, [rcx+10h]
0x18018d1bb  mov     [rax], r15
0x18018d1be  lea     esi, [rbx-16h]
0x18018d1c1  mov     [rsp+440h+var_400], esi
0x18018d1c5  mov     [rsp+440h+var_3F8], rax
0x18018d1ca  mov     [rsp+440h+var_3F0], rcx
0x18018d1cf  lea     rdx, [rsp+440h+var_3F8]
0x18018d1d4  lea     rcx, [rsp+440h+TokenHandle]
0x18018d1d9  call    ??4?$shared_ptr@VEtwProcessingDataEntry@Diagnostics@Autopilot@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry>::operator=(std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry> &&)
0x18018d1de  mov     rcx, [rsp+440h+var_3F0]; this
0x18018d1e3  test    rcx, rcx
0x18018d1e6  jz      short loc_18018D1ED
0x18018d1e8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18018d1ed  call    cs:__imp_GetCurrentProcess
0x18018d1f4  nop     dword ptr [rax+rax+00h]
0x18018d1f9  mov     r8, [rsp+440h+TokenHandle]; TokenHandle
0x18018d1fe  mov     edx, 0Eh; DesiredAccess
0x18018d203  mov     rcx, rax; ProcessHandle
0x18018d206  call    cs:__imp_OpenProcessToken
0x18018d20d  nop     dword ptr [rax+rax+00h]
0x18018d212  mov     rcx, [rbp+348h]; this
0x18018d219  test    eax, eax
0x18018d21b  jz      loc_18018D5ED
0x18018d221  mov     rcx, rbx; Size
0x18018d224  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18018d229  mov     rdi, rax
0x18018d22c  mov     [rbp+340h+var_3B8], rax
0x18018d230  xorps   xmm0, xmm0
0x18018d233  movups  xmmword ptr [rax], xmm0
0x18018d236  mov     [rax+8], r13d
0x18018d23a  mov     [rax+0Ch], r13d
0x18018d23e  lea     rax, ??_7?$_Ref_count_obj2@VAutopilotUpdateCtacRegistryKeyManager@Autopilot@Windows@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Windows::Autopilot::AutopilotUpdateCtacRegistryKeyManager>::`vftable'
0x18018d245  mov     [rdi], rax
0x18018d248  lea     rbx, [rdi+10h]
0x18018d24c  mov     rcx, rbx; this
0x18018d24f  call    ??0AutopilotUpdateCtacRegistryKeyManager@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::AutopilotUpdateCtacRegistryKeyManager::AutopilotUpdateCtacRegistryKeyManager(void)
0x18018d254  or      esi, 4
0x18018d257  mov     [rsp+440h+var_400], esi
0x18018d25b  mov     [rbp+340h+var_3A0], rbx
0x18018d25f  mov     [rbp+340h+var_398], rdi
0x18018d263  lea     rdx, aManagementoobe; "ManagementOOBE"
0x18018d26a  lea     rcx, [rbp+340h+var_3C0]
0x18018d26e  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18018d273  nop
0x18018d274  mov     rcx, [r14]
0x18018d277  mov     rax, [rcx]
0x18018d27a  mov     rdx, [rbp+340h+var_3C0]
0x18018d27e  mov     rax, [rax+40h]
0x18018d282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018d287  mov     rcx, [rbp+348h]; this
0x18018d28e  lea     rdx, aFailedToPutCli; "Failed to put_ClientApplicationID"
0x18018d295  mov     qword ptr [rsp+440h+var_420], rdx; int
0x18018d29a  mov     r9d, eax; char *
0x18018d29d  lea     r14, aOnecoreuapAdmi_110; "onecoreuap\\admin\\moderndeployment\\au"...
0x18018d2a4  mov     r8, r14; unsigned int
0x18018d2a7  mov     edx, 311h; void *
0x18018d2ac  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18018d2b1  mov     [rsp+440h+var_3E0], r15
0x18018d2b6  mov     [rbp+340h+var_360], r15
0x18018d2ba  mov     r9d, 39h ; '9'; unsigned int
0x18018d2c0  lea     r8d, [r9+1]; unsigned int
0x18018d2c4  lea     rdx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsManager@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x18018d2cb  lea     rcx, [rbp+340h+hstringHeader]; hstringHeader
0x18018d2cf  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18018d2d4  nop
0x18018d2d5  mov     rbx, [rbp+340h+var_360]
0x18018d2d9  lea     rcx, [rsp+440h+var_3E0]
0x18018d2de  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018d2e3  lea     r8, [rsp+440h+var_3E0]
0x18018d2e8  lea     rdx, _GUID_6ebfc469_e65b_45eb_9863_b3f57e2a5017
0x18018d2ef  mov     rcx, rbx
0x18018d2f2  call    cs:__imp_RoGetActivationFactory
0x18018d2f9  nop     dword ptr [rax+rax+00h]
0x18018d2fe  mov     rcx, [rbp+348h]; this
0x18018d305  test    eax, eax
0x18018d307  js      loc_18018D5DC
0x18018d30d  mov     [rsp+440h+var_3D8], r15
0x18018d312  mov     rdi, [rsp+440h+var_3E0]
0x18018d317  mov     rax, [rdi]
0x18018d31a  mov     rbx, [rax+38h]
0x18018d31e  lea     rcx, [rsp+440h+var_3D8]
0x18018d323  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018d328  mov     [rbp+340h+var_360], r15
0x18018d32c  mov     r9d, 4; unsigned int
0x18018d332  lea     r8d, [r9+1]; unsigned int
0x18018d336  lea     rdx, aCtac; "CTAC"
0x18018d33d  lea     rcx, [rbp+340h+hstringHeader]; hstringHeader
0x18018d341  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18018d346  nop
0x18018d347  lea     r9, [rsp+440h+var_3D8]
0x18018d34c  xor     r8d, r8d
0x18018d34f  mov     rdx, [rbp+340h+var_360]
0x18018d353  mov     rcx, rdi
0x18018d356  mov     rax, rbx
0x18018d359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018d35e  mov     rcx, [rbp+348h]; this
0x18018d365  test    eax, eax
0x18018d367  jns     short loc_18018D37A
0x18018d369  mov     r9d, eax; char *
0x18018d36c  mov     r8, r14; unsigned int
0x18018d36f  mov     edx, 319h; void *
0x18018d374  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18018d379  nop
0x18018d37a  mov     [r12], r15
0x18018d37e  or      esi, r13d
0x18018d381  mov     [rsp+440h+var_400], esi
0x18018d385  mov     ecx, 0A8h; Size
0x18018d38a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18018d38f  mov     rdi, rax
0x18018d392  mov     [rsp+440h+var_3F8], rax
0x18018d397  xorps   xmm0, xmm0
0x18018d39a  movups  xmmword ptr [rax], xmm0
0x18018d39d  mov     [rax+8], r13d
0x18018d3a1  mov     [rax+0Ch], r13d
0x18018d3a5  lea     rax, ??_7?$_Ref_count_obj2@VAutopilotUpdateOperationContext@Autopilot@Windows@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Windows::Autopilot::AutopilotUpdateOperationContext>::`vftable'
0x18018d3ac  mov     [rdi], rax
0x18018d3af  lea     rbx, [rdi+10h]
0x18018d3b3  lea     rcx, [rbx+0Ah]; void *
0x18018d3b7  xor     edx, edx; Val
0x18018d3b9  mov     r8d, 8Eh; Size
0x18018d3bf  call    memset_0
0x18018d3c4  lea     rax, ??_7AutopilotUpdateOperationContext@Autopilot@Windows@Microsoft@@6B@; const Microsoft::Windows::Autopilot::AutopilotUpdateOperationContext::`vftable'
0x18018d3cb  mov     [rbx], rax
0x18018d3ce  mov     [rbx+8], r15w
0x18018d3d3  lea     rcx, [rbx+10h]; lpCriticalSection
0x18018d3d7  xor     r8d, r8d; Flags
0x18018d3da  xor     edx, edx; dwSpinCount
0x18018d3dc  call    cs:__imp_InitializeCriticalSectionEx
0x18018d3e3  nop     dword ptr [rax+rax+00h]
0x18018d3e8  mov     [rbx+38h], r15
0x18018d3ec  mov     [rbx+40h], r15
0x18018d3f0  mov     [rbx+48h], r15
0x18018d3f4  mov     [rbx+50h], r15
0x18018d3f8  mov     [rbx+90h], r15
0x18018d3ff  or      esi, 8
0x18018d402  mov     [rsp+440h+var_400], esi
0x18018d406  mov     [rbp+340h+var_390], rbx
0x18018d40a  mov     [rbp+340h+var_388], rdi
0x18018d40e  mov     ecx, 30h ; '0'; Size
0x18018d413  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18018d418  mov     r15, rax
0x18018d41b  mov     [rsp+440h+var_3F8], rax
0x18018d420  xorps   xmm0, xmm0
0x18018d423  movups  xmmword ptr [rax], xmm0
0x18018d426  mov     [rax+8], r13d
0x18018d42a  mov     [rax+0Ch], r13d
0x18018d42e  lea     rax, ??_7?$_Ref_count_obj2@VAutopilotUpdateSearcher@Autopilot@Windows@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Windows::Autopilot::AutopilotUpdateSearcher>::`vftable'
0x18018d435  mov     [r15], rax
0x18018d438  lea     r13, [r15+10h]
0x18018d43c  lock inc dword ptr [rdi+8]
0x18018d440  mov     [rsp+440h+var_3F8], rbx
0x18018d445  mov     [rsp+440h+var_3F0], rdi
0x18018d44a  lea     rax, ??_7AutopilotUpdateSearcher@Autopilot@Windows@Microsoft@@6B@; const Microsoft::Windows::Autopilot::AutopilotUpdateSearcher::`vftable'
0x18018d451  mov     [r13+0], rax
0x18018d455  mov     rcx, qword ptr [rsp+440h+var_3E8]
0x18018d45a  mov     rcx, [rcx]
0x18018d45d  mov     [r13+8], rcx
0x18018d461  test    rcx, rcx
0x18018d464  jz      short loc_18018D473
0x18018d466  mov     rax, [rcx]
0x18018d469  mov     rax, [rax+8]
0x18018d46d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018d472  nop
0x18018d473  lea     rcx, [r13+10h]
0x18018d477  lea     rdx, [rsp+440h+var_3F8]
0x18018d47c  call    ??0?$shared_ptr@VAutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager> const &)
0x18018d481  mov     rcx, rdi; this
0x18018d484  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18018d489  or      esi, 10h
0x18018d48c  mov     [rsp+440h+var_400], esi
0x18018d490  mov     qword ptr [rbp+340h+hstringHeader.Reserved], r13
0x18018d494  mov     qword ptr [rbp+340h+hstringHeader.Reserved+8], r15
0x18018d498  mov     rax, [rbp+340h+var_3B0]
0x18018d49c  mov     rax, [rax]
0x18018d49f  mov     qword ptr [rsp+440h+var_3E8], rax
0x18018d4a4  lea     rcx, [rsp+440h+var_3E8]
0x18018d4a9  call    ?InternalAddRef@?$ComPtr@U?$IAsyncOperationCompletedHandler@PEAUIDiscoveryUrlRequestInfo@Core@Autopilot@ModernDeployment@@@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<ModernDeployment::Autopilot::Core::IDiscoveryUrlRequestInfo *>>::InternalAddRef(void)
0x18018d4ae  nop
0x18018d4af  lea     rax, [rsp+440h+TokenHandle]
0x18018d4b4  mov     [rsp+440h+var_408], rax
0x18018d4b9  lea     rax, [rbp+340h+var_3A0]
0x18018d4bd  mov     [rsp+440h+var_410], rax
0x18018d4c2  lea     rax, [rsp+440h+var_3E8]
0x18018d4c7  mov     [rsp+440h+var_418], rax; char *
0x18018d4cc  mov     rax, [rbp+340h+var_3A8]
0x18018d4d0  mov     qword ptr [rsp+440h+var_420], rax
0x18018d4d5  lea     r9, [rbp+340h+var_350]
0x18018d4d9  lea     r8, [rbp+340h+var_390]
0x18018d4dd  lea     rdx, [rbp+340h+hstringHeader]
0x18018d4e1  lea     rcx, [rbp+340h+var_200]
0x18018d4e8  call    _lambda_a19a8da35514efa0f6ca678ab46fa2c8____lambda_a19a8da35514efa0f6ca678ab46fa2c8__0
0x18018d4ed  mov     rbx, rax
0x18018d4f0  mov     rcx, r12
0x18018d4f3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018d4f8  mov     [rsp+440h+var_3F8], 4
0x18018d501  mov     dword ptr [rsp+440h+var_3F0], 0
0x18018d509  mov     rcx, rbx
0x18018d50c  call    Windows__Internal__MakeOpLambda_1_Windows__Internal__ProgressResult_Windows__Internal__CBasicResult_enum_EnterpriseDeviceManagement__Service__AutoPilot__AutopilotUpdateStatus_1__EnterpriseDeviceManagement__Service__AutoPilot__AutopilotUpdateProgress___lambda_a19a8da35514efa0f6ca678ab46fa2c8___
0x18018d511  mov     r9, rax
0x18018d514  mov     rdx, r12
0x18018d517  lea     rcx, [rsp+440h+var_3F8]
0x18018d51c  call    ??$MakeAsyncOperationWithProgressHelper@V?$ProgressResult@V?$CBasicResult@W4AutopilotUpdateStatus@AutoPilot@Service@EnterpriseDeviceManagement@@$00@Internal@Windows@@UAutopilotUpdateProgress@AutoPilot@Service@EnterpriseDeviceManagement@@@Internal@Windows@@W4AutopilotUpdateStatus@AutoPilot@Service@EnterpriseDeviceManagement@@UAutopilotUpdateProgress@567@VComTaskPoolHandler@23@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperationWithProgress@W4AutopilotUpdateStatus@AutoPilot@Service@EnterpriseDeviceManagement@@UAutopilotUpdateProgress@234@@Foundation@1@W4TrustLevel@@PEAV?$AsyncCallbackBase@V?$ProgressResult@V?$CBasicResult@W4AutopilotUpdateStatus@AutoPilot@Service@EnterpriseDeviceManagement@@$00@Internal@Windows@@UAutopilotUpdateProgress@AutoPilot@Service@EnterpriseDeviceManagement@@@Internal@Windows@@@01@@Z; Windows::Internal::MakeAsyncOperationWithProgressHelper<Windows::Internal::ProgressResult<Windows::Internal::CBasicResult<EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUpdateStatus,1>,EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUpdateProgress>,EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUpdateStatus,EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUpdateProgress,Windows::Internal::ComTaskPoolHandler>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperationWithProgress<EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUpdateStatus,EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUpdateProgress> * *,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::ProgressResult<Windows::Internal::CBasicResult<EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUpdateStatus,1>,EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUpdateProgress>> *)
0x18018d521  mov     ebx, eax
0x18018d523  lea     rcx, [rbp+340h+var_200]
0x18018d52a  call    _lambda_a19a8da35514efa0f6ca678ab46fa2c8_____lambda_a19a8da35514efa0f6ca678ab46fa2c8_
0x18018d52f  mov     rcx, [rbp+348h]; this
0x18018d536  lea     rax, aFailedToMakeAu; "Failed to make Autopilot update operati"...
0x18018d53d  mov     qword ptr [rsp+440h+var_420], rax; int
0x18018d542  mov     r9d, ebx; char *
0x18018d545  mov     r8, r14; unsigned int
0x18018d548  mov     edx, 3A4h; void *
0x18018d54d  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18018d552  nop
0x18018d553  lea     rcx, [rsp+440h+var_3E8]
0x18018d558  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018d55d  nop
0x18018d55e  mov     rcx, r15; this
0x18018d561  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18018d566  nop
0x18018d567  mov     rcx, rdi; this
0x18018d56a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18018d56f  nop
0x18018d570  lea     rcx, [rsp+440h+var_3D8]
0x18018d575  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018d57a  nop
0x18018d57b  lea     rcx, [rsp+440h+var_3E0]
0x18018d580  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018d585  nop
0x18018d586  lea     rcx, [rbp+340h+var_3C0]
0x18018d58a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18018d58f  nop
0x18018d590  mov     rcx, [rbp+340h+var_3B8]; this
0x18018d594  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18018d599  nop
0x18018d59a  lea     rcx, [rsp+440h+TokenHandle]
0x18018d59f  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x18018d5a4  nop
0x18018d5a5  lea     rcx, [rbp+340h+var_350]; this
0x18018d5a9  call    ??1Update@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Update::~Update(void)
0x18018d5ae  mov     rax, r12
0x18018d5b1  mov     rcx, [rbp+340h+var_40]
0x18018d5b8  xor     rcx, rsp; StackCookie
0x18018d5bb  call    __security_check_cookie
0x18018d5c0  mov     rbx, [rsp+440h+arg_10]
0x18018d5c8  add     rsp, 410h
0x18018d5cf  pop     r15
0x18018d5d1  pop     r14
  ... truncated ...
```
