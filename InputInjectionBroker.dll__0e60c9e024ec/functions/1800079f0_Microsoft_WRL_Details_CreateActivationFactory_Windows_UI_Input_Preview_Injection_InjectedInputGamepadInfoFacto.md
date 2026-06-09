# Microsoft::WRL::Details::CreateActivationFactory<Windows::UI::Input::Preview::Injection::InjectedInputGamepadInfoFactory>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x1800079f0`
- end: `0x180007b22`
- name: `??$CreateActivationFactory@VInjectedInputGamepadInfoFactory@Injection@Preview@Input@UI@Windows@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `306`
- prototype: `__int64 __fastcall(_BYTE *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001e68`
- `0x1800060bc`
- `0x1800079f0`
- `0x1800082c0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateActivationFactory<Windows::UI::Input::Preview::Injection::InjectedInputGamepadInfoFactory>(
        _BYTE *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  char *v8; // rax
  char *v9; // rbx
  _QWORD *v11; // rsi
  int CanCastTo; // esi
  signed __int32 v13; // eax

  v8 = (char *)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( !v8 )
    return 2147942414LL;
  v11 = v8 + 8;
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v8 + 8));
  *((_DWORD *)v9 + 17) = 1;
  *(_QWORD *)v9 = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::UI::Input::Preview::Injection::IInjectedInputGamepadInfoFactory>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable';
  *v11 = &Windows::UI::Input::Preview::Injection::InjectedInputGamepadInfoFactory::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::UI::Input::Preview::Injection::IInjectedInputGamepadInfoFactory>>'};
  *((_QWORD *)v9 + 5) = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::UI::Input::Preview::Injection::IInjectedInputGamepadInfoFactory>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::UI::Input::Preview::Injection::IInjectedInputGamepadInfoFactory>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::UI::Input::Preview::Injection::IInjectedInputGamepadInfoFactory>>'};
  *((_QWORD *)v9 + 10) = 0;
  *((_DWORD *)v9 + 22) = 4;
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v9 = &Windows::UI::Input::Preview::Injection::InjectedInputGamepadInfoFactory::`vftable';
  *v11 = &Windows::UI::Input::Preview::Injection::InjectedInputGamepadInfoFactory::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::UI::Input::Preview::Injection::IInjectedInputGamepadInfoFactory>>'};
  *((_QWORD *)v9 + 5) = &Windows::UI::Input::Preview::Injection::InjectedInputGamepadInfoFactory::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::UI::Input::Preview::Injection::IInjectedInputGamepadInfoFactory>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::UI::Input::Preview::Injection::IInjectedInputGamepadInfoFactory>>'};
  ((void (__fastcall *)(char *))Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::UI::Input::Preview::Injection::IInjectedInputGamepadInfoFactory>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef)(v9);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 16LL))(v9);
  CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::UI::Input::Preview::Injection::IInjectedInputGamepadInfoFactory>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(
                v9,
                a3,
                a4);
  if ( CanCastTo >= 0 )
  {
    if ( (*a1 & 4) == 0 )
    {
      do
        v13 = *((_DWORD *)v9 + 17);
      while ( v13 != 0x7FFFFFFF && v13 != _InterlockedCompareExchange((volatile signed __int32 *)v9 + 17, v13 + 1, v13) );
    }
    *((_DWORD *)v9 + 22) = *(_DWORD *)a1;
    *((_QWORD *)v9 + 10) = a2;
    return 0;
  }
  else
  {
    (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 16LL))(v9);
    return (unsigned int)CanCastTo;
  }
}

```

## disassembly

