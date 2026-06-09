# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::ChainInterfaces<IWebRuntimeCoreHost,IOleWindow,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IWebPlatformNavigationEvents,Microsoft::WRL::ChainInterfaces<IHttpSecurity,IWindowForBindingUI,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IServiceProvider,IWebPlatformSecurityManager,IWebPlatformPermanentSecurityManager,IWebPlatformVisualViewportEvents>::Release(void)

- ea: `0x140005880`
- end: `0x1400058d2`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$ChainInterfaces@UIWebRuntimeCoreHost@@UIOleWindow@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIWebPlatformNavigationEvents@@U?$ChainInterfaces@UIHttpSecurity@@UIWindowForBindingUI@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIServiceProvider@@UIWebPlatformSecurityManager@@UIWebPlatformPermanentSecurityManager@@UIWebPlatformVisualViewportEvents@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `82`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400058e0`
- `0x1400058f0`
- `0x140005900`
- `0x140005910`
- `0x140005920`
- `0x140005930`

## callees

- `0x140005880`
- `0x140005d68`
- `0x140014010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::ChainInterfaces<IWebRuntimeCoreHost,IOleWindow,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IWebPlatformNavigationEvents,Microsoft::WRL::ChainInterfaces<IHttpSecurity,IWindowForBindingUI,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IServiceProvider,IWebPlatformSecurityManager,IWebPlatformPermanentSecurityManager,IWebPlatformVisualViewportEvents>::Release(
        __int64 a1,
        volatile int *a2)
{
  unsigned int v2; // ebx
  __int64 v3; // r10

  v2 = Microsoft::WRL::Details::SafeUnknownDecrementReference((Microsoft::WRL::Details *)(a1 + 60), a2);
  if ( !v2 )
  {
    if ( v3 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 208LL))(v3, v2 + 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v2;
}

```

## disassembly

```asm
0x140005880  push    rbx
0x140005882  sub     rsp, 20h
0x140005886  mov     r10, rcx
0x140005889  add     rcx, 3Ch ; '<'; this
0x14000588d  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x140005892  mov     ebx, eax
0x140005894  test    eax, eax
0x140005896  jnz     short loc_1400058CA
0x140005898  test    r10, r10
0x14000589b  jz      short loc_1400058B2
0x14000589d  mov     rdx, [r10]
0x1400058a0  mov     rcx, r10
0x1400058a3  mov     rax, [rdx+0D0h]
0x1400058aa  lea     edx, [rbx+1]
0x1400058ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400058b2  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1400058b9  test    rcx, rcx
0x1400058bc  jz      short loc_1400058CA
0x1400058be  mov     rax, [rcx]
0x1400058c1  mov     rax, [rax+10h]
0x1400058c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400058ca  mov     eax, ebx
0x1400058cc  add     rsp, 20h
0x1400058d0  pop     rbx
0x1400058d1  retn
```
