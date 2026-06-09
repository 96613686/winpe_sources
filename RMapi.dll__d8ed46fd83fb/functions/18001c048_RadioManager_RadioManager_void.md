# RadioManager::~RadioManager(void)

- ea: `0x18001c048`
- end: `0x18001c20c`
- name: `??1RadioManager@@UEAA@XZ`
- size: `452`
- prototype: `void __fastcall(RadioManager *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d9d0`

## callees

- `0x1800075d4`
- `0x1800085e4`
- `0x18000a470`
- `0x18000a6a0`
- `0x18000c010`
- `0x180011944`
- `0x180019f9c`
- `0x18001bff0`
- `0x18001c018`
- `0x18001c048`
- `0x18002056c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c0fd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c1df`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c0fd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c1df`

## pseudocode

```c
void __fastcall RadioManager::~RadioManager(RadioManager *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx

  *(_QWORD *)this = &RadioManager::`vftable';
  *((_QWORD *)this + 1) = &RadioManager::`vftable'{for `IConnectionPoint'};
  *((_QWORD *)this + 2) = &RadioManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IUIRadioManager,IUIRadioManager2,IUIRadioManagerInternal>'};
  *((_QWORD *)this + 3) = &RadioManager::`vftable'{for `IUIRadioManager2'};
  *((_QWORD *)this + 4) = &RadioManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IUIRadioManagerInternal>'};
  RadioManager::_Cleanup(this);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>((char *)this + 720);
  WcmCommon::ThreadPoolWorkQueue::~ThreadPoolWorkQueue((RadioManager *)((char *)this + 440));
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>((char *)this + 432);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>((char *)this + 416);
  v2 = *((_QWORD *)this + 49);
  if ( v2 )
  {
    std::_Deallocate<16>(v2, (*((_QWORD *)this + 51) - v2) & 0xFFFFFFFFFFFFFFF0uLL);
    *((_QWORD *)this + 49) = 0;
    *((_QWORD *)this + 50) = 0;
    *((_QWORD *)this + 51) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 352));
  v3 = *((_QWORD *)this + 41);
  if ( v3 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<AdviseInstance>>>(v3, *((_QWORD *)this + 42));
    std::_Deallocate<16>(
      *((_QWORD *)this + 41),
      (*((_QWORD *)this + 43) - *((_QWORD *)this + 41)) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 41) = 0;
    *((_QWORD *)this + 42) = 0;
    *((_QWORD *)this + 43) = 0;
  }
  v4 = *((_QWORD *)this + 38);
  if ( v4 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<RADIO_INSTANCE>>>(v4, *((_QWORD *)this + 39));
    std::_Deallocate<16>(
      *((_QWORD *)this + 38),
      (*((_QWORD *)this + 40) - *((_QWORD *)this + 38)) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 38) = 0;
    *((_QWORD *)this + 39) = 0;
    *((_QWORD *)this + 40) = 0;
  }
  v5 = *((_QWORD *)this + 35);
  if ( v5 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<MEDIA_RADIO_MANAGER>>>(v5, *((_QWORD *)this + 36));
    std::_Deallocate<16>(
      *((_QWORD *)this + 35),
      (*((_QWORD *)this + 37) - *((_QWORD *)this + 35)) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 35) = 0;
    *((_QWORD *)this + 36) = 0;
    *((_QWORD *)this + 37) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 6);
  ConnectionPointContainer::~ConnectionPointContainer((RadioManager *)((char *)this + 168));
  ProtectedSystemState::~ProtectedSystemState((RadioManager *)((char *)this + 48));
  *((_DWORD *)this + 11) = -1073741823;
}

