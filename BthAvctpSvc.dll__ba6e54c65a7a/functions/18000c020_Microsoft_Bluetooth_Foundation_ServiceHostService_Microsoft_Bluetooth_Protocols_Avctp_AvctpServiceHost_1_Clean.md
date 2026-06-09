# Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost,1>::Cleanup(void *,uchar)

- ea: `0x18000c020`
- end: `0x18000c139`
- name: `?Cleanup@?$ServiceHostService@VAvctpServiceHost@Avctp@Protocols@Bluetooth@Microsoft@@$00@Foundation@Bluetooth@Microsoft@@CAXPEAXE@Z`
- size: `281`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x1800021a0`
- `0x180004060`
- `0x18000b7e4`
- `0x18000c020`
- `0x18000cf60`
- `0x18000dab0`
- `0x18000dd7c`
- `0x18000de78`
- `0x18000e1cc`
- `0x18000e210`
- `0x180027ec0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c0ea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c0ea`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18000c099`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18000c099`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18000c04b`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18000c04b`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost,1>::Cleanup(
        Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost *a1)
{
  const char *v1; // r9
  _QWORD *p_Ptr; // rdi
  __int64 v3; // rdx
  __int64 v4; // rsi
  __int64 v5; // rax
  void *v6; // rdx
  unsigned int v7; // r8d
  int v8; // r9d
  unsigned int v9; // edx
  void *v10; // rcx
  Microsoft::Bluetooth::Foundation::AsyncObjectRegistrar *v11; // rcx
  std::_Ref_count_base *v12; // rbx
  _BYTE v13[8]; // [rsp+20h] [rbp-18h] BYREF
  std::_Ref_count_base *v14; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  RTL_SRWLOCK *v16; // [rsp+40h] [rbp+8h] BYREF

  v16 = (RTL_SRWLOCK *)a1;
  try
  {
    p_Ptr = a1;
    Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost::OnStop(a1);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xFA,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\ServiceHost.h",
      v1);
    p_Ptr = &v16->Ptr;
  }
  PowerSettingUnregisterNotification(Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost,1>::s_hBattNotifHandle);
  v3 = p_Ptr[6];
  p_Ptr[6] = 0;
  if ( v3 )
    std::default_delete<Microsoft::Bluetooth::Foundation::ThreadProcessorControl>::operator()();
  v4 = p_Ptr[4];
  v5 = Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>>::Instance(v13);
  wil::handle_wait(*(wil **)(*(_QWORD *)v5 + 16LL), v6, v7, v8);
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  CloseThreadpoolCleanupGroupMembers(*(PTP_CLEANUP_GROUP *)(v4 + 16), 0, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_CLEANUP_GROUP *,void (*)(_TP_CLEANUP_GROUP *),&public: static void wil::details::DestroyThreadpoolCleanupGroup::Destroy(_TP_CLEANUP_GROUP *),wistd::integral_constant<unsigned __int64,0>,_TP_CLEANUP_GROUP *,_TP_CLEANUP_GROUP *,0,std::nullptr_t>>::reset(
    v4 + 16,
    0);
  v10 = *(void **)(v4 + 8);
  *(_QWORD *)(v4 + 8) = 0;
  if ( v10 )
    operator delete(v10, (const struct std::nothrow_t *)0x48);
  v11 = (Microsoft::Bluetooth::Foundation::AsyncObjectRegistrar *)p_Ptr[2];
  if ( v11 )
    Microsoft::Bluetooth::Foundation::AsyncObjectRegistrar::WaitOnNoObjects(v11, v9);
  Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost,1>::SetStatus(
    p_Ptr,
    1);
  AcquireSRWLockExclusive(&Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost,1>::m_serviceStaticsLock);
  v16 = &Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost,1>::m_serviceStaticsLock;
  Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost,1>::s_service = 0;
  v12 = qword_180076A50;
  qword_180076A50 = 0;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
  if ( v12 )
    std::_Ref_count_base::_Decref(v12);
}

```

## disassembly

