# Windows::Foundation::Collections::Internal::SimpleVectorView<Windows::Networking::UX::DnsServer,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,XWinRT::IntVersionTag,1>::GetIids(ulong *,_GUID * *)

- ea: `0x180053e40`
- end: `0x180053eaa`
- name: `?GetIids@?$SimpleVectorView@UDnsServer@UX@Networking@Windows@@V?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@4@UDnsServerLifetimePredicate@6234@UIntVersionTag@XWinRT@@$00@Internal@Collections@Foundation@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180053eb0`

## callees

- `0x180053a14`
- `0x180053e40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053e62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053e62`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::SimpleVectorView<Windows::Networking::UX::DnsServer,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,XWinRT::IntVersionTag,1>::GetIids(
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
  *v5 = GUID_f478e5b0_6967_5571_b9d4_67c3b38c80b8;
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
0x180053e40  mov     [rsp+arg_0], rbx
0x180053e45  push    rdi
0x180053e46  sub     rsp, 20h
0x180053e4a  mov     qword ptr [r8], 0
0x180053e51  mov     ecx, 30h ; '0'; cb
0x180053e56  mov     dword ptr [rdx], 0
0x180053e5c  mov     rbx, r8
0x180053e5f  mov     rdi, rdx
0x180053e62  call    cs:__imp_CoTaskMemAlloc
0x180053e68  mov     r8, rax
0x180053e6b  test    rax, rax
0x180053e6e  jnz     short loc_180053E77
0x180053e70  mov     eax, 8007000Eh
0x180053e75  jmp     short loc_180053E9F
0x180053e77  movups  xmm0, xmmword ptr cs:_GUID_f478e5b0_6967_5571_b9d4_67c3b38c80b8.Data1
0x180053e7e  lea     rdx, [rsp+28h+arg_8]
0x180053e83  mov     [rsp+28h+arg_8], 1
0x180053e8b  movdqu  xmmword ptr [rax], xmm0
0x180053e8f  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$IIterable@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Networking::UX::DnsServer>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180053e94  mov     dword ptr [rdi], 3
0x180053e9a  xor     eax, eax
0x180053e9c  mov     [rbx], r8
0x180053e9f  mov     rbx, [rsp+28h+arg_0]
0x180053ea4  add     rsp, 20h
0x180053ea8  pop     rdi
0x180053ea9  retn
```
