# Microsoft::WRL::Details::MakeAndInitialize<CredUXParameters,Windows::Internal::UI::Credentials::Controller::ICredUXParameters,CredUXParametersBlob *,Windows::Internal::UI::Credentials::Controller::ICredUXExtension * &,Windows::Internal::UI::Credentials::Controller::IConsentUXContext * &,Windows::Internal::UI::Credentials::Controller::ICredUXSecurePrompt * &>(Windows::Internal::UI::Credentials::Controller::ICredUXParameters * *,CredUXParametersBlob * &&,Windows::Internal::UI::Credentials::Controller::ICredUXExtension * &,Windows::Internal::UI::Credentials::Controller::IConsentUXContext * &,Windows::Internal::UI::Credentials::Controller::ICredUXSecurePrompt * &)

- ea: `0x140005d0c`
- end: `0x140005dcd`
- name: `??$MakeAndInitialize@VCredUXParameters@@UICredUXParameters@Controller@Credentials@UI@Internal@Windows@@PEAUCredUXParametersBlob@@AEAPEAUICredUXExtension@34567@AEAPEAUIConsentUXContext@34567@AEAPEAUICredUXSecurePrompt@34567@@Details@WRL@Microsoft@@YAJPEAPEAUICredUXParameters@Controller@Credentials@UI@Internal@Windows@@$$QEAPEAUCredUXParametersBlob@@AEAPEAUICredUXExtension@45678@AEAPEAUIConsentUXContext@45678@AEAPEAUICredUXSecurePrompt@45678@@Z`
- size: `193`
- prototype: `__int64 __fastcall(_QWORD *, struct CredUXParametersBlob **, struct Windows::Internal::UI::Credentials::Controller::ICredUXExtension **, struct Windows::Internal::UI::Credentials::Controller::IConsentUXContext **, struct Windows::Internal::UI::Credentials::Controller::ICredUXSecurePrompt **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000af00`

## callees

- `0x140003644`
- `0x140004bf4`
- `0x140005d0c`
- `0x1400081e4`
- `0x140008920`
- `0x140012b00`
- `0x140013ae4`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CredUXParameters,Windows::Internal::UI::Credentials::Controller::ICredUXParameters,CredUXParametersBlob *,Windows::Internal::UI::Credentials::Controller::ICredUXExtension * &,Windows::Internal::UI::Credentials::Controller::IConsentUXContext * &,Windows::Internal::UI::Credentials::Controller::ICredUXSecurePrompt * &>(
        _QWORD *a1,
        struct CredUXParametersBlob **a2,
        struct Windows::Internal::UI::Credentials::Controller::ICredUXExtension **a3,
        struct Windows::Internal::UI::Credentials::Controller::IConsentUXContext **a4,
        struct Windows::Internal::UI::Credentials::Controller::ICredUXSecurePrompt **a5)
{
  CredUXParameters *v9; // rax
  int v10; // edi
  CredUXParameters *v11; // rbx
  struct Windows::Internal::UI::Credentials::Controller::IConsentUXContext *v12; // r9
  struct Windows::Internal::UI::Credentials::Controller::ICredUXExtension *v13; // r8
  CredUXParameters *v15; // [rsp+50h] [rbp+8h] BYREF

