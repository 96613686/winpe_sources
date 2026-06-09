# Windows::Foundation::Collections::Internal::SimpleVectorView<Windows::Networking::UX::MbOperatorInfo,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::MbOperatorInfo,Windows::Networking::UX::Internal::MboEqualityPredicate,Windows::Networking::UX::Internal::MboLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::MbOperatorInfo,0,1,0>>,Windows::Networking::UX::Internal::MboLifetimePredicate,XWinRT::IntVersionTag,1>::GetIids(ulong *,_GUID * *)

- ea: `0x18003d7e0`
- end: `0x18003d84a`
- name: `?GetIids@?$SimpleVectorView@UMbOperatorInfo@UX@Networking@Windows@@V?$Vector@UMbOperatorInfo@UX@Networking@Windows@@UMboEqualityPredicate@Internal@234@UMboLifetimePredicate@6234@U?$VectorOptions@UMbOperatorInfo@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@4@UMboLifetimePredicate@6234@UIntVersionTag@XWinRT@@$00@Internal@Collections@Foundation@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003d850`

## callees

- `0x18003d374`
- `0x18003d7e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d802`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d802`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::SimpleVectorView<Windows::Networking::UX::MbOperatorInfo,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::MbOperatorInfo,Windows::Networking::UX::Internal::MboEqualityPredicate,Windows::Networking::UX::Internal::MboLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::MbOperatorInfo,0,1,0>>,Windows::Networking::UX::Internal::MboLifetimePredicate,XWinRT::IntVersionTag,1>::GetIids(
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
  *v5 = GUID_c978465e_eabf_5de8_aa48_c64ce1db06a2;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Networking::UX::MbOperatorInfo>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x18003d7e0  mov     [rsp+arg_0], rbx
0x18003d7e5  push    rdi
0x18003d7e6  sub     rsp, 20h
0x18003d7ea  mov     qword ptr [r8], 0
0x18003d7f1  mov     ecx, 30h ; '0'; cb
0x18003d7f6  mov     dword ptr [rdx], 0
0x18003d7fc  mov     rbx, r8
0x18003d7ff  mov     rdi, rdx
0x18003d802  call    cs:__imp_CoTaskMemAlloc
0x18003d808  mov     r8, rax
0x18003d80b  test    rax, rax
0x18003d80e  jnz     short loc_18003D817
0x18003d810  mov     eax, 8007000Eh
0x18003d815  jmp     short loc_18003D83F
0x18003d817  movups  xmm0, xmmword ptr cs:_GUID_c978465e_eabf_5de8_aa48_c64ce1db06a2.Data1
0x18003d81e  lea     rdx, [rsp+28h+arg_8]
0x18003d823  mov     [rsp+28h+arg_8], 1
0x18003d82b  movdqu  xmmword ptr [rax], xmm0
0x18003d82f  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$IIterable@UMbOperatorInfo@UX@Networking@Windows@@@Collections@Foundation@Windows@@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Networking::UX::MbOperatorInfo>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18003d834  mov     dword ptr [rdi], 3
0x18003d83a  xor     eax, eax
0x18003d83c  mov     [rbx], r8
0x18003d83f  mov     rbx, [rsp+28h+arg_0]
0x18003d844  add     rsp, 20h
0x18003d848  pop     rdi
0x18003d849  retn
```
