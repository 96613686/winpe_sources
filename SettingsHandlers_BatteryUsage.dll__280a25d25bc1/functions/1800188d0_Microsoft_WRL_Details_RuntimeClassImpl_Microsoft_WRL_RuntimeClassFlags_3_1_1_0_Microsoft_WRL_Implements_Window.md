# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x1800188d0`
- end: `0x180018952`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAUIInspectable@@@234@U?$IObservableVector@PEAUIInspectable@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `130`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018960`
- `0x180018970`

## callees

- `0x18001837c`
- `0x1800188d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800188f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800188f2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::GetIids(
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
  v5 = (GUID *)CoTaskMemAlloc(0x40u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 3;
  *v5 = GUID_b32bdca4_5e52_5b27_bc5d_d66a1a268c2a;
  v5[1] = GUID_092b849b_60b1_52be_a44a_6fe8e933cbe4;
  v5[2] = GUID_7b81c56a_0985_518d_baa9_0da9ae009f65;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v6,
    &v9,
    v5);
  *a2 = 4;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x1800188d0  mov     [rsp+arg_0], rbx
0x1800188d5  push    rdi
0x1800188d6  sub     rsp, 20h
0x1800188da  mov     qword ptr [r8], 0
0x1800188e1  mov     ecx, 40h ; '@'; cb
0x1800188e6  mov     dword ptr [rdx], 0
0x1800188ec  mov     rbx, r8
0x1800188ef  mov     rdi, rdx
0x1800188f2  call    cs:__imp_CoTaskMemAlloc
0x1800188f8  mov     r8, rax
0x1800188fb  test    rax, rax
0x1800188fe  jnz     short loc_180018907
0x180018900  mov     eax, 8007000Eh
0x180018905  jmp     short loc_180018947
0x180018907  movups  xmm0, xmmword ptr cs:_GUID_b32bdca4_5e52_5b27_bc5d_d66a1a268c2a.Data1
0x18001890e  lea     rdx, [rsp+28h+arg_8]
0x180018913  mov     [rsp+28h+arg_8], 3
0x18001891b  movdqu  xmmword ptr [rax], xmm0
0x18001891f  movups  xmm1, xmmword ptr cs:_GUID_092b849b_60b1_52be_a44a_6fe8e933cbe4.Data1
0x180018926  movdqu  xmmword ptr [rax+10h], xmm1
0x18001892b  movups  xmm0, xmmword ptr cs:_GUID_7b81c56a_0985_518d_baa9_0da9ae009f65.Data1
0x180018932  movdqu  xmmword ptr [rax+20h], xmm0
0x180018937  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18001893c  mov     dword ptr [rdi], 4
0x180018942  xor     eax, eax
0x180018944  mov     [rbx], r8
0x180018947  mov     rbx, [rsp+28h+arg_0]
0x18001894c  add     rsp, 20h
0x180018950  pop     rdi
0x180018951  retn
```
