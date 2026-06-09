# Execution::BackgroundManager::~BackgroundManager(void)

- ea: `0x18006e860`
- end: `0x18006ebe3`
- name: `??1BackgroundManager@Execution@@UEAA@XZ`
- size: `899`
- prototype: `void __fastcall(Execution::BackgroundManager *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180089b50`

## callees

- `0x18001d04c`
- `0x18001ef7c`
- `0x18001ff28`
- `0x1800215e8`
- `0x18006e860`
- `0x18006ebec`
- `0x18006ec14`
- `0x18006ec3c`
- `0x18006f54c`
- `0x18006f9f4`
- `0x180070eec`
- `0x180089814`
- `0x18008bff0`
- `0x18008c6d8`
- `0x18008c90c`
- `0x180095010`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18006e8ea`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18006e903`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18006e8ea`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18006e903`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e93e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e93e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006eafe`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006eafe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e9fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e9fa`
- `RPCRT4!RpcBindingFree` at `0x18006e91f`
- `RPCRT4!RpcBindingFree` at `0x18006e91f`
- `ResourcePolicyClient!InterruptiveUIStateChanged_Unsubscribe` at `0x18006e92e`
- `ResourcePolicyClient!InterruptiveUIStateChanged_Unsubscribe` at `0x18006e92e`
- `RMCLIENT!HamDisconnectFromServer` at `0x18006ea0c`
- `RMCLIENT!HamDisconnectFromServer` at `0x18006ea0c`

## pseudocode

