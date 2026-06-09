# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CViewPositionControllerBase,IImmersiveLayoutChanges>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CViewPositionControllerBase,IImmersiveLayoutChanges>(void)

- ea: `0x1800293a4`
- end: `0x18002945b`
- name: `??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VCViewPositionControllerBase@@UIImmersiveLayoutChanges@@@WRL@Microsoft@@QEAA@XZ`
- size: `183`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180029270`

## callees

- `0x18002934c`
- `0x1800293a4`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800293de`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800293e8`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800293de`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800293e8`
- `USER32!SetRectEmpty` at `0x1800293fa`
- `USER32!SetRectEmpty` at `0x1800293fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CViewPositionControllerBase,IImmersiveLayoutChanges>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CViewPositionControllerBase,IImmersiveLayoutChanges>(
        __int64 a1)
{
  Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,CWRLObjectWithSite,IViewPositionController,Windows::Foundation::Collections::MapChangedEventHandler<HSTRING__ *,IInspectable *>>::Implements<Microsoft::WRL::RuntimeClassFlags<2>,CWRLObjectWithSite,IViewPositionController,Windows::Foundation::Collections::MapChangedEventHandler<HSTRING__ *,IInspectable *>>();
  *(_QWORD *)a1 = &CViewPositionControllerBase::`vftable';
  *(_QWORD *)(a1 + 24) = &CViewPositionControllerBase::`vftable'{for `IViewPositionController'};
  *(_QWORD *)(a1 + 32) = &CViewPositionControllerBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::Collections::MapChangedEventHandler<HSTRING__ *,IInspectable *>>'};
  *(_QWORD *)(a1 + 64) = 0;
  InitializeSRWLock((PSRWLOCK)(a1 + 72));
  InitializeSRWLock((PSRWLOCK)(a1 + 80));
  *(_QWORD *)(a1 + 96) = 0;
  SetRectEmpty((LPRECT)(a1 + 48));
  *(_QWORD *)(a1 + 88) = 0;
  *(_DWORD *)(a1 + 124) = 1;
  *(_QWORD *)a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CViewPositionControllerBase,IImmersiveLayoutChanges>::`vftable'{for `Microsoft::WRL::Details::Selector<CViewPositionControllerBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CViewPositionControllerBase>,IImmersiveLayoutChanges>>'};
  *(_QWORD *)(a1 + 24) = &CSearchPanePositionController::`vftable'{for `IViewPositionController'};
  *(_QWORD *)(a1 + 32) = &CSearchPanePositionController::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::Collections::MapChangedEventHandler<HSTRING__ *,IInspectable *>>'};
  *(_QWORD *)(a1 + 112) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CViewPositionControllerBase,IImmersiveLayoutChanges>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IImmersiveLayoutChanges>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CViewPositionControllerBase>,IImmersiveLayoutChanges>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  return a1;
}

```

## disassembly

```asm
0x1800293a4  push    rbx
0x1800293a6  sub     rsp, 20h
0x1800293aa  mov     rbx, rcx
0x1800293ad  call    ??0?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VCWRLObjectWithSite@@UIViewPositionController@@U?$MapChangedEventHandler@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,CWRLObjectWithSite,IViewPositionController,Windows::Foundation::Collections::MapChangedEventHandler<HSTRING__ *,IInspectable *>>::Implements<Microsoft::WRL::RuntimeClassFlags<2>,CWRLObjectWithSite,IViewPositionController,Windows::Foundation::Collections::MapChangedEventHandler<HSTRING__ *,IInspectable *>>(void)
0x1800293b2  lea     r9, ??_7CViewPositionControllerBase@@6B@; const CViewPositionControllerBase::`vftable'
0x1800293b9  mov     [rbx], r9
0x1800293bc  lea     rax, ??_7CViewPositionControllerBase@@6BIViewPositionController@@@; const CViewPositionControllerBase::`vftable'{for `IViewPositionController'}
0x1800293c3  mov     [rbx+18h], rax
0x1800293c7  lea     rax, ??_7CViewPositionControllerBase@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$MapChangedEventHandler@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@@; const CViewPositionControllerBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::Collections::MapChangedEventHandler<HSTRING__ *,IInspectable *>>'}
0x1800293ce  mov     [rbx+20h], rax
0x1800293d2  mov     qword ptr [rbx+40h], 0
0x1800293da  lea     rcx, [rbx+48h]; SRWLock
0x1800293de  call    cs:__imp_InitializeSRWLock
0x1800293e4  lea     rcx, [rbx+50h]; SRWLock
0x1800293e8  call    cs:__imp_InitializeSRWLock
0x1800293ee  mov     qword ptr [rbx+60h], 0
0x1800293f6  lea     rcx, [rbx+30h]; lprc
0x1800293fa  call    cs:__imp_SetRectEmpty
0x180029400  mov     qword ptr [rbx+58h], 0
0x180029408  mov     dword ptr [rbx+7Ch], 1
0x18002940f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VCViewPositionControllerBase@@UIImmersiveLayoutChanges@@@WRL@Microsoft@@6B?$Selector@VCViewPositionControllerBase@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCViewPositionControllerBase@@@Details@23@UIImmersiveLayoutChanges@@@Details@WRL@Microsoft@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CViewPositionControllerBase,IImmersiveLayoutChanges>::`vftable'{for `Microsoft::WRL::Details::Selector<CViewPositionControllerBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CViewPositionControllerBase>,IImmersiveLayoutChanges>>'}
0x180029416  mov     [rbx], rax
0x180029419  lea     rax, ??_7CSearchPanePositionController@@6BIViewPositionController@@@; const CSearchPanePositionController::`vftable'{for `IViewPositionController'}
0x180029420  mov     [rbx+18h], rax
0x180029424  lea     rax, ??_7CSearchPanePositionController@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$MapChangedEventHandler@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@@; const CSearchPanePositionController::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::Collections::MapChangedEventHandler<HSTRING__ *,IInspectable *>>'}
0x18002942b  mov     [rbx+20h], rax
0x18002942f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VCViewPositionControllerBase@@UIImmersiveLayoutChanges@@@WRL@Microsoft@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIImmersiveLayoutChanges@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCViewPositionControllerBase@@@Details@23@UIImmersiveLayoutChanges@@@234@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CViewPositionControllerBase,IImmersiveLayoutChanges>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IImmersiveLayoutChanges>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CViewPositionControllerBase>,IImmersiveLayoutChanges>>'}
0x180029436  mov     [rbx+70h], rax
0x18002943a  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180029441  test    rcx, rcx
0x180029444  jz      short loc_180029452
0x180029446  mov     rax, [rcx]
0x180029449  mov     rax, [rax+8]
0x18002944d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029452  mov     rax, rbx
0x180029455  add     rsp, 20h
0x180029459  pop     rbx
0x18002945a  retn
```
