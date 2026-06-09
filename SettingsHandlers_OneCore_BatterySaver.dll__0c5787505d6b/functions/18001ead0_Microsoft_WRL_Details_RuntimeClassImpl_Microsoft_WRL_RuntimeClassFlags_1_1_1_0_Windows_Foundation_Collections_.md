# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<IInspectable *>,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001ead0`
- end: `0x18001eb2f`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IIterator@PEAUIInspectable@@@Collections@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001dadc`
- `0x18001ead0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001eaf2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001eaf2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<IInspectable *>,Microsoft::WRL::FtmBase>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IIterator<IInspectable *>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x18001ead0  mov     [rsp+arg_0], rbx
0x18001ead5  push    rdi
0x18001ead6  sub     rsp, 20h
0x18001eada  mov     qword ptr [r8], 0
0x18001eae1  mov     ecx, 20h ; ' '; cb
0x18001eae6  mov     dword ptr [rdx], 0
0x18001eaec  mov     rbx, r8
0x18001eaef  mov     rdi, rdx
0x18001eaf2  call    cs:__imp_CoTaskMemAlloc
0x18001eaf8  mov     r8, rax
0x18001eafb  test    rax, rax
0x18001eafe  jnz     short loc_18001EB07
0x18001eb00  mov     eax, 8007000Eh
0x18001eb05  jmp     short loc_18001EB24
0x18001eb07  lea     rdx, [rsp+28h+arg_8]
0x18001eb0c  mov     [rsp+28h+arg_8], 0
0x18001eb14  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@U?$IIterator@PEAUIInspectable@@@Collections@Foundation@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IIterator<IInspectable *>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18001eb19  mov     dword ptr [rdi], 2
0x18001eb1f  xor     eax, eax
0x18001eb21  mov     [rbx], r8
0x18001eb24  mov     rbx, [rsp+28h+arg_0]
0x18001eb29  add     rsp, 20h
0x18001eb2d  pop     rdi
0x18001eb2e  retn
```