```

## disassembly

```asm
0x18001c048  mov     [rsp+arg_0], rbx
0x18001c04d  push    rdi
0x18001c04e  sub     rsp, 20h
0x18001c052  lea     rax, ??_7RadioManager@@6B@; const RadioManager::`vftable'
0x18001c059  mov     rbx, rcx
0x18001c05c  mov     [rcx], rax
0x18001c05f  lea     rax, ??_7RadioManager@@6BIConnectionPoint@@@; const RadioManager::`vftable'{for `IConnectionPoint'}
0x18001c066  mov     [rcx+8], rax
0x18001c06a  lea     rax, ??_7RadioManager@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIUIRadioManager@@UIUIRadioManager2@@UIUIRadioManagerInternal@@@Details@WRL@Microsoft@@@; const RadioManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IUIRadioManager,IUIRadioManager2,IUIRadioManagerInternal>'}
0x18001c071  mov     [rcx+10h], rax
0x18001c075  lea     rax, ??_7RadioManager@@6BIUIRadioManager2@@@; const RadioManager::`vftable'{for `IUIRadioManager2'}
0x18001c07c  mov     [rcx+18h], rax
0x18001c080  lea     rax, ??_7RadioManager@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIUIRadioManagerInternal@@@Details@WRL@Microsoft@@@; const RadioManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IUIRadioManagerInternal>'}
0x18001c087  mov     [rcx+20h], rax
0x18001c08b  call    ?_Cleanup@RadioManager@@AEAAXXZ; RadioManager::_Cleanup(void)
0x18001c090  lea     rcx, [rbx+2D0h]
0x18001c097  call    ??1?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(void)
0x18001c09c  lea     rcx, [rbx+1B8h]; this
0x18001c0a3  call    ??1ThreadPoolWorkQueue@WcmCommon@@QEAA@XZ; WcmCommon::ThreadPoolWorkQueue::~ThreadPoolWorkQueue(void)
0x18001c0a8  lea     rcx, [rbx+1B0h]
0x18001c0af  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
0x18001c0b4  lea     rcx, [rbx+1A0h]
0x18001c0bb  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
0x18001c0c0  mov     rcx, [rbx+188h]
0x18001c0c7  xor     edi, edi
0x18001c0c9  test    rcx, rcx
0x18001c0cc  jz      short loc_18001C0F6
0x18001c0ce  mov     rdx, [rbx+198h]
0x18001c0d5  sub     rdx, rcx
0x18001c0d8  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18001c0dc  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001c0e1  mov     [rbx+188h], rdi
0x18001c0e8  mov     [rbx+190h], rdi
0x18001c0ef  mov     [rbx+198h], rdi
0x18001c0f6  lea     rcx, [rbx+160h]; lpCriticalSection
0x18001c0fd  call    cs:__imp_DeleteCriticalSection
0x18001c103  mov     rcx, [rbx+148h]
0x18001c10a  test    rcx, rcx
0x18001c10d  jz      short loc_18001C14A
0x18001c10f  mov     rdx, [rbx+150h]
0x18001c116  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VAdviseInstance@@U?$default_delete@VAdviseInstance@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VAdviseInstance@@U?$default_delete@VAdviseInstance@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VAdviseInstance@@U?$default_delete@VAdviseInstance@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<AdviseInstance>>>(std::unique_ptr<AdviseInstance> *,std::unique_ptr<AdviseInstance> * const,std::allocator<std::unique_ptr<AdviseInstance>> &)
0x18001c11b  mov     rcx, [rbx+148h]
0x18001c122  mov     rdx, [rbx+158h]
0x18001c129  sub     rdx, rcx
0x18001c12c  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001c130  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001c135  mov     [rbx+148h], rdi
0x18001c13c  mov     [rbx+150h], rdi
0x18001c143  mov     [rbx+158h], rdi
0x18001c14a  mov     rcx, [rbx+130h]
0x18001c151  test    rcx, rcx
0x18001c154  jz      short loc_18001C191
0x18001c156  mov     rdx, [rbx+138h]
0x18001c15d  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@URADIO_INSTANCE@@U?$default_delete@URADIO_INSTANCE@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@URADIO_INSTANCE@@U?$default_delete@URADIO_INSTANCE@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@URADIO_INSTANCE@@U?$default_delete@URADIO_INSTANCE@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<RADIO_INSTANCE>>>(std::unique_ptr<RADIO_INSTANCE> *,std::unique_ptr<RADIO_INSTANCE> * const,std::allocator<std::unique_ptr<RADIO_INSTANCE>> &)
0x18001c162  mov     rcx, [rbx+130h]
0x18001c169  mov     rdx, [rbx+140h]
0x18001c170  sub     rdx, rcx
0x18001c173  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001c177  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001c17c  mov     [rbx+130h], rdi
0x18001c183  mov     [rbx+138h], rdi
0x18001c18a  mov     [rbx+140h], rdi
0x18001c191  mov     rcx, [rbx+118h]
0x18001c198  test    rcx, rcx
0x18001c19b  jz      short loc_18001C1D8
0x18001c19d  mov     rdx, [rbx+120h]
0x18001c1a4  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@UMEDIA_RADIO_MANAGER@@U?$default_delete@UMEDIA_RADIO_MANAGER@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@UMEDIA_RADIO_MANAGER@@U?$default_delete@UMEDIA_RADIO_MANAGER@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@UMEDIA_RADIO_MANAGER@@U?$default_delete@UMEDIA_RADIO_MANAGER@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<MEDIA_RADIO_MANAGER>>>(std::unique_ptr<MEDIA_RADIO_MANAGER> *,std::unique_ptr<MEDIA_RADIO_MANAGER> * const,std::allocator<std::unique_ptr<MEDIA_RADIO_MANAGER>> &)
0x18001c1a9  mov     rcx, [rbx+118h]
0x18001c1b0  mov     rdx, [rbx+128h]
0x18001c1b7  sub     rdx, rcx
0x18001c1ba  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001c1be  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001c1c3  mov     [rbx+118h], rdi
0x18001c1ca  mov     [rbx+120h], rdi
0x18001c1d1  mov     [rbx+128h], rdi
0x18001c1d8  lea     rcx, [rbx+0F0h]; lpCriticalSection
0x18001c1df  call    cs:__imp_DeleteCriticalSection
0x18001c1e5  lea     rcx, [rbx+0A8h]; this
0x18001c1ec  call    ??1ConnectionPointContainer@@QEAA@XZ; ConnectionPointContainer::~ConnectionPointContainer(void)
0x18001c1f1  lea     rcx, [rbx+30h]; this
0x18001c1f5  call    ??1ProtectedSystemState@@QEAA@XZ; ProtectedSystemState::~ProtectedSystemState(void)
0x18001c1fa  mov     dword ptr [rbx+2Ch], 0C0000001h
0x18001c201  mov     rbx, [rsp+28h+arg_0]
0x18001c206  add     rsp, 20h
0x18001c20a  pop     rdi
0x18001c20b  retn
```
