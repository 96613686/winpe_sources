# Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::MbOperatorInfo,Windows::Networking::UX::Internal::MboEqualityPredicate,Windows::Networking::UX::Internal::MboLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::MbOperatorInfo,0,1,0>>::GetIids(ulong *,_GUID * *)

- ea: `0x18003d990`
- end: `0x18003d9fa`
- name: `?GetIids@?$Vector@UMbOperatorInfo@UX@Networking@Windows@@UMboEqualityPredicate@Internal@234@UMboLifetimePredicate@6234@U?$VectorOptions@UMbOperatorInfo@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003da00`

## callees

- `0x18003d374`
- `0x18003d990`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d9b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d9b2`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::MbOperatorInfo,Windows::Networking::UX::Internal::MboEqualityPredicate,Windows::Networking::UX::Internal::MboLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::MbOperatorInfo,0,1,0>>::GetIids(
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
  *v5 = GUID_5e042397_774c_5c83_9706_eed8f3c5952b;
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
0x18003d990  mov     [rsp+arg_0], rbx
0x18003d995  push    rdi
0x18003d996  sub     rsp, 20h
0x18003d99a  mov     qword ptr [r8], 0
0x18003d9a1  mov     ecx, 30h ; '0'; cb
0x18003d9a6  mov     dword ptr [rdx], 0
0x18003d9ac  mov     rbx, r8
0x18003d9af  mov     rdi, rdx
0x18003d9b2  call    cs:__imp_CoTaskMemAlloc
0x18003d9b8  mov     r8, rax
0x18003d9bb  test    rax, rax
0x18003d9be  jnz     short loc_18003D9C7
0x18003d9c0  mov     eax, 8007000Eh
0x18003d9c5  jmp     short loc_18003D9EF
0x18003d9c7  movups  xmm0, xmmword ptr cs:_GUID_5e042397_774c_5c83_9706_eed8f3c5952b.Data1
0x18003d9ce  lea     rdx, [rsp+28h+arg_8]
0x18003d9d3  mov     [rsp+28h+arg_8], 1
0x18003d9db  movdqu  xmmword ptr [rax], xmm0
0x18003d9df  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$IIterable@UMbOperatorInfo@UX@Networking@Windows@@@Collections@Foundation@Windows@@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Networking::UX::MbOperatorInfo>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18003d9e4  mov     dword ptr [rdi], 3
0x18003d9ea  xor     eax, eax
0x18003d9ec  mov     [rbx], r8
0x18003d9ef  mov     rbx, [rsp+28h+arg_0]
0x18003d9f4  add     rsp, 20h
0x18003d9f8  pop     rdi
0x18003d9f9  retn
```
