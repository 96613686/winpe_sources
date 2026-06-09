# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::ChainInterfaces<IWebRuntimeCoreHost,IOleWindow,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IWebPlatformNavigationEvents,Microsoft::WRL::ChainInterfaces<IHttpSecurity,IWindowForBindingUI,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IServiceProvider,IWebPlatformSecurityManager,IWebPlatformPermanentSecurityManager,IWebPlatformVisualViewportEvents>::`vector deleting destructor'(uint)

- ea: `0x140004930`
- end: `0x140004953`
- name: `??_E?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ChainInterfaces@UIWebRuntimeCoreHost@@UIOleWindow@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIWebPlatformNavigationEvents@@U?$ChainInterfaces@UIHttpSecurity@@UIWindowForBindingUI@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIServiceProvider@@UIWebPlatformSecurityManager@@UIWebPlatformPermanentSecurityManager@@UIWebPlatformVisualViewportEvents@@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x140004930`
- `0x140012d4c`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::ChainInterfaces<IWebRuntimeCoreHost,IOleWindow,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IWebPlatformNavigationEvents,Microsoft::WRL::ChainInterfaces<IHttpSecurity,IWindowForBindingUI,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IServiceProvider,IWebPlatformSecurityManager,IWebPlatformPermanentSecurityManager,IWebPlatformVisualViewportEvents>::`vector deleting destructor'(
        _DWORD *a1,
        char a2)
{
  a1[15] = -1073741823;
  if ( (a2 & 1) != 0 )
    Common::GlobalHeap::Free(a1);
  return a1;
}

```

## disassembly

```asm
0x140004930  push    rbx
0x140004932  sub     rsp, 20h
0x140004936  mov     rbx, rcx
0x140004939  mov     dword ptr [rcx+3Ch], 0C0000001h
0x140004940  test    dl, 1
0x140004943  jz      short loc_14000494A
0x140004945  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x14000494a  mov     rax, rbx
0x14000494d  add     rsp, 20h
0x140004951  pop     rbx
0x140004952  retn
```
