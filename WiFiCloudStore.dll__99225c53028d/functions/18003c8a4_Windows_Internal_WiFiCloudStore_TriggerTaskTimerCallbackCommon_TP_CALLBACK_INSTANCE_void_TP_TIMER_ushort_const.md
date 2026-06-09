# Windows::Internal::WiFiCloudStore::TriggerTaskTimerCallbackCommon(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *,ushort const *)

- ea: `0x18003c8a4`
- end: `0x18003c935`
- name: `?TriggerTaskTimerCallbackCommon@WiFiCloudStore@Internal@Windows@@YAJPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@PEBG@Z`
- size: `145`
- prototype: `__int64 __fastcall(Windows::Internal::WiFiCloudStore *this, struct _TP_CALLBACK_INSTANCE *, void *, OLECHAR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003c940`

## callees

- `0x18002477c`
- `0x18002931c`
- `0x18003c884`
- `0x18003c8a4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x18003c8b6`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x18003c8b6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003c90e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003c916`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003c90e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003c916`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18003c8c0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18003c8c0`

## string_xrefs

- `0x18003c8d1`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`
- `0x18003c8fa`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::WiFiCloudStore::TriggerTaskTimerCallbackCommon(
        Windows::Internal::WiFiCloudStore *this,
        struct _TP_CALLBACK_INSTANCE *a2,
        void *a3,
        OLECHAR *a4)
{
  HRESULT v5; // eax
  const unsigned __int16 *v6; // rdx
  unsigned int v7; // ebx
  int v8; // eax
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *v12; // [rsp+40h] [rbp+18h] BYREF

  v12 = a3;
  FreeLibraryWhenCallbackReturns(this, (HMODULE)a2);
  v5 = CoInitializeEx(0, 0);
  v7 = v5;
  if ( v5 >= 0 )
  {
    v8 = Windows::Internal::WiFiCloudStore::TriggerTask(a4, v6);
    v7 = v8;
    if ( v8 >= 0 )
    {
      CoUninitialize();
      v7 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
        (const char *)(unsigned int)v8,
        v10);
      CoUninitialize();
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
      (const char *)(unsigned int)v5,
      v10);
  }
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(&v12);
  return v7;
}

```

## disassembly

```asm
0x18003c8a4  mov     [rsp+arg_0], rbx
0x18003c8a9  push    rdi; int
0x18003c8aa  sub     rsp, 20h
0x18003c8ae  mov     rdi, r9
0x18003c8b1  mov     [rsp+28h+arg_10], r8
0x18003c8b6  call    cs:__imp_FreeLibraryWhenCallbackReturns
0x18003c8bc  xor     edx, edx; dwCoInit
0x18003c8be  xor     ecx, ecx; pvReserved
0x18003c8c0  call    cs:__imp_CoInitializeEx
0x18003c8c6  mov     ebx, eax
0x18003c8c8  test    eax, eax
0x18003c8ca  jns     short loc_18003C8E7
0x18003c8cc  mov     rcx, [rsp+28h]; this
0x18003c8d1  lea     r8, aOnecoreNetWifi_2; "onecore\\net\\wificloudstore\\registry"...
0x18003c8d8  mov     r9d, eax; char *
0x18003c8db  mov     edx, 4Fh ; 'O'; void *
0x18003c8e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c8e5  jmp     short loc_18003C91E
0x18003c8e7  mov     rcx, rdi; psz
0x18003c8ea  call    ?TriggerTask@WiFiCloudStore@Internal@Windows@@YAJPEBG@Z; Windows::Internal::WiFiCloudStore::TriggerTask(ushort const *)
0x18003c8ef  mov     ebx, eax
0x18003c8f1  test    eax, eax
0x18003c8f3  jns     short loc_18003C916
0x18003c8f5  mov     rcx, [rsp+28h]; this
0x18003c8fa  lea     r8, aOnecoreNetWifi_2; "onecore\\net\\wificloudstore\\registry"...
0x18003c901  mov     r9d, eax; char *
0x18003c904  mov     edx, 51h ; 'Q'; void *
0x18003c909  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c90e  call    cs:__imp_CoUninitialize
0x18003c914  jmp     short loc_18003C91E
0x18003c916  call    cs:__imp_CoUninitialize
0x18003c91c  xor     ebx, ebx
0x18003c91e  lea     rcx, [rsp+28h+arg_10]
0x18003c923  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
0x18003c928  mov     eax, ebx
0x18003c92a  mov     rbx, [rsp+28h+arg_0]
0x18003c92f  add     rsp, 20h
0x18003c933  pop     rdi
0x18003c934  retn
```
