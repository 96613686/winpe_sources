# CSearchPaneTypeToSearchService::CSearchPaneTypeToSearchService(void)

- ea: `0x180026e2c`
- end: `0x180026f5b`
- name: `??0CSearchPaneTypeToSearchService@@QEAA@XZ`
- size: `303`
- prototype: `CSearchPaneTypeToSearchService *__fastcall(CSearchPaneTypeToSearchService *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180026c90`

## callees

- `0x180026e0c`
- `0x180026e2c`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180026f0d`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180026f1a`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180026f0d`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180026f1a`
- `SHCORE!SHTaskPoolGetUniqueContext` at `0x180026f20`
- `SHCORE!SHTaskPoolGetUniqueContext` at `0x180026f20`

## pseudocode

```c
CSearchPaneTypeToSearchService *__fastcall CSearchPaneTypeToSearchService::CSearchPaneTypeToSearchService(
        CSearchPaneTypeToSearchService *this)
{
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CWRLObjectWithSite,IViewService,IServiceProvider,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CWRLObjectWithSite,IViewService,IServiceProvider,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>();
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CWRLObjectWithSite,IViewService,IServiceProvider,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>::`vftable'{for `Microsoft::WRL::Details::Selector<CWRLObjectWithSite,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWRLObjectWithSite>,IViewService,IServiceProvider,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>>'};
  *((_QWORD *)this + 3) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CWRLObjectWithSite,IViewService,IServiceProvider,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IViewService,IServiceProvider,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWRLObjectWithSite>,IViewService,IServiceProvider,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>>'};
  *((_QWORD *)this + 4) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CWRLObjectWithSite,IViewService,IServiceProvider,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>::`vftable'{for `IServiceProvider'};
  *((_QWORD *)this + 5) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CWRLObjectWithSite,IViewService,IServiceProvider,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>'};
  *((_QWORD *)this + 6) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CWRLObjectWithSite,IViewService,IServiceProvider,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>::`vftable'{for `IXAMLHostWindowMessageHook'};
  *((_QWORD *)this + 7) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CWRLObjectWithSite,IViewService,IServiceProvider,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IStartMenuXAMLViewService>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)this = &CSearchPaneTypeToSearchService::`vftable'{for `Microsoft::WRL::Details::Selector<CWRLObjectWithSite,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWRLObjectWithSite>,IViewService,IServiceProvider,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>>'};
  *((_QWORD *)this + 3) = &CSearchPaneTypeToSearchService::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IViewService,IServiceProvider,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWRLObjectWithSite>,IViewService,IServiceProvider,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>>'};
  *((_QWORD *)this + 4) = &CSearchPaneTypeToSearchService::`vftable'{for `IServiceProvider'};
  *((_QWORD *)this + 5) = &CSearchPaneTypeToSearchService::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>'};
  *((_QWORD *)this + 6) = &CSearchPaneTypeToSearchService::`vftable'{for `IXAMLHostWindowMessageHook'};
  *((_QWORD *)this + 7) = &CSearchPaneTypeToSearchService::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IStartMenuXAMLViewService>'};
  *((_DWORD *)this + 18) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  InitializeSRWLock((PSRWLOCK)this + 22);
  InitializeSRWLock((PSRWLOCK)this + 23);
  *((_DWORD *)this + 48) = SHTaskPoolGetUniqueContext();
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  return this;
}

