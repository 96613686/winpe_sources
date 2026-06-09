# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>>::GetIids(ulong *,_GUID * *)

- ea: `0x180046f10`
- end: `0x180046f71`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180046f10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046f32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046f32`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x20u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_09335560_6c6b_5a26_9348_97b781132b20;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180046f10  mov     [rsp+arg_0], rbx
0x180046f15  push    rdi
0x180046f16  sub     rsp, 20h
0x180046f1a  mov     qword ptr [r8], 0
0x180046f21  mov     ecx, 20h ; ' '; cb
0x180046f26  mov     dword ptr [rdx], 0
0x180046f2c  mov     rbx, r8
0x180046f2f  mov     rdi, rdx
0x180046f32  call    cs:__imp_CoTaskMemAlloc
0x180046f38  test    rax, rax
0x180046f3b  jnz     short loc_180046F44
0x180046f3d  mov     eax, 8007000Eh
0x180046f42  jmp     short loc_180046F66
0x180046f44  movups  xmm0, xmmword ptr cs:_GUID_09335560_6c6b_5a26_9348_97b781132b20.Data1
0x180046f4b  movdqu  xmmword ptr [rax], xmm0
0x180046f4f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180046f56  movdqu  xmmword ptr [rax+10h], xmm1
0x180046f5b  mov     dword ptr [rdi], 2
0x180046f61  mov     [rbx], rax
0x180046f64  xor     eax, eax
0x180046f66  mov     rbx, [rsp+28h+arg_0]
0x180046f6b  add     rsp, 20h
0x180046f6f  pop     rdi
0x180046f70  retn
```
