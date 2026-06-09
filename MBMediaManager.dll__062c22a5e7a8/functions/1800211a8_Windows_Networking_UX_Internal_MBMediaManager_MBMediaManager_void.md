# Windows::Networking::UX::Internal::MBMediaManager::~MBMediaManager(void)

- ea: `0x1800211a8`
- end: `0x180021307`
- name: `??1MBMediaManager@Internal@UX@Networking@Windows@@UEAA@XZ`
- size: `351`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::MBMediaManager *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800328a0`

## callees

- `0x180003920`
- `0x18000bde0`
- `0x18000fde0`
- `0x18000fe58`
- `0x1800211a8`
- `0x180021310`
- `0x180021408`
- `0x180022a1c`
- `0x180022d08`
- `0x180022e9c`
- `0x180022ecc`
- `0x180023058`
- `0x18002d20c`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800212f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800212f1`
- `SHCORE!SHTaskPoolQueueTask` at `0x180021289`
- `SHCORE!SHTaskPoolQueueTask` at `0x180021289`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x1800211fb`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x1800211fb`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::MBMediaManager::~MBMediaManager(
        Windows::Networking::UX::Internal::MBMediaManager *this)
{
  Windows::Networking::UX::Internal::NlmClient *v2; // rcx
  unsigned int v3; // ebp
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rax
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  __int64 v7; // rcx
  struct _RTL_CRITICAL_SECTION *v8; // [rsp+60h] [rbp+8h] BYREF

  *(_QWORD *)this = &Windows::Networking::UX::Internal::MBMediaManager::`vftable';
  *((_QWORD *)this + 8) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Networking::UX::Internal::MediaManagerBase,Windows::Networking::UX::Internal::INlmListener>::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 9) = &Windows::Networking::UX::Internal::MBMediaManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Networking::UX::Internal::INlmListener>'};
  MBSettingUXLogging::Warn(
    "Windows::Networking::UX::Internal::MBMediaManager::~MBMediaManager",
    0x19u,
    "Destroying MBMM [%p]",
    this);
  if ( *((_QWORD *)this + 21) )
  {
    UnsubscribeServiceChangeNotifications();
    *((_QWORD *)this + 21) = 0;
  }
  Windows::Networking::UX::Internal::MBMediaManager::_StopListeningToWwanRpc(this);
  v2 = (Windows::Networking::UX::Internal::NlmClient *)*((_QWORD *)this + 18);
  if ( v2 )
    Windows::Networking::UX::Internal::NlmClient::Stop(v2);
  v3 = *((_DWORD *)this + 24);
  v4 = 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  v8 = v5;
  if ( v5 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(v5);
    v6->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&off_18005C3D8;
    v4 = v6;
    v8 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator_Windows::Networking::UX::Internal::WorkThreadHelper::CTaskWrapper__Windows::Networking::UX::Internal::MBStateMachine::PostMediaEvent_::_2_::_lambda_1_____::_MakeAllocator_Windows::Networking::UX::Internal::WorkThreadHelper::CTaskWrapper__Windows::Networking::UX::Internal::MBStateMachine::PostMediaEvent_::_2_::_lambda_1_____(&v8);
  SHTaskPoolQueueTask(0, 290, v3, 0, v4, 0);
  if ( v4 )
    ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v4->DebugInfo->ProcessLocksList.Flink)(v4);
  wil::EnterCriticalSection(&v8, (char *)this + 104);
  Windows::Networking::UX::Internal::MBMediaManager::_RemoveAllCategories(this);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v8);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>((char *)this + 152);
  v7 = *((_QWORD *)this + 18);
  if ( v7 )
  {
    *((_QWORD *)this + 18) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(v7);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Networking::UX::Internal::MediaManagerBase,Windows::Networking::UX::Internal::INlmListener>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Networking::UX::Internal::MediaManagerBase,Windows::Networking::UX::Internal::INlmListener>(this);
}

```

## disassembly

```asm
0x1800211a8  push    rbx
0x1800211aa  push    rbp
0x1800211ab  push    rsi
0x1800211ac  push    rdi
0x1800211ad  sub     rsp, 38h
0x1800211b1  mov     rdi, rcx
0x1800211b4  lea     rax, ??_7MBMediaManager@Internal@UX@Networking@Windows@@6B@; const Windows::Networking::UX::Internal::MBMediaManager::`vftable'
0x1800211bb  mov     [rcx], rax
0x1800211be  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VMediaManagerBase@Internal@UX@Networking@Windows@@VINlmListener@5678@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Networking::UX::Internal::MediaManagerBase,Windows::Networking::UX::Internal::INlmListener>::`vftable'{for `IWeakReferenceSource'}
0x1800211c5  mov     [rcx+40h], rax
0x1800211c9  lea     rax, ??_7MBMediaManager@Internal@UX@Networking@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00VINlmListener@Internal@UX@Networking@Windows@@@Details@WRL@Microsoft@@@; const Windows::Networking::UX::Internal::MBMediaManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Networking::UX::Internal::INlmListener>'}
0x1800211d0  mov     [rcx+48h], rax
0x1800211d4  mov     r9, rcx
0x1800211d7  lea     r8, aDestroyingMbmm; "Destroying MBMM [%p]"
0x1800211de  mov     edx, 19h; unsigned int
0x1800211e3  lea     rcx, aWindowsNetwork_157; "Windows::Networking::UX::Internal::MBMe"...
0x1800211ea  call    ?Warn@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Warn(char const *,ulong,char const *,...)
0x1800211ef  mov     rcx, [rdi+0A8h]
0x1800211f6  test    rcx, rcx
0x1800211f9  jz      short loc_18002120C
0x1800211fb  call    cs:__imp_UnsubscribeServiceChangeNotifications
0x180021201  mov     qword ptr [rdi+0A8h], 0
0x18002120c  mov     rcx, rdi; this
0x18002120f  call    ?_StopListeningToWwanRpc@MBMediaManager@Internal@UX@Networking@Windows@@AEAAXXZ; Windows::Networking::UX::Internal::MBMediaManager::_StopListeningToWwanRpc(void)
0x180021214  mov     rcx, [rdi+90h]; this
0x18002121b  test    rcx, rcx
0x18002121e  jz      short loc_180021225
0x180021220  call    ?Stop@NlmClient@Internal@UX@Networking@Windows@@QEAAXXZ; Windows::Networking::UX::Internal::NlmClient::Stop(void)
0x180021225  mov     ebp, [rdi+60h]
0x180021228  xor     ebx, ebx
0x18002122a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180021231  lea     ecx, [rbx+18h]; unsigned __int64
0x180021234  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180021239  mov     rsi, rax
0x18002123c  mov     [rsp+58h+arg_0], rax
0x180021241  test    rax, rax
0x180021244  jz      short loc_180021264
0x180021246  mov     rcx, rax
0x180021249  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(void)
0x18002124e  lea     rax, off_18005C3D8
0x180021255  mov     [rsi], rax
0x180021258  mov     rbx, rsi
0x18002125b  mov     [rsp+58h+arg_0], 0
0x180021264  lea     rcx, [rsp+58h+arg_0]
0x180021269  call    Microsoft__WRL__Details__MakeAllocator_Windows__Networking__UX__Internal__WorkThreadHelper__CTaskWrapper__Windows__Networking__UX__Internal__MBStateMachine__PostMediaEvent____2____lambda_1________MakeAllocator_Windows__Networking__UX__Internal__WorkThreadHelper__CTaskWrapper__Windows__Networking__UX__Internal__MBStateMachine__PostMediaEvent____2____lambda_1_____
0x18002126e  mov     [rsp+58h+var_30], 0
0x180021277  mov     [rsp+58h+var_38], rbx
0x18002127c  xor     r9d, r9d
0x18002127f  mov     r8d, ebp
0x180021282  mov     edx, 122h
0x180021287  xor     ecx, ecx
0x180021289  call    cs:__imp_SHTaskPoolQueueTask
0x18002128f  nop
0x180021290  test    rbx, rbx
0x180021293  jz      short loc_1800212A5
0x180021295  mov     rax, [rbx]
0x180021298  mov     rcx, rbx
0x18002129b  mov     rax, [rax+10h]
0x18002129f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212a4  nop
0x1800212a5  lea     rdx, [rdi+68h]
0x1800212a9  lea     rcx, [rsp+58h+arg_0]
0x1800212ae  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800212b3  mov     rcx, rdi
0x1800212b6  call    ?_RemoveAllCategories@MBMediaManager@Internal@UX@Networking@Windows@@AEAAXUwrite_lock_required@wil@@@Z; Windows::Networking::UX::Internal::MBMediaManager::_RemoveAllCategories(wil::write_lock_required)
0x1800212bb  lea     rcx, [rsp+58h+arg_0]
0x1800212c0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800212c5  lea     rcx, [rdi+98h]
0x1800212cc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(void)
0x1800212d1  mov     rcx, [rdi+90h]
0x1800212d8  test    rcx, rcx
0x1800212db  jz      short loc_1800212ED
0x1800212dd  mov     qword ptr [rdi+90h], 0
0x1800212e8  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)
0x1800212ed  lea     rcx, [rdi+68h]; lpCriticalSection
0x1800212f1  call    cs:__imp_DeleteCriticalSection
0x1800212f7  mov     rcx, rdi; this
0x1800212fa  add     rsp, 38h
0x1800212fe  pop     rdi
0x1800212ff  pop     rsi
0x180021300  pop     rbp
0x180021301  pop     rbx
0x180021302  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VMediaManagerBase@Internal@UX@Networking@Windows@@VINlmListener@5678@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Networking::UX::Internal::MediaManagerBase,Windows::Networking::UX::Internal::INlmListener>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Networking::UX::Internal::MediaManagerBase,Windows::Networking::UX::Internal::INlmListener>(void)
```
