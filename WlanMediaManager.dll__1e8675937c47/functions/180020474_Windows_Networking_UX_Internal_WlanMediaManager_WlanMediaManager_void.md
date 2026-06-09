# Windows::Networking::UX::Internal::WlanMediaManager::~WlanMediaManager(void)

- ea: `0x180020474`
- end: `0x1800205f1`
- name: `??1WlanMediaManager@Internal@UX@Networking@Windows@@UEAA@XZ`
- size: `381`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::WlanMediaManager *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000bfd0`

## callees

- `0x18000b5e0`
- `0x18000b620`
- `0x18000b658`
- `0x18000bad0`
- `0x18000bb7c`
- `0x18000bbf4`
- `0x18000d740`
- `0x180012228`
- `0x18001239c`
- `0x180013fd0`
- `0x18001cb10`
- `0x18001f5d0`
- `0x180020474`
- `0x180020a9c`
- `0x1800240b0`
- `0x180025dc4`
- `0x18007d32c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020581`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800205c4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020581`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800205c4`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::WlanMediaManager::~WlanMediaManager(
        Windows::Networking::UX::Internal::WlanMediaManager *this)
{
  Windows::Networking::UX::Internal::NlmClient *v2; // rcx
  unsigned int v3; // edx
  _QWORD *v4; // rdi
  _QWORD *i; // rbx
  Windows::Networking::UX::Internal::WlanInterface *v6; // rcx
  unsigned int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)this = &Windows::Networking::UX::Internal::WlanMediaManager::`vftable';
  *((_QWORD *)this + 1) = &Windows::Networking::UX::Internal::WlanMediaManager::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &Windows::Networking::UX::Internal::WlanMediaManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Networking::UX::IWiFiSettings,Windows::Networking::UX::Internal::IProfileManagerNotificationClient,Windows::Networking::UX::Internal::INlmListener>'};
  *((_QWORD *)this + 3) = &Windows::Networking::UX::Internal::WlanMediaManager::`vftable'{for `Windows::Networking::UX::Internal::IProfileManagerNotificationClient'};
  *((_QWORD *)this + 4) = &Windows::Networking::UX::Internal::WlanMediaManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Networking::UX::Internal::INlmListener>'};
  Windows::Networking::UX::Internal::WlanMediaManager::ImpersonateCurrentUser((__int64)this, &v14);
  v2 = (Windows::Networking::UX::Internal::NlmClient *)*((_QWORD *)this + 118);
  if ( v2 )
    Windows::Networking::UX::Internal::NlmClient::Stop(v2);
  Windows::Networking::UX::Internal::WlanMediaManager::StopAllScans(this);
  Windows::Networking::UX::Internal::WlanClient::DeInit((Windows::Networking::UX::Internal::WlanMediaManager *)((char *)this + 144));
  v4 = (_QWORD *)*((_QWORD *)this + 8);
  for ( i = (_QWORD *)*v4; i != v4; i = (_QWORD *)*i )
  {
    v6 = (Windows::Networking::UX::Internal::WlanInterface *)i[2];
    if ( v6 )
      Windows::Networking::UX::Internal::WlanInterface::`scalar deleting destructor'(v6, v3);
  }
  v7 = std::_Atomic_storage<unsigned long,4>::load((char *)this + 56);
  Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::Internal::WlanMediaManager::_WlanMediaManager_::_2_::_lambda_1___(
    v8,
    258,
    v7);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v14);
  v11 = *((_QWORD *)this + 126);
  if ( v11 )
  {
    std::_Destroy_range<std::allocator<Microsoft::WRL::WeakRef>>(v11, *((_QWORD *)this + 127), v9, v10);
    std::_Deallocate<16>(
      *((void **)this + 126),
      (struct std::nothrow_t *)((*((_QWORD *)this + 128) - *((_QWORD *)this + 126)) & 0xFFFFFFFFFFFFFFF8uLL));
    *((_QWORD *)this + 126) = 0;
    *((_QWORD *)this + 127) = 0;
    *((_QWORD *)this + 128) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 968));
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 960);
  v12 = *((_QWORD *)this + 118);
  if ( v12 )
  {
    *((_QWORD *)this + 118) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(v12);
  }
  Windows::Networking::UX::Internal::WlanClient::~WlanClient((Windows::Networking::UX::Internal::WlanMediaManager *)((char *)this + 144));
  Microsoft::WRL::EventSource<Windows::Networking::UX::IAvailableNetworkEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Networking::UX::IAvailableNetworkEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 120);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 2);
  std::_List_node<Windows::Networking::UX::Internal::WlanInterface *,void *>::_Free_non_head<std::allocator<std::_List_node<Windows::Networking::UX::Internal::WlanInterface *,void *>>>(
    v13,
    *((_QWORD *)this + 8));
  std::_Deallocate<16>(*((void **)this + 8), (struct std::nothrow_t *)0x18);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CUserInputType,Windows::Networking::UX::IWiFiWCNPinUIPrompt>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CUserInputType,Windows::Networking::UX::IWiFiWCNPinUIPrompt>(this);
}

```

## disassembly

```asm
0x180020474  push    rbx
0x180020476  push    rbp
0x180020477  push    rsi
0x180020478  push    rdi
0x180020479  sub     rsp, 28h
0x18002047d  mov     rsi, rcx
0x180020480  lea     rax, ??_7WlanMediaManager@Internal@UX@Networking@Windows@@6B@; const Windows::Networking::UX::Internal::WlanMediaManager::`vftable'
0x180020487  mov     [rcx], rax
0x18002048a  lea     rax, ??_7WlanMediaManager@Internal@UX@Networking@Windows@@6BIWeakReferenceSource@@@; const Windows::Networking::UX::Internal::WlanMediaManager::`vftable'{for `IWeakReferenceSource'}
0x180020491  mov     [rcx+8], rax
0x180020495  lea     rax, ??_7WlanMediaManager@Internal@UX@Networking@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWiFiSettings@UX@Networking@Windows@@VIProfileManagerNotificationClient@Internal@567@VINlmListener@9567@@Details@WRL@Microsoft@@@; const Windows::Networking::UX::Internal::WlanMediaManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Networking::UX::IWiFiSettings,Windows::Networking::UX::Internal::IProfileManagerNotificationClient,Windows::Networking::UX::Internal::INlmListener>'}
0x18002049c  mov     [rcx+10h], rax
0x1800204a0  lea     rax, ??_7WlanMediaManager@Internal@UX@Networking@Windows@@6BIProfileManagerNotificationClient@1234@@; const Windows::Networking::UX::Internal::WlanMediaManager::`vftable'{for `Windows::Networking::UX::Internal::IProfileManagerNotificationClient'}
0x1800204a7  mov     [rcx+18h], rax
0x1800204ab  lea     rax, ??_7WlanMediaManager@Internal@UX@Networking@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00VINlmListener@Internal@UX@Networking@Windows@@@Details@WRL@Microsoft@@@; const Windows::Networking::UX::Internal::WlanMediaManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Networking::UX::Internal::INlmListener>'}
0x1800204b2  mov     [rcx+20h], rax
0x1800204b6  lea     rdx, [rsp+48h+arg_0]
0x1800204bb  call    ?ImpersonateCurrentUser@WlanMediaManager@Internal@UX@Networking@Windows@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@XZ; Windows::Networking::UX::Internal::WlanMediaManager::ImpersonateCurrentUser(void)
0x1800204c0  mov     rcx, [rsi+3B0h]; this
0x1800204c7  test    rcx, rcx
0x1800204ca  jz      short loc_1800204D1
0x1800204cc  call    ?Stop@NlmClient@Internal@UX@Networking@Windows@@QEAAXXZ; Windows::Networking::UX::Internal::NlmClient::Stop(void)
0x1800204d1  mov     rcx, rsi; this
0x1800204d4  call    ?StopAllScans@WlanMediaManager@Internal@UX@Networking@Windows@@IEAAXXZ; Windows::Networking::UX::Internal::WlanMediaManager::StopAllScans(void)
0x1800204d9  lea     rbp, [rsi+90h]
0x1800204e0  mov     rcx, rbp; this
0x1800204e3  call    ?DeInit@WlanClient@Internal@UX@Networking@Windows@@QEAAXXZ; Windows::Networking::UX::Internal::WlanClient::DeInit(void)
0x1800204e8  mov     rdi, [rsi+40h]
0x1800204ec  mov     rbx, [rdi]
0x1800204ef  cmp     rbx, rdi
0x1800204f2  jz      short loc_180020507
0x1800204f4  mov     rcx, [rbx+10h]; this
0x1800204f8  test    rcx, rcx
0x1800204fb  jz      short loc_180020502
0x1800204fd  call    ??_GWlanInterface@Internal@UX@Networking@Windows@@QEAAPEAXI@Z; Windows::Networking::UX::Internal::WlanInterface::`scalar deleting destructor'(uint)
0x180020502  mov     rbx, [rbx]
0x180020505  jmp     short loc_1800204EF
0x180020507  lea     rcx, [rsi+38h]
0x18002050b  call    ?load@?$_Atomic_storage@K$03@std@@QEBAKW4memory_order@2@@Z; std::_Atomic_storage<ulong,4>::load(std::memory_order)
0x180020510  mov     r8d, eax
0x180020513  mov     edx, 102h
0x180020518  call    Windows__Internal__ComTaskPool__QueueTask__Windows__Networking__UX__Internal__WlanMediaManager___WlanMediaManager____2____lambda_1___
0x18002051d  lea     rcx, [rsp+48h+arg_0]
0x180020522  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180020527  mov     rcx, [rsi+3F0h]
0x18002052e  test    rcx, rcx
0x180020531  jz      short loc_18002057A
0x180020533  mov     rdx, [rsi+3F8h]
0x18002053a  call    ??$_Destroy_range@V?$allocator@VWeakRef@WRL@Microsoft@@@std@@@std@@YAXPEAVWeakRef@WRL@Microsoft@@QEAV123@AEAV?$allocator@VWeakRef@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::WeakRef>>(Microsoft::WRL::WeakRef *,Microsoft::WRL::WeakRef * const,std::allocator<Microsoft::WRL::WeakRef> &)
0x18002053f  mov     rcx, [rsi+3F0h]
0x180020546  mov     rdx, [rsi+400h]
0x18002054d  sub     rdx, rcx
0x180020550  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180020554  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180020559  mov     qword ptr [rsi+3F0h], 0
0x180020564  mov     qword ptr [rsi+3F8h], 0
0x18002056f  mov     qword ptr [rsi+400h], 0
0x18002057a  lea     rcx, [rsi+3C8h]; lpCriticalSection
0x180020581  call    cs:__imp_DeleteCriticalSection
0x180020587  lea     rcx, [rsi+3C0h]
0x18002058e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180020593  mov     rcx, [rsi+3B0h]
0x18002059a  test    rcx, rcx
0x18002059d  jz      short loc_1800205AF
0x18002059f  mov     qword ptr [rsi+3B0h], 0
0x1800205aa  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800205af  mov     rcx, rbp; this
0x1800205b2  call    ??1WlanClient@Internal@UX@Networking@Windows@@QEAA@XZ; Windows::Networking::UX::Internal::WlanClient::~WlanClient(void)
0x1800205b7  lea     rcx, [rsi+78h]
0x1800205bb  call    ??1?$EventSource@UIAvailableNetworkEventHandler@UX@Networking@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Networking::UX::IAvailableNetworkEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Networking::UX::IAvailableNetworkEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x1800205c0  lea     rcx, [rsi+50h]; lpCriticalSection
0x1800205c4  call    cs:__imp_DeleteCriticalSection
0x1800205ca  mov     rdx, [rsi+40h]
0x1800205ce  call    ??$_Free_non_head@V?$allocator@U?$_List_node@PEAVWlanInterface@Internal@UX@Networking@Windows@@PEAX@std@@@std@@@?$_List_node@PEAVWlanInterface@Internal@UX@Networking@Windows@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@PEAVWlanInterface@Internal@UX@Networking@Windows@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<Windows::Networking::UX::Internal::WlanInterface *,void *>::_Free_non_head<std::allocator<std::_List_node<Windows::Networking::UX::Internal::WlanInterface *,void *>>>(std::allocator<std::_List_node<Windows::Networking::UX::Internal::WlanInterface *,void *>> &,std::_List_node<Windows::Networking::UX::Internal::WlanInterface *,void *> *)
0x1800205d3  mov     edx, 18h
0x1800205d8  mov     rcx, [rsi+40h]
0x1800205dc  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800205e1  mov     rcx, rsi
0x1800205e4  add     rsp, 28h
0x1800205e8  pop     rdi
0x1800205e9  pop     rsi
0x1800205ea  pop     rbp
0x1800205eb  pop     rbx
0x1800205ec  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VCUserInputType@Internal@UX@Networking@Windows@@UIWiFiWCNPinUIPrompt@678@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CUserInputType,Windows::Networking::UX::IWiFiWCNPinUIPrompt>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CUserInputType,Windows::Networking::UX::IWiFiWCNPinUIPrompt>(void)
```
