# Windows::Foundation::Collections::Internal::SimpleVectorView<IUnknown *,Windows::Foundation::Collections::Internal::Vector<IUnknown *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IUnknown *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IUnknown *>,Windows::Foundation::Collections::Internal::VectorOptions<IUnknown *,0,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IUnknown *>,XWinRT::IntVersionTag,1>::GetIids(ulong *,_GUID * *)

- ea: `0x180039010`
- end: `0x18003907a`
- name: `?GetIids@?$SimpleVectorView@PEAUIUnknown@@V?$Vector@PEAUIUnknown@@U?$DefaultEqualityPredicate@PEAUIUnknown@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIUnknown@@@3456@U?$VectorOptions@PEAUIUnknown@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIUnknown@@@3456@UIntVersionTag@XWinRT@@$00@Internal@Collections@Foundation@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180039080`

## callees

- `0x180038b6c`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039032`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039032`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::SimpleVectorView<IUnknown *,Windows::Foundation::Collections::Internal::Vector<IUnknown *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IUnknown *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IUnknown *>,Windows::Foundation::Collections::Internal::VectorOptions<IUnknown *,0,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IUnknown *>,XWinRT::IntVersionTag,1>::GetIids(
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
  *v5 = GUID_a63034be_3e54_5b5a_9794_87c9735b31a5;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<IUnknown *>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x180039010  mov     [rsp+arg_0], rbx
0x180039015  push    rdi
0x180039016  sub     rsp, 20h
0x18003901a  mov     qword ptr [r8], 0
0x180039021  mov     ecx, 30h ; '0'; cb
0x180039026  mov     dword ptr [rdx], 0
0x18003902c  mov     rbx, r8
0x18003902f  mov     rdi, rdx
0x180039032  call    cs:__imp_CoTaskMemAlloc
0x180039038  mov     r8, rax
0x18003903b  test    rax, rax
0x18003903e  jnz     short loc_180039047
0x180039040  mov     eax, 8007000Eh
0x180039045  jmp     short loc_18003906F
0x180039047  movups  xmm0, xmmword ptr cs:_GUID_a63034be_3e54_5b5a_9794_87c9735b31a5.Data1
0x18003904e  lea     rdx, [rsp+28h+arg_8]
0x180039053  mov     [rsp+28h+arg_8], 1
0x18003905b  movdqu  xmmword ptr [rax], xmm0
0x18003905f  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$IIterable@PEAUIUnknown@@@Collections@Foundation@Windows@@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<IUnknown *>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180039064  mov     dword ptr [rdi], 3
0x18003906a  xor     eax, eax
0x18003906c  mov     [rbx], r8
0x18003906f  mov     rbx, [rsp+28h+arg_0]
0x180039074  add     rsp, 20h
0x180039078  pop     rdi
0x180039079  retn
```