```c
void __fastcall Execution::BackgroundManager::~BackgroundManager(Execution::BackgroundManager *this)
{
  unsigned int v2; // edx
  Execution::_BM_POLICY_ENTRY **v3; // rsi
  Execution::_BM_POLICY_ENTRY *v4; // rdi
  Execution::_BM_POLICY_ENTRY *v5; // rax
  __int64 v6; // rcx
  Execution::_BM_EVENT_SETTINGS_ENTRY **v7; // rdi
  Execution::_BM_EVENT_SETTINGS_ENTRY *v8; // rcx
  Execution::_BM_EVENT_SETTINGS_ENTRY *v9; // rax
  Execution::_BM_EVENT_SETTINGS_ENTRY **v10; // rdi
  Execution::_BM_EVENT_SETTINGS_ENTRY *v11; // rcx
  Execution::_BM_EVENT_SETTINGS_ENTRY *v12; // rax
  __int64 **v13; // rdi
  __int64 *v14; // rcx
  __int64 *v15; // rdx
  __int64 v16; // rax
  char **v17; // rdi
  char *v18; // rdx
  _QWORD *v19; // rcx
  __int64 v20; // rax
  char **v21; // rdi
  char *v22; // rdx
  _QWORD *v23; // rcx
  __int64 v24; // rax
  __int64 **v25; // rdi
  __int64 *v26; // rcx
  __int64 *v27; // rdx
  __int64 v28; // rax
  __int64 **v29; // rdi
  __int64 *v30; // rcx
  __int64 *v31; // rdx
  __int64 v32; // rax
  char **v33; // rdi
  char *v34; // rdx
  _QWORD *v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rcx

  *(_QWORD *)this = &Execution::BackgroundManager::`vftable'{for `IInspectable'};
  *((_QWORD *)this + 1) = &Execution::BackgroundManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Execution::IBackgroundManager,IWeakReferenceSource,Execution::IBackgroundManagerInitialize,Execution::IBackgroundManagerInternal,IBackgroundManagerControl,IBackgroundManagerControl2,IBackgroundManagerControl3,IThreadPoolCallback,Execution::IBackgroundManagerSessionCallbackHandler>'};
  *((_QWORD *)this + 2) = &Execution::BackgroundManager::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 3) = &Execution::BackgroundManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Execution::IBackgroundManagerInitialize,Execution::IBackgroundManagerInternal,IBackgroundManagerControl,IBackgroundManagerControl2,IBackgroundManagerControl3,IThreadPoolCallback,Execution::IBackgroundManagerSessionCallbackHandler>'};
  *((_QWORD *)this + 4) = &Execution::BackgroundManager::`vftable'{for `Execution::IBackgroundManagerInternal'};
  *((_QWORD *)this + 5) = &Execution::BackgroundManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IBackgroundManagerControl,IBackgroundManagerControl2,IBackgroundManagerControl3,IThreadPoolCallback,Execution::IBackgroundManagerSessionCallbackHandler>'};
  *((_QWORD *)this + 6) = &Execution::BackgroundManager::`vftable'{for `IBackgroundManagerControl2'};
  *((_QWORD *)this + 7) = &Execution::BackgroundManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IBackgroundManagerControl3,IThreadPoolCallback,Execution::IBackgroundManagerSessionCallbackHandler>'};
  *((_QWORD *)this + 8) = &Execution::BackgroundManager::`vftable'{for `IThreadPoolCallback'};
  *((_QWORD *)this + 9) = &Execution::BackgroundManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Execution::IBackgroundManagerSessionCallbackHandler>'};
  if ( *((_QWORD *)this + 39) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 39) = 0;
  }
  if ( *((_QWORD *)this + 41) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 41) = 0;
  }
  if ( *((_QWORD *)this + 42) )
  {
    RpcBindingFree((RPC_BINDING_HANDLE *)this + 42);
    *((_QWORD *)this + 42) = 0;
  }
  InterruptiveUIStateChanged_Unsubscribe(*((unsigned int *)this + 178));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  v3 = (Execution::_BM_POLICY_ENTRY **)((char *)this + 248);
  while ( 1 )
  {
    v4 = *v3;
    if ( *v3 == (Execution::_BM_POLICY_ENTRY *)v3 )
      break;
    if ( *((Execution::_BM_POLICY_ENTRY ***)v4 + 1) != v3
      || (v5 = *(Execution::_BM_POLICY_ENTRY **)v4, *(Execution::_BM_POLICY_ENTRY **)(*(_QWORD *)v4 + 8LL) != v4) )
    {
LABEL_24:
      __fastfail(3u);
    }
    *v3 = v5;
    *((_QWORD *)v5 + 1) = v3;
    v6 = *((_QWORD *)v4 + 2);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 32LL))(v6);
    Execution::_BM_POLICY_ENTRY::~_BM_POLICY_ENTRY(v4);
    operator delete(v4);
  }
  v7 = (Execution::_BM_EVENT_SETTINGS_ENTRY **)((char *)this + 504);
  while ( 1 )
  {
    v8 = *v7;
    if ( *v7 == (Execution::_BM_EVENT_SETTINGS_ENTRY *)v7 )
      break;
    if ( *((Execution::_BM_EVENT_SETTINGS_ENTRY ***)v8 + 1) != v7 )
      goto LABEL_24;
    v9 = *(Execution::_BM_EVENT_SETTINGS_ENTRY **)v8;
    if ( *(Execution::_BM_EVENT_SETTINGS_ENTRY **)(*(_QWORD *)v8 + 8LL) != v8 )
      goto LABEL_24;
    *v7 = v9;
    *((_QWORD *)v9 + 1) = v7;
    Execution::_BM_EVENT_SETTINGS_ENTRY::`scalar deleting destructor'(v8, v2);
  }
  v10 = (Execution::_BM_EVENT_SETTINGS_ENTRY **)((char *)this + 352);
  while ( 1 )
  {
    v11 = *v10;
    if ( *v10 == (Execution::_BM_EVENT_SETTINGS_ENTRY *)v10 )
      break;
    if ( *((Execution::_BM_EVENT_SETTINGS_ENTRY ***)v11 + 1) != v10 )
      goto LABEL_24;
    v12 = *(Execution::_BM_EVENT_SETTINGS_ENTRY **)v11;
    if ( *(Execution::_BM_EVENT_SETTINGS_ENTRY **)(*(_QWORD *)v11 + 8LL) != v11 )
      goto LABEL_24;
    *v10 = v12;
    *((_QWORD *)v12 + 1) = v10;
    Execution::_BM_EVENT_SETTINGS_ENTRY::`scalar deleting destructor'(v11, v2);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  if ( *((_QWORD *)this + 96) )
    HamDisconnectFromServer();
  Execution::BackgroundManager::m_sManager = 0;
  McGenEventUnregister_EventUnregister(&MICROSOFT_WINDOWS_APPMODEL_EXEC_PUBLISHER_Context);
  BmResourceSetCache::~BmResourceSetCache((Execution::BackgroundManager *)((char *)this + 720));
  CTelemetryHelperCounter::~CTelemetryHelperCounter((Execution::BackgroundManager *)((char *)this + 600));
  Execution::BmHostInfoManager::~BmHostInfoManager((Execution::BackgroundManager *)((char *)this + 520));
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 496);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 488);
  v13 = (__int64 **)((char *)this + 448);
  while ( 1 )
  {
    v14 = *v13;
    if ( *v13 == (__int64 *)v13 )
      break;
    v15 = (__int64 *)v14[1];
    v16 = *v14;
    *v15 = *v14;
    *(_QWORD *)(v16 + 8) = v15;
    operator delete(v14);
  }
  *((_QWORD *)this + 59) = 0;
  utl::_HashTable<enum RmResourceSetType,utl::pair<enum RmResourceSetType const,unsigned long>,utl::hash<enum RmResourceSetType>,utl::equal_to<enum RmResourceSetType>,utl::allocator<utl::pair<enum RmResourceSetType const,unsigned long>>,0>::_FreeBuckets(v13);
  v17 = (char **)((char *)this + 408);
  while ( 1 )
  {
    v18 = *v17;
    if ( *v17 == (char *)v17 )
      break;
    v19 = (_QWORD *)*((_QWORD *)v18 + 1);
    v20 = *(_QWORD *)v18;
    *v19 = *(_QWORD *)v18;
    *(_QWORD *)(v20 + 8) = v19;
    utl::_ContainerBase<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>>>::_DeleteNode<utl::_HashNode<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>>>(
      (__int64)v19,
      v18);
  }
  *((_QWORD *)this + 54) = 0;
  utl::_HashTable<enum RmResourceSetType,utl::pair<enum RmResourceSetType const,unsigned long>,utl::hash<enum RmResourceSetType>,utl::equal_to<enum RmResourceSetType>,utl::allocator<utl::pair<enum RmResourceSetType const,unsigned long>>,0>::_FreeBuckets((char *)this + 408);
  v21 = (char **)((char *)this + 368);
  while ( 1 )
  {
    v22 = *v21;
    if ( *v21 == (char *)v21 )
      break;
    v23 = (_QWORD *)*((_QWORD *)v22 + 1);
    v24 = *(_QWORD *)v22;
    *v23 = *(_QWORD *)v22;
    *(_QWORD *)(v24 + 8) = v23;
    utl::_ContainerBase<utl::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<Execution::BmHostInfo>>,utl::allocator<utl::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<Execution::BmHostInfo>>>>::_DeleteNode<utl::_HashNode<utl::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<Execution::BmHostInfo>>>>(
      (__int64)v23,
      v22);
  }
  *((_QWORD *)this + 49) = 0;
  utl::_HashTable<enum RmResourceSetType,utl::pair<enum RmResourceSetType const,unsigned long>,utl::hash<enum RmResourceSetType>,utl::equal_to<enum RmResourceSetType>,utl::allocator<utl::pair<enum RmResourceSetType const,unsigned long>>,0>::_FreeBuckets((char *)this + 368);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 240);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 232);
  v25 = (__int64 **)((char *)this + 192);
  while ( 1 )
  {
    v26 = *v25;
    if ( *v25 == (__int64 *)v25 )
      break;
    v27 = (__int64 *)v26[1];
    v28 = *v26;
    *v27 = *v26;
    *(_QWORD *)(v28 + 8) = v27;
    operator delete(v26);
  }
  *((_QWORD *)this + 27) = 0;
  utl::_HashTable<enum RmResourceSetType,utl::pair<enum RmResourceSetType const,unsigned long>,utl::hash<enum RmResourceSetType>,utl::equal_to<enum RmResourceSetType>,utl::allocator<utl::pair<enum RmResourceSetType const,unsigned long>>,0>::_FreeBuckets((char *)this + 192);
  v29 = (__int64 **)((char *)this + 152);
  while ( 1 )
  {
    v30 = *v29;
    if ( *v29 == (__int64 *)v29 )
      break;
    v31 = (__int64 *)v30[1];
    v32 = *v30;
    *v31 = *v30;
    *(_QWORD *)(v32 + 8) = v31;
    operator delete(v30);
  }
  *((_QWORD *)this + 22) = 0;
  utl::_HashTable<enum RmResourceSetType,utl::pair<enum RmResourceSetType const,unsigned long>,utl::hash<enum RmResourceSetType>,utl::equal_to<enum RmResourceSetType>,utl::allocator<utl::pair<enum RmResourceSetType const,unsigned long>>,0>::_FreeBuckets((char *)this + 152);
  v33 = (char **)((char *)this + 112);
  while ( 1 )
  {
    v34 = *v33;
    if ( *v33 == (char *)v33 )
      break;
    v35 = (_QWORD *)*((_QWORD *)v34 + 1);
    v36 = *(_QWORD *)v34;
    *v35 = *(_QWORD *)v34;
    *(_QWORD *)(v36 + 8) = v35;
    utl::_ContainerBase<utl::pair<_GUID const,Microsoft::WRL::ComPtr<Execution::BmTaskInstance>>,utl::allocator<utl::pair<_GUID const,Microsoft::WRL::ComPtr<Execution::BmTaskInstance>>>>::_DeleteNode<utl::_HashNode<utl::pair<_GUID const,Microsoft::WRL::ComPtr<Execution::BmTaskInstance>>>>(
      (__int64)v35,
      v34);
  }
  *((_QWORD *)this + 17) = 0;
  utl::_HashTable<enum RmResourceSetType,utl::pair<enum RmResourceSetType const,unsigned long>,utl::hash<enum RmResourceSetType>,utl::equal_to<enum RmResourceSetType>,utl::allocator<utl::pair<enum RmResourceSetType const,unsigned long>>,0>::_FreeBuckets((char *)this + 112);
  v37 = *((_QWORD *)this + 13);
  if ( v37 )
  {
    *((_QWORD *)this + 13) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 96);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Execution::IBackgroundManager,Execution::IBackgroundManagerInitialize,Execution::IBackgroundManagerInternal,IBackgroundManagerControl,IBackgroundManagerControl2,IBackgroundManagerControl3,IThreadPoolCallback,Execution::IBackgroundManagerSessionCallbackHandler>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Execution::IBackgroundManager,Execution::IBackgroundManagerInitialize,Execution::IBackgroundManagerInternal,IBackgroundManagerControl,IBackgroundManagerControl2,IBackgroundManagerControl3,IThreadPoolCallback,Execution::IBackgroundManagerSessionCallbackHandler>((__int64)this);
}