  *a1 = 0;
  v9 = (CredUXParameters *)operator new(0x128u, (const struct std::nothrow_t *)&std::nothrow);
  v15 = v9;
  if ( v9 )
  {
    v11 = CredUXParameters::CredUXParameters(v9);
    v12 = *a4;
    v13 = *a3;
    v15 = 0;
    v10 = CredUXParameters::RuntimeClassInitialize(v11, *a2, v13, v12, *a5);
    if ( v10 >= 0 )
      v10 = Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::UI::Credentials::Controller::ICredUXParameters,Microsoft::WRL::FtmBase>>(
              v11,
              &GUID_e3add5fc_628c_4af1_ac29_7947e28b8d66,
              a1);
    if ( v11 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::UI::Credentials::Controller::ICredUXParameters,Microsoft::WRL::FtmBase>::Release(v11);
  }
  else
  {
    v10 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>(&v15);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140005d0c  mov     [rsp+arg_8], rbx
0x140005d11  mov     [rsp+arg_10], rsi
0x140005d16  push    rdi
0x140005d17  push    r14
0x140005d19  push    r15
0x140005d1b  sub     rsp, 30h
0x140005d1f  mov     r15, rdx
0x140005d22  mov     qword ptr [rcx], 0
0x140005d29  mov     rsi, rcx
0x140005d2c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140005d33  mov     ecx, 128h; unsigned __int64
0x140005d38  mov     rdi, r9
0x140005d3b  mov     r14, r8
0x140005d3e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140005d43  mov     [rsp+48h+arg_0], rax
0x140005d48  test    rax, rax
0x140005d4b  jnz     short loc_140005D54
0x140005d4d  mov     edi, 8007000Eh
0x140005d52  jmp     short loc_140005DAD
0x140005d54  mov     rcx, rax; this
0x140005d57  call    ??0CredUXParameters@@QEAA@XZ; CredUXParameters::CredUXParameters(void)
0x140005d5c  mov     rcx, [rsp+48h+arg_20]
0x140005d61  mov     rbx, rax
0x140005d64  mov     r9, [rdi]; struct Windows::Internal::UI::Credentials::Controller::IConsentUXContext *
0x140005d67  mov     r8, [r14]; struct Windows::Internal::UI::Credentials::Controller::ICredUXExtension *
0x140005d6a  mov     [rsp+48h+arg_0], 0
0x140005d73  mov     rdx, [rcx]
0x140005d76  mov     rcx, rax; this
0x140005d79  mov     [rsp+48h+var_28], rdx; struct Windows::Internal::UI::Credentials::Controller::ICredUXSecurePrompt *
0x140005d7e  mov     rdx, [r15]; struct CredUXParametersBlob *
0x140005d81  call    ?RuntimeClassInitialize@CredUXParameters@@QEAAJPEAUCredUXParametersBlob@@PEAUICredUXExtension@Controller@Credentials@UI@Internal@Windows@@PEAUIConsentUXContext@45678@PEAUICredUXSecurePrompt@45678@@Z; CredUXParameters::RuntimeClassInitialize(CredUXParametersBlob *,Windows::Internal::UI::Credentials::Controller::ICredUXExtension *,Windows::Internal::UI::Credentials::Controller::IConsentUXContext *,Windows::Internal::UI::Credentials::Controller::ICredUXSecurePrompt *)
0x140005d86  mov     edi, eax
0x140005d88  test    eax, eax
0x140005d8a  js      short loc_140005DA0
0x140005d8c  mov     r8, rsi
0x140005d8f  lea     rdx, _GUID_e3add5fc_628c_4af1_ac29_7947e28b8d66
0x140005d96  mov     rcx, rbx
0x140005d99  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UICredUXParameters@Controller@Credentials@UI@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UICredUXParameters@Controller@Credentials@UI@Internal@Windows@@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::UI::Credentials::Controller::ICredUXParameters,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::UI::Credentials::Controller::ICredUXParameters,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x140005d9e  mov     edi, eax
0x140005da0  test    rbx, rbx
0x140005da3  jz      short loc_140005DAD
0x140005da5  mov     rcx, rbx
0x140005da8  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UICredUXParameters@Controller@Credentials@UI@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::UI::Credentials::Controller::ICredUXParameters,Microsoft::WRL::FtmBase>::Release(void)
0x140005dad  lea     rcx, [rsp+48h+arg_0]
0x140005db2  call    ??1?$MakeAllocator@V?$SimpleClassFactory@VCCredUIBrokerForNonAppContainersFailedMip@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>(void)
0x140005db7  mov     rbx, [rsp+48h+arg_8]
0x140005dbc  mov     eax, edi
0x140005dbe  mov     rsi, [rsp+48h+arg_10]
0x140005dc3  add     rsp, 30h
0x140005dc7  pop     r15
0x140005dc9  pop     r14
0x140005dcb  pop     rdi
0x140005dcc  retn
```
