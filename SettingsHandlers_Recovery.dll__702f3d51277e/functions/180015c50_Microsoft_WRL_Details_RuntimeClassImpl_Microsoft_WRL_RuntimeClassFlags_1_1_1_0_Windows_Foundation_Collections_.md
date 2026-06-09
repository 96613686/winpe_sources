# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorView<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x180015c50`
- end: `0x180015cbd`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IVectorView@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAUIInspectable@@@567@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180015cd0`
- `0x180015fe0`

## callees

- `0x180015c50`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180015c72`
- `ole32!CoTaskMemAlloc` at `0x180015c72`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorView<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_a6487363_b074_5c60_ab16_866dce4ee54d;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_092b849b_60b1_52be_a44a_6fe8e933cbe4;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180015c50  mov     [rsp+arg_0], rbx
0x180015c55  push    rdi
0x180015c56  sub     rsp, 20h
0x180015c5a  mov     qword ptr [r8], 0
0x180015c61  mov     ecx, 30h ; '0'; cb
0x180015c66  mov     dword ptr [rdx], 0
0x180015c6c  mov     rbx, r8
0x180015c6f  mov     rdi, rdx
0x180015c72  call    cs:__imp_CoTaskMemAlloc
0x180015c78  test    rax, rax
0x180015c7b  jnz     short loc_180015C84
0x180015c7d  mov     eax, 8007000Eh
0x180015c82  jmp     short loc_180015CB2
0x180015c84  movups  xmm0, xmmword ptr cs:_GUID_a6487363_b074_5c60_ab16_866dce4ee54d.Data1
0x180015c8b  movdqu  xmmword ptr [rax], xmm0
0x180015c8f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180015c96  movdqu  xmmword ptr [rax+10h], xmm1
0x180015c9b  movups  xmm0, xmmword ptr cs:_GUID_092b849b_60b1_52be_a44a_6fe8e933cbe4.Data1
0x180015ca2  movdqu  xmmword ptr [rax+20h], xmm0
0x180015ca7  mov     dword ptr [rdi], 3
0x180015cad  mov     [rbx], rax
0x180015cb0  xor     eax, eax
0x180015cb2  mov     rbx, [rsp+28h+arg_0]
0x180015cb7  add     rsp, 20h
0x180015cbb  pop     rdi
0x180015cbc  retn
```
