# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Microsoft::WRL::Implements<Windows::Networking::UX::ITextInputFactory,Windows::Networking::UX::INetworkLocationInputFactory,Windows::Networking::UX::IUserCredInputFactory,Windows::Networking::UX::IEAPGenericIdentityInputFactory,Windows::Networking::UX::IEAPValidateServerCertInputFactory,Windows::Networking::UX::IPasswordChangeInputFactory,Windows::Networking::UX::IEAPTLSCertSelectInputFactory,Windows::Networking::UX::IEAPSimIdentityInputFactory,Microsoft::WRL::Implements<Windows::Networking::UX::IWcnPinInputFactory,Windows::Networking::UX::IDACredUIInputFactory,Windows::Networking::UX::IRasCredUIInputFactory,Windows::Networking::UX::IRasThirdpartyAuthTokenInputFactory>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::GetIids(ulong *,_GUID * *)

- ea: `0x180008b10`
- end: `0x180008b7a`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@$00$0A@UIActivationFactory@@U?$Implements@UITextInputFactory@UX@Networking@Windows@@UINetworkLocationInputFactory@234@UIUserCredInputFactory@234@UIEAPGenericIdentityInputFactory@234@UIEAPValidateServerCertInputFactory@234@UIPasswordChangeInputFactory@234@UIEAPTLSCertSelectInputFactory@234@UIEAPSimIdentityInputFactory@234@U?$Implements@UIWcnPinInputFactory@UX@Networking@Windows@@UIDACredUIInputFactory@234@UIRasCredUIInputFactory@234@UIRasThirdpartyAuthTokenInputFactory@234@@WRL@Microsoft@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008b80`
- `0x180008b90`
- `0x180008ba0`
- `0x180008bb0`
- `0x180008bc0`
- `0x180008bd0`
- `0x180008be0`
- `0x180008bf0`
- `0x180008c00`
- `0x180008c10`
- `0x180008c20`
- `0x180008c30`

## callees

- `0x180008850`
- `0x180008b10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008b32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008b32`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Microsoft::WRL::Implements<Windows::Networking::UX::ITextInputFactory,Windows::Networking::UX::INetworkLocationInputFactory,Windows::Networking::UX::IUserCredInputFactory,Windows::Networking::UX::IEAPGenericIdentityInputFactory,Windows::Networking::UX::IEAPValidateServerCertInputFactory,Windows::Networking::UX::IPasswordChangeInputFactory,Windows::Networking::UX::IEAPTLSCertSelectInputFactory,Windows::Networking::UX::IEAPSimIdentityInputFactory,Microsoft::WRL::Implements<Windows::Networking::UX::IWcnPinInputFactory,Windows::Networking::UX::IDACredUIInputFactory,Windows::Networking::UX::IRasCredUIInputFactory,Windows::Networking::UX::IRasThirdpartyAuthTokenInputFactory>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0xD0u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 1;
  *v5 = GUID_00000035_0000_0000_c000_000000000046;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Networking::UX::ITextInputFactory,Windows::Networking::UX::INetworkLocationInputFactory,Windows::Networking::UX::IUserCredInputFactory,Windows::Networking::UX::IEAPGenericIdentityInputFactory,Windows::Networking::UX::IEAPValidateServerCertInputFactory,Windows::Networking::UX::IPasswordChangeInputFactory,Windows::Networking::UX::IEAPTLSCertSelectInputFactory,Windows::Networking::UX::IEAPSimIdentityInputFactory,Microsoft::WRL::Implements<Windows::Networking::UX::IWcnPinInputFactory,Windows::Networking::UX::IDACredUIInputFactory,Windows::Networking::UX::IRasCredUIInputFactory,Windows::Networking::UX::IRasThirdpartyAuthTokenInputFactory>>::FillArrayWithIid(
    v6,
    &v9,
    v5);
  *a2 = 13;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x180008b10  mov     [rsp+arg_0], rbx
0x180008b15  push    rdi
0x180008b16  sub     rsp, 20h
0x180008b1a  mov     qword ptr [r8], 0
0x180008b21  mov     ecx, 0D0h; cb
0x180008b26  mov     dword ptr [rdx], 0
0x180008b2c  mov     rbx, r8
0x180008b2f  mov     rdi, rdx
0x180008b32  call    cs:__imp_CoTaskMemAlloc
0x180008b38  mov     r8, rax
0x180008b3b  test    rax, rax
0x180008b3e  jnz     short loc_180008B47
0x180008b40  mov     eax, 8007000Eh
0x180008b45  jmp     short loc_180008B6F
0x180008b47  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x180008b4e  lea     rdx, [rsp+28h+arg_8]
0x180008b53  mov     [rsp+28h+arg_8], 1
0x180008b5b  movdqu  xmmword ptr [rax], xmm0
0x180008b5f  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UITextInputFactory@UX@Networking@Windows@@UINetworkLocationInputFactory@567@UIUserCredInputFactory@567@UIEAPGenericIdentityInputFactory@567@UIEAPValidateServerCertInputFactory@567@UIPasswordChangeInputFactory@567@UIEAPTLSCertSelectInputFactory@567@UIEAPSimIdentityInputFactory@567@U?$Implements@UIWcnPinInputFactory@UX@Networking@Windows@@UIDACredUIInputFactory@234@UIRasCredUIInputFactory@234@UIRasThirdpartyAuthTokenInputFactory@234@@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Networking::UX::ITextInputFactory,Windows::Networking::UX::INetworkLocationInputFactory,Windows::Networking::UX::IUserCredInputFactory,Windows::Networking::UX::IEAPGenericIdentityInputFactory,Windows::Networking::UX::IEAPValidateServerCertInputFactory,Windows::Networking::UX::IPasswordChangeInputFactory,Windows::Networking::UX::IEAPTLSCertSelectInputFactory,Windows::Networking::UX::IEAPSimIdentityInputFactory,Microsoft::WRL::Implements<Windows::Networking::UX::IWcnPinInputFactory,Windows::Networking::UX::IDACredUIInputFactory,Windows::Networking::UX::IRasCredUIInputFactory,Windows::Networking::UX::IRasThirdpartyAuthTokenInputFactory>>::FillArrayWithIid(ulong *,_GUID *)
0x180008b64  mov     dword ptr [rdi], 0Dh
0x180008b6a  xor     eax, eax
0x180008b6c  mov     [rbx], r8
0x180008b6f  mov     rbx, [rsp+28h+arg_0]
0x180008b74  add     rsp, 20h
0x180008b78  pop     rdi
0x180008b79  retn
```
