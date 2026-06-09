# Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::Initialize(void)

- ea: `0x18000bb6c`
- end: `0x18000be16`
- name: `?Initialize@?$ServiceHostService@VDeServiceHost@ServiceHost@DisplayEnhancement@Windows@Microsoft@@$00@Foundation@Bluetooth@Microsoft@@AEAAXXZ`
- size: `682`
- prototype: `__int64 __fastcall(LPVOID lpContext)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000df70`

## callees

- `0x180005860`
- `0x1800058bc`
- `0x180007c2c`
- `0x180008c50`
- `0x180009094`
- `0x180009928`
- `0x1800099d4`
- `0x180009a84`
- `0x180009f68`
- `0x18000bb6c`
- `0x18000be1c`
- `0x18000bec8`
- `0x18000bff4`
- `0x18000e5dc`
- `0x18000eca0`
- `0x18000f778`
- `0x18000f7b0`
- `0x18000f9f0`
- `0x18000fa0c`
- `0x18000fa68`
- `0x18000fa98`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000bc59`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000bc59`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bbf7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bbf7`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18000bd5a`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18000bd5a`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000bc12`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000bc12`

## string_xrefs

- `0x18000bbc8`: `DisplayEnhancementService`
- `0x18000bc0b`: `DisplayEnhancementService`
- `0x18000bdc0`: `onecore\private\drivers\inc\bluetooth\foundation\ServiceHost.h`
- `0x18000bdf2`: `onecore\private\drivers\inc\bluetooth\foundation\ServiceHost.h`
- `0x18000be04`: `onecore\private\drivers\inc\bluetooth\foundation\ServiceHost.h`
- `0x18000bdaa`: `Failed to submit OnStart threadpool callback.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
bool __fastcall Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::Initialize(
        char *lpContext)
{
  __int64 (__fastcall *v2)(std::_Ref_count_base **, const WCHAR *, _QWORD, __int64 (__fastcall *)()); // r10
  unsigned int v3; // eax
  const char *v4; // r9
  __int64 *v5; // rax
  __int64 *v6; // rax
  Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator **v7; // rbx
  Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator *v8; // rsi
  __int64 *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  void *v12; // rbx
  char v13; // bl
  unsigned int v15; // [rsp+20h] [rbp-79h]
  const char *v16; // [rsp+30h] [rbp-69h]
  __int128 v17; // [rsp+40h] [rbp-59h] BYREF
  std::_Ref_count_base *v18[2]; // [rsp+50h] [rbp-49h] BYREF
  char *v19; // [rsp+60h] [rbp-39h] BYREF
  std::_Ref_count_base *v20; // [rsp+68h] [rbp-31h] BYREF
  char v21; // [rsp+70h] [rbp-29h]
  _QWORD v22[8]; // [rsp+80h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v2 = *(__int64 (__fastcall **)(std::_Ref_count_base **, const WCHAR *, _QWORD, __int64 (__fastcall *)()))(Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::s_globalData + 192);
  v19 = lpContext + 56;
  v20 = 0;
  v21 = 1;
  v15 = (unsigned int)lpContext;
  v3 = v2(
         &v20,
         L"DisplayEnhancementService",
         *((_QWORD *)lpContext + 6),
         Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::Cleanup);
  if ( v3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x73,
      (unsigned int)"onecore\\private\\drivers\\inc\\bluetooth\\foundation\\ServiceHost.h",
      (const char *)v3,
      v15);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int UnregisterWait(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int UnregisterWait(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v19);
  AcquireSRWLockExclusive((PSRWLOCK)lpContext + 8);
  *(_QWORD *)&v17 = lpContext + 64;
  *((_QWORD *)lpContext + 9) = RegisterServiceCtrlHandlerExW(
                                 L"DisplayEnhancementService",
                                 _lambda_6986e48f90b04fc393362309f28d1c09_::_lambda_invoker_cdecl_,
                                 lpContext);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v17);
  if ( !*((_QWORD *)lpContext + 9) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x85,
      (unsigned int)"onecore\\private\\drivers\\inc\\bluetooth\\foundation\\ServiceHost.h",
      v4);
  *((_DWORD *)lpContext + 20) = 32;
  *(_QWORD *)(lpContext + 84) = 1;
  *(_QWORD *)(lpContext + 92) = 0;
  *((_DWORD *)lpContext + 25) = 0;
  *((_DWORD *)lpContext + 26) = 10000;
  if ( IsDebuggerPresent() )
    *((_DWORD *)lpContext + 26) = 3600000;
  Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::SetStatus(
    lpContext,
    2);
  v5 = (__int64 *)Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::AsyncObjectRegistrar,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::AsyncObjectRegistrar>>::Instance(v18);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    (_QWORD *)lpContext + 2,
    v5);
  if ( v18[1] )
    std::_Ref_count_base::_Decref(v18[1]);
  v6 = (__int64 *)Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::Instance(v18);
  v7 = (Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator **)(lpContext + 32);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    (_QWORD *)lpContext + 4,
    v6);
  if ( v18[1] )
    std::_Ref_count_base::_Decref(v18[1]);
  Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator::InitializeForService(*v7);
  v8 = *v7;
  *(_OWORD *)v18 = 0;
  if ( !std::_Ptr_base<Microsoft::Bluetooth::Foundation::TokenWithStatusServer<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::ModifierChanged>>::_Construct_from_weak<Microsoft::Bluetooth::Foundation::TokenWithStatusServer<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::ModifierChanged>>(
          (__int64)v18,
          (__int64)lpContext) )
    std::_Throw_bad_weak_ptr();
  v9 = (__int64 *)std::weak_ptr<Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::DeManagerNotificationManagerImpl>::weak_ptr<Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::DeManagerNotificationManagerImpl>(
                    &v19,
                    v18);
  v10 = *v9;
  v11 = v9[1];
  *v9 = 0;
  v9[1] = 0;
  v22[0] = &std::_Func_impl_no_alloc<_lambda_2c75e64ac2bbd7aff421cf5c86ce3a5d_,void,>::`vftable';
  v22[1] = v10;
  v22[2] = v11;
  v17 = 0;
  v22[7] = v22;
  v12 = operator new(0x40u);
  *(_QWORD *)&v17 = v12;
  std::function<void (void)>::function<void (void)>(v12, v22);
  *(_QWORD *)&v17 = v12;
  if ( TrySubmitThreadpoolCallback(
         _lambda_ee30e70c11de689a6e32301a2b79ebe4_::_lambda_invoker_cdecl_,
         v12,
         *((PTP_CALLBACK_ENVIRON *)v8 + 1)) )
  {
    v13 = 1;
    *(_QWORD *)&v17 = 0;
  }
  else
  {
    v13 = 0;
  }
  __1__unique_ptr_UContext__1__TrySubmitCallback_ThreadpoolCoordinator_Foundation_Bluetooth_Microsoft__QEAA_N__QEAV__function___A6AXXZ_std___Z_U__default_delete_UContext__1__TrySubmitCallback_ThreadpoolCoordinator_Foundation_Bluetooth_Microsoft__QEAA_N__QEAV__function___A6AXXZ_std___Z__8__std__QEAA_XZ(&v17);
  std::function<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementULongSettingType (void)>::~function<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementULongSettingType (void)>(v22);
  if ( v20 )
    std::_Ref_count_base::_Decwref(v20);
  if ( v18[1] )
    std::_Ref_count_base::_Decref(v18[1]);
  return wil::details::in1diag3::Throw_HrIfMsg(
           retaddr,
           (void *)0xBB,
           (unsigned int)"onecore\\private\\drivers\\inc\\bluetooth\\foundation\\ServiceHost.h",
           (const char *)0x80004005LL,
           v13 ^ 1,
           (bool)"Failed to submit OnStart threadpool callback.",
           v16);
}

```

