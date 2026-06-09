# DeviceConfiguration::WNFListener::~WNFListener(void)

- ea: `0x18000b968`
- end: `0x18000b9af`
- name: `??1WNFListener@DeviceConfiguration@@QEAA@XZ`
- size: `71`
- prototype: `void __fastcall(DeviceConfiguration::WNFListener *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000ba14`

## callees

- `0x18000af54`
- `0x18000b94c`
- `0x18000b968`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b975`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b975`

## pseudocode

```c
void __fastcall DeviceConfiguration::WNFListener::~WNFListener(DeviceConfiguration::WNFListener *this)
{
  struct wil::details::wnf_subscription_state_base *v2; // rdx
  struct wil::details::wnf_subscription_state_base *v3; // rdx
  std::_Ref_count_base *v4; // rcx
  std::_Ref_count_base *v5; // rcx

  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(
    (wil::details **)this + 5,
    v2);
  v4 = (std::_Ref_count_base *)*((_QWORD *)this + 4);
  if ( v4 )
    std::_Ref_count_base::_Decref(v4);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(
    (wil::details **)this + 2,
    v3);
  v5 = (std::_Ref_count_base *)*((_QWORD *)this + 1);
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
}

```

## disassembly

```asm
0x18000b968  push    rbx
0x18000b96a  sub     rsp, 20h
0x18000b96e  mov     rbx, rcx
0x18000b971  add     rcx, 30h ; '0'; lpCriticalSection
0x18000b975  call    cs:__imp_DeleteCriticalSection
0x18000b97b  lea     rcx, [rbx+28h]
0x18000b97f  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x18000b984  mov     rcx, [rbx+20h]; this
0x18000b988  test    rcx, rcx
0x18000b98b  jz      short loc_18000B992
0x18000b98d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000b992  lea     rcx, [rbx+10h]
0x18000b996  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x18000b99b  mov     rcx, [rbx+8]; this
0x18000b99f  test    rcx, rcx
0x18000b9a2  jz      short loc_18000B9A9
0x18000b9a4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000b9a9  add     rsp, 20h
0x18000b9ad  pop     rbx
0x18000b9ae  retn
```
