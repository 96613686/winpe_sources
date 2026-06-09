# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001ed20`
- end: `0x18001eda2`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAUIInspectable@@@234@U?$IObservableVector@PEAUIInspectable@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `130`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001edb0`
- `0x18001edc0`

## callees

- `0x18001dabc`
- `0x18001ed20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ed42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ed42`

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
0x18001ed20  mov     [rsp+arg_0], rbx
0x18001ed25  push    rdi
0x18001ed26  sub     rsp, 20h
0x18001ed2a  mov     qword ptr [r8], 0
0x18001ed31  mov     ecx, 40h ; '@'; cb
0x18001ed36  mov     dword ptr [rdx], 0
0x18001ed3c  mov     rbx, r8
0x18001ed3f  mov     rdi, rdx
0x18001ed42  call    cs:__imp_CoTaskMemAlloc
0x18001ed48  mov     r8, rax
0x18001ed4b  test    rax, rax
0x18001ed4e  jnz     short loc_18001ED57
0x18001ed50  mov     eax, 8007000Eh
0x18001ed55  jmp     short loc_18001ED97
0x18001ed57  movups  xmm0, xmmword ptr cs:_GUID_b32bdca4_5e52_5b27_bc5d_d66a1a268c2a.Data1
0x18001ed5e  lea     rdx, [rsp+28h+arg_8]
0x18001ed63  mov     [rsp+28h+arg_8], 3
0x18001ed6b  movdqu  xmmword ptr [rax], xmm0
0x18001ed6f  movups  xmm1, xmmword ptr cs:_GUID_092b849b_60b1_52be_a44a_6fe8e933cbe4.Data1
0x18001ed76  movdqu  xmmword ptr [rax+10h], xmm1
0x18001ed7b  movups  xmm0, xmmword ptr cs:_GUID_7b81c56a_0985_518d_baa9_0da9ae009f65.Data1
0x18001ed82  movdqu  xmmword ptr [rax+20h], xmm0
0x18001ed87  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18001ed8c  mov     dword ptr [rdi], 4
0x18001ed92  xor     eax, eax
0x18001ed94  mov     [rbx], r8
0x18001ed97  mov     rbx, [rsp+28h+arg_0]
0x18001ed9c  add     rsp, 20h
0x18001eda0  pop     rdi
0x18001eda1  retn
```
