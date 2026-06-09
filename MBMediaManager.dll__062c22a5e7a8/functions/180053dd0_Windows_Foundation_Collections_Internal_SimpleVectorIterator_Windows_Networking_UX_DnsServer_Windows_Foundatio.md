# Windows::Foundation::Collections::Internal::SimpleVectorIterator<Windows::Networking::UX::DnsServer,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,XWinRT::IntVersionTag,1>::GetIids(ulong *,_GUID * *)

- ea: `0x180053dd0`
- end: `0x180053e2f`
- name: `?GetIids@?$SimpleVectorIterator@UDnsServer@UX@Networking@Windows@@V?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@4@UDnsServerLifetimePredicate@6234@UIntVersionTag@XWinRT@@$00@Internal@Collections@Foundation@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180053a38`
- `0x180053dd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053df2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053df2`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::SimpleVectorIterator<Windows::Networking::UX::DnsServer,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,XWinRT::IntVersionTag,1>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IIterator<Windows::Networking::UX::DnsServer>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &v9,
    v6);
  *a2 = 2;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x180053dd0  mov     [rsp+arg_0], rbx
0x180053dd5  push    rdi
0x180053dd6  sub     rsp, 20h
0x180053dda  mov     qword ptr [r8], 0
0x180053de1  mov     ecx, 20h ; ' '; cb
0x180053de6  mov     dword ptr [rdx], 0
0x180053dec  mov     rbx, r8
0x180053def  mov     rdi, rdx
0x180053df2  call    cs:__imp_CoTaskMemAlloc
0x180053df8  mov     r8, rax
0x180053dfb  test    rax, rax
0x180053dfe  jnz     short loc_180053E07
0x180053e00  mov     eax, 8007000Eh
0x180053e05  jmp     short loc_180053E24
0x180053e07  lea     rdx, [rsp+28h+arg_8]
0x180053e0c  mov     [rsp+28h+arg_8], 0
0x180053e14  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@U?$IIterator@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IIterator<Windows::Networking::UX::DnsServer>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180053e19  mov     dword ptr [rdi], 2
0x180053e1f  xor     eax, eax
0x180053e21  mov     [rbx], r8
0x180053e24  mov     rbx, [rsp+28h+arg_0]
0x180053e29  add     rsp, 20h
0x180053e2d  pop     rdi
0x180053e2e  retn
```
