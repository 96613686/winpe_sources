# WNFNotificationDispatcher::~WNFNotificationDispatcher(void)

- ea: `0x18000b60c`
- end: `0x18000b633`
- name: `??1WNFNotificationDispatcher@@QEAA@XZ`
- size: `39`
- prototype: `void __fastcall(WNFNotificationDispatcher *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x18000591c`

## callees

- `0x18000b5f0`
- `0x18000b910`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b62c`

## pseudocode

```c
void __fastcall WNFNotificationDispatcher::~WNFNotificationDispatcher(WNFNotificationDispatcher *this)
{
  WNFNotificationDispatcher::Shutdown(this);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>((_QWORD *)this + 8);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x18000b60c  push    rbx
0x18000b60e  sub     rsp, 20h
0x18000b612  mov     rbx, rcx
0x18000b615  call    ?Shutdown@WNFNotificationDispatcher@@QEAAXXZ; WNFNotificationDispatcher::Shutdown(void)
0x18000b61a  lea     rcx, [rbx+40h]
0x18000b61e  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(void)
0x18000b623  lea     rcx, [rbx+10h]
0x18000b627  add     rsp, 20h
0x18000b62b  pop     rbx
0x18000b62c  jmp     cs:__imp_DeleteCriticalSection
```
