# Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,1>::GetIids(ulong *,_GUID * *)

- ea: `0x18003b750`
- end: `0x18003b7af`
- name: `?GetIids@?$SimpleKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@$00@Internal@Collections@Foundation@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18003b17c`
- `0x18003b750`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b772`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b772`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,1>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x18003b750  mov     [rsp+arg_0], rbx
0x18003b755  push    rdi
0x18003b756  sub     rsp, 20h
0x18003b75a  mov     qword ptr [r8], 0
0x18003b761  mov     ecx, 20h ; ' '; cb
0x18003b766  mov     dword ptr [rdx], 0
0x18003b76c  mov     rbx, r8
0x18003b76f  mov     rdi, rdx
0x18003b772  call    cs:__imp_CoTaskMemAlloc
0x18003b778  mov     r8, rax
0x18003b77b  test    rax, rax
0x18003b77e  jnz     short loc_18003B787
0x18003b780  mov     eax, 8007000Eh
0x18003b785  jmp     short loc_18003B7A4
0x18003b787  lea     rdx, [rsp+28h+arg_8]
0x18003b78c  mov     [rsp+28h+arg_8], 0
0x18003b794  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@U?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18003b799  mov     dword ptr [rdi], 2
0x18003b79f  xor     eax, eax
0x18003b7a1  mov     [rbx], r8
0x18003b7a4  mov     rbx, [rsp+28h+arg_0]
0x18003b7a9  add     rsp, 20h
0x18003b7ad  pop     rdi
0x18003b7ae  retn
```