## disassembly

```asm
0x18000bb6c  push    rbp
0x18000bb6e  push    rbx
0x18000bb6f  push    rsi
0x18000bb70  push    rdi
0x18000bb71  lea     rbp, [rsp-3Fh]
0x18000bb76  sub     rsp, 0D8h
0x18000bb7d  mov     rax, cs:__security_cookie
0x18000bb84  xor     rax, rsp
0x18000bb87  mov     [rbp+57h+var_30], rax
0x18000bb8b  mov     rdi, rcx
0x18000bb8e  mov     rax, cs:?s_globalData@?$ServiceHostService@VDeServiceHost@ServiceHost@DisplayEnhancement@Windows@Microsoft@@$00@Foundation@Bluetooth@Microsoft@@0PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::s_globalData
0x18000bb95  mov     r10, [rax+0C0h]
0x18000bb9c  lea     rax, [rcx+38h]
0x18000bba0  mov     [rbp+57h+var_90], rax
0x18000bba4  mov     [rbp+57h+var_88], 0
0x18000bbac  mov     [rbp+57h+var_80], 1
0x18000bbb0  mov     dword ptr [rsp+0F0h+var_C8], 8
0x18000bbb8  mov     qword ptr [rsp+0F0h+var_D0], rcx; unsigned int
0x18000bbbd  lea     r9, ?Cleanup@?$ServiceHostService@VDeServiceHost@ServiceHost@DisplayEnhancement@Windows@Microsoft@@$00@Foundation@Bluetooth@Microsoft@@CAXPEAXE@Z; Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::Cleanup(void *,uchar)
0x18000bbc4  mov     r8, [rcx+30h]
0x18000bbc8  lea     rdx, SourceString; "DisplayEnhancementService"
0x18000bbcf  lea     rcx, [rbp+57h+var_88]
0x18000bbd3  mov     rax, r10
0x18000bbd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbdb  mov     rcx, [rbp+5Fh]; this
0x18000bbdf  test    eax, eax
0x18000bbe1  jnz     loc_18000BDEF
0x18000bbe7  lea     rcx, [rbp+57h+var_90]
0x18000bbeb  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?UnregisterWait@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&UnregisterWait(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&UnregisterWait(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x18000bbf0  lea     rbx, [rdi+40h]
0x18000bbf4  mov     rcx, rbx; SRWLock
0x18000bbf7  call    cs:__imp_AcquireSRWLockExclusive
0x18000bbfd  mov     qword ptr [rbp+57h+var_B0], rbx
0x18000bc01  mov     r8, rdi; lpContext
0x18000bc04  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_6986e48f90b04fc393362309f28d1c09_@@CA@KKPEAX0@Z; lpHandlerProc
0x18000bc0b  lea     rcx, SourceString; "DisplayEnhancementService"
0x18000bc12  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000bc18  mov     [rdi+48h], rax
0x18000bc1c  lea     rcx, [rbp+57h+var_B0]
0x18000bc20  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000bc25  mov     rcx, [rbp+5Fh]; this
0x18000bc29  cmp     qword ptr [rdi+48h], 0
0x18000bc2e  jz      loc_18000BE04
0x18000bc34  mov     dword ptr [rdi+50h], 20h ; ' '
0x18000bc3b  mov     qword ptr [rdi+54h], 1
0x18000bc43  mov     qword ptr [rdi+5Ch], 0
0x18000bc4b  mov     dword ptr [rdi+64h], 0
0x18000bc52  mov     dword ptr [rdi+68h], 2710h
0x18000bc59  call    cs:__imp_IsDebuggerPresent
0x18000bc5f  test    eax, eax
0x18000bc61  jz      short loc_18000BC6A
0x18000bc63  mov     dword ptr [rdi+68h], 36EE80h
0x18000bc6a  mov     edx, 2
0x18000bc6f  mov     rcx, rdi
0x18000bc72  call    ?SetStatus@?$ServiceHostService@VDeServiceHost@ServiceHost@DisplayEnhancement@Windows@Microsoft@@$00@Foundation@Bluetooth@Microsoft@@AEAAXK@Z; Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::SetStatus(ulong)
0x18000bc77  lea     rcx, [rbp+57h+var_A0]
0x18000bc7b  call    ?Instance@?$SingletonWithFactory@VAsyncObjectRegistrar@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VAsyncObjectRegistrar@Foundation@Bluetooth@Microsoft@@@234@@Foundation@Bluetooth@Microsoft@@SA?AV?$shared_ptr@VAsyncObjectRegistrar@Foundation@Bluetooth@Microsoft@@@std@@XZ; Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::AsyncObjectRegistrar,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::AsyncObjectRegistrar>>::Instance(void)
0x18000bc80  lea     rcx, [rdi+10h]
0x18000bc84  mov     rdx, rax
0x18000bc87  call    ??$?4V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@$0A@@?$shared_ptr@V?$OEMSetting@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV?$shared_ptr@V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@1@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>> &&)
0x18000bc8c  mov     rcx, [rbp+57h+var_A0+8]; this
0x18000bc90  test    rcx, rcx
0x18000bc93  jz      short loc_18000BC9A
0x18000bc95  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000bc9a  lea     rcx, [rbp+57h+var_A0]
0x18000bc9e  call    ?Instance@?$SingletonWithFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@234@@Foundation@Bluetooth@Microsoft@@SA?AV?$shared_ptr@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@std@@XZ; Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::Instance(void)
0x18000bca3  lea     rbx, [rdi+20h]
0x18000bca7  mov     rdx, rax
0x18000bcaa  mov     rcx, rbx
0x18000bcad  call    ??$?4V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@$0A@@?$shared_ptr@V?$OEMSetting@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV?$shared_ptr@V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@1@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>> &&)
0x18000bcb2  mov     rcx, [rbp+57h+var_A0+8]; this
0x18000bcb6  test    rcx, rcx
0x18000bcb9  jz      short loc_18000BCC0
0x18000bcbb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000bcc0  mov     rcx, [rbx]; this
0x18000bcc3  call    ?InitializeForService@ThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@QEAAXXZ; Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator::InitializeForService(void)
0x18000bcc8  mov     rsi, [rbx]
0x18000bccb  xorps   xmm0, xmm0
0x18000bcce  movdqu  xmmword ptr [rbp+57h+var_A0], xmm0
0x18000bcd3  mov     rdx, rdi
0x18000bcd6  lea     rcx, [rbp+57h+var_A0]
0x18000bcda  call    ??$_Construct_from_weak@V?$TokenWithStatusServer@UModifierChanged@AutobrightnessConfiguration@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@@Foundation@Bluetooth@Microsoft@@@?$_Ptr_base@V?$TokenWithStatusServer@UModifierChanged@AutobrightnessConfiguration@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@@Foundation@Bluetooth@Microsoft@@@std@@IEAA_NAEBV?$weak_ptr@V?$TokenWithStatusServer@UModifierChanged@AutobrightnessConfiguration@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@@Foundation@Bluetooth@Microsoft@@@1@@Z; std::_Ptr_base<Microsoft::Bluetooth::Foundation::TokenWithStatusServer<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::ModifierChanged>>::_Construct_from_weak<Microsoft::Bluetooth::Foundation::TokenWithStatusServer<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::ModifierChanged>>(std::weak_ptr<Microsoft::Bluetooth::Foundation::TokenWithStatusServer<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::AutobrightnessConfiguration::ModifierChanged>> const &)
0x18000bcdf  test    al, al
0x18000bce1  jz      loc_18000BDE9
0x18000bce7  lea     rdx, [rbp+57h+var_A0]
0x18000bceb  lea     rcx, [rbp+57h+var_90]
0x18000bcef  call    ??0?$weak_ptr@VDeManagerNotificationManagerImpl@DisplayEnhancementManager@DisplayEnhancement@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::weak_ptr<Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::DeManagerNotificationManagerImpl>::weak_ptr<Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::DeManagerNotificationManagerImpl>(std::weak_ptr<Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::DeManagerNotificationManagerImpl> const &)
0x18000bcf4  nop
0x18000bcf5  mov     rdx, [rax]
0x18000bcf8  mov     rcx, [rax+8]
0x18000bcfc  mov     qword ptr [rax], 0
0x18000bd03  mov     qword ptr [rax+8], 0
0x18000bd0b  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_2c75e64ac2bbd7aff421cf5c86ce3a5d_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_2c75e64ac2bbd7aff421cf5c86ce3a5d_,void,>::`vftable'
0x18000bd12  mov     [rbp+57h+var_70], rax
0x18000bd16  mov     [rbp+57h+var_68], rdx
0x18000bd1a  mov     [rbp+57h+var_60], rcx
0x18000bd1e  movdqu  [rbp+57h+var_B0], xmm0
0x18000bd23  lea     rax, [rbp+57h+var_70]
0x18000bd27  mov     [rbp+57h+var_38], rax
0x18000bd2b  mov     ecx, 40h ; '@'; Size
0x18000bd30  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bd35  mov     rbx, rax
0x18000bd38  mov     qword ptr [rbp+57h+var_B0], rax
0x18000bd3c  lea     rdx, [rbp+57h+var_70]
0x18000bd40  mov     rcx, rax
0x18000bd43  call    ??0?$function@$$A6AXXZ@std@@QEAA@$$QEAV01@@Z; std::function<void (void)>::function<void (void)>(std::function<void (void)> &&)
0x18000bd48  mov     qword ptr [rbp+57h+var_B0], rbx
0x18000bd4c  mov     r8, [rsi+8]; pcbe
0x18000bd50  mov     rdx, rbx; pv
0x18000bd53  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_ee30e70c11de689a6e32301a2b79ebe4_@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18000bd5a  call    cs:__imp_TrySubmitThreadpoolCallback
0x18000bd60  test    eax, eax
0x18000bd62  jz      short loc_18000BD70
0x18000bd64  mov     bl, 1
0x18000bd66  mov     qword ptr [rbp+57h+var_B0], 0
0x18000bd6e  jmp     short loc_18000BD72
0x18000bd70  xor     bl, bl
0x18000bd72  lea     rcx, [rbp+57h+var_B0]
0x18000bd76  call    ??1?$unique_ptr@UContext@?1??TrySubmitCallback@ThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@QEAA_N$$QEAV?$function@$$A6AXXZ@std@@@Z@U?$default_delete@UContext@?1??TrySubmitCallback@ThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@QEAA_N$$QEAV?$function@$$A6AXXZ@std@@@Z@@8@@std@@QEAA@XZ; std::unique_ptr<`Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator::TrySubmitCallback(std::function<void (void)> &&)'::`2'::Context,std::default_delete<`Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator::TrySubmitCallback(std::function<void (void)> &&)'::`2'::Context>>::~unique_ptr<`Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator::TrySubmitCallback(std::function<void (void)> &&)'::`2'::Context,std::default_delete<`Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator::TrySubmitCallback(std::function<void (void)> &&)'::`2'::Context>>(void)
0x18000bd7b  nop
0x18000bd7c  lea     rcx, [rbp+57h+var_70]
0x18000bd80  call    ??1?$function@$$A6A?AVDeManagementULongSettingType@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@XZ@std@@QEAA@XZ; std::function<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementULongSettingType (void)>::~function<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementULongSettingType (void)>(void)
0x18000bd85  nop
0x18000bd86  mov     rcx, [rbp+57h+var_88]; this
0x18000bd8a  test    rcx, rcx
0x18000bd8d  jz      short loc_18000BD95
0x18000bd8f  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18000bd94  nop
0x18000bd95  mov     rcx, [rbp+57h+var_A0+8]; this
0x18000bd99  test    rcx, rcx
0x18000bd9c  jz      short loc_18000BDA3
0x18000bd9e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000bda3  xor     bl, 1
0x18000bda6  mov     rcx, [rbp+5Fh]; this
0x18000bdaa  lea     rax, aFailedToSubmit; "Failed to submit OnStart threadpool cal"...
0x18000bdb1  mov     qword ptr [rsp+0F0h+var_C8], rax; bool
0x18000bdb6  mov     [rsp+0F0h+var_D0], bl; char
0x18000bdba  mov     r9d, 80004005h; char *
0x18000bdc0  lea     r8, aOnecorePrivate_3; "onecore\\private\\drivers\\inc\\bluetoo"...
0x18000bdc7  mov     edx, 0BBh; void *
0x18000bdcc  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18000bdd1  mov     rcx, [rbp+57h+var_30]
0x18000bdd5  xor     rcx, rsp; StackCookie
0x18000bdd8  call    __security_check_cookie
0x18000bddd  add     rsp, 0D8h
0x18000bde4  pop     rdi
0x18000bde5  pop     rsi
0x18000bde6  pop     rbx
0x18000bde7  pop     rbp
0x18000bde8  retn
0x18000bde9  call    ?_Throw_bad_weak_ptr@std@@YAXXZ; std::_Throw_bad_weak_ptr(void)
0x18000bdef  mov     r9d, eax; char *
0x18000bdf2  lea     r8, aOnecorePrivate_3; "onecore\\private\\drivers\\inc\\bluetoo"...
0x18000bdf9  mov     edx, 73h ; 's'; void *
0x18000bdfe  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000be04  lea     r8, aOnecorePrivate_3; "onecore\\private\\drivers\\inc\\bluetoo"...
0x18000be0b  mov     edx, 85h; void *
0x18000be10  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
