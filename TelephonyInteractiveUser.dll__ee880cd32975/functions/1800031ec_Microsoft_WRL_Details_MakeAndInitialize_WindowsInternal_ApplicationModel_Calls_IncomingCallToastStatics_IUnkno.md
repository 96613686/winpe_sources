# Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics,IUnknown,>(IUnknown * *)

- ea: `0x1800031ec`
- end: `0x1800032c8`
- name: `??$MakeAndInitialize@VIncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003750`

## callees

- `0x180001de4`
- `0x1800031ec`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics,IUnknown,>(
        _QWORD *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rdi
  struct Microsoft::WRL::Details::ModuleBase *v5; // rcx
  unsigned int v6; // ebx

  *a1 = 0;
  v2 = operator new(0x48u, (const struct std::nothrow_t *)std::nothrow);
  v3 = v2;
  if ( !v2 )
    return 2147942414LL;
  v5 = Microsoft::WRL::Details::ModuleBase::module_;
  *((_DWORD *)v2 + 11) = 1;
  *v2 = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable';
  v2[1] = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics'};
  v2[2] = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,INotificationActivationCallback>'};
  v2[7] = 0;
  *((_DWORD *)v2 + 16) = 4;
  if ( v5 )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v5 + 8LL))(v5);
  *v3 = &WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::`vftable';
  v3[1] = &WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::`vftable'{for `WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics'};
  v3[2] = &WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,INotificationActivationCallback>'};
  v6 = ((__int64 (__fastcall *)(_QWORD *, GUID *, _QWORD *))WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::`vftable')(
         v3,
         &GUID_00000000_0000_0000_c000_000000000046,
         a1);
  (*(void (__fastcall **)(_QWORD *))(*v3 + 16LL))(v3);
  return v6;
}

```

## disassembly

```asm
0x1800031ec  mov     [rsp+arg_8], rbx
0x1800031f1  push    rdi
0x1800031f2  sub     rsp, 20h
0x1800031f6  mov     rbx, rcx
0x1800031f9  mov     qword ptr [rcx], 0
0x180003200  mov     ecx, 48h ; 'H'; unsigned __int64
0x180003205  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000320c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180003211  mov     rdi, rax
0x180003214  test    rax, rax
0x180003217  jnz     short loc_180003223
0x180003219  mov     eax, 8007000Eh
0x18000321e  jmp     loc_1800032BD
0x180003223  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000322a  mov     dword ptr [rax+2Ch], 1
0x180003231  lea     rax, ??_7?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UINotificationActivationCallback@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'
0x180003238  mov     [rdi], rax
0x18000323b  lea     rax, ??_7?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UINotificationActivationCallback@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6BIIncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics'}
0x180003242  mov     [rdi+8], rax
0x180003246  lea     rax, ??_7?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UINotificationActivationCallback@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UINotificationActivationCallback@@@Details@12@@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,INotificationActivationCallback>'}
0x18000324d  mov     [rdi+10h], rax
0x180003251  mov     qword ptr [rdi+38h], 0
0x180003259  mov     dword ptr [rdi+40h], 4
0x180003260  test    rcx, rcx
0x180003263  jz      short loc_180003271
0x180003265  mov     rax, [rcx]
0x180003268  mov     rax, [rax+8]
0x18000326c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003271  lea     rax, ??_7IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@6B@; const WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::`vftable'
0x180003278  mov     r8, rbx
0x18000327b  mov     [rdi], rax
0x18000327e  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180003285  lea     rax, ??_7IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@6BIIncomingCallToastStatics@123@@; const WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::`vftable'{for `WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics'}
0x18000328c  mov     rcx, rdi
0x18000328f  mov     [rdi+8], rax
0x180003293  lea     rax, ??_7IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UINotificationActivationCallback@@@Details@WRL@Microsoft@@@; const WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,INotificationActivationCallback>'}
0x18000329a  mov     [rdi+10h], rax
0x18000329e  mov     rax, cs:??_7IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@6B@; const WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::`vftable'
0x1800032a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032aa  mov     rcx, [rdi]
0x1800032ad  mov     ebx, eax
0x1800032af  mov     rax, [rcx+10h]
0x1800032b3  mov     rcx, rdi
0x1800032b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032bb  mov     eax, ebx
0x1800032bd  mov     rbx, [rsp+28h+arg_8]
0x1800032c2  add     rsp, 20h
0x1800032c6  pop     rdi
0x1800032c7  retn
```
