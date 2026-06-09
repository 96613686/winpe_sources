# Windows::Foundation::Collections::Internal::SimpleVectorIterator<Windows::Networking::UX::DnsServer,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,XWinRT::IntVersionTag,1>::GetIids(ulong *,_GUID * *)

- ea: `0x180015050`
- end: `0x1800150af`
- name: `?GetIids@?$SimpleVectorIterator@UDnsServer@UX@Networking@Windows@@V?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@4@UDnsServerLifetimePredicate@6234@UIntVersionTag@XWinRT@@$00@Internal@Collections@Foundation@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180013fd4`
- `0x180015050`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015072`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015072`

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
0x180015050  mov     [rsp+arg_0], rbx
0x180015055  push    rdi
0x180015056  sub     rsp, 20h
0x18001505a  mov     qword ptr [r8], 0
0x180015061  mov     ecx, 20h ; ' '; cb
0x180015066  mov     dword ptr [rdx], 0
0x18001506c  mov     rbx, r8
0x18001506f  mov     rdi, rdx
0x180015072  call    cs:__imp_CoTaskMemAlloc
0x180015078  mov     r8, rax
0x18001507b  test    rax, rax
0x18001507e  jnz     short loc_180015087
0x180015080  mov     eax, 8007000Eh
0x180015085  jmp     short loc_1800150A4
0x180015087  lea     rdx, [rsp+28h+arg_8]
0x18001508c  mov     [rsp+28h+arg_8], 0
0x180015094  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@U?$IIterator@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IIterator<Windows::Networking::UX::DnsServer>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180015099  mov     dword ptr [rdi], 2
0x18001509f  xor     eax, eax
0x1800150a1  mov     [rbx], r8
0x1800150a4  mov     rbx, [rsp+28h+arg_0]
0x1800150a9  add     rsp, 20h
0x1800150ad  pop     rdi
0x1800150ae  retn
```
