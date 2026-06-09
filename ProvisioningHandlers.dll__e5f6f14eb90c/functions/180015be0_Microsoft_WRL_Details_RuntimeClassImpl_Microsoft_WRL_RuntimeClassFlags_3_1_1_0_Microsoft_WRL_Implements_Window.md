# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x180015be0`
- end: `0x180015c69`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAUIInspectable@@@234@U?$IObservableVector@PEAUIInspectable@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `137`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180015c70`
- `0x180015c80`

## callees

- `0x180014aa8`
- `0x180015be0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015c02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015c02`

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
0x180015be0  mov     [rsp+arg_0], rbx
0x180015be5  push    rdi
0x180015be6  sub     rsp, 20h
0x180015bea  mov     qword ptr [r8], 0
0x180015bf1  mov     ecx, 40h ; '@'; cb
0x180015bf6  mov     dword ptr [rdx], 0
0x180015bfc  mov     rbx, r8
0x180015bff  mov     rdi, rdx
0x180015c02  call    cs:__imp_CoTaskMemAlloc
0x180015c09  nop     dword ptr [rax+rax+00h]
0x180015c0e  mov     r8, rax
0x180015c11  test    rax, rax
0x180015c14  jnz     short loc_180015C1D
0x180015c16  mov     eax, 8007000Eh
0x180015c1b  jmp     short loc_180015C5D
0x180015c1d  movups  xmm0, xmmword ptr cs:_GUID_b32bdca4_5e52_5b27_bc5d_d66a1a268c2a.Data1
0x180015c24  lea     rdx, [rsp+28h+arg_8]
0x180015c29  mov     [rsp+28h+arg_8], 3
0x180015c31  movdqu  xmmword ptr [rax], xmm0
0x180015c35  movups  xmm1, xmmword ptr cs:_GUID_092b849b_60b1_52be_a44a_6fe8e933cbe4.Data1
0x180015c3c  movdqu  xmmword ptr [rax+10h], xmm1
0x180015c41  movups  xmm0, xmmword ptr cs:_GUID_7b81c56a_0985_518d_baa9_0da9ae009f65.Data1
0x180015c48  movdqu  xmmword ptr [rax+20h], xmm0
0x180015c4d  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180015c52  mov     dword ptr [rdi], 4
0x180015c58  xor     eax, eax
0x180015c5a  mov     [rbx], r8
0x180015c5d  mov     rbx, [rsp+28h+arg_0]
0x180015c62  add     rsp, 20h
0x180015c66  pop     rdi
0x180015c67  retn
```
