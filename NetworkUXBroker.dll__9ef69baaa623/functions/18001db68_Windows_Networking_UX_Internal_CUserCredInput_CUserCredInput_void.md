# Windows::Networking::UX::Internal::CUserCredInput::~CUserCredInput(void)

- ea: `0x18001db68`
- end: `0x18001dbd2`
- name: `??1CUserCredInput@Internal@UX@Networking@Windows@@UEAA@XZ`
- size: `106`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::CUserCredInput *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001de20`

## callees

- `0x18001b958`
- `0x18001d7f8`
- `0x18001db68`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dbb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dbb7`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::CUserCredInput::~CUserCredInput(
        Windows::Networking::UX::Internal::CUserCredInput *this)
{
  _BYTE *v2; // rdx

  *(_QWORD *)this = &Windows::Networking::UX::Internal::CUserCredInput::`vftable'{for `Microsoft::WRL::Details::Selector<Windows::Networking::UX::Internal::CUserInputType,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Microsoft::WRL::Details::ImplementsMarker<Windows::Networking::UX::Internal::CUserInputType>,IWeakReferenceSource,Windows::Networking::UX::IUserCredInput,Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 3) = &Windows::Networking::UX::Internal::CUserCredInput::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Networking::UX::IUserCredInput,Microsoft::WRL::FtmBase>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Microsoft::WRL::Details::ImplementsMarker<Windows::Networking::UX::Internal::CUserInputType>,IWeakReferenceSource,Windows::Networking::UX::IUserCredInput,Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 4) = &Windows::Networking::UX::Internal::CUserCredInput::`vftable'{for `Windows::Networking::UX::IUserCredInput'};
  *((_QWORD *)this + 5) = &Windows::Networking::UX::Internal::CUserCredInput::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
0x18001db68  push    rbx
0x18001db6a  sub     rsp, 20h
0x18001db6e  mov     rbx, rcx
0x18001db71  lea     rax, ??_7CUserCredInput@Internal@UX@Networking@Windows@@6B?$Selector@VCUserInputType@Internal@UX@Networking@Windows@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCUserInputType@Internal@UX@Networking@Windows@@@Details@23@UIWeakReferenceSource@@UIUserCredInput@UX@Networking@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@@; const Windows::Networking::UX::Internal::CUserCredInput::`vftable'{for `Microsoft::WRL::Details::Selector<Windows::Networking::UX::Internal::CUserInputType,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Microsoft::WRL::Details::ImplementsMarker<Windows::Networking::UX::Internal::CUserInputType>,IWeakReferenceSource,Windows::Networking::UX::IUserCredInput,Microsoft::WRL::FtmBase>>'}
0x18001db78  mov     [rcx], rax
0x18001db7b  lea     rax, ??_7CUserCredInput@Internal@UX@Networking@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIUserCredInput@UX@Networking@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCUserInputType@Internal@UX@Networking@Windows@@@Details@23@UIWeakReferenceSource@@UIUserCredInput@UX@Networking@Windows@@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const Windows::Networking::UX::Internal::CUserCredInput::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Networking::UX::IUserCredInput,Microsoft::WRL::FtmBase>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Microsoft::WRL::Details::ImplementsMarker<Windows::Networking::UX::Internal::CUserInputType>,IWeakReferenceSource,Windows::Networking::UX::IUserCredInput,Microsoft::WRL::FtmBase>>'}
0x18001db82  mov     [rcx+18h], rax
0x18001db86  lea     rax, ??_7CUserCredInput@Internal@UX@Networking@Windows@@6BIUserCredInput@234@@; const Windows::Networking::UX::Internal::CUserCredInput::`vftable'{for `Windows::Networking::UX::IUserCredInput'}
0x18001db8d  mov     [rcx+20h], rax
0x18001db91  lea     rax, ??_7CUserCredInput@Internal@UX@Networking@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Networking::UX::Internal::CUserCredInput::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001db98  mov     [rcx+28h], rax
0x18001db9c  mov     rdx, [rcx+68h]
0x18001dba0  mov     qword ptr [rcx+68h], 0
0x18001dba8  test    rdx, rdx
0x18001dbab  jz      short loc_18001DBB3
0x18001dbad  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18001dbb2  nop
0x18001dbb3  mov     rcx, [rbx+58h]; string
0x18001dbb7  call    cs:__imp_WindowsDeleteString
0x18001dbbd  mov     qword ptr [rbx+58h], 0
0x18001dbc5  mov     rcx, rbx
0x18001dbc8  add     rsp, 20h
0x18001dbcc  pop     rbx
0x18001dbcd  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VCUserInputType@Internal@UX@Networking@Windows@@UIDACredUIInput@678@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CUserInputType,Windows::Networking::UX::IDACredUIInput,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CUserInputType,Windows::Networking::UX::IDACredUIInput,Microsoft::WRL::FtmBase>(void)
```
