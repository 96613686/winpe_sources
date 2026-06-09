# Windows::Networking::UX::Internal::CRasThirdpartyAuthTokenInput::~CRasThirdpartyAuthTokenInput(void)

- ea: `0x18001daac`
- end: `0x18001db2d`
- name: `??1CRasThirdpartyAuthTokenInput@Internal@UX@Networking@Windows@@UEAA@XZ`
- size: `129`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::CRasThirdpartyAuthTokenInput *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001dda0`

## callees

- `0x18001b958`
- `0x18001d7f8`
- `0x18001daac`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001db12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001db12`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Networking::UX::Internal::CRasThirdpartyAuthTokenInput::~CRasThirdpartyAuthTokenInput(
        Windows::Networking::UX::Internal::CRasThirdpartyAuthTokenInput *this)
{
  _BYTE *v2; // rdx
  _BYTE *v3; // rdx

  *(_QWORD *)this = &Windows::Networking::UX::Internal::CRasThirdpartyAuthTokenInput::`vftable'{for `Microsoft::WRL::Details::Selector<Windows::Networking::UX::Internal::CUserInputType,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Microsoft::WRL::Details::ImplementsMarker<Windows::Networking::UX::Internal::CUserInputType>,IWeakReferenceSource,Windows::Networking::UX::IRasThirdpartyAuthTokenInput,Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 3) = &Windows::Networking::UX::Internal::CRasThirdpartyAuthTokenInput::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Networking::UX::IRasThirdpartyAuthTokenInput,Microsoft::WRL::FtmBase>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Microsoft::WRL::Details::ImplementsMarker<Windows::Networking::UX::Internal::CUserInputType>,IWeakReferenceSource,Windows::Networking::UX::IRasThirdpartyAuthTokenInput,Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 4) = &Windows::Networking::UX::Internal::CRasThirdpartyAuthTokenInput::`vftable'{for `Windows::Networking::UX::IRasThirdpartyAuthTokenInput'};
  *((_QWORD *)this + 5) = &Windows::Networking::UX::Internal::CRasThirdpartyAuthTokenInput::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v2 = (_BYTE *)*((_QWORD *)this + 15);
  *((_QWORD *)this + 15) = 0;
  if ( v2 )
    wil::cotaskmem_secure_deleter::operator()<unsigned short>((__int64)this, v2);
  v3 = (_BYTE *)*((_QWORD *)this + 13);
  *((_QWORD *)this + 13) = 0;
  if ( v3 )
    wil::cotaskmem_secure_deleter::operator()<unsigned short>((__int64)this, v3);
  WindowsDeleteString(*((HSTRING *)this + 11));
  *((_QWORD *)this + 11) = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CUserInputType,Windows::Networking::UX::IDACredUIInput,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CUserInputType,Windows::Networking::UX::IDACredUIInput,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x18001daac  push    rbx
0x18001daae  sub     rsp, 20h
0x18001dab2  mov     rbx, rcx
0x18001dab5  lea     rax, ??_7CRasThirdpartyAuthTokenInput@Internal@UX@Networking@Windows@@6B?$Selector@VCUserInputType@Internal@UX@Networking@Windows@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCUserInputType@Internal@UX@Networking@Windows@@@Details@23@UIWeakReferenceSource@@UIRasThirdpartyAuthTokenInput@UX@Networking@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@@; const Windows::Networking::UX::Internal::CRasThirdpartyAuthTokenInput::`vftable'{for `Microsoft::WRL::Details::Selector<Windows::Networking::UX::Internal::CUserInputType,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Microsoft::WRL::Details::ImplementsMarker<Windows::Networking::UX::Internal::CUserInputType>,IWeakReferenceSource,Windows::Networking::UX::IRasThirdpartyAuthTokenInput,Microsoft::WRL::FtmBase>>'}
0x18001dabc  mov     [rcx], rax
0x18001dabf  lea     rax, ??_7CRasThirdpartyAuthTokenInput@Internal@UX@Networking@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIRasThirdpartyAuthTokenInput@UX@Networking@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCUserInputType@Internal@UX@Networking@Windows@@@Details@23@UIWeakReferenceSource@@UIRasThirdpartyAuthTokenInput@UX@Networking@Windows@@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const Windows::Networking::UX::Internal::CRasThirdpartyAuthTokenInput::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Networking::UX::IRasThirdpartyAuthTokenInput,Microsoft::WRL::FtmBase>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Microsoft::WRL::Details::ImplementsMarker<Windows::Networking::UX::Internal::CUserInputType>,IWeakReferenceSource,Windows::Networking::UX::IRasThirdpartyAuthTokenInput,Microsoft::WRL::FtmBase>>'}
0x18001dac6  mov     [rcx+18h], rax
0x18001daca  lea     rax, ??_7CRasThirdpartyAuthTokenInput@Internal@UX@Networking@Windows@@6BIRasThirdpartyAuthTokenInput@234@@; const Windows::Networking::UX::Internal::CRasThirdpartyAuthTokenInput::`vftable'{for `Windows::Networking::UX::IRasThirdpartyAuthTokenInput'}
0x18001dad1  mov     [rcx+20h], rax
0x18001dad5  lea     rax, ??_7CRasThirdpartyAuthTokenInput@Internal@UX@Networking@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Networking::UX::Internal::CRasThirdpartyAuthTokenInput::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001dadc  mov     [rcx+28h], rax
0x18001dae0  mov     rdx, [rcx+78h]
0x18001dae4  mov     qword ptr [rcx+78h], 0
0x18001daec  test    rdx, rdx
0x18001daef  jz      short loc_18001DAF7
0x18001daf1  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18001daf6  nop
0x18001daf7  mov     rdx, [rbx+68h]
0x18001dafb  mov     qword ptr [rbx+68h], 0
0x18001db03  test    rdx, rdx
0x18001db06  jz      short loc_18001DB0E
0x18001db08  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18001db0d  nop
0x18001db0e  mov     rcx, [rbx+58h]; string
0x18001db12  call    cs:__imp_WindowsDeleteString
0x18001db18  mov     qword ptr [rbx+58h], 0
0x18001db20  mov     rcx, rbx
0x18001db23  add     rsp, 20h
0x18001db27  pop     rbx
0x18001db28  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VCUserInputType@Internal@UX@Networking@Windows@@UIDACredUIInput@678@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CUserInputType,Windows::Networking::UX::IDACredUIInput,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CUserInputType,Windows::Networking::UX::IDACredUIInput,Microsoft::WRL::FtmBase>(void)
```
