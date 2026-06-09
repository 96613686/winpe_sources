# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::ChainInterfaces<IWebRuntimeCoreHost,IOleWindow,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IWebPlatformNavigationEvents,Microsoft::WRL::ChainInterfaces<IHttpSecurity,IWindowForBindingUI,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IServiceProvider,IWebPlatformSecurityManager,IWebPlatformPermanentSecurityManager,IWebPlatformVisualViewportEvents>::QueryInterface(_GUID const &,void * *)

- ea: `0x140005780`
- end: `0x14000580f`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$ChainInterfaces@UIWebRuntimeCoreHost@@UIOleWindow@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIWebPlatformNavigationEvents@@U?$ChainInterfaces@UIHttpSecurity@@UIWindowForBindingUI@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIServiceProvider@@UIWebPlatformSecurityManager@@UIWebPlatformPermanentSecurityManager@@UIWebPlatformVisualViewportEvents@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `143`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140005820`
- `0x140005830`
- `0x140005840`
- `0x140005850`
- `0x140005860`
- `0x140005870`

## callees

- `0x140004a10`
- `0x140005590`
- `0x140005780`
- `0x140014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::ChainInterfaces<IWebRuntimeCoreHost,IOleWindow,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IWebPlatformNavigationEvents,Microsoft::WRL::ChainInterfaces<IHttpSecurity,IWindowForBindingUI,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IServiceProvider,IWebPlatformSecurityManager,IWebPlatformPermanentSecurityManager,IWebPlatformVisualViewportEvents>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        _QWORD *a3)
{
  const struct _GUID *v3; // rcx
  _QWORD *v4; // r8
  __int64 v5; // r9
  const struct _GUID *v6; // rcx
  _QWORD *v7; // r8
  __int64 v8; // r9
  __int64 v9; // r10
  int CanCastTo; // ebx

  *a3 = 0;
  if ( (unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046) )
  {
    *v4 = v5;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    return 0;
  }
  if ( (unsigned int)InlineIsEqualGUID(v3, &GUID_ed1ae000_7923_4cf0_83f9_c978b7110a11)
    || (unsigned int)InlineIsEqualGUID(v6, &GUID_00000114_0000_0000_c000_000000000046) )
  {
    *v7 = v8;
    CanCastTo = 0;
LABEL_6:
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 8LL))(*v7);
    return (unsigned int)CanCastTo;
  }
  CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IWebPlatformNavigationEvents,Microsoft::WRL::ChainInterfaces<IHttpSecurity,IWindowForBindingUI,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IServiceProvider,IWebPlatformSecurityManager,IWebPlatformPermanentSecurityManager,IWebPlatformVisualViewportEvents>::CanCastTo(
                v8 + 8,
                v9);
  if ( CanCastTo >= 0 )
    goto LABEL_6;
  return (unsigned int)CanCastTo;
}

```

## disassembly

```asm
0x140005780  push    rbx
0x140005782  sub     rsp, 20h
0x140005786  mov     r10, rdx
0x140005789  mov     r9, rcx
0x14000578c  mov     qword ptr [r8], 0
0x140005793  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x14000579a  mov     rcx, r10; struct _GUID *
0x14000579d  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x1400057a2  test    eax, eax
0x1400057a4  jnz     short loc_1400057F3
0x1400057a6  lea     rdx, _GUID_ed1ae000_7923_4cf0_83f9_c978b7110a11; struct _GUID *
0x1400057ad  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x1400057b2  test    eax, eax
0x1400057b4  jnz     short loc_1400057C6
0x1400057b6  lea     rdx, _GUID_00000114_0000_0000_c000_000000000046; struct _GUID *
0x1400057bd  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x1400057c2  test    eax, eax
0x1400057c4  jz      short loc_1400057D0
0x1400057c6  mov     rax, r8
0x1400057c9  mov     [rax], r9
0x1400057cc  xor     ebx, ebx
0x1400057ce  jmp     short loc_1400057E2
0x1400057d0  lea     rcx, [r9+8]
0x1400057d4  mov     rdx, r10
0x1400057d7  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIWebPlatformNavigationEvents@@U?$ChainInterfaces@UIHttpSecurity@@UIWindowForBindingUI@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIServiceProvider@@UIWebPlatformSecurityManager@@UIWebPlatformPermanentSecurityManager@@UIWebPlatformVisualViewportEvents@@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IWebPlatformNavigationEvents,Microsoft::WRL::ChainInterfaces<IHttpSecurity,IWindowForBindingUI,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IServiceProvider,IWebPlatformSecurityManager,IWebPlatformPermanentSecurityManager,IWebPlatformVisualViewportEvents>::CanCastTo(_GUID const &,void * *,bool *)
0x1400057dc  mov     ebx, eax
0x1400057de  test    eax, eax
0x1400057e0  js      short loc_140005807
0x1400057e2  mov     rcx, [r8]
0x1400057e5  mov     rax, [rcx]
0x1400057e8  mov     rax, [rax+8]
0x1400057ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400057f1  jmp     short loc_140005807
0x1400057f3  mov     [r8], r9
0x1400057f6  mov     rax, [r9]
0x1400057f9  mov     rcx, r9
0x1400057fc  mov     rax, [rax+8]
0x140005800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005805  xor     ebx, ebx
0x140005807  mov     eax, ebx
0x140005809  add     rsp, 20h
0x14000580d  pop     rbx
0x14000580e  retn
```
