# Windows::Networking::UX::Internal::CEAPTLSCertSelectInput::~CEAPTLSCertSelectInput(void)

- ea: `0x18001d97c`
- end: `0x18001d9bb`
- name: `??1CEAPTLSCertSelectInput@Internal@UX@Networking@Windows@@UEAA@XZ`
- size: `63`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::CEAPTLSCertSelectInput *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001dce0`

## callees

- `0x18001b958`
- `0x18001d7f8`
- `0x18001d97c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d9a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d9a0`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::CEAPTLSCertSelectInput::~CEAPTLSCertSelectInput(
        Windows::Networking::UX::Internal::CEAPTLSCertSelectInput *this)
{
  _BYTE *v2; // rdx

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
0x18001d97c  push    rbx
0x18001d97e  sub     rsp, 20h
0x18001d982  mov     rbx, rcx
0x18001d985  mov     rdx, [rcx+70h]
0x18001d989  mov     qword ptr [rcx+70h], 0
0x18001d991  test    rdx, rdx
0x18001d994  jz      short loc_18001D99C
0x18001d996  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18001d99b  nop
0x18001d99c  mov     rcx, [rbx+60h]; string
0x18001d9a0  call    cs:__imp_WindowsDeleteString
0x18001d9a6  mov     qword ptr [rbx+60h], 0
0x18001d9ae  mov     rcx, rbx
0x18001d9b1  add     rsp, 20h
0x18001d9b5  pop     rbx
0x18001d9b6  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VCUserInputType@Internal@UX@Networking@Windows@@UIDACredUIInput@678@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CUserInputType,Windows::Networking::UX::IDACredUIInput,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CUserInputType,Windows::Networking::UX::IDACredUIInput,Microsoft::WRL::FtmBase>(void)
```