```asm
0x18000c020  mov     [rsp+arg_8], rbx
0x18000c025  mov     [rsp+arg_10], rsi
0x18000c02a  mov     [rsp+arg_0], rcx
0x18000c02f  push    rdi
0x18000c030  sub     rsp, 30h
0x18000c034  mov     rdi, rcx
0x18000c037  call    ?OnStop@AvctpServiceHost@Avctp@Protocols@Bluetooth@Microsoft@@QEAAXXZ; Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost::OnStop(void)
0x18000c03c  nop
0x18000c03d  jmp     short loc_18000C044
0x18000c03f  mov     rdi, [rsp+38h+arg_0]
0x18000c044  mov     rcx, cs:?s_hBattNotifHandle@?$ServiceHostService@VAvctpServiceHost@Avctp@Protocols@Bluetooth@Microsoft@@$00@Foundation@Bluetooth@Microsoft@@0PEAXEA; RegistrationHandle
0x18000c04b  call    cs:__imp_PowerSettingUnregisterNotification
0x18000c051  mov     rdx, [rdi+30h]
0x18000c055  mov     qword ptr [rdi+30h], 0
0x18000c05d  test    rdx, rdx
0x18000c060  jz      short loc_18000C067
0x18000c062  call    ??R?$default_delete@VThreadProcessorControl@Foundation@Bluetooth@Microsoft@@@std@@QEBAXPEAVThreadProcessorControl@Foundation@Bluetooth@Microsoft@@@Z; std::default_delete<Microsoft::Bluetooth::Foundation::ThreadProcessorControl>::operator()(Microsoft::Bluetooth::Foundation::ThreadProcessorControl *)
0x18000c067  mov     rsi, [rdi+20h]
0x18000c06b  lea     rcx, [rsp+38h+var_18]
0x18000c070  call    ?Instance@?$SingletonWithFactory@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@@345@@Foundation@Bluetooth@Microsoft@@SA?AV?$shared_ptr@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@@std@@XZ; Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>>::Instance(void)
0x18000c075  mov     rcx, [rax]
0x18000c078  mov     rcx, [rcx+10h]; this
0x18000c07c  call    ?handle_wait@wil@@YA_NPEAXKH@Z; wil::handle_wait(void *,ulong,int)
0x18000c081  mov     rcx, [rsp+38h+var_10]; this
0x18000c086  test    rcx, rcx
0x18000c089  jz      short loc_18000C090
0x18000c08b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c090  xor     r8d, r8d; pvCleanupContext
0x18000c093  xor     edx, edx; fCancelPendingCallbacks
0x18000c095  mov     rcx, [rsi+10h]; ptpcg
0x18000c099  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18000c09f  xor     edx, edx
0x18000c0a1  lea     rcx, [rsi+10h]
0x18000c0a5  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_CLEANUP_GROUP@@P6AXPEAU1@@Z$1?Destroy@DestroyThreadpoolCleanupGroup@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_CLEANUP_GROUP@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_CLEANUP_GROUP *,void (*)(_TP_CLEANUP_GROUP *),&wil::details::DestroyThreadpoolCleanupGroup::Destroy(_TP_CLEANUP_GROUP *),wistd::integral_constant<unsigned __int64,0>,_TP_CLEANUP_GROUP *,_TP_CLEANUP_GROUP *,0,std::nullptr_t>>::reset(_TP_CLEANUP_GROUP *)
0x18000c0aa  mov     rcx, [rsi+8]; void *
0x18000c0ae  mov     qword ptr [rsi+8], 0
0x18000c0b6  test    rcx, rcx
0x18000c0b9  jz      short loc_18000C0C5
0x18000c0bb  mov     edx, 48h ; 'H'; struct std::nothrow_t *
0x18000c0c0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c0c5  mov     rcx, [rdi+10h]; this
0x18000c0c9  test    rcx, rcx
0x18000c0cc  jz      short loc_18000C0D3
0x18000c0ce  call    ?WaitOnNoObjects@AsyncObjectRegistrar@Foundation@Bluetooth@Microsoft@@QEAA_NK@Z; Microsoft::Bluetooth::Foundation::AsyncObjectRegistrar::WaitOnNoObjects(ulong)
0x18000c0d3  mov     edx, 1
0x18000c0d8  mov     rcx, rdi
0x18000c0db  call    ?SetStatus@?$ServiceHostService@VAvctpServiceHost@Avctp@Protocols@Bluetooth@Microsoft@@$00@Foundation@Bluetooth@Microsoft@@AEAAXK@Z; Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost,1>::SetStatus(ulong)
0x18000c0e0  lea     rbx, ?m_serviceStaticsLock@?$ServiceHostService@VAvctpServiceHost@Avctp@Protocols@Bluetooth@Microsoft@@$00@Foundation@Bluetooth@Microsoft@@0Vsrwlock@wil@@A; wil::srwlock Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost,1>::m_serviceStaticsLock
0x18000c0e7  mov     rcx, rbx; SRWLock
0x18000c0ea  call    cs:__imp_AcquireSRWLockExclusive
0x18000c0f0  mov     [rsp+38h+arg_0], rbx
0x18000c0f5  mov     cs:?s_service@?$ServiceHostService@VAvctpServiceHost@Avctp@Protocols@Bluetooth@Microsoft@@$00@Foundation@Bluetooth@Microsoft@@0V?$shared_ptr@VAvctpServiceHost@Avctp@Protocols@Bluetooth@Microsoft@@@std@@A, 0; std::shared_ptr<Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost> Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost,1>::s_service
0x18000c100  mov     rbx, cs:qword_180076A50
0x18000c107  mov     cs:qword_180076A50, 0
0x18000c112  lea     rcx, [rsp+38h+arg_0]
0x18000c117  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000c11c  test    rbx, rbx
0x18000c11f  jz      short loc_18000C129
0x18000c121  mov     rcx, rbx; this
0x18000c124  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c129  mov     rbx, [rsp+38h+arg_8]
0x18000c12e  mov     rsi, [rsp+38h+arg_10]
0x18000c133  add     rsp, 30h
0x18000c137  pop     rdi
0x18000c138  retn
```
