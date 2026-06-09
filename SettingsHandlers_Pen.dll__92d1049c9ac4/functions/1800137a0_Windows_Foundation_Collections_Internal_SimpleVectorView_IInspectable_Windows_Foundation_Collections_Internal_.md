# Windows::Foundation::Collections::Internal::SimpleVectorView<IInspectable *,Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,XWinRT::IntVersionTag,1>::GetIids(ulong *,_GUID * *)

- ea: `0x1800137a0`
- end: `0x18001380a`
- name: `?GetIids@?$SimpleVectorView@PEAUIInspectable@@V?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@UIntVersionTag@XWinRT@@$00@Internal@Collections@Foundation@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013810`

## callees

- `0x180012fac`
- `0x1800137a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800137c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800137c2`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::SimpleVectorView<IInspectable *,Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,XWinRT::IntVersionTag,1>::GetIids(
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
  *v5 = GUID_a6487363_b074_5c60_ab16_866dce4ee54d;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<IInspectable *>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x1800137a0  mov     [rsp+arg_0], rbx
0x1800137a5  push    rdi
0x1800137a6  sub     rsp, 20h
0x1800137aa  mov     qword ptr [r8], 0
0x1800137b1  mov     ecx, 30h ; '0'; cb
0x1800137b6  mov     dword ptr [rdx], 0
0x1800137bc  mov     rbx, r8
0x1800137bf  mov     rdi, rdx
0x1800137c2  call    cs:__imp_CoTaskMemAlloc
0x1800137c8  mov     r8, rax
0x1800137cb  test    rax, rax
0x1800137ce  jnz     short loc_1800137D7
0x1800137d0  mov     eax, 8007000Eh
0x1800137d5  jmp     short loc_1800137FF
0x1800137d7  movups  xmm0, xmmword ptr cs:_GUID_a6487363_b074_5c60_ab16_866dce4ee54d.Data1
0x1800137de  lea     rdx, [rsp+28h+arg_8]
0x1800137e3  mov     [rsp+28h+arg_8], 1
0x1800137eb  movdqu  xmmword ptr [rax], xmm0
0x1800137ef  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$IIterable@PEAUIInspectable@@@Collections@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<IInspectable *>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800137f4  mov     dword ptr [rdi], 3
0x1800137fa  xor     eax, eax
0x1800137fc  mov     [rbx], r8
0x1800137ff  mov     rbx, [rsp+28h+arg_0]
0x180013804  add     rsp, 20h
0x180013808  pop     rdi
0x180013809  retn
```
