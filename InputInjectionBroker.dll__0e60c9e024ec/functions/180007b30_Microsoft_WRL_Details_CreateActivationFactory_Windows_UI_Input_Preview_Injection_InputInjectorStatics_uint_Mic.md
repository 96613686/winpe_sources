# Microsoft::WRL::Details::CreateActivationFactory<Windows::UI::Input::Preview::Injection::InputInjectorStatics>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180007b30`
- end: `0x180007c70`
- name: `??$CreateActivationFactory@VInputInjectorStatics@Injection@Preview@Input@UI@Windows@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `320`
- prototype: `__int64 __fastcall(_BYTE *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001e68`
- `0x180007b30`
- `0x180008390`
- `0x18000c8bc`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateActivationFactory<Windows::UI::Input::Preview::Injection::InputInjectorStatics>(
        _BYTE *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  int IsInjectionBrokerAllowed; // edi
  __int64 v11; // rax
  signed __int32 v13; // eax

  v8 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( !v8 )
    return (unsigned int)-2147024882;
  v8[7] = 1;
  *(_QWORD *)v8 = &Microsoft::WRL::ActivationFactory<Windows::UI::Input::Preview::Injection::IInputInjectorStatics,Windows::UI::Input::Preview::Injection::IInputInjectorStatics2,Microsoft::WRL::Details::Nil,0>::`vftable';
  *((_QWORD *)v8 + 1) = &Microsoft::WRL::ActivationFactory<Windows::UI::Input::Preview::Injection::IInputInjectorStatics,Windows::UI::Input::Preview::Injection::IInputInjectorStatics2,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Windows::UI::Input::Preview::Injection::IInputInjectorStatics'};
  *((_QWORD *)v8 + 2) = &Microsoft::WRL::ActivationFactory<Windows::UI::Input::Preview::Injection::IInputInjectorStatics,Windows::UI::Input::Preview::Injection::IInputInjectorStatics2,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Windows::UI::Input::Preview::Injection::IInputInjectorStatics2,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
  *((_QWORD *)v8 + 5) = 0;
  v8[12] = 4;
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v9 = &Windows::UI::Input::Preview::Injection::InputInjectorStatics::`vftable';
  *((_QWORD *)v9 + 1) = &Windows::UI::Input::Preview::Injection::InputInjectorStatics::`vftable'{for `Windows::UI::Input::Preview::Injection::IInputInjectorStatics'};
  *((_QWORD *)v9 + 2) = &Windows::UI::Input::Preview::Injection::InputInjectorStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Windows::UI::Input::Preview::Injection::IInputInjectorStatics2,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
  IsInjectionBrokerAllowed = Windows::UI::Input::Preview::Injection::InputInjector::IsInjectionBrokerAllowed();
  v11 = *(_QWORD *)v9;
  if ( IsInjectionBrokerAllowed < 0 )
  {
    (*(void (__fastcall **)(_DWORD *))(v11 + 16))(v9);
    return (unsigned int)IsInjectionBrokerAllowed;
  }
  (*(void (__fastcall **)(_DWORD *))(v11 + 8))(v9);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 16LL))(v9);
  IsInjectionBrokerAllowed = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Windows::UI::Input::Preview::Injection::IInputInjectorStatics,Windows::UI::Input::Preview::Injection::IInputInjectorStatics2,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(
                               v9,
                               a3,
                               a4);
  if ( IsInjectionBrokerAllowed < 0 )
  {
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 16LL))(v9);
    return (unsigned int)IsInjectionBrokerAllowed;
  }
  if ( (*a1 & 4) == 0 )
  {
    do
      v13 = v9[7];
    while ( v13 != 0x7FFFFFFF && v13 != _InterlockedCompareExchange(v9 + 7, v13 + 1, v13) );
  }
  v9[12] = *(_DWORD *)a1;
  *((_QWORD *)v9 + 5) = a2;
  return 0;
}

