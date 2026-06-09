# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorView<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>>::GetIids(ulong *,_GUID * *)

- ea: `0x180040720`
- end: `0x18004078d`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IVectorView@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAUIInspectable@@@567@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800407a0`
- `0x180040840`

## callees

- `0x180040720`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180040742`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180040742`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorView<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>>::GetIids(
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
0x180040720  mov     [rsp+arg_0], rbx
0x180040725  push    rdi
0x180040726  sub     rsp, 20h
0x18004072a  mov     qword ptr [r8], 0
0x180040731  mov     ecx, 30h ; '0'; cb
0x180040736  mov     dword ptr [rdx], 0
0x18004073c  mov     rbx, r8
0x18004073f  mov     rdi, rdx
0x180040742  call    cs:__imp_CoTaskMemAlloc
0x180040748  test    rax, rax
0x18004074b  jnz     short loc_180040754
0x18004074d  mov     eax, 8007000Eh
0x180040752  jmp     short loc_180040782
0x180040754  movups  xmm0, xmmword ptr cs:_GUID_a6487363_b074_5c60_ab16_866dce4ee54d.Data1
0x18004075b  movdqu  xmmword ptr [rax], xmm0
0x18004075f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180040766  movdqu  xmmword ptr [rax+10h], xmm1
0x18004076b  movups  xmm0, xmmword ptr cs:_GUID_092b849b_60b1_52be_a44a_6fe8e933cbe4.Data1
0x180040772  movdqu  xmmword ptr [rax+20h], xmm0
0x180040777  mov     dword ptr [rdi], 3
0x18004077d  mov     [rbx], rax
0x180040780  xor     eax, eax
0x180040782  mov     rbx, [rsp+28h+arg_0]
0x180040787  add     rsp, 20h
0x18004078b  pop     rdi
0x18004078c  retn
```
