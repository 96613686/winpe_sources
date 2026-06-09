# ServiceBase::~ServiceBase(void)

- ea: `0x1800200a8`
- end: `0x1800200e2`
- name: `??1ServiceBase@@UEAA@XZ`
- size: `58`
- prototype: `void __fastcall(ServiceBase *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180020068`
- `0x18002bd70`

## callees

- `0x1800200f4`
- `0x180020110`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800200ce`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800200ce`

## pseudocode

```c
void __fastcall ServiceBase::~ServiceBase(ServiceBase *this)
{
  void *v2; // rdx

  *(_QWORD *)this = &ServiceBase::`vftable';
  wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>((_QWORD *)this + 23);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    (wil::details **)this + 10,
    v2);
}

```

## disassembly

```asm
0x1800200a8  push    rbx
0x1800200aa  sub     rsp, 20h
0x1800200ae  lea     rax, ??_7ServiceBase@@6B@; const ServiceBase::`vftable'
0x1800200b5  mov     rbx, rcx
0x1800200b8  mov     [rcx], rax
0x1800200bb  add     rcx, 0B8h
0x1800200c2  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(void)
0x1800200c7  lea     rcx, [rbx+88h]; lpCriticalSection
0x1800200ce  call    cs:__imp_DeleteCriticalSection
0x1800200d4  lea     rcx, [rbx+50h]
0x1800200d8  add     rsp, 20h
0x1800200dc  pop     rbx
0x1800200dd  jmp     ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
```
