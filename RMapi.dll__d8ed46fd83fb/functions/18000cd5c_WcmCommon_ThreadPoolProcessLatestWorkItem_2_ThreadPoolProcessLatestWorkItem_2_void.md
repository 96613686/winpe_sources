# WcmCommon::ThreadPoolProcessLatestWorkItem<2>::~ThreadPoolProcessLatestWorkItem<2>(void)

- ea: `0x18000cd5c`
- end: `0x18000cda9`
- name: `??1?$ThreadPoolProcessLatestWorkItem@$01@WcmCommon@@QEAA@XZ`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cd0c`

## callees

- `0x180008620`
- `0x18000a518`
- `0x18000c31c`
- `0x18000d2fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cda2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WcmCommon::ThreadPoolProcessLatestWorkItem<2>::~ThreadPoolProcessLatestWorkItem<2>(__int64 a1)
{
  WcmCommon::ThreadPoolProcessLatestWorkItem<2>::Cancel(a1);
  `eh vector destructor iterator'((void *)(a1 + 152), 0x40u, 2u, (void (*)(void *))std::any::~any);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(a1 + 120);
  wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>((struct _TP_POOL **)(a1 + 112));
  DeleteCriticalSection((LPCRITICAL_SECTION)a1);
}

```

## disassembly

```asm
0x18000cd5c  push    rbx
0x18000cd5e  sub     rsp, 20h
0x18000cd62  mov     rbx, rcx
0x18000cd65  call    ?Cancel@?$ThreadPoolProcessLatestWorkItem@$01@WcmCommon@@QEAAXXZ; WcmCommon::ThreadPoolProcessLatestWorkItem<2>::Cancel(void)
0x18000cd6a  nop
0x18000cd6b  lea     rcx, [rbx+98h]; void *
0x18000cd72  lea     r9, ??1any@std@@QEAA@XZ; void (*)(void *)
0x18000cd79  mov     edx, 40h ; '@'; unsigned __int64
0x18000cd7e  lea     r8d, [rdx-3Eh]; unsigned __int64
0x18000cd82  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18000cd87  nop
0x18000cd88  lea     rcx, [rbx+78h]
0x18000cd8c  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(void)
0x18000cd91  lea     rcx, [rbx+70h]
0x18000cd95  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_POOL@@P6AXPEAU1@@Z$1?CloseThreadpool@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>(void)
0x18000cd9a  mov     rcx, rbx
0x18000cd9d  add     rsp, 20h
0x18000cda1  pop     rbx
0x18000cda2  jmp     cs:__imp_DeleteCriticalSection
```
