# Microsoft::WRL::SimpleActivationFactory<Windows::UI::Input::InjectionBrokerImpl,0>::ActivateInstance(IInspectable * *)

- ea: `0x1800062f0`
- end: `0x1800063ed`
- name: `?ActivateInstance@?$SimpleActivationFactory@VInjectionBrokerImpl@Input@UI@Windows@@$0A@@WRL@Microsoft@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `253`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001e68`
- `0x1800060bc`
- `0x1800062f0`
- `0x18000c8bc`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleActivationFactory<Windows::UI::Input::InjectionBrokerImpl,0>::ActivateInstance(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *v3; // rax
  _QWORD *v4; // rbx
  int IsInjectionBrokerAllowed; // edi
  _QWORD *v6; // rdi
  __int64 v7; // rax

  *a2 = 0;
  v3 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v4 = v3;
  if ( v3 )
  {
    v6 = v3 + 2;
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v3 + 2));
    v4[7] = 1;
    *v4 = &Microsoft::WRL::RuntimeClass<Windows::UI::Input::IInjectionBroker,Microsoft::WRL::FtmBase>::`vftable';
    v4[1] = &Microsoft::WRL::RuntimeClass<Windows::UI::Input::IInjectionBroker,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'};
    *v6 = &Microsoft::WRL::RuntimeClass<Windows::UI::Input::IInjectionBroker,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v4 = &Windows::UI::Input::InjectionBrokerImpl::`vftable';
    v4[1] = &Windows::UI::Input::InjectionBrokerImpl::`vftable'{for `IWeakReferenceSource'};
    *v6 = &Windows::UI::Input::InjectionBrokerImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    IsInjectionBrokerAllowed = Windows::UI::Input::Preview::Injection::InputInjector::IsInjectionBrokerAllowed();
    v7 = *v4;
    if ( IsInjectionBrokerAllowed >= 0 )
    {
      IsInjectionBrokerAllowed = (*(__int64 (__fastcall **)(_QWORD *, GUID *, _QWORD *))v7)(
                                   v4,
                                   &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                                   a2);
      (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
    }
    else
    {
      (*(void (__fastcall **)(_QWORD *))(v7 + 16))(v4);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)IsInjectionBrokerAllowed;
}

```

## disassembly

```asm
0x1800062f0  mov     [rsp+arg_0], rbx
0x1800062f5  mov     [rsp+arg_8], rsi
0x1800062fa  push    rdi
0x1800062fb  sub     rsp, 20h
0x1800062ff  mov     rsi, rdx
0x180006302  mov     qword ptr [rdx], 0
0x180006309  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006310  mov     ecx, 40h ; '@'; unsigned __int64
0x180006315  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000631a  mov     rbx, rax
0x18000631d  test    rax, rax
0x180006320  jnz     short loc_18000632C
0x180006322  mov     edi, 8007000Eh
0x180006327  jmp     loc_1800063DB
0x18000632c  lea     rdi, [rax+10h]
0x180006330  mov     rcx, rdi; this
0x180006333  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180006338  mov     qword ptr [rbx+38h], 1
0x180006340  lea     rax, ??_7?$RuntimeClass@UIInjectionBroker@Input@UI@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Windows::UI::Input::IInjectionBroker,Microsoft::WRL::FtmBase>::`vftable'
0x180006347  mov     [rbx], rax
0x18000634a  lea     rax, ??_7?$RuntimeClass@UIInjectionBroker@Input@UI@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Windows::UI::Input::IInjectionBroker,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'}
0x180006351  mov     [rbx+8], rax
0x180006355  lea     rax, ??_7?$RuntimeClass@UIInjectionBroker@Input@UI@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::UI::Input::IInjectionBroker,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000635c  mov     [rdi], rax
0x18000635f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180006366  test    rcx, rcx
0x180006369  jz      short loc_180006378
0x18000636b  mov     rax, [rcx]
0x18000636e  mov     rax, [rax+8]
0x180006372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006377  nop
0x180006378  lea     rax, ??_7InjectionBrokerImpl@Input@UI@Windows@@6B@; const Windows::UI::Input::InjectionBrokerImpl::`vftable'
0x18000637f  mov     [rbx], rax
0x180006382  lea     rax, ??_7InjectionBrokerImpl@Input@UI@Windows@@6BIWeakReferenceSource@@@; const Windows::UI::Input::InjectionBrokerImpl::`vftable'{for `IWeakReferenceSource'}
0x180006389  mov     [rbx+8], rax
0x18000638d  lea     rax, ??_7InjectionBrokerImpl@Input@UI@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::UI::Input::InjectionBrokerImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180006394  mov     [rdi], rax
0x180006397  call    ?IsInjectionBrokerAllowed@InputInjector@Injection@Preview@Input@UI@Windows@@SAJXZ; Windows::UI::Input::Preview::Injection::InputInjector::IsInjectionBrokerAllowed(void)
0x18000639c  mov     edi, eax
0x18000639e  mov     rax, [rbx]
0x1800063a1  test    edi, edi
0x1800063a3  jns     short loc_1800063B4
0x1800063a5  mov     rcx, rbx
0x1800063a8  mov     rax, [rax+10h]
0x1800063ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063b1  nop
0x1800063b2  jmp     short loc_1800063DB
0x1800063b4  mov     r8, rsi
0x1800063b7  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x1800063be  mov     rcx, rbx
0x1800063c1  mov     rax, [rax]
0x1800063c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063c9  mov     edi, eax
0x1800063cb  mov     rcx, [rbx]
0x1800063ce  mov     rax, [rcx+10h]
0x1800063d2  mov     rcx, rbx
0x1800063d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063da  nop
0x1800063db  mov     eax, edi
0x1800063dd  mov     rbx, [rsp+28h+arg_0]
0x1800063e2  mov     rsi, [rsp+28h+arg_8]
0x1800063e7  add     rsp, 20h
0x1800063eb  pop     rdi
0x1800063ec  retn
```
