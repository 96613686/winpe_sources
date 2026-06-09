# [thunk]:Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::ChainInterfaces<IWebRuntimeCoreHost,IOleWindow,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IWebPlatformNavigationEvents,Microsoft::WRL::ChainInterfaces<IHttpSecurity,IWindowForBindingUI,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IServiceProvider,IWebPlatformSecurityManager,IWebPlatformPermanentSecurityManager,IWebPlatformVisualViewportEvents>::QueryInterface`adjustor{40}' (_GUID const &,void * *)

- ea: `0x140005860`
- end: `0x140005869`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$ChainInterfaces@UIWebRuntimeCoreHost@@UIOleWindow@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIWebPlatformNavigationEvents@@U?$ChainInterfaces@UIHttpSecurity@@UIWindowForBindingUI@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIServiceProvider@@UIWebPlatformSecurityManager@@UIWebPlatformPermanentSecurityManager@@UIWebPlatformVisualViewportEvents@@@Details@WRL@Microsoft@@WCI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140005780`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::ChainInterfaces<IWebRuntimeCoreHost,IOleWindow,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IWebPlatformNavigationEvents,Microsoft::WRL::ChainInterfaces<IHttpSecurity,IWindowForBindingUI,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IServiceProvider,IWebPlatformSecurityManager,IWebPlatformPermanentSecurityManager,IWebPlatformVisualViewportEvents>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        _QWORD *a3)
{
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::ChainInterfaces<IWebRuntimeCoreHost,IOleWindow,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IWebPlatformNavigationEvents,Microsoft::WRL::ChainInterfaces<IHttpSecurity,IWindowForBindingUI,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IServiceProvider,IWebPlatformSecurityManager,IWebPlatformPermanentSecurityManager,IWebPlatformVisualViewportEvents>::QueryInterface(
           a1 - 40,
           a2,
           a3);
}

```

## disassembly

```asm
0x140005860  sub     rcx, 28h ; '('
0x140005864  jmp     ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$ChainInterfaces@UIWebRuntimeCoreHost@@UIOleWindow@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIWebPlatformNavigationEvents@@U?$ChainInterfaces@UIHttpSecurity@@UIWindowForBindingUI@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIServiceProvider@@UIWebPlatformSecurityManager@@UIWebPlatformPermanentSecurityManager@@UIWebPlatformVisualViewportEvents@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::ChainInterfaces<IWebRuntimeCoreHost,IOleWindow,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IWebPlatformNavigationEvents,Microsoft::WRL::ChainInterfaces<IHttpSecurity,IWindowForBindingUI,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IServiceProvider,IWebPlatformSecurityManager,IWebPlatformPermanentSecurityManager,IWebPlatformVisualViewportEvents>::QueryInterface(_GUID const &,void * *)
```
