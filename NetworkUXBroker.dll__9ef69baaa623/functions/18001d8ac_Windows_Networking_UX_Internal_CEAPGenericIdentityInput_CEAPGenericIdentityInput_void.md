# Windows::Networking::UX::Internal::CEAPGenericIdentityInput::~CEAPGenericIdentityInput(void)

- ea: `0x18001d8ac`
- end: `0x18001d916`
- name: `??1CEAPGenericIdentityInput@Internal@UX@Networking@Windows@@UEAA@XZ`
- size: `106`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::CEAPGenericIdentityInput *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001dc60`

## callees

- `0x18001b958`
- `0x18001d7f8`
- `0x18001d8ac`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d8fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d8fb`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::CEAPGenericIdentityInput::~CEAPGenericIdentityInput(
        Windows::Networking::UX::Internal::CEAPGenericIdentityInput *this)
{
  _BYTE *v2; // rdx

  *(_QWORD *)this = &Windows::Networking::UX::Internal::CEAPGenericIdentityInput::`vftable'{for `Microsoft::WRL::Details::Selector<Windows::Networking::UX::Internal::CUserInputType,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Microsoft::WRL::Details::ImplementsMarker<Windows::Networking::UX::Internal::CUserInputType>,IWeakReferenceSource,Windows::Networking::UX::IEAPGenericIdentityInput,Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 3) = &Windows::Networking::UX::Internal::CEAPGenericIdentityInput::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Networking::UX::IEAPGenericIdentityInput,Microsoft::WRL::FtmBase>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Microsoft::WRL::Details::ImplementsMarker<Windows::Networking::UX::Internal::CUserInputType>,IWeakReferenceSource,Windows::Networking::UX::IEAPGenericIdentityInput,Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 4) = &Windows::Networking::UX::Internal::CEAPGenericIdentityInput::`vftable'{for `Windows::Networking::UX::IEAPGenericIdentityInput'};
  *((_QWORD *)this + 5) = &Windows::Networking::UX::Internal::CEAPGenericIdentityInput::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v2 = (_BYTE *)*((_QWORD *)this + 13);
  *((_QWORD *)this + 13) = 0;
  if ( v2 )
    wil::cotaskmem_secure_deleter::operator()<unsigned short>((__int64)this, v2);
  WindowsDeleteString(*((HSTRING *)this + 11));
  *((_QWORD *)this + 11) = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CUserInputType,Windows::Networking::UX::IDACredUIInput,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CUserInputType,Windows::Networking::UX::IDACredUIInput,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x18001d8ac  push    rbx
0x18001d8ae  sub     rsp, 20h
0x18001d8b2  mov     rbx, rcx
0x18001d8b5  lea     rax, ??_7CEAPGenericIdentityInput@Internal@UX@Networking@Windows@@6B?$Selector@VCUserInputType@Internal@UX@Networking@Windows@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCUserInputType@Internal@UX@Networking@Windows@@@Details@23@UIWeakReferenceSource@@UIEAPGenericIdentityInput@UX@Networking@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@@; const Windows::Networking::UX::Internal::CEAPGenericIdentityInput::`vftable'{for `Microsoft::WRL::Details::Selector<Windows::Networking::UX::Internal::CUserInputType,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Microsoft::WRL::Details::ImplementsMarker<Windows::Networking::UX::Internal::CUserInputType>,IWeakReferenceSource,Windows::Networking::UX::IEAPGenericIdentityInput,Microsoft::WRL::FtmBase>>'}
0x18001d8bc  mov     [rcx], rax
0x18001d8bf  lea     rax, ??_7CEAPGenericIdentityInput@Internal@UX@Networking@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIEAPGenericIdentityInput@UX@Networking@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCUserInputType@Internal@UX@Networking@Windows@@@Details@23@UIWeakReferenceSource@@UIEAPGenericIdentityInput@UX@Networking@Windows@@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const Windows::Networking::UX::Internal::CEAPGenericIdentityInput::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Networking::UX::IEAPGenericIdentityInput,Microsoft::WRL::FtmBase>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Microsoft::WRL::Details::ImplementsMarker<Windows::Networking::UX::Internal::CUserInputType>,IWeakReferenceSource,Windows::Networking::UX::IEAPGenericIdentityInput,Microsoft::WRL::FtmBase>>'}
0x18001d8c6  mov     [rcx+18h], rax
0x18001d8ca  lea     rax, ??_7CEAPGenericIdentityInput@Internal@UX@Networking@Windows@@6BIEAPGenericIdentityInput@234@@; const Windows::Networking::UX::Internal::CEAPGenericIdentityInput::`vftable'{for `Windows::Networking::UX::IEAPGenericIdentityInput'}
0x18001d8d1  mov     [rcx+20h], rax
0x18001d8d5  lea     rax, ??_7CEAPGenericIdentityInput@Internal@UX@Networking@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Networking::UX::Internal::CEAPGenericIdentityInput::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001d8dc  mov     [rcx+28h], rax
0x18001d8e0  mov     rdx, [rcx+68h]
0x18001d8e4  mov     qword ptr [rcx+68h], 0
0x18001d8ec  test    rdx, rdx
0x18001d8ef  jz      short loc_18001D8F7
0x18001d8f1  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18001d8f6  nop
0x18001d8f7  mov     rcx, [rbx+58h]; string
0x18001d8fb  call    cs:__imp_WindowsDeleteString
0x18001d901  mov     qword ptr [rbx+58h], 0
0x18001d909  mov     rcx, rbx
0x18001d90c  add     rsp, 20h
0x18001d910  pop     rbx
0x18001d911  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VCUserInputType@Internal@UX@Networking@Windows@@UIDACredUIInput@678@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CUserInputType,Windows::Networking::UX::IDACredUIInput,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CUserInputType,Windows::Networking::UX::IDACredUIInput,Microsoft::WRL::FtmBase>(void)
```