```asm
0x1800079f0  push    rbx
0x1800079f2  push    rbp
0x1800079f3  push    rsi
0x1800079f4  push    rdi
0x1800079f5  push    r14
0x1800079f7  push    r15
0x1800079f9  sub     rsp, 28h
0x1800079fd  mov     r14, r9
0x180007a00  mov     r15, r8
0x180007a03  mov     rbp, rdx
0x180007a06  mov     rdi, rcx
0x180007a09  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007a10  mov     ecx, 60h ; '`'; unsigned __int64
0x180007a15  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007a1a  mov     rbx, rax
0x180007a1d  test    rax, rax
0x180007a20  jnz     short loc_180007A2C
0x180007a22  mov     eax, 8007000Eh
0x180007a27  jmp     loc_180007B15
0x180007a2c  lea     rsi, [rax+8]
0x180007a30  mov     rcx, rsi; this
0x180007a33  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180007a38  mov     dword ptr [rbx+44h], 1
0x180007a3f  lea     rax, ??_7?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIInjectedInputGamepadInfoFactory@Injection@Preview@Input@UI@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::UI::Input::Preview::Injection::IInjectedInputGamepadInfoFactory>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'
0x180007a46  mov     [rbx], rax
0x180007a49  lea     rax, ??_7InjectedInputGamepadInfoFactory@Injection@Preview@Input@UI@Windows@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIInjectedInputGamepadInfoFactory@Injection@Preview@Input@UI@Windows@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::UI::Input::Preview::Injection::InjectedInputGamepadInfoFactory::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::UI::Input::Preview::Injection::IInjectedInputGamepadInfoFactory>>'}
0x180007a50  mov     [rsi], rax
0x180007a53  lea     rax, ??_7?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIInjectedInputGamepadInfoFactory@Injection@Preview@Input@UI@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIInjectedInputGamepadInfoFactory@Injection@Preview@Input@UI@Windows@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIInjectedInputGamepadInfoFactory@Injection@Preview@Input@UI@Windows@@@234@@Details@12@@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::UI::Input::Preview::Injection::IInjectedInputGamepadInfoFactory>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::UI::Input::Preview::Injection::IInjectedInputGamepadInfoFactory>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::UI::Input::Preview::Injection::IInjectedInputGamepadInfoFactory>>'}
0x180007a5a  mov     [rbx+28h], rax
0x180007a5e  mov     qword ptr [rbx+50h], 0
0x180007a66  mov     dword ptr [rbx+58h], 4
0x180007a6d  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180007a74  test    rcx, rcx
0x180007a77  jz      short loc_180007A86
0x180007a79  mov     rax, [rcx]
0x180007a7c  mov     rax, [rax+8]
0x180007a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a85  nop
0x180007a86  lea     rax, ??_7InjectedInputGamepadInfoFactory@Injection@Preview@Input@UI@Windows@@6B@; const Windows::UI::Input::Preview::Injection::InjectedInputGamepadInfoFactory::`vftable'
0x180007a8d  mov     [rbx], rax
0x180007a90  lea     rax, ??_7InjectedInputGamepadInfoFactory@Injection@Preview@Input@UI@Windows@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIInjectedInputGamepadInfoFactory@Injection@Preview@Input@UI@Windows@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::UI::Input::Preview::Injection::InjectedInputGamepadInfoFactory::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::UI::Input::Preview::Injection::IInjectedInputGamepadInfoFactory>>'}
0x180007a97  mov     [rsi], rax
0x180007a9a  lea     rax, ??_7InjectedInputGamepadInfoFactory@Injection@Preview@Input@UI@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIInjectedInputGamepadInfoFactory@Injection@Preview@Input@UI@Windows@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIInjectedInputGamepadInfoFactory@Injection@Preview@Input@UI@Windows@@@234@@Details@WRL@Microsoft@@@; const Windows::UI::Input::Preview::Injection::InjectedInputGamepadInfoFactory::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::UI::Input::Preview::Injection::IInjectedInputGamepadInfoFactory>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::UI::Input::Preview::Injection::IInjectedInputGamepadInfoFactory>>'}
0x180007aa1  mov     [rbx+28h], rax
0x180007aa5  mov     rcx, rbx
0x180007aa8  mov     rax, cs:off_180014818
0x180007aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ab4  nop
0x180007ab5  mov     rax, [rbx]
0x180007ab8  mov     rcx, rbx
0x180007abb  mov     rax, [rax+10h]
0x180007abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ac4  nop
0x180007ac5  mov     r8, r14
0x180007ac8  mov     rdx, r15
0x180007acb  mov     rcx, rbx
0x180007ace  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UIInjectedInputGamepadInfoFactory@Injection@Preview@Input@UI@Windows@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::UI::Input::Preview::Injection::IInjectedInputGamepadInfoFactory>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(_GUID const &,void * *,bool *)
0x180007ad3  mov     esi, eax
0x180007ad5  test    eax, eax
0x180007ad7  jns     short loc_180007AED
0x180007ad9  mov     rcx, [rbx]
0x180007adc  mov     rax, [rcx+10h]
0x180007ae0  mov     rcx, rbx
0x180007ae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ae8  nop
0x180007ae9  mov     eax, esi
0x180007aeb  jmp     short loc_180007B15
0x180007aed  test    byte ptr [rdi], 4
0x180007af0  jnz     short loc_180007B0A
0x180007af2  mov     edx, 7FFFFFFFh
0x180007af7  jmp     short loc_180007B03
0x180007af9  lea     ecx, [rax+1]
0x180007afc  lock cmpxchg [rbx+44h], ecx
0x180007b01  jz      short loc_180007B0A
0x180007b03  mov     eax, [rbx+44h]
0x180007b06  cmp     eax, edx
0x180007b08  jnz     short loc_180007AF9
0x180007b0a  mov     eax, [rdi]
0x180007b0c  mov     [rbx+58h], eax
0x180007b0f  mov     [rbx+50h], rbp
0x180007b13  xor     eax, eax
0x180007b15  add     rsp, 28h
0x180007b19  pop     r15
0x180007b1b  pop     r14
0x180007b1d  pop     rdi
0x180007b1e  pop     rsi
0x180007b1f  pop     rbp
0x180007b20  pop     rbx
0x180007b21  retn
```
