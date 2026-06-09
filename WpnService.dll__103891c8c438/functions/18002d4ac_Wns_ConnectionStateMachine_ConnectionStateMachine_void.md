# Wns::ConnectionStateMachine::~ConnectionStateMachine(void)

- ea: `0x18002d4ac`
- end: `0x18002d50f`
- name: `??1ConnectionStateMachine@Wns@@QEAA@XZ`
- size: `99`
- prototype: `void __fastcall(Wns::ConnectionStateMachine *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002d484`

## callees

- `0x180016684`
- `0x1800200f4`
- `0x180020110`
- `0x180024c5c`
- `0x18002d35c`
- `0x18002d3ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002d508`

## pseudocode

```c
void __fastcall Wns::ConnectionStateMachine::~ConnectionStateMachine(Wns::ConnectionStateMachine *this)
{
  struct wil::details::wnf_subscription_state_base *v2; // rdx
  void *v3; // rdx
  void *v4; // rdx

  wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>((_QWORD *)this + 52);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void DeleteWakeTimer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void DeleteWakeTimer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)this + 50);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(
    (wil::details **)this + 47,
    v2);
  std::unique_ptr<Wns::ConnectionProviderLoader>::~unique_ptr<Wns::ConnectionProviderLoader>((__int64 (__fastcall ****)(_QWORD, __int64))this + 46);
  Wns::CPTransactionRequestManager::~CPTransactionRequestManager((Wns::ConnectionStateMachine *)((char *)this + 64));
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    (wil::details **)this + 7,
    v3);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    (wil::details **)this + 6,
    v4);
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x18002d4ac  push    rbx
0x18002d4ae  sub     rsp, 20h
0x18002d4b2  mov     rbx, rcx
0x18002d4b5  add     rcx, 1A0h
0x18002d4bc  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(void)
0x18002d4c1  lea     rcx, [rbx+190h]
0x18002d4c8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?DeleteWakeTimer@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&DeleteWakeTimer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&DeleteWakeTimer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002d4cd  lea     rcx, [rbx+178h]
0x18002d4d4  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x18002d4d9  lea     rcx, [rbx+170h]
0x18002d4e0  call    ??1?$unique_ptr@VConnectionProviderLoader@Wns@@U?$default_delete@VConnectionProviderLoader@Wns@@@std@@@std@@QEAA@XZ; std::unique_ptr<Wns::ConnectionProviderLoader>::~unique_ptr<Wns::ConnectionProviderLoader>(void)
0x18002d4e5  lea     rcx, [rbx+40h]; this
0x18002d4e9  call    ??1CPTransactionRequestManager@Wns@@QEAA@XZ; Wns::CPTransactionRequestManager::~CPTransactionRequestManager(void)
0x18002d4ee  lea     rcx, [rbx+38h]
0x18002d4f2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002d4f7  lea     rcx, [rbx+30h]
0x18002d4fb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002d500  mov     rcx, rbx
0x18002d503  add     rsp, 20h
0x18002d507  pop     rbx
0x18002d508  jmp     cs:__imp_DeleteCriticalSection
```
