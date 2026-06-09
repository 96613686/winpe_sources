# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>>::GetIids(ulong *,_GUID * *)

- ea: `0x1800407b0`
- end: `0x18004081d`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAUIInspectable@@@567@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180040830`
- `0x180040860`

## callees

- `0x1800407b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800407d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800407d2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_b32bdca4_5e52_5b27_bc5d_d66a1a268c2a;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_092b849b_60b1_52be_a44a_6fe8e933cbe4;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800407b0  mov     [rsp+arg_0], rbx
0x1800407b5  push    rdi
0x1800407b6  sub     rsp, 20h
0x1800407ba  mov     qword ptr [r8], 0
0x1800407c1  mov     ecx, 30h ; '0'; cb
0x1800407c6  mov     dword ptr [rdx], 0
0x1800407cc  mov     rbx, r8
0x1800407cf  mov     rdi, rdx
0x1800407d2  call    cs:__imp_CoTaskMemAlloc
0x1800407d8  test    rax, rax
0x1800407db  jnz     short loc_1800407E4
0x1800407dd  mov     eax, 8007000Eh
0x1800407e2  jmp     short loc_180040812
0x1800407e4  movups  xmm0, xmmword ptr cs:_GUID_b32bdca4_5e52_5b27_bc5d_d66a1a268c2a.Data1
0x1800407eb  movdqu  xmmword ptr [rax], xmm0
0x1800407ef  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x1800407f6  movdqu  xmmword ptr [rax+10h], xmm1
0x1800407fb  movups  xmm0, xmmword ptr cs:_GUID_092b849b_60b1_52be_a44a_6fe8e933cbe4.Data1
0x180040802  movdqu  xmmword ptr [rax+20h], xmm0
0x180040807  mov     dword ptr [rdi], 3
0x18004080d  mov     [rbx], rax
0x180040810  xor     eax, eax
0x180040812  mov     rbx, [rsp+28h+arg_0]
0x180040817  add     rsp, 20h
0x18004081b  pop     rdi
0x18004081c  retn
```