```

## disassembly

```asm
0x180007b30  push    rbx
0x180007b32  push    rbp
0x180007b33  push    rsi
0x180007b34  push    rdi
0x180007b35  push    r14
0x180007b37  push    r15
0x180007b39  sub     rsp, 28h
0x180007b3d  mov     r14, r9
0x180007b40  mov     r15, r8
0x180007b43  mov     rbp, rdx
0x180007b46  mov     rsi, rcx
0x180007b49  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007b50  mov     ecx, 38h ; '8'; unsigned __int64
0x180007b55  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007b5a  mov     rbx, rax
0x180007b5d  test    rax, rax
0x180007b60  jnz     short loc_180007B6C
0x180007b62  mov     edi, 8007000Eh
0x180007b67  jmp     loc_180007BF6
0x180007b6c  mov     dword ptr [rax+1Ch], 1
0x180007b73  lea     rax, ??_7?$ActivationFactory@UIInputInjectorStatics@Injection@Preview@Input@UI@Windows@@UIInputInjectorStatics2@23456@VNil@Details@WRL@Microsoft@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::ActivationFactory<Windows::UI::Input::Preview::Injection::IInputInjectorStatics,Windows::UI::Input::Preview::Injection::IInputInjectorStatics2,Microsoft::WRL::Details::Nil,0>::`vftable'
0x180007b7a  mov     [rbx], rax
0x180007b7d  lea     rax, ??_7?$ActivationFactory@UIInputInjectorStatics@Injection@Preview@Input@UI@Windows@@UIInputInjectorStatics2@23456@VNil@Details@WRL@Microsoft@@$0A@@WRL@Microsoft@@6BIInputInjectorStatics@Injection@Preview@Input@UI@Windows@@@; const Microsoft::WRL::ActivationFactory<Windows::UI::Input::Preview::Injection::IInputInjectorStatics,Windows::UI::Input::Preview::Injection::IInputInjectorStatics2,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Windows::UI::Input::Preview::Injection::IInputInjectorStatics'}
0x180007b84  mov     [rbx+8], rax
0x180007b88  lea     rax, ??_7?$ActivationFactory@UIInputInjectorStatics@Injection@Preview@Input@UI@Windows@@UIInputInjectorStatics2@23456@VNil@Details@WRL@Microsoft@@$0A@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$00UIInputInjectorStatics2@Injection@Preview@Input@UI@Windows@@VNil@Details@23@VNil@Details@23@@Details@12@@; const Microsoft::WRL::ActivationFactory<Windows::UI::Input::Preview::Injection::IInputInjectorStatics,Windows::UI::Input::Preview::Injection::IInputInjectorStatics2,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Windows::UI::Input::Preview::Injection::IInputInjectorStatics2,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x180007b8f  mov     [rbx+10h], rax
0x180007b93  mov     qword ptr [rbx+28h], 0
0x180007b9b  mov     dword ptr [rbx+30h], 4
0x180007ba2  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180007ba9  test    rcx, rcx
0x180007bac  jz      short loc_180007BBB
0x180007bae  mov     rax, [rcx]
0x180007bb1  mov     rax, [rax+8]
0x180007bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bba  nop
0x180007bbb  lea     rax, ??_7InputInjectorStatics@Injection@Preview@Input@UI@Windows@@6B@; const Windows::UI::Input::Preview::Injection::InputInjectorStatics::`vftable'
0x180007bc2  mov     [rbx], rax
0x180007bc5  lea     rax, ??_7InputInjectorStatics@Injection@Preview@Input@UI@Windows@@6BIInputInjectorStatics@12345@@; const Windows::UI::Input::Preview::Injection::InputInjectorStatics::`vftable'{for `Windows::UI::Input::Preview::Injection::IInputInjectorStatics'}
0x180007bcc  mov     [rbx+8], rax
0x180007bd0  lea     rax, ??_7InputInjectorStatics@Injection@Preview@Input@UI@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$00UIInputInjectorStatics2@Injection@Preview@Input@UI@Windows@@VNil@Details@23@VNil@Details@23@@Details@WRL@Microsoft@@@; const Windows::UI::Input::Preview::Injection::InputInjectorStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Windows::UI::Input::Preview::Injection::IInputInjectorStatics2,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x180007bd7  mov     [rbx+10h], rax
0x180007bdb  call    ?IsInjectionBrokerAllowed@InputInjector@Injection@Preview@Input@UI@Windows@@SAJXZ; Windows::UI::Input::Preview::Injection::InputInjector::IsInjectionBrokerAllowed(void)
0x180007be0  mov     edi, eax
0x180007be2  mov     rax, [rbx]
0x180007be5  test    edi, edi
0x180007be7  jns     short loc_180007BFA
0x180007be9  mov     rcx, rbx
0x180007bec  mov     rax, [rax+10h]
0x180007bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bf5  nop
0x180007bf6  mov     eax, edi
0x180007bf8  jmp     short loc_180007C63
0x180007bfa  mov     rcx, rbx
0x180007bfd  mov     rax, [rax+8]
0x180007c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c06  nop
0x180007c07  mov     rax, [rbx]
0x180007c0a  mov     rcx, rbx
0x180007c0d  mov     rax, [rax+10h]
0x180007c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c16  nop
0x180007c17  mov     r8, r14
0x180007c1a  mov     rdx, r15
0x180007c1d  mov     rcx, rbx
0x180007c20  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@UIInputInjectorStatics@Injection@Preview@Input@UI@Windows@@UIInputInjectorStatics2@6789Windows@@VNil@Details@23@VNil@Details@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Windows::UI::Input::Preview::Injection::IInputInjectorStatics,Windows::UI::Input::Preview::Injection::IInputInjectorStatics2,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(_GUID const &,void * *,bool *)
0x180007c25  mov     edi, eax
0x180007c27  test    eax, eax
0x180007c29  jns     short loc_180007C3D
0x180007c2b  mov     rcx, [rbx]
0x180007c2e  mov     rax, [rcx+10h]
0x180007c32  mov     rcx, rbx
0x180007c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c3a  nop
0x180007c3b  jmp     short loc_180007BF6
0x180007c3d  test    byte ptr [rsi], 4
0x180007c40  jnz     short loc_180007C58
0x180007c42  mov     edx, 7FFFFFFFh
0x180007c47  mov     eax, [rbx+1Ch]
0x180007c4a  cmp     eax, edx
0x180007c4c  jz      short loc_180007C58
0x180007c4e  lea     ecx, [rax+1]
0x180007c51  lock cmpxchg [rbx+1Ch], ecx
0x180007c56  jnz     short loc_180007C47
0x180007c58  mov     eax, [rsi]
0x180007c5a  mov     [rbx+30h], eax
0x180007c5d  mov     [rbx+28h], rbp
0x180007c61  xor     eax, eax
0x180007c63  add     rsp, 28h
0x180007c67  pop     r15
0x180007c69  pop     r14
0x180007c6b  pop     rdi
0x180007c6c  pop     rsi
0x180007c6d  pop     rbp
0x180007c6e  pop     rbx
0x180007c6f  retn
```
