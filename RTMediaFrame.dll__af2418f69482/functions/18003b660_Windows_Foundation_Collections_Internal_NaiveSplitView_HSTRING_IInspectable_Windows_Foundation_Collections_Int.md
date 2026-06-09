# Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::GetIids(ulong *,_GUID * *)

- ea: `0x18003b660`
- end: `0x18003b6ca`
- name: `?GetIids@?$NaiveSplitView@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003b6d0`

## callees

- `0x18003b134`
- `0x18003b660`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b682`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b682`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::GetIids(
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
  *v5 = GUID_bb78502a_f79d_54fa_92c9_90c5039fdf7e;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x18003b660  mov     [rsp+arg_0], rbx
0x18003b665  push    rdi
0x18003b666  sub     rsp, 20h
0x18003b66a  mov     qword ptr [r8], 0
0x18003b671  mov     ecx, 30h ; '0'; cb
0x18003b676  mov     dword ptr [rdx], 0
0x18003b67c  mov     rbx, r8
0x18003b67f  mov     rdi, rdx
0x18003b682  call    cs:__imp_CoTaskMemAlloc
0x18003b688  mov     r8, rax
0x18003b68b  test    rax, rax
0x18003b68e  jnz     short loc_18003B697
0x18003b690  mov     eax, 8007000Eh
0x18003b695  jmp     short loc_18003B6BF
0x18003b697  movups  xmm0, xmmword ptr cs:_GUID_bb78502a_f79d_54fa_92c9_90c5039fdf7e.Data1
0x18003b69e  lea     rdx, [rsp+28h+arg_8]
0x18003b6a3  mov     [rsp+28h+arg_8], 1
0x18003b6ab  movdqu  xmmword ptr [rax], xmm0
0x18003b6af  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18003b6b4  mov     dword ptr [rdi], 3
0x18003b6ba  xor     eax, eax
0x18003b6bc  mov     [rbx], r8
0x18003b6bf  mov     rbx, [rsp+28h+arg_0]
0x18003b6c4  add     rsp, 20h
0x18003b6c8  pop     rdi
0x18003b6c9  retn
```
