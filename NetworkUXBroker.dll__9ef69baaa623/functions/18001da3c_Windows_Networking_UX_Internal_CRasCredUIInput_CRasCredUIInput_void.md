# Windows::Networking::UX::Internal::CRasCredUIInput::~CRasCredUIInput(void)

- ea: `0x18001da3c`
- end: `0x18001daa6`
- name: `??1CRasCredUIInput@Internal@UX@Networking@Windows@@UEAA@XZ`
- size: `106`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::CRasCredUIInput *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001dd60`

## callees

- `0x18001b958`
- `0x18001d7f8`
- `0x18001da3c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001da8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001da8b`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::CRasCredUIInput::~CRasCredUIInput(
        Windows::Networking::UX::Internal::CRasCredUIInput *this)
{
  _BYTE *v2; // rdx

  *(_QWORD *)this = &Windows::Networking::UX::Internal::CRasCredUIInput::`vftable'{for `Microsoft::WRL::Details::Selector<Windows::Networking::UX::Internal::CUserInputType,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Microsoft::WRL::Details::ImplementsMarker<Windows::Networking::UX::Internal::CUserInputType>,IWeakReferenceSource,Windows::Networking::UX::IRasCredUIInput,Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 3) = &Windows::Networking::UX::Internal::CRasCredUIInput::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Networking::UX::IRasCredUIInput,Microsoft::WRL::FtmBase>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Microsoft::WRL::Details::ImplementsMarker<Windows::Networking::UX::Internal::CUserInputType>,IWeakReferenceSource,Windows::Networking::UX::IRasCredUIInput,Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 4) = &Windows::Networking::UX::Internal::CRasCredUIInput::`vftable'{for `Windows::Networking::UX::IRasCredUIInput'};
  *((_QWORD *)this + 5) = &Windows::Networking::UX::Internal::CRasCredUIInput::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v2 = (_BYTE *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = 0;
  if ( v2 )
    wil::cotaskmem_secure_deleter::operator()<unsigned short>((__int64)this, v2);
  WindowsDeleteString(*((HSTRING *)this + 12));
  *((_QWORD *)this + 12) = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CUserInputType,Windows::Networking::UX::IDACredUIInput,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CUserInputType,Windows::Networking::UX::IDACredUIInput,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x18001da3c  push    rbx
0x18001da3e  sub     rsp, 20h
0x18001da42  mov     rbx, rcx
0x18001da45  lea     rax, ??_7CRasCredUIInput@Internal@UX@Networking@Windows@@6B?$Selector@VCUserInputType@Internal@UX@Networking@Windows@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCUserInputType@Internal@UX@Networking@Windows@@@Details@23@UIWeakReferenceSource@@UIRasCredUIInput@UX@Networking@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@@; const Windows::Networking::UX::Internal::CRasCredUIInput::`vftable'{for `Microsoft::WRL::Details::Selector<Windows::Networking::UX::Internal::CUserInputType,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Microsoft::WRL::Details::ImplementsMarker<Windows::Networking::UX::Internal::CUserInputType>,IWeakReferenceSource,Windows::Networking::UX::IRasCredUIInput,Microsoft::WRL::FtmBase>>'}
0x18001da4c  mov     [rcx], rax
0x18001da4f  lea     rax, ??_7CRasCredUIInput@Internal@UX@Networking@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIRasCredUIInput@UX@Networking@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCUserInputType@Internal@UX@Networking@Windows@@@Details@23@UIWeakReferenceSource@@UIRasCredUIInput@UX@Networking@Windows@@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const Windows::Networking::UX::Internal::CRasCredUIInput::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Networking::UX::IRasCredUIInput,Microsoft::WRL::FtmBase>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Microsoft::WRL::Details::ImplementsMarker<Windows::Networking::UX::Internal::CUserInputType>,IWeakReferenceSource,Windows::Networking::UX::IRasCredUIInput,Microsoft::WRL::FtmBase>>'}
0x18001da56  mov     [rcx+18h], rax
0x18001da5a  lea     rax, ??_7CRasCredUIInput@Internal@UX@Networking@Windows@@6BIRasCredUIInput@234@@; const Windows::Networking::UX::Internal::CRasCredUIInput::`vftable'{for `Windows::Networking::UX::IRasCredUIInput'}
0x18001da61  mov     [rcx+20h], rax
0x18001da65  lea     rax, ??_7CRasCredUIInput@Internal@UX@Networking@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Networking::UX::Internal::CRasCredUIInput::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001da6c  mov     [rcx+28h], rax
0x18001da70  mov     rdx, [rcx+70h]
0x18001da74  mov     qword ptr [rcx+70h], 0
0x18001da7c  test    rdx, rdx
0x18001da7f  jz      short loc_18001DA87
0x18001da81  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18001da86  nop
0x18001da87  mov     rcx, [rbx+60h]; string
0x18001da8b  call    cs:__imp_WindowsDeleteString
0x18001da91  mov     qword ptr [rbx+60h], 0
0x18001da99  mov     rcx, rbx
0x18001da9c  add     rsp, 20h
0x18001daa0  pop     rbx
0x18001daa1  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VCUserInputType@Internal@UX@Networking@Windows@@UIDACredUIInput@678@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CUserInputType,Windows::Networking::UX::IDACredUIInput,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CUserInputType,Windows::Networking::UX::IDACredUIInput,Microsoft::WRL::FtmBase>(void)
```
