# Windows::Foundation::Collections::Internal::SimpleVectorIterator<IUnknown *,Windows::Foundation::Collections::Internal::Vector<IUnknown *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IUnknown *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IUnknown *>,Windows::Foundation::Collections::Internal::VectorOptions<IUnknown *,0,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IUnknown *>,XWinRT::IntVersionTag,1>::GetIids(ulong *,_GUID * *)

- ea: `0x180038fa0`
- end: `0x180038fff`
- name: `?GetIids@?$SimpleVectorIterator@PEAUIUnknown@@V?$Vector@PEAUIUnknown@@U?$DefaultEqualityPredicate@PEAUIUnknown@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIUnknown@@@3456@U?$VectorOptions@PEAUIUnknown@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIUnknown@@@3456@UIntVersionTag@XWinRT@@$00@Internal@Collections@Foundation@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180038bb0`
- `0x180038fa0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038fc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038fc2`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::SimpleVectorIterator<IUnknown *,Windows::Foundation::Collections::Internal::Vector<IUnknown *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IUnknown *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IUnknown *>,Windows::Foundation::Collections::Internal::VectorOptions<IUnknown *,0,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IUnknown *>,XWinRT::IntVersionTag,1>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IIterator<IUnknown *>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x180038fa0  mov     [rsp+arg_0], rbx
0x180038fa5  push    rdi
0x180038fa6  sub     rsp, 20h
0x180038faa  mov     qword ptr [r8], 0
0x180038fb1  mov     ecx, 20h ; ' '; cb
0x180038fb6  mov     dword ptr [rdx], 0
0x180038fbc  mov     rbx, r8
0x180038fbf  mov     rdi, rdx
0x180038fc2  call    cs:__imp_CoTaskMemAlloc
0x180038fc8  mov     r8, rax
0x180038fcb  test    rax, rax
0x180038fce  jnz     short loc_180038FD7
0x180038fd0  mov     eax, 8007000Eh
0x180038fd5  jmp     short loc_180038FF4
0x180038fd7  lea     rdx, [rsp+28h+arg_8]
0x180038fdc  mov     [rsp+28h+arg_8], 0
0x180038fe4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@U?$IIterator@PEAUIUnknown@@@Collections@Foundation@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IIterator<IUnknown *>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180038fe9  mov     dword ptr [rdi], 2
0x180038fef  xor     eax, eax
0x180038ff1  mov     [rbx], r8
0x180038ff4  mov     rbx, [rsp+28h+arg_0]
0x180038ff9  add     rsp, 20h
0x180038ffd  pop     rdi
0x180038ffe  retn
```
