# DeviceConfiguration::PrintDeviceConfigurationService::~PrintDeviceConfigurationService(void)

- ea: `0x18000ab48`
- end: `0x18000abb8`
- name: `??1PrintDeviceConfigurationService@DeviceConfiguration@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(DeviceConfiguration::PrintDeviceConfigurationService *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000ac6c`

## callees

- `0x180004ea4`
- `0x180004f08`
- `0x18000aacc`
- `0x18000ab48`
- `0x18000af54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ab88`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ab92`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ab88`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ab92`

## pseudocode

```c
void __fastcall DeviceConfiguration::PrintDeviceConfigurationService::~PrintDeviceConfigurationService(
        DeviceConfiguration::PrintDeviceConfigurationService *this)
{
  std::_Ref_count_base *v2; // rcx
  std::_Ref_count_base *v3; // rcx
  std::_Ref_count_base *v4; // rcx
  void *v5; // rdx

  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 20);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 18);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  v4 = (std::_Ref_count_base *)*((_QWORD *)this + 16);
  if ( v4 )
    std::_Ref_count_base::_Decref(v4);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 2);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>((struct _TP_TIMER **)this + 3);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int UnregisterWait(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int UnregisterWait(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((char *)this + 16);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    (wil::details **)this + 1,
    v5);
}

```

## disassembly

```asm
0x18000ab48  push    rbx
0x18000ab4a  sub     rsp, 20h
0x18000ab4e  mov     rbx, rcx
0x18000ab51  mov     rcx, [rcx+0A0h]; this
0x18000ab58  test    rcx, rcx
0x18000ab5b  jz      short loc_18000AB62
0x18000ab5d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000ab62  mov     rcx, [rbx+90h]; this
0x18000ab69  test    rcx, rcx
0x18000ab6c  jz      short loc_18000AB73
0x18000ab6e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000ab73  mov     rcx, [rbx+80h]; this
0x18000ab7a  test    rcx, rcx
0x18000ab7d  jz      short loc_18000AB84
0x18000ab7f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000ab84  lea     rcx, [rbx+50h]; lpCriticalSection
0x18000ab88  call    cs:__imp_DeleteCriticalSection
0x18000ab8e  lea     rcx, [rbx+28h]; lpCriticalSection
0x18000ab92  call    cs:__imp_DeleteCriticalSection
0x18000ab98  lea     rcx, [rbx+18h]
0x18000ab9c  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
0x18000aba1  lea     rcx, [rbx+10h]
0x18000aba5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?UnregisterWait@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&UnregisterWait(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&UnregisterWait(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000abaa  lea     rcx, [rbx+8]
0x18000abae  add     rsp, 20h
0x18000abb2  pop     rbx
0x18000abb3  jmp     ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
```
