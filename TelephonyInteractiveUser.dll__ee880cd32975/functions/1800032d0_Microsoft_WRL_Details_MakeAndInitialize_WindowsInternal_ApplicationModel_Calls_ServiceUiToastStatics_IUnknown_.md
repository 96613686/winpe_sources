# Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics,IUnknown,>(IUnknown * *)

- ea: `0x1800032d0`
- end: `0x180003385`
- name: `??$MakeAndInitialize@VServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003810`

## callees

- `0x180001de4`
- `0x1800032d0`
- `0x180004010`
- `0x180004220`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics,IUnknown,>(
        _QWORD *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rdi
  struct Microsoft::WRL::Details::ModuleBase *v5; // rcx
  unsigned int Interface; // ebx
  __int64 v7; // rdx

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  v3 = v2;
  if ( !v2 )
    return 2147942414LL;
  v5 = Microsoft::WRL::Details::ModuleBase::module_;
  *((_DWORD *)v2 + 9) = 1;
  *v2 = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `IActivationFactory'};
  v2[1] = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
  v2[6] = 0;
  *((_DWORD *)v2 + 14) = 4;
  if ( v5 )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v5 + 8LL))(v5);
  *v3 = &WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::`vftable'{for `IActivationFactory'};
  v3[1] = &WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
  Interface = Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::QueryInterface(
                v3,
                &GUID_00000000_0000_0000_c000_000000000046,
                a1);
  Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(
    (__int64)v3,
    v7);
  return Interface;
}

```

## disassembly

```asm
0x1800032d0  mov     [rsp+arg_8], rbx
0x1800032d5  push    rdi
0x1800032d6  sub     rsp, 20h
0x1800032da  mov     rbx, rcx
0x1800032dd  mov     qword ptr [rcx], 0
0x1800032e4  mov     ecx, 40h ; '@'; unsigned __int64
0x1800032e9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800032f0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800032f5  mov     rdi, rax
0x1800032f8  test    rax, rax
0x1800032fb  jnz     short loc_180003304
0x1800032fd  mov     eax, 8007000Eh
0x180003302  jmp     short loc_18000337A
0x180003304  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000330b  mov     dword ptr [rax+24h], 1
0x180003312  lea     rax, ??_7?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6BIActivationFactory@@@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `IActivationFactory'}
0x180003319  mov     [rdi], rax
0x18000331c  lea     rax, ??_7?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$00U?$ImplementsMarker@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@@WRL@Microsoft@@@Details@23@VNil@523@V6523@V6523@@Details@12@@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x180003323  mov     [rdi+8], rax
0x180003327  mov     qword ptr [rdi+30h], 0
0x18000332f  mov     dword ptr [rdi+38h], 4
0x180003336  test    rcx, rcx
0x180003339  jz      short loc_180003347
0x18000333b  mov     rax, [rcx]
0x18000333e  mov     rax, [rax+8]
0x180003342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003347  lea     rax, ??_7ServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@6BIActivationFactory@@@; const WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::`vftable'{for `IActivationFactory'}
0x18000334e  mov     r8, rbx
0x180003351  mov     [rdi], rax
0x180003354  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000335b  lea     rax, ??_7ServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$00U?$ImplementsMarker@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@@WRL@Microsoft@@@Details@23@VNil@523@V6523@V6523@@Details@WRL@Microsoft@@@; const WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x180003362  mov     rcx, rdi
0x180003365  mov     [rdi+8], rax
0x180003369  call    ?QueryInterface@?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::QueryInterface(_GUID const &,void * *)
0x18000336e  mov     rcx, rdi
0x180003371  mov     ebx, eax
0x180003373  call    ?Release@?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x180003378  mov     eax, ebx
0x18000337a  mov     rbx, [rsp+28h+arg_8]
0x18000337f  add     rsp, 20h
0x180003383  pop     rdi
0x180003384  retn
```
