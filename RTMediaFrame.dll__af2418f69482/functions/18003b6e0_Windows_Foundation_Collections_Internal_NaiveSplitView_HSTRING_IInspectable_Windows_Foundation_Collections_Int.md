# Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::SplitIterator::GetIids(ulong *,_GUID * *)

- ea: `0x18003b6e0`
- end: `0x18003b73f`
- name: `?GetIids@SplitIterator@?$NaiveSplitView@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18003b158`
- `0x18003b6e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b702`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b702`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::SplitIterator::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x18003b6e0  mov     [rsp+arg_0], rbx
0x18003b6e5  push    rdi
0x18003b6e6  sub     rsp, 20h
0x18003b6ea  mov     qword ptr [r8], 0
0x18003b6f1  mov     ecx, 20h ; ' '; cb
0x18003b6f6  mov     dword ptr [rdx], 0
0x18003b6fc  mov     rbx, r8
0x18003b6ff  mov     rdi, rdx
0x18003b702  call    cs:__imp_CoTaskMemAlloc
0x18003b708  mov     r8, rax
0x18003b70b  test    rax, rax
0x18003b70e  jnz     short loc_18003B717
0x18003b710  mov     eax, 8007000Eh
0x18003b715  jmp     short loc_18003B734
0x18003b717  lea     rdx, [rsp+28h+arg_8]
0x18003b71c  mov     [rsp+28h+arg_8], 0
0x18003b724  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@U?$IIterator@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18003b729  mov     dword ptr [rdi], 2
0x18003b72f  xor     eax, eax
0x18003b731  mov     [rbx], r8
0x18003b734  mov     rbx, [rsp+28h+arg_0]
0x18003b739  add     rsp, 20h
0x18003b73d  pop     rdi
0x18003b73e  retn
```
