# Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost,1>::Initialize(void)

- ea: `0x18000c870`
- end: `0x18000cb73`
- name: `?Initialize@?$ServiceHostService@VAvctpServiceHost@Avctp@Protocols@Bluetooth@Microsoft@@$00@Foundation@Bluetooth@Microsoft@@AEAAXXZ`
- size: `771`
- prototype: `__int64 __fastcall(LPVOID lpContext)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000d9a0`

## callees

- `0x180001dd0`
- `0x1800021dc`
- `0x180004060`
- `0x180009920`
- `0x18000a97c`
- `0x18000ae5c`
- `0x18000b2d0`
- `0x18000b358`
- `0x18000b3d4`
- `0x18000b69c`
- `0x18000b7e4`
- `0x18000c870`
- `0x18000cb7c`
- `0x18000cd10`
- `0x18000ce3c`
- `0x18000dab0`
- `0x18000dca8`
- `0x18000dcc4`
- `0x18000de78`
- `0x18000deb0`
- `0x18000e0e0`
- `0x18000e13c`
- `0x18000e16c`
- `0x180010b28`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c8fb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c8fb`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18000cab7`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18000cab7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c95d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c95d`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000c916`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000c916`

## string_xrefs

- `0x18000cb1d`: `onecore\drivers\bluetooth\foundation\lib\ServiceHost.h`
- `0x18000cb4f`: `onecore\drivers\bluetooth\foundation\lib\ServiceHost.h`
- `0x18000cb61`: `onecore\drivers\bluetooth\foundation\lib\ServiceHost.h`
- `0x18000cb07`: `Failed to submit OnStart threadpool callback.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
bool __fastcall Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost,1>::Initialize(
        char *lpContext)
{
  __int64 (__fastcall *v2)(std::_Ref_count_base **, const WCHAR *, _QWORD, __int64 (__fastcall *)()); // r10
  unsigned int v3; // eax
  const char *v4; // r9
  __int64 v5; // rax
  __int64 v6; // rax
  Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator **v7; // rbx
  _QWORD *DefaultInstance; // rax
  __int64 v9; // rax
  __int64 v10; // rdx
  Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator *v11; // rsi
  __int64 *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  void *v15; // rbx
  char v16; // bl
  unsigned int v18; // [rsp+20h] [rbp-79h]
  const char *v19; // [rsp+30h] [rbp-69h]
  __int128 v20; // [rsp+40h] [rbp-59h] BYREF
  std::_Ref_count_base *v21[2]; // [rsp+50h] [rbp-49h] BYREF
  char *v22; // [rsp+60h] [rbp-39h] BYREF
  std::_Ref_count_base *v23; // [rsp+68h] [rbp-31h] BYREF
  char v24; // [rsp+70h] [rbp-29h]
  _QWORD v25[8]; // [rsp+80h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v2 = *(__int64 (__fastcall **)(std::_Ref_count_base **, const WCHAR *, _QWORD, __int64 (__fastcall *)()))(Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost,1>::s_globalData + 192);
  v22 = lpContext + 64;
  v23 = 0;
  v24 = 1;
  v18 = (unsigned int)lpContext;
  v3 = v2(
         &v23,
         L"BthAVCTPSvc",
         *((_QWORD *)lpContext + 7),
         Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost,1>::Cleanup);
  if ( v3 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x73,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\ServiceHost.h",
      (const char *)v3,
      v18);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int UnregisterWait(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int UnregisterWait(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v22);
  AcquireSRWLockExclusive((PSRWLOCK)lpContext + 9);
  *(_QWORD *)&v20 = lpContext + 72;
  *((_QWORD *)lpContext + 10) = RegisterServiceCtrlHandlerExW(
                                  L"BthAVCTPSvc",
                                  _lambda_eca249686c8894c444090674405dc4d0_::_lambda_invoker_cdecl_,
                                  lpContext);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v20);
  if ( !*((_QWORD *)lpContext + 10) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x85,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\ServiceHost.h",
      v4);
  *((_DWORD *)lpContext + 22) = 32;
  *(_QWORD *)(lpContext + 92) = 1;
  *(_QWORD *)(lpContext + 100) = 0;
  *((_DWORD *)lpContext + 27) = 0;
  *((_DWORD *)lpContext + 28) = 10000;
  if ( IsDebuggerPresent() )
    *((_DWORD *)lpContext + 28) = 3600000;
  Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost,1>::SetStatus(
    lpContext,
    2);
  v5 = Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::AsyncObjectRegistrar,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::AsyncObjectRegistrar>>::Instance(v21);
  std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncDeviceInterfaceWatcher>::operator=(lpContext + 16, v5);
  if ( v21[1] )
    std::_Ref_count_base::_Decref(v21[1]);
  v6 = Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::Instance(v21);
  v7 = (Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator **)(lpContext + 32);
  std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncDeviceInterfaceWatcher>::operator=(lpContext + 32, v6);
  if ( v21[1] )
    std::_Ref_count_base::_Decref(v21[1]);
  Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator::InitializeForService(*v7);
  DefaultInstance = (_QWORD *)Microsoft::Bluetooth::Foundation::Details::ThreadProcessorProvider::GetDefaultInstance(v21);
  (*(void (__fastcall **)(_QWORD, __int128 *, __int64))(*(_QWORD *)*DefaultInstance + 8LL))(
    *DefaultInstance,
    &v20,
    1869180788);
  if ( v21[1] )
    std::_Ref_count_base::_Decref(v21[1]);
  v9 = v20;
  *(_QWORD *)&v20 = 0;
  v10 = *((_QWORD *)lpContext + 6);
  *((_QWORD *)lpContext + 6) = v9;
  if ( v10 )
    std::default_delete<Microsoft::Bluetooth::Foundation::ThreadProcessorControl>::operator()();
  std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::RequestDispatcher>::~unique_ptr<Microsoft::Bluetooth::Foundation::Details::RequestDispatcher>(&v20);
  v11 = *v7;
  *(_OWORD *)v21 = 0;
  if ( !(unsigned __int8)std::_Ptr_base<Microsoft::Bluetooth::Foundation::Details::AsyncRadioEnumeratorImpl>::_Construct_from_weak<Microsoft::Bluetooth::Foundation::Details::AsyncRadioEnumeratorImpl>(
                           v21,
                           lpContext) )
    std::_Throw_bad_weak_ptr();
  v12 = std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<unsigned char>,long>>::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<unsigned char>,long>>(
          &v22,
          v21);
  v13 = *v12;
  v14 = v12[1];
  *v12 = 0;
  v12[1] = 0;
  v25[0] = &std::_Func_impl_no_alloc<_lambda_75ca5b0294875c693bc0b8f02cdd6ad9_,void,>::`vftable';
  v25[1] = v13;
  v25[2] = v14;
  v20 = 0;
  v25[7] = v25;
  v15 = operator new(0x40u);
  *(_QWORD *)&v20 = v15;
  std::function<void (void)>::function<void (void)>(v15, v25);
  *(_QWORD *)&v20 = v15;
  if ( TrySubmitThreadpoolCallback(
         _lambda_4312f3ad3f7a3d3f8ba09c7a67669e2f_::_lambda_invoker_cdecl_,
         v15,
         *((PTP_CALLBACK_ENVIRON *)v11 + 1)) )
  {
    v16 = 1;
    *(_QWORD *)&v20 = 0;
  }
  else
  {
    v16 = 0;
  }
  __1__unique_ptr_UContext__1__TrySubmitCallback_ThreadpoolCoordinator_Foundation_Bluetooth_Microsoft__QEAA_N__QEAV__function___A6AXXZ_std___Z_U__default_delete_UContext__1__TrySubmitCallback_ThreadpoolCoordinator_Foundation_Bluetooth_Microsoft__QEAA_N__QEAV__function___A6AXXZ_std___Z__8__std__QEAA_XZ(&v20);
  std::_Func_class<void,enum Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,unsigned short const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy(v25);
  if ( v23 )
    std::_Ref_count_base::_Decwref(v23);
  if ( v21[1] )
    std::_Ref_count_base::_Decref(v21[1]);
  return wil::details::in1diag3::Throw_HrIfMsg(
           retaddr,
           (void *)0xBB,
           (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\ServiceHost.h",
           (const char *)0x80004005LL,
           v16 ^ 1,
           (bool)"Failed to submit OnStart threadpool callback.",
           v19);
}

```

## disassembly

```asm
0x18000c870  push    rbp
0x18000c872  push    rbx
0x18000c873  push    rsi
0x18000c874  push    rdi
0x18000c875  lea     rbp, [rsp-3Fh]
0x18000c87a  sub     rsp, 0D8h
0x18000c881  mov     rax, cs:__security_cookie
0x18000c888  xor     rax, rsp
0x18000c88b  mov     [rbp+57h+var_30], rax
0x18000c88f  mov     rdi, rcx
0x18000c892  mov     rax, cs:?s_globalData@?$ServiceHostService@VAvctpServiceHost@Avctp@Protocols@Bluetooth@Microsoft@@$00@Foundation@Bluetooth@Microsoft@@0PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost,1>::s_globalData
0x18000c899  mov     r10, [rax+0C0h]
0x18000c8a0  lea     rax, [rcx+40h]
0x18000c8a4  mov     [rbp+57h+var_90], rax
0x18000c8a8  mov     [rbp+57h+var_88], 0
0x18000c8b0  mov     [rbp+57h+var_80], 1
0x18000c8b4  mov     dword ptr [rsp+0F0h+var_C8], 8
0x18000c8bc  mov     qword ptr [rsp+0F0h+var_D0], rcx; unsigned int
0x18000c8c1  lea     r9, ?Cleanup@?$ServiceHostService@VAvctpServiceHost@Avctp@Protocols@Bluetooth@Microsoft@@$00@Foundation@Bluetooth@Microsoft@@CAXPEAXE@Z; Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost,1>::Cleanup(void *,uchar)
0x18000c8c8  mov     r8, [rcx+38h]
0x18000c8cc  lea     rdx, ServiceName; "BthAVCTPSvc"
0x18000c8d3  lea     rcx, [rbp+57h+var_88]
0x18000c8d7  mov     rax, r10
0x18000c8da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8df  mov     rcx, [rbp+5Fh]; this
0x18000c8e3  test    eax, eax
0x18000c8e5  jnz     loc_18000CB4C
0x18000c8eb  lea     rcx, [rbp+57h+var_90]
0x18000c8ef  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?UnregisterWait@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&UnregisterWait(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&UnregisterWait(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x18000c8f4  lea     rbx, [rdi+48h]
0x18000c8f8  mov     rcx, rbx; SRWLock
0x18000c8fb  call    cs:__imp_AcquireSRWLockExclusive
0x18000c901  mov     qword ptr [rbp+57h+var_B0], rbx
0x18000c905  mov     r8, rdi; lpContext
0x18000c908  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_eca249686c8894c444090674405dc4d0_@@CA@KKPEAX0@Z; lpHandlerProc
0x18000c90f  lea     rcx, ServiceName; "BthAVCTPSvc"
0x18000c916  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000c91c  mov     [rdi+50h], rax
0x18000c920  lea     rcx, [rbp+57h+var_B0]
0x18000c924  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000c929  mov     rcx, [rbp+5Fh]; this
0x18000c92d  cmp     qword ptr [rdi+50h], 0
0x18000c932  jz      loc_18000CB61
0x18000c938  mov     dword ptr [rdi+58h], 20h ; ' '
0x18000c93f  mov     qword ptr [rdi+5Ch], 1
0x18000c947  mov     qword ptr [rdi+64h], 0
0x18000c94f  mov     dword ptr [rdi+6Ch], 0
0x18000c956  mov     dword ptr [rdi+70h], 2710h
0x18000c95d  call    cs:__imp_IsDebuggerPresent
0x18000c963  test    eax, eax
0x18000c965  jz      short loc_18000C96E
0x18000c967  mov     dword ptr [rdi+70h], 36EE80h
0x18000c96e  mov     edx, 2
0x18000c973  mov     rcx, rdi
0x18000c976  call    ?SetStatus@?$ServiceHostService@VAvctpServiceHost@Avctp@Protocols@Bluetooth@Microsoft@@$00@Foundation@Bluetooth@Microsoft@@AEAAXK@Z; Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost,1>::SetStatus(ulong)
0x18000c97b  lea     rcx, [rbp+57h+var_A0]
0x18000c97f  call    ?Instance@?$SingletonWithFactory@VAsyncObjectRegistrar@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VAsyncObjectRegistrar@Foundation@Bluetooth@Microsoft@@@234@@Foundation@Bluetooth@Microsoft@@SA?AV?$shared_ptr@VAsyncObjectRegistrar@Foundation@Bluetooth@Microsoft@@@std@@XZ; Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::AsyncObjectRegistrar,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::AsyncObjectRegistrar>>::Instance(void)
0x18000c984  lea     rcx, [rdi+10h]
0x18000c988  mov     rdx, rax
0x18000c98b  call    ??4?$shared_ptr@VAsyncDeviceInterfaceWatcher@Foundation@Bluetooth@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncDeviceInterfaceWatcher>::operator=(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncDeviceInterfaceWatcher> &&)
0x18000c990  mov     rcx, [rbp+57h+var_A0+8]; this
0x18000c994  test    rcx, rcx
0x18000c997  jz      short loc_18000C99E
0x18000c999  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c99e  lea     rcx, [rbp+57h+var_A0]
0x18000c9a2  call    ?Instance@?$SingletonWithFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@234@@Foundation@Bluetooth@Microsoft@@SA?AV?$shared_ptr@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@std@@XZ; Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::Instance(void)
0x18000c9a7  lea     rbx, [rdi+20h]
0x18000c9ab  mov     rdx, rax
0x18000c9ae  mov     rcx, rbx
0x18000c9b1  call    ??4?$shared_ptr@VAsyncDeviceInterfaceWatcher@Foundation@Bluetooth@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncDeviceInterfaceWatcher>::operator=(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncDeviceInterfaceWatcher> &&)
0x18000c9b6  mov     rcx, [rbp+57h+var_A0+8]; this
0x18000c9ba  test    rcx, rcx
0x18000c9bd  jz      short loc_18000C9C4
0x18000c9bf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c9c4  mov     rcx, [rbx]; this
0x18000c9c7  call    ?InitializeForService@ThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@QEAAXXZ; Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator::InitializeForService(void)
0x18000c9cc  lea     rcx, [rbp+57h+var_A0]
0x18000c9d0  call    ?GetDefaultInstance@ThreadProcessorProvider@Details@Foundation@Bluetooth@Microsoft@@SA?AV?$shared_ptr@VThreadProcessorProvider@Details@Foundation@Bluetooth@Microsoft@@@std@@XZ; Microsoft::Bluetooth::Foundation::Details::ThreadProcessorProvider::GetDefaultInstance(void)
0x18000c9d5  nop
0x18000c9d6  mov     rcx, [rax]
0x18000c9d9  mov     rax, [rcx]
0x18000c9dc  mov     r8d, 6F696F74h
0x18000c9e2  lea     rdx, [rbp+57h+var_B0]
0x18000c9e6  mov     rax, [rax+8]
0x18000c9ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9ef  nop
0x18000c9f0  mov     rcx, [rbp+57h+var_A0+8]; this
0x18000c9f4  test    rcx, rcx
0x18000c9f7  jz      short loc_18000C9FE
0x18000c9f9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c9fe  mov     rax, qword ptr [rbp+57h+var_B0]
0x18000ca02  mov     qword ptr [rbp+57h+var_B0], 0
0x18000ca0a  mov     rdx, [rdi+30h]
0x18000ca0e  mov     [rdi+30h], rax
0x18000ca12  test    rdx, rdx
0x18000ca15  jz      short loc_18000CA1C
0x18000ca17  call    ??R?$default_delete@VThreadProcessorControl@Foundation@Bluetooth@Microsoft@@@std@@QEBAXPEAVThreadProcessorControl@Foundation@Bluetooth@Microsoft@@@Z; std::default_delete<Microsoft::Bluetooth::Foundation::ThreadProcessorControl>::operator()(Microsoft::Bluetooth::Foundation::ThreadProcessorControl *)
0x18000ca1c  lea     rcx, [rbp+57h+var_B0]
0x18000ca20  call    ??1?$unique_ptr@VRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@U?$default_delete@VRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::RequestDispatcher>::~unique_ptr<Microsoft::Bluetooth::Foundation::Details::RequestDispatcher>(void)
0x18000ca25  mov     rsi, [rbx]
0x18000ca28  xorps   xmm0, xmm0
0x18000ca2b  movdqu  xmmword ptr [rbp+57h+var_A0], xmm0
0x18000ca30  mov     rdx, rdi
0x18000ca33  lea     rcx, [rbp+57h+var_A0]
0x18000ca37  call    ??$_Construct_from_weak@VAsyncRadioEnumeratorImpl@Details@Foundation@Bluetooth@Microsoft@@@?$_Ptr_base@VAsyncRadioEnumeratorImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@IEAA_NAEBV?$weak_ptr@VAsyncRadioEnumeratorImpl@Details@Foundation@Bluetooth@Microsoft@@@1@@Z; std::_Ptr_base<Microsoft::Bluetooth::Foundation::Details::AsyncRadioEnumeratorImpl>::_Construct_from_weak<Microsoft::Bluetooth::Foundation::Details::AsyncRadioEnumeratorImpl>(std::weak_ptr<Microsoft::Bluetooth::Foundation::Details::AsyncRadioEnumeratorImpl> const &)
0x18000ca3c  test    al, al
0x18000ca3e  jz      loc_18000CB46
0x18000ca44  lea     rdx, [rbp+57h+var_A0]
0x18000ca48  lea     rcx, [rbp+57h+var_90]
0x18000ca4c  call    ??$?0V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@$0A@@?$weak_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@std@@QEAA@AEBV?$shared_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@1@@Z; std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>>::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>>(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>> const &)
0x18000ca51  nop
0x18000ca52  mov     rdx, [rax]
0x18000ca55  mov     rcx, [rax+8]
0x18000ca59  mov     qword ptr [rax], 0
0x18000ca60  mov     qword ptr [rax+8], 0
0x18000ca68  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_75ca5b0294875c693bc0b8f02cdd6ad9_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_75ca5b0294875c693bc0b8f02cdd6ad9_,void,>::`vftable'
0x18000ca6f  mov     [rbp+57h+var_70], rax
0x18000ca73  mov     [rbp+57h+var_68], rdx
0x18000ca77  mov     [rbp+57h+var_60], rcx
0x18000ca7b  movdqu  [rbp+57h+var_B0], xmm0
0x18000ca80  lea     rax, [rbp+57h+var_70]
0x18000ca84  mov     [rbp+57h+var_38], rax
0x18000ca88  mov     ecx, 40h ; '@'; Size
0x18000ca8d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ca92  mov     rbx, rax
0x18000ca95  mov     qword ptr [rbp+57h+var_B0], rax
0x18000ca99  lea     rdx, [rbp+57h+var_70]
0x18000ca9d  mov     rcx, rax
0x18000caa0  call    ??0?$function@$$A6AXXZ@std@@QEAA@$$QEAV01@@Z; std::function<void (void)>::function<void (void)>(std::function<void (void)> &&)
0x18000caa5  mov     qword ptr [rbp+57h+var_B0], rbx
0x18000caa9  mov     r8, [rsi+8]; pcbe
0x18000caad  mov     rdx, rbx; pv
0x18000cab0  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_4312f3ad3f7a3d3f8ba09c7a67669e2f_@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18000cab7  call    cs:__imp_TrySubmitThreadpoolCallback
0x18000cabd  test    eax, eax
0x18000cabf  jz      short loc_18000CACD
0x18000cac1  mov     bl, 1
0x18000cac3  mov     qword ptr [rbp+57h+var_B0], 0
0x18000cacb  jmp     short loc_18000CACF
0x18000cacd  xor     bl, bl
0x18000cacf  lea     rcx, [rbp+57h+var_B0]
0x18000cad3  call    ??1?$unique_ptr@UContext@?1??TrySubmitCallback@ThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@QEAA_N$$QEAV?$function@$$A6AXXZ@std@@@Z@U?$default_delete@UContext@?1??TrySubmitCallback@ThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@QEAA_N$$QEAV?$function@$$A6AXXZ@std@@@Z@@8@@std@@QEAA@XZ; std::unique_ptr<`Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator::TrySubmitCallback(std::function<void (void)> &&)'::`2'::Context,std::default_delete<`Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator::TrySubmitCallback(std::function<void (void)> &&)'::`2'::Context>>::~unique_ptr<`Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator::TrySubmitCallback(std::function<void (void)> &&)'::`2'::Context,std::default_delete<`Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator::TrySubmitCallback(std::function<void (void)> &&)'::`2'::Context>>(void)
0x18000cad8  nop
0x18000cad9  lea     rcx, [rbp+57h+var_70]
0x18000cadd  call    ?_Tidy@?$_Func_class@XW4DeviceChangeEventType@AvrcpTransportEnumerator@Avrcp@Profiles@Bluetooth@Microsoft@@PEBGAEBV?$shared_ptr@VAvrcpTransport@Avrcp@Profiles@Bluetooth@Microsoft@@@std@@@std@@IEAAXXZ; std::_Func_class<void,Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,ushort const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy(void)
0x18000cae2  nop
0x18000cae3  mov     rcx, [rbp+57h+var_88]; this
0x18000cae7  test    rcx, rcx
0x18000caea  jz      short loc_18000CAF2
0x18000caec  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18000caf1  nop
0x18000caf2  mov     rcx, [rbp+57h+var_A0+8]; this
0x18000caf6  test    rcx, rcx
0x18000caf9  jz      short loc_18000CB00
0x18000cafb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000cb00  xor     bl, 1
0x18000cb03  mov     rcx, [rbp+5Fh]; this
0x18000cb07  lea     rax, aFailedToSubmit; "Failed to submit OnStart threadpool cal"...
0x18000cb0e  mov     qword ptr [rsp+0F0h+var_C8], rax; bool
0x18000cb13  mov     [rsp+0F0h+var_D0], bl; char
0x18000cb17  mov     r9d, 80004005h; char *
0x18000cb1d  lea     r8, aOnecoreDrivers_35; "onecore\\drivers\\bluetooth\\foundation"...
0x18000cb24  mov     edx, 0BBh; void *
0x18000cb29  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18000cb2e  mov     rcx, [rbp+57h+var_30]
0x18000cb32  xor     rcx, rsp; StackCookie
0x18000cb35  call    __security_check_cookie
0x18000cb3a  add     rsp, 0D8h
0x18000cb41  pop     rdi
0x18000cb42  pop     rsi
0x18000cb43  pop     rbx
0x18000cb44  pop     rbp
0x18000cb45  retn
0x18000cb46  call    ?_Throw_bad_weak_ptr@std@@YAXXZ; std::_Throw_bad_weak_ptr(void)
0x18000cb4c  mov     r9d, eax; char *
0x18000cb4f  lea     r8, aOnecoreDrivers_35; "onecore\\drivers\\bluetooth\\foundation"...
0x18000cb56  mov     edx, 73h ; 's'; void *
0x18000cb5b  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000cb61  lea     r8, aOnecoreDrivers_35; "onecore\\drivers\\bluetooth\\foundation"...
0x18000cb68  mov     edx, 85h; void *
0x18000cb6d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
