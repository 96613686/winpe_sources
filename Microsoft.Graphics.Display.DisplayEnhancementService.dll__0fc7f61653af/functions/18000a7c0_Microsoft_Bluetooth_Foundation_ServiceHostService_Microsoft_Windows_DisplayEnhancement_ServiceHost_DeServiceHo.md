# Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::Cleanup(void *,uchar)

- ea: `0x18000a7c0`
- end: `0x18000a8cf`
- name: `?Cleanup@?$ServiceHostService@VDeServiceHost@ServiceHost@DisplayEnhancement@Windows@Microsoft@@$00@Foundation@Bluetooth@Microsoft@@CAXPEAXE@Z`
- size: `271`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180005884`
- `0x180009a84`
- `0x18000a7c0`
- `0x18000c118`
- `0x18000e5dc`
- `0x18000f03c`
- `0x18000f778`
- `0x18000fdd8`
- `0x18000ff38`
- `0x180011724`
- `0x180011750`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a880`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a880`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18000a82f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18000a82f`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18000a7f4`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18000a7f4`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::Cleanup(
        __int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rsi
  __int64 v4; // rax
  unsigned int v5; // r8d
  int v6; // r9d
  unsigned int v7; // edx
  void *v8; // rcx
  Microsoft::Bluetooth::Foundation::AsyncObjectRegistrar *v9; // rcx
  std::_Ref_count_base *v10; // rbx
  _BYTE v11[8]; // [rsp+20h] [rbp-18h] BYREF
  std::_Ref_count_base *v12; // [rsp+28h] [rbp-10h]
  RTL_SRWLOCK *v13; // [rsp+40h] [rbp+8h] BYREF

  v13 = (RTL_SRWLOCK *)a1;
  std::unique_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::RpcServerLifetime<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer> (*)(void),&public: static std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer> Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer::GetOrMakeShared(void),>>::reset(
    a1,
    0);
  std::unique_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::RpcServerLifetime<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer> (*)(void),&public: static std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer> Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer::GetOrMakeShared(void),>>::reset(
    v2,
    0);
  PowerSettingUnregisterNotification(Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::s_hBattNotifHandle);
  v3 = *(_QWORD *)(a1 + 32);
  v4 = Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>>::Instance(v11);
  wil::handle_wait(*(wil **)(*(_QWORD *)v4 + 16LL), (void *)0xFFFFFFFFLL, v5, v6);
  if ( v12 )
    std::_Ref_count_base::_Decref(v12);
  CloseThreadpoolCleanupGroupMembers(*(PTP_CLEANUP_GROUP *)(v3 + 16), 0, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_CLEANUP_GROUP *,void (*)(_TP_CLEANUP_GROUP *),&public: static void wil::details::DestroyThreadpoolCleanupGroup::Destroy(_TP_CLEANUP_GROUP *),wistd::integral_constant<unsigned __int64,0>,_TP_CLEANUP_GROUP *,_TP_CLEANUP_GROUP *,0,std::nullptr_t>>::reset(
    v3 + 16,
    0);
  v8 = *(void **)(v3 + 8);
  *(_QWORD *)(v3 + 8) = 0;
  if ( v8 )
    operator delete(v8, (const struct std::nothrow_t *)0x48);
  v9 = *(Microsoft::Bluetooth::Foundation::AsyncObjectRegistrar **)(a1 + 16);
  if ( v9 )
    Microsoft::Bluetooth::Foundation::AsyncObjectRegistrar::WaitOnNoObjects(v9, v7);
  Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::SetStatus(
    a1,
    1);
  AcquireSRWLockExclusive(&Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::m_serviceStaticsLock);
  v13 = &Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::m_serviceStaticsLock;
  Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::s_service = 0;
  v10 = qword_180129370;
  qword_180129370 = 0;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
}

```

## disassembly

```asm
0x18000a7c0  mov     [rsp+arg_8], rbx
0x18000a7c5  mov     [rsp+arg_10], rsi
0x18000a7ca  mov     [rsp+arg_0], rcx
0x18000a7cf  push    rdi
0x18000a7d0  sub     rsp, 30h
0x18000a7d4  mov     rdi, rcx
0x18000a7d7  xor     edx, edx
0x18000a7d9  call    ?reset@?$unique_ptr@V?$RpcServerLifetime@VDeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@P6A?AV?$shared_ptr@VDeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ$1?GetOrMakeShared@11234@SA?AV56@XZ$$V@Foundation@DisplayEnhancement@Windows@Microsoft@@U?$default_delete@V?$RpcServerLifetime@VDeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@P6A?AV?$shared_ptr@VDeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ$1?GetOrMakeShared@11234@SA?AV56@XZ$$V@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@QEAAXPEAV?$RpcServerLifetime@VDeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@P6A?AV?$shared_ptr@VDeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ$1?GetOrMakeShared@11234@SA?AV56@XZ$$V@Foundation@DisplayEnhancement@Windows@Microsoft@@@Z; std::unique_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::RpcServerLifetime<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer> (*)(void),&Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer::GetOrMakeShared(void),>>::reset(Microsoft::Windows::DisplayEnhancement::Foundation::RpcServerLifetime<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer> (*)(void),&Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer::GetOrMakeShared(void),> *)
0x18000a7de  xor     edx, edx
0x18000a7e0  call    ?reset@?$unique_ptr@V?$RpcServerLifetime@VDeoRpcServer@1DisplayEnhancement@Windows@Microsoft@@P6A?AV?$shared_ptr@VDeoRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ$1?GetOrMakeShared@11234@SA?AV56@XZ$$V@Foundation@DisplayEnhancement@Windows@Microsoft@@U?$default_delete@V?$RpcServerLifetime@VDeoRpcServer@1DisplayEnhancement@Windows@Microsoft@@P6A?AV?$shared_ptr@VDeoRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ$1?GetOrMakeShared@11234@SA?AV56@XZ$$V@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@QEAAXPEAV?$RpcServerLifetime@VDeoRpcServer@1DisplayEnhancement@Windows@Microsoft@@P6A?AV?$shared_ptr@VDeoRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ$1?GetOrMakeShared@11234@SA?AV56@XZ$$V@Foundation@DisplayEnhancement@Windows@Microsoft@@@Z; std::unique_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::RpcServerLifetime<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer> (*)(void),&Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer::GetOrMakeShared(void),>>::reset(Microsoft::Windows::DisplayEnhancement::Foundation::RpcServerLifetime<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer> (*)(void),&Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer::GetOrMakeShared(void),> *)
0x18000a7e5  nop
0x18000a7e6  jmp     short loc_18000A7ED
0x18000a7e8  mov     rdi, [rsp+38h+arg_0]
0x18000a7ed  mov     rcx, cs:?s_hBattNotifHandle@?$ServiceHostService@VDeServiceHost@ServiceHost@DisplayEnhancement@Windows@Microsoft@@$00@Foundation@Bluetooth@Microsoft@@0PEAXEA; RegistrationHandle
0x18000a7f4  call    cs:__imp_PowerSettingUnregisterNotification
0x18000a7fa  mov     rsi, [rdi+20h]
0x18000a7fe  lea     rcx, [rsp+38h+var_18]
0x18000a803  call    ?Instance@?$SingletonWithFactory@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@@345@@Foundation@Bluetooth@Microsoft@@SA?AV?$shared_ptr@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@@std@@XZ; Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>>::Instance(void)
0x18000a808  mov     rcx, [rax]
0x18000a80b  or      edx, 0FFFFFFFFh; void *
0x18000a80e  mov     rcx, [rcx+10h]; this
0x18000a812  call    ?handle_wait@wil@@YA_NPEAXKH@Z; wil::handle_wait(void *,ulong,int)
0x18000a817  mov     rcx, [rsp+38h+var_10]; this
0x18000a81c  test    rcx, rcx
0x18000a81f  jz      short loc_18000A826
0x18000a821  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a826  xor     r8d, r8d; pvCleanupContext
0x18000a829  xor     edx, edx; fCancelPendingCallbacks
0x18000a82b  mov     rcx, [rsi+10h]; ptpcg
0x18000a82f  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18000a835  xor     edx, edx
0x18000a837  lea     rcx, [rsi+10h]
0x18000a83b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_CLEANUP_GROUP@@P6AXPEAU1@@Z$1?Destroy@DestroyThreadpoolCleanupGroup@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_CLEANUP_GROUP@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_CLEANUP_GROUP *,void (*)(_TP_CLEANUP_GROUP *),&wil::details::DestroyThreadpoolCleanupGroup::Destroy(_TP_CLEANUP_GROUP *),wistd::integral_constant<unsigned __int64,0>,_TP_CLEANUP_GROUP *,_TP_CLEANUP_GROUP *,0,std::nullptr_t>>::reset(_TP_CLEANUP_GROUP *)
0x18000a840  mov     rcx, [rsi+8]; void *
0x18000a844  mov     qword ptr [rsi+8], 0
0x18000a84c  test    rcx, rcx
0x18000a84f  jz      short loc_18000A85B
0x18000a851  mov     edx, 48h ; 'H'; struct std::nothrow_t *
0x18000a856  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a85b  mov     rcx, [rdi+10h]; this
0x18000a85f  test    rcx, rcx
0x18000a862  jz      short loc_18000A869
0x18000a864  call    ?WaitOnNoObjects@AsyncObjectRegistrar@Foundation@Bluetooth@Microsoft@@QEAA_NK@Z; Microsoft::Bluetooth::Foundation::AsyncObjectRegistrar::WaitOnNoObjects(ulong)
0x18000a869  mov     edx, 1
0x18000a86e  mov     rcx, rdi
0x18000a871  call    ?SetStatus@?$ServiceHostService@VDeServiceHost@ServiceHost@DisplayEnhancement@Windows@Microsoft@@$00@Foundation@Bluetooth@Microsoft@@AEAAXK@Z; Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::SetStatus(ulong)
0x18000a876  lea     rbx, ?m_serviceStaticsLock@?$ServiceHostService@VDeServiceHost@ServiceHost@DisplayEnhancement@Windows@Microsoft@@$00@Foundation@Bluetooth@Microsoft@@0Vsrwlock@wil@@A; wil::srwlock Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::m_serviceStaticsLock
0x18000a87d  mov     rcx, rbx; SRWLock
0x18000a880  call    cs:__imp_AcquireSRWLockExclusive
0x18000a886  mov     [rsp+38h+arg_0], rbx
0x18000a88b  mov     cs:?s_service@?$ServiceHostService@VDeServiceHost@ServiceHost@DisplayEnhancement@Windows@Microsoft@@$00@Foundation@Bluetooth@Microsoft@@0V?$shared_ptr@VDeServiceHost@ServiceHost@DisplayEnhancement@Windows@Microsoft@@@std@@A, 0; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost> Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::s_service
0x18000a896  mov     rbx, cs:qword_180129370
0x18000a89d  mov     cs:qword_180129370, 0
0x18000a8a8  lea     rcx, [rsp+38h+arg_0]
0x18000a8ad  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000a8b2  test    rbx, rbx
0x18000a8b5  jz      short loc_18000A8BF
0x18000a8b7  mov     rcx, rbx; this
0x18000a8ba  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a8bf  mov     rbx, [rsp+38h+arg_8]
0x18000a8c4  mov     rsi, [rsp+38h+arg_10]
0x18000a8c9  add     rsp, 30h
0x18000a8cd  pop     rdi
0x18000a8ce  retn
```