```

## disassembly

```asm
0x180026e2c  mov     [rsp+arg_0], rbx
0x180026e31  push    rdi
0x180026e32  sub     rsp, 20h
0x180026e36  mov     rbx, rcx
0x180026e39  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VCWRLObjectWithSite@@UIViewService@@UIServiceProvider@@UITypeToSearch2@@UIXAMLHostWindowMessageHook@@UIStartMenuXAMLViewService@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CWRLObjectWithSite,IViewService,IServiceProvider,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CWRLObjectWithSite,IViewService,IServiceProvider,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>(void)
0x180026e3e  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VCWRLObjectWithSite@@UIViewService@@UIServiceProvider@@UITypeToSearch2@@UIXAMLHostWindowMessageHook@@UIStartMenuXAMLViewService@@@WRL@Microsoft@@6B?$Selector@VCWRLObjectWithSite@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCWRLObjectWithSite@@@Details@23@UIViewService@@UIServiceProvider@@UITypeToSearch2@@UIXAMLHostWindowMessageHook@@UIStartMenuXAMLViewService@@@Details@WRL@Microsoft@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CWRLObjectWithSite,IViewService,IServiceProvider,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>::`vftable'{for `Microsoft::WRL::Details::Selector<CWRLObjectWithSite,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWRLObjectWithSite>,IViewService,IServiceProvider,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>>'}
0x180026e45  mov     [rbx], rcx
0x180026e48  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VCWRLObjectWithSite@@UIViewService@@UIServiceProvider@@UITypeToSearch2@@UIXAMLHostWindowMessageHook@@UIStartMenuXAMLViewService@@@WRL@Microsoft@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIViewService@@UIServiceProvider@@UITypeToSearch2@@UIXAMLHostWindowMessageHook@@UIStartMenuXAMLViewService@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCWRLObjectWithSite@@@Details@23@UIViewService@@UIServiceProvider@@UITypeToSearch2@@UIXAMLHostWindowMessageHook@@UIStartMenuXAMLViewService@@@234@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CWRLObjectWithSite,IViewService,IServiceProvider,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IViewService,IServiceProvider,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWRLObjectWithSite>,IViewService,IServiceProvider,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>>'}
0x180026e4f  mov     [rbx+18h], rax
0x180026e53  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VCWRLObjectWithSite@@UIViewService@@UIServiceProvider@@UITypeToSearch2@@UIXAMLHostWindowMessageHook@@UIStartMenuXAMLViewService@@@WRL@Microsoft@@6BIServiceProvider@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CWRLObjectWithSite,IViewService,IServiceProvider,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>::`vftable'{for `IServiceProvider'}
0x180026e5a  mov     [rbx+20h], rax
0x180026e5e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VCWRLObjectWithSite@@UIViewService@@UIServiceProvider@@UITypeToSearch2@@UIXAMLHostWindowMessageHook@@UIStartMenuXAMLViewService@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UITypeToSearch2@@UIXAMLHostWindowMessageHook@@UIStartMenuXAMLViewService@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CWRLObjectWithSite,IViewService,IServiceProvider,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>'}
0x180026e65  mov     [rbx+28h], rax
0x180026e69  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VCWRLObjectWithSite@@UIViewService@@UIServiceProvider@@UITypeToSearch2@@UIXAMLHostWindowMessageHook@@UIStartMenuXAMLViewService@@@WRL@Microsoft@@6BIXAMLHostWindowMessageHook@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CWRLObjectWithSite,IViewService,IServiceProvider,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>::`vftable'{for `IXAMLHostWindowMessageHook'}
0x180026e70  mov     [rbx+30h], rax
0x180026e74  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VCWRLObjectWithSite@@UIViewService@@UIServiceProvider@@UITypeToSearch2@@UIXAMLHostWindowMessageHook@@UIStartMenuXAMLViewService@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIStartMenuXAMLViewService@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CWRLObjectWithSite,IViewService,IServiceProvider,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IStartMenuXAMLViewService>'}
0x180026e7b  mov     [rbx+38h], rax
0x180026e7f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180026e86  xor     edi, edi
0x180026e88  test    rcx, rcx
0x180026e8b  jz      short loc_180026E9A
0x180026e8d  mov     rax, [rcx]
0x180026e90  mov     rax, [rax+8]
0x180026e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e99  nop
0x180026e9a  lea     rax, ??_7CSearchPaneTypeToSearchService@@6B?$Selector@VCWRLObjectWithSite@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCWRLObjectWithSite@@@Details@23@UIViewService@@UIServiceProvider@@UITypeToSearch2@@UIXAMLHostWindowMessageHook@@UIStartMenuXAMLViewService@@@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@@; const CSearchPaneTypeToSearchService::`vftable'{for `Microsoft::WRL::Details::Selector<CWRLObjectWithSite,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWRLObjectWithSite>,IViewService,IServiceProvider,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>>'}
0x180026ea1  mov     [rbx], rax
0x180026ea4  lea     rax, ??_7CSearchPaneTypeToSearchService@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIViewService@@UIServiceProvider@@UITypeToSearch2@@UIXAMLHostWindowMessageHook@@UIStartMenuXAMLViewService@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCWRLObjectWithSite@@@Details@23@UIViewService@@UIServiceProvider@@UITypeToSearch2@@UIXAMLHostWindowMessageHook@@UIStartMenuXAMLViewService@@@234@@Details@WRL@Microsoft@@@; const CSearchPaneTypeToSearchService::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IViewService,IServiceProvider,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWRLObjectWithSite>,IViewService,IServiceProvider,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>>'}
0x180026eab  mov     [rbx+18h], rax
0x180026eaf  lea     rax, ??_7CSearchPaneTypeToSearchService@@6BIServiceProvider@@@; const CSearchPaneTypeToSearchService::`vftable'{for `IServiceProvider'}
0x180026eb6  mov     [rbx+20h], rax
0x180026eba  lea     rax, ??_7CSearchPaneTypeToSearchService@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UITypeToSearch2@@UIXAMLHostWindowMessageHook@@UIStartMenuXAMLViewService@@@Details@WRL@Microsoft@@@; const CSearchPaneTypeToSearchService::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ITypeToSearch2,IXAMLHostWindowMessageHook,IStartMenuXAMLViewService>'}
0x180026ec1  mov     [rbx+28h], rax
0x180026ec5  lea     rax, ??_7CSearchPaneTypeToSearchService@@6BIXAMLHostWindowMessageHook@@@; const CSearchPaneTypeToSearchService::`vftable'{for `IXAMLHostWindowMessageHook'}
0x180026ecc  mov     [rbx+30h], rax
0x180026ed0  lea     rax, ??_7CSearchPaneTypeToSearchService@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIStartMenuXAMLViewService@@@Details@WRL@Microsoft@@@; const CSearchPaneTypeToSearchService::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IStartMenuXAMLViewService>'}
0x180026ed7  mov     [rbx+38h], rax
0x180026edb  mov     [rbx+48h], edi
0x180026ede  mov     [rbx+50h], rdi
0x180026ee2  mov     [rbx+58h], rdi
0x180026ee6  mov     [rbx+60h], rdi
0x180026eea  mov     [rbx+90h], rdi
0x180026ef1  mov     [rbx+98h], rdi
0x180026ef8  mov     [rbx+0A0h], rdi
0x180026eff  mov     [rbx+0A8h], rdi
0x180026f06  lea     rcx, [rbx+0B0h]; SRWLock
0x180026f0d  call    cs:__imp_InitializeSRWLock
0x180026f13  lea     rcx, [rbx+0B8h]; SRWLock
0x180026f1a  call    cs:__imp_InitializeSRWLock
0x180026f20  call    cs:__imp_SHTaskPoolGetUniqueContext
0x180026f26  mov     [rbx+0C0h], eax
0x180026f2c  mov     [rbx+0C8h], rdi
0x180026f33  mov     [rbx+68h], rdi
0x180026f37  mov     [rbx+70h], rdi
0x180026f3b  mov     [rbx+78h], rdi
0x180026f3f  mov     [rbx+80h], rdi
0x180026f46  mov     [rbx+88h], rdi
0x180026f4d  mov     rax, rbx
0x180026f50  mov     rbx, [rsp+28h+arg_0]
0x180026f55  add     rsp, 20h
0x180026f59  pop     rdi
0x180026f5a  retn
```