```

## disassembly

```asm
0x18006e860  push    rbx
0x18006e862  push    rbp
0x18006e863  push    rsi
0x18006e864  push    rdi
0x18006e865  push    r14
0x18006e867  sub     rsp, 20h
0x18006e86b  lea     rax, ??_7BackgroundManager@Execution@@6BIInspectable@@@; const Execution::BackgroundManager::`vftable'{for `IInspectable'}
0x18006e872  mov     rbx, rcx
0x18006e875  mov     [rcx], rax
0x18006e878  xor     r14d, r14d
0x18006e87b  lea     rax, ??_7BackgroundManager@Execution@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIBackgroundManager@Execution@@UIWeakReferenceSource@@UIBackgroundManagerInitialize@5@UIBackgroundManagerInternal@5@UIBackgroundManagerControl@@UIBackgroundManagerControl2@@UIBackgroundManagerControl3@@UIThreadPoolCallback@@UIBackgroundManagerSessionCallbackHandler@5@@Details@WRL@Microsoft@@@; const Execution::BackgroundManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Execution::IBackgroundManager,IWeakReferenceSource,Execution::IBackgroundManagerInitialize,Execution::IBackgroundManagerInternal,IBackgroundManagerControl,IBackgroundManagerControl2,IBackgroundManagerControl3,IThreadPoolCallback,Execution::IBackgroundManagerSessionCallbackHandler>'}
0x18006e882  mov     [rcx+8], rax
0x18006e886  lea     rax, ??_7BackgroundManager@Execution@@6BIWeakReferenceSource@@@; const Execution::BackgroundManager::`vftable'{for `IWeakReferenceSource'}
0x18006e88d  mov     [rcx+10h], rax
0x18006e891  lea     rax, ??_7BackgroundManager@Execution@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIBackgroundManagerInitialize@Execution@@UIBackgroundManagerInternal@5@UIBackgroundManagerControl@@UIBackgroundManagerControl2@@UIBackgroundManagerControl3@@UIThreadPoolCallback@@UIBackgroundManagerSessionCallbackHandler@5@@Details@WRL@Microsoft@@@; const Execution::BackgroundManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Execution::IBackgroundManagerInitialize,Execution::IBackgroundManagerInternal,IBackgroundManagerControl,IBackgroundManagerControl2,IBackgroundManagerControl3,IThreadPoolCallback,Execution::IBackgroundManagerSessionCallbackHandler>'}
0x18006e898  mov     [rcx+18h], rax
0x18006e89c  lea     rax, ??_7BackgroundManager@Execution@@6BIBackgroundManagerInternal@1@@; const Execution::BackgroundManager::`vftable'{for `Execution::IBackgroundManagerInternal'}
0x18006e8a3  mov     [rcx+20h], rax
0x18006e8a7  lea     rax, ??_7BackgroundManager@Execution@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIBackgroundManagerControl@@UIBackgroundManagerControl2@@UIBackgroundManagerControl3@@UIThreadPoolCallback@@UIBackgroundManagerSessionCallbackHandler@Execution@@@Details@WRL@Microsoft@@@; const Execution::BackgroundManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IBackgroundManagerControl,IBackgroundManagerControl2,IBackgroundManagerControl3,IThreadPoolCallback,Execution::IBackgroundManagerSessionCallbackHandler>'}
0x18006e8ae  mov     [rcx+28h], rax
0x18006e8b2  lea     rax, ??_7BackgroundManager@Execution@@6BIBackgroundManagerControl2@@@; const Execution::BackgroundManager::`vftable'{for `IBackgroundManagerControl2'}
0x18006e8b9  mov     [rcx+30h], rax
0x18006e8bd  lea     rax, ??_7BackgroundManager@Execution@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIBackgroundManagerControl3@@UIThreadPoolCallback@@UIBackgroundManagerSessionCallbackHandler@Execution@@@Details@WRL@Microsoft@@@; const Execution::BackgroundManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IBackgroundManagerControl3,IThreadPoolCallback,Execution::IBackgroundManagerSessionCallbackHandler>'}
0x18006e8c4  mov     [rcx+38h], rax
0x18006e8c8  lea     rax, ??_7BackgroundManager@Execution@@6BIThreadPoolCallback@@@; const Execution::BackgroundManager::`vftable'{for `IThreadPoolCallback'}
0x18006e8cf  mov     [rcx+40h], rax
0x18006e8d3  lea     rax, ??_7BackgroundManager@Execution@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIBackgroundManagerSessionCallbackHandler@Execution@@@Details@WRL@Microsoft@@@; const Execution::BackgroundManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Execution::IBackgroundManagerSessionCallbackHandler>'}
0x18006e8da  mov     [rcx+48h], rax
0x18006e8de  mov     rcx, [rcx+138h]
0x18006e8e5  test    rcx, rcx
0x18006e8e8  jz      short loc_18006E8F7
0x18006e8ea  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18006e8f0  mov     [rbx+138h], r14
0x18006e8f7  mov     rcx, [rbx+148h]
0x18006e8fe  test    rcx, rcx
0x18006e901  jz      short loc_18006E910
0x18006e903  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18006e909  mov     [rbx+148h], r14
0x18006e910  lea     rdi, [rbx+150h]
0x18006e917  cmp     [rdi], r14
0x18006e91a  jz      short loc_18006E928
0x18006e91c  mov     rcx, rdi; Binding
0x18006e91f  call    cs:__imp_RpcBindingFree
0x18006e925  mov     [rdi], r14
0x18006e928  mov     ecx, [rbx+2C8h]
0x18006e92e  call    cs:__imp_InterruptiveUIStateChanged_Unsubscribe
0x18006e934  lea     rbp, [rbx+108h]
0x18006e93b  mov     rcx, rbp; lpCriticalSection
0x18006e93e  call    cs:__imp_EnterCriticalSection
0x18006e944  lea     rsi, [rbx+0F8h]
0x18006e94b  mov     rdi, [rsi]
0x18006e94e  cmp     rdi, rsi
0x18006e951  jz      short loc_18006E998
0x18006e953  cmp     [rdi+8], rsi
0x18006e957  jnz     loc_18006E9F0
0x18006e95d  mov     rax, [rdi]
0x18006e960  cmp     [rax+8], rdi
0x18006e964  jnz     loc_18006E9F0
0x18006e96a  mov     [rsi], rax
0x18006e96d  mov     [rax+8], rsi
0x18006e971  mov     rcx, [rdi+10h]
0x18006e975  test    rcx, rcx
0x18006e978  jz      short loc_18006E986
0x18006e97a  mov     rax, [rcx]
0x18006e97d  mov     rax, [rax+20h]
0x18006e981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e986  mov     rcx, rdi; this
0x18006e989  call    ??1_BM_POLICY_ENTRY@Execution@@QEAA@XZ; Execution::_BM_POLICY_ENTRY::~_BM_POLICY_ENTRY(void)
0x18006e98e  mov     rcx, rdi; Block
0x18006e991  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006e996  jmp     short loc_18006E94B
0x18006e998  lea     rdi, [rbx+1F8h]
0x18006e99f  mov     rcx, [rdi]; this
0x18006e9a2  cmp     rcx, rdi
0x18006e9a5  jz      short loc_18006E9C4
0x18006e9a7  cmp     [rcx+8], rdi
0x18006e9ab  jnz     short loc_18006E9F0
0x18006e9ad  mov     rax, [rcx]
0x18006e9b0  cmp     [rax+8], rcx
0x18006e9b4  jnz     short loc_18006E9F0
0x18006e9b6  mov     [rdi], rax
0x18006e9b9  mov     [rax+8], rdi
0x18006e9bd  call    ??_G_BM_EVENT_SETTINGS_ENTRY@Execution@@QEAAPEAXI@Z; Execution::_BM_EVENT_SETTINGS_ENTRY::`scalar deleting destructor'(uint)
0x18006e9c2  jmp     short loc_18006E99F
0x18006e9c4  lea     rdi, [rbx+160h]
0x18006e9cb  mov     rcx, [rdi]; this
0x18006e9ce  cmp     rcx, rdi
0x18006e9d1  jz      short loc_18006E9F7
0x18006e9d3  cmp     [rcx+8], rdi
0x18006e9d7  jnz     short loc_18006E9F0
0x18006e9d9  mov     rax, [rcx]
0x18006e9dc  cmp     [rax+8], rcx
0x18006e9e0  jnz     short loc_18006E9F0
0x18006e9e2  mov     [rdi], rax
0x18006e9e5  mov     [rax+8], rdi
0x18006e9e9  call    ??_G_BM_EVENT_SETTINGS_ENTRY@Execution@@QEAAPEAXI@Z; Execution::_BM_EVENT_SETTINGS_ENTRY::`scalar deleting destructor'(uint)
0x18006e9ee  jmp     short loc_18006E9CB
0x18006e9f0  mov     ecx, 3
0x18006e9f5  int     29h; Win8: RtlFailFast(ecx)
0x18006e9f7  mov     rcx, rbp; lpCriticalSection
0x18006e9fa  call    cs:__imp_LeaveCriticalSection
0x18006ea00  mov     rcx, [rbx+300h]
0x18006ea07  test    rcx, rcx
0x18006ea0a  jz      short loc_18006EA12
0x18006ea0c  call    cs:__imp_HamDisconnectFromServer
0x18006ea12  lea     rcx, MICROSOFT_WINDOWS_APPMODEL_EXEC_PUBLISHER_Context
0x18006ea19  mov     cs:?m_sManager@BackgroundManager@Execution@@1PEAV12@EA, r14; Execution::BackgroundManager * Execution::BackgroundManager::m_sManager
0x18006ea20  call    McGenEventUnregister_EventUnregister
0x18006ea25  lea     rcx, [rbx+2D0h]; this
0x18006ea2c  call    ??1BmResourceSetCache@@QEAA@XZ; BmResourceSetCache::~BmResourceSetCache(void)
0x18006ea31  lea     rcx, [rbx+258h]; this
0x18006ea38  call    ??1CTelemetryHelperCounter@@UEAA@XZ; CTelemetryHelperCounter::~CTelemetryHelperCounter(void)
0x18006ea3d  lea     rcx, [rbx+208h]; this
0x18006ea44  call    ??1BmHostInfoManager@Execution@@QEAA@XZ; Execution::BmHostInfoManager::~BmHostInfoManager(void)
0x18006ea49  lea     rcx, [rbx+1F0h]
0x18006ea50  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006ea55  lea     rcx, [rbx+1E8h]
0x18006ea5c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006ea61  lea     rdi, [rbx+1C0h]
0x18006ea68  lea     rsi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18006ea6f  mov     rcx, [rdi]; Block
0x18006ea72  cmp     rcx, rdi
0x18006ea75  jz      short loc_18006EA8F
0x18006ea77  mov     rdx, [rcx+8]
0x18006ea7b  mov     rax, [rcx]
0x18006ea7e  mov     [rdx], rax
0x18006ea81  mov     [rax+8], rdx
0x18006ea85  mov     rdx, rsi
0x18006ea88  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006ea8d  jmp     short loc_18006EA6F
0x18006ea8f  mov     rcx, rdi
0x18006ea92  mov     [rdi+18h], r14
0x18006ea96  call    ?_FreeBuckets@?$_HashTable@W4RmResourceSetType@@U?$pair@$$CBW4RmResourceSetType@@K@utl@@U?$hash@W4RmResourceSetType@@@3@U?$equal_to@W4RmResourceSetType@@@3@V?$allocator@U?$pair@$$CBW4RmResourceSetType@@K@utl@@@3@$0A@@utl@@AEAAXXZ; utl::_HashTable<RmResourceSetType,utl::pair<RmResourceSetType const,ulong>,utl::hash<RmResourceSetType>,utl::equal_to<RmResourceSetType>,utl::allocator<utl::pair<RmResourceSetType const,ulong>>,0>::_FreeBuckets(void)
0x18006ea9b  lea     rdi, [rbx+198h]
0x18006eaa2  mov     rdx, [rdi]
0x18006eaa5  cmp     rdx, rdi
0x18006eaa8  jz      short loc_18006EABF
0x18006eaaa  mov     rcx, [rdx+8]
0x18006eaae  mov     rax, [rdx]
0x18006eab1  mov     [rcx], rax
0x18006eab4  mov     [rax+8], rcx
0x18006eab8  call    ??$_DeleteNode@U?$_HashNode@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@K@utl@@@utl@@@?$_ContainerBase@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@K@utl@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@K@utl@@@2@@utl@@IEAAXPEAU?$_HashNode@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@K@utl@@@1@@Z; utl::_ContainerBase<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ulong>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ulong>>>::_DeleteNode<utl::_HashNode<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ulong>>>(utl::_HashNode<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ulong>> *)
0x18006eabd  jmp     short loc_18006EAA2
0x18006eabf  mov     rcx, rdi
0x18006eac2  mov     [rdi+18h], r14
0x18006eac6  call    ?_FreeBuckets@?$_HashTable@W4RmResourceSetType@@U?$pair@$$CBW4RmResourceSetType@@K@utl@@U?$hash@W4RmResourceSetType@@@3@U?$equal_to@W4RmResourceSetType@@@3@V?$allocator@U?$pair@$$CBW4RmResourceSetType@@K@utl@@@3@$0A@@utl@@AEAAXXZ; utl::_HashTable<RmResourceSetType,utl::pair<RmResourceSetType const,ulong>,utl::hash<RmResourceSetType>,utl::equal_to<RmResourceSetType>,utl::allocator<utl::pair<RmResourceSetType const,ulong>>,0>::_FreeBuckets(void)
0x18006eacb  lea     rdi, [rbx+170h]
0x18006ead2  mov     rdx, [rdi]
0x18006ead5  cmp     rdx, rdi
0x18006ead8  jz      short loc_18006EAEF
0x18006eada  mov     rcx, [rdx+8]
0x18006eade  mov     rax, [rdx]
0x18006eae1  mov     [rcx], rax
0x18006eae4  mov     [rax+8], rcx
0x18006eae8  call    ??$_DeleteNode@U?$_HashNode@U?$pair@$$CB_KV?$ComPtr@VBmHostInfo@Execution@@@WRL@Microsoft@@@utl@@@utl@@@?$_ContainerBase@U?$pair@$$CB_KV?$ComPtr@VBmHostInfo@Execution@@@WRL@Microsoft@@@utl@@V?$allocator@U?$pair@$$CB_KV?$ComPtr@VBmHostInfo@Execution@@@WRL@Microsoft@@@utl@@@2@@utl@@IEAAXPEAU?$_HashNode@U?$pair@$$CB_KV?$ComPtr@VBmHostInfo@Execution@@@WRL@Microsoft@@@utl@@@1@@Z; utl::_ContainerBase<utl::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<Execution::BmHostInfo>>,utl::allocator<utl::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<Execution::BmHostInfo>>>>::_DeleteNode<utl::_HashNode<utl::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<Execution::BmHostInfo>>>>(utl::_HashNode<utl::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<Execution::BmHostInfo>>> *)
0x18006eaed  jmp     short loc_18006EAD2
0x18006eaef  mov     rcx, rdi
0x18006eaf2  mov     [rdi+18h], r14
0x18006eaf6  call    ?_FreeBuckets@?$_HashTable@W4RmResourceSetType@@U?$pair@$$CBW4RmResourceSetType@@K@utl@@U?$hash@W4RmResourceSetType@@@3@U?$equal_to@W4RmResourceSetType@@@3@V?$allocator@U?$pair@$$CBW4RmResourceSetType@@K@utl@@@3@$0A@@utl@@AEAAXXZ; utl::_HashTable<RmResourceSetType,utl::pair<RmResourceSetType const,ulong>,utl::hash<RmResourceSetType>,utl::equal_to<RmResourceSetType>,utl::allocator<utl::pair<RmResourceSetType const,ulong>>,0>::_FreeBuckets(void)
0x18006eafb  mov     rcx, rbp; lpCriticalSection
0x18006eafe  call    cs:__imp_DeleteCriticalSection
0x18006eb04  lea     rcx, [rbx+0F0h]
0x18006eb0b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006eb10  lea     rcx, [rbx+0E8h]
0x18006eb17  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006eb1c  lea     rdi, [rbx+0C0h]
0x18006eb23  mov     rcx, [rdi]; Block
0x18006eb26  cmp     rcx, rdi
0x18006eb29  jz      short loc_18006EB43
0x18006eb2b  mov     rdx, [rcx+8]
0x18006eb2f  mov     rax, [rcx]
0x18006eb32  mov     [rdx], rax
0x18006eb35  mov     [rax+8], rdx
0x18006eb39  mov     rdx, rsi
0x18006eb3c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006eb41  jmp     short loc_18006EB23
0x18006eb43  mov     rcx, rdi
0x18006eb46  mov     [rdi+18h], r14
0x18006eb4a  call    ?_FreeBuckets@?$_HashTable@W4RmResourceSetType@@U?$pair@$$CBW4RmResourceSetType@@K@utl@@U?$hash@W4RmResourceSetType@@@3@U?$equal_to@W4RmResourceSetType@@@3@V?$allocator@U?$pair@$$CBW4RmResourceSetType@@K@utl@@@3@$0A@@utl@@AEAAXXZ; utl::_HashTable<RmResourceSetType,utl::pair<RmResourceSetType const,ulong>,utl::hash<RmResourceSetType>,utl::equal_to<RmResourceSetType>,utl::allocator<utl::pair<RmResourceSetType const,ulong>>,0>::_FreeBuckets(void)
0x18006eb4f  lea     rdi, [rbx+98h]
0x18006eb56  mov     rcx, [rdi]; Block
0x18006eb59  cmp     rcx, rdi
0x18006eb5c  jz      short loc_18006EB76
0x18006eb5e  mov     rdx, [rcx+8]
0x18006eb62  mov     rax, [rcx]
0x18006eb65  mov     [rdx], rax
0x18006eb68  mov     [rax+8], rdx
0x18006eb6c  mov     rdx, rsi
0x18006eb6f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006eb74  jmp     short loc_18006EB56
0x18006eb76  mov     rcx, rdi
0x18006eb79  mov     [rdi+18h], r14
0x18006eb7d  call    ?_FreeBuckets@?$_HashTable@W4RmResourceSetType@@U?$pair@$$CBW4RmResourceSetType@@K@utl@@U?$hash@W4RmResourceSetType@@@3@U?$equal_to@W4RmResourceSetType@@@3@V?$allocator@U?$pair@$$CBW4RmResourceSetType@@K@utl@@@3@$0A@@utl@@AEAAXXZ; utl::_HashTable<RmResourceSetType,utl::pair<RmResourceSetType const,ulong>,utl::hash<RmResourceSetType>,utl::equal_to<RmResourceSetType>,utl::allocator<utl::pair<RmResourceSetType const,ulong>>,0>::_FreeBuckets(void)
0x18006eb82  lea     rdi, [rbx+70h]
0x18006eb86  mov     rdx, [rdi]
0x18006eb89  cmp     rdx, rdi
0x18006eb8c  jz      short loc_18006EBA3
0x18006eb8e  mov     rcx, [rdx+8]
0x18006eb92  mov     rax, [rdx]
0x18006eb95  mov     [rcx], rax
0x18006eb98  mov     [rax+8], rcx
0x18006eb9c  call    ??$_DeleteNode@U?$_HashNode@U?$pair@$$CBU_GUID@@V?$ComPtr@VBmTaskInstance@Execution@@@WRL@Microsoft@@@utl@@@utl@@@?$_ContainerBase@U?$pair@$$CBU_GUID@@V?$ComPtr@VBmTaskInstance@Execution@@@WRL@Microsoft@@@utl@@V?$allocator@U?$pair@$$CBU_GUID@@V?$ComPtr@VBmTaskInstance@Execution@@@WRL@Microsoft@@@utl@@@2@@utl@@IEAAXPEAU?$_HashNode@U?$pair@$$CBU_GUID@@V?$ComPtr@VBmTaskInstance@Execution@@@WRL@Microsoft@@@utl@@@1@@Z; utl::_ContainerBase<utl::pair<_GUID const,Microsoft::WRL::ComPtr<Execution::BmTaskInstance>>,utl::allocator<utl::pair<_GUID const,Microsoft::WRL::ComPtr<Execution::BmTaskInstance>>>>::_DeleteNode<utl::_HashNode<utl::pair<_GUID const,Microsoft::WRL::ComPtr<Execution::BmTaskInstance>>>>(utl::_HashNode<utl::pair<_GUID const,Microsoft::WRL::ComPtr<Execution::BmTaskInstance>>> *)
0x18006eba1  jmp     short loc_18006EB86
0x18006eba3  mov     rcx, rdi
0x18006eba6  mov     [rdi+18h], r14
0x18006ebaa  call    ?_FreeBuckets@?$_HashTable@W4RmResourceSetType@@U?$pair@$$CBW4RmResourceSetType@@K@utl@@U?$hash@W4RmResourceSetType@@@3@U?$equal_to@W4RmResourceSetType@@@3@V?$allocator@U?$pair@$$CBW4RmResourceSetType@@K@utl@@@3@$0A@@utl@@AEAAXXZ; utl::_HashTable<RmResourceSetType,utl::pair<RmResourceSetType const,ulong>,utl::hash<RmResourceSetType>,utl::equal_to<RmResourceSetType>,utl::allocator<utl::pair<RmResourceSetType const,ulong>>,0>::_FreeBuckets(void)
0x18006ebaf  mov     rcx, [rbx+68h]
0x18006ebb3  test    rcx, rcx
0x18006ebb6  jz      short loc_18006EBC8
0x18006ebb8  mov     [rbx+68h], r14
0x18006ebbc  mov     rax, [rcx]
0x18006ebbf  mov     rax, [rax+10h]
0x18006ebc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ebc8  lea     rcx, [rbx+60h]
0x18006ebcc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006ebd1  mov     rcx, rbx
0x18006ebd4  add     rsp, 20h
0x18006ebd8  pop     r14
0x18006ebda  pop     rdi
0x18006ebdb  pop     rsi
0x18006ebdc  pop     rbp
0x18006ebdd  pop     rbx
0x18006ebde  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIBackgroundManager@Execution@@UIBackgroundManagerInitialize@5@UIBackgroundManagerInternal@5@UIBackgroundManagerControl@@UIBackgroundManagerControl2@@UIBackgroundManagerControl3@@UIThreadPoolCallback@@UIBackgroundManagerSessionCallbackHandler@5@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Execution::IBackgroundManager,Execution::IBackgroundManagerInitialize,Execution::IBackgroundManagerInternal,IBackgroundManagerControl,IBackgroundManagerControl2,IBackgroundManagerControl3,IThreadPoolCallback,Execution::IBackgroundManagerSessionCallbackHandler>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Execution::IBackgroundManager,Execution::IBackgroundManagerInitialize,Execution::IBackgroundManagerInternal,IBackgroundManagerControl,IBackgroundManagerControl2,IBackgroundManagerControl3,IThreadPoolCallback,Execution::IBackgroundManagerSessionCallbackHandler>(void)
```
