# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::Collections::IVector<Windows::Networking::UX::DnsServer>,Windows::Foundation::Collections::IIterable<Windows::Networking::UX::DnsServer>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x180053f30`
- end: `0x180053f9a`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$IVector@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@U?$IIterable@UDnsServer@UX@Networking@Windows@@@567@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180053fa0`

## callees

- `0x180053a14`
- `0x180053f30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053f52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053f52`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::Collections::IVector<Windows::Networking::UX::DnsServer>,Windows::Foundation::Collections::IIterable<Windows::Networking::UX::DnsServer>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::GetIids(
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
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 1;
  *v5 = GUID_4ccaced4_1e75_5ac2_8666_85e9d31aa703;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Networking::UX::DnsServer>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v6,
    &v9,
    v5);
  *a2 = 3;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x180053f30  mov     [rsp+arg_0], rbx
0x180053f35  push    rdi
0x180053f36  sub     rsp, 20h
0x180053f3a  mov     qword ptr [r8], 0
0x180053f41  mov     ecx, 30h ; '0'; cb
0x180053f46  mov     dword ptr [rdx], 0
0x180053f4c  mov     rbx, r8
0x180053f4f  mov     rdi, rdx
0x180053f52  call    cs:__imp_CoTaskMemAlloc
0x180053f58  mov     r8, rax
0x180053f5b  test    rax, rax
0x180053f5e  jnz     short loc_180053F67
0x180053f60  mov     eax, 8007000Eh
0x180053f65  jmp     short loc_180053F8F
0x180053f67  movups  xmm0, xmmword ptr cs:_GUID_4ccaced4_1e75_5ac2_8666_85e9d31aa703.Data1
0x180053f6e  lea     rdx, [rsp+28h+arg_8]
0x180053f73  mov     [rsp+28h+arg_8], 1
0x180053f7b  movdqu  xmmword ptr [rax], xmm0
0x180053f7f  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$IIterable@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Networking::UX::DnsServer>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180053f84  mov     dword ptr [rdi], 3
0x180053f8a  xor     eax, eax
0x180053f8c  mov     [rbx], r8
0x180053f8f  mov     rbx, [rsp+28h+arg_0]
0x180053f94  add     rsp, 20h
0x180053f98  pop     rdi
0x180053f99  retn
```
