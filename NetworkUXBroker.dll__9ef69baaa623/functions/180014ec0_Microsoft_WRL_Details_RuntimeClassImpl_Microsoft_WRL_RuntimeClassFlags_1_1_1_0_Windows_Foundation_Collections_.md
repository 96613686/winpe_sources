# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,uchar>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,uchar> *>>::GetIids(ulong *,_GUID * *)

- ea: `0x180014ec0`
- end: `0x180014f2d`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IMap@PEAUHSTRING__@@E@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@E@Collections@Foundation@Windows@@@567@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014f40`

## callees

- `0x180014ec0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014ee2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014ee2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,unsigned char>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,unsigned char> *>>::GetIids(
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
  *v5 = GUID_25c55baa_a035_5284_bb06_b49c1c7e61cc;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_2a8cd53f_ffbd_57ea_867c_12a448d00aae;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180014ec0  mov     [rsp+arg_0], rbx
0x180014ec5  push    rdi
0x180014ec6  sub     rsp, 20h
0x180014eca  mov     qword ptr [r8], 0
0x180014ed1  mov     ecx, 30h ; '0'; cb
0x180014ed6  mov     dword ptr [rdx], 0
0x180014edc  mov     rbx, r8
0x180014edf  mov     rdi, rdx
0x180014ee2  call    cs:__imp_CoTaskMemAlloc
0x180014ee8  test    rax, rax
0x180014eeb  jnz     short loc_180014EF4
0x180014eed  mov     eax, 8007000Eh
0x180014ef2  jmp     short loc_180014F22
0x180014ef4  movups  xmm0, xmmword ptr cs:_GUID_25c55baa_a035_5284_bb06_b49c1c7e61cc.Data1
0x180014efb  movdqu  xmmword ptr [rax], xmm0
0x180014eff  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180014f06  movdqu  xmmword ptr [rax+10h], xmm1
0x180014f0b  movups  xmm0, xmmword ptr cs:_GUID_2a8cd53f_ffbd_57ea_867c_12a448d00aae.Data1
0x180014f12  movdqu  xmmword ptr [rax+20h], xmm0
0x180014f17  mov     dword ptr [rdi], 3
0x180014f1d  mov     [rbx], rax
0x180014f20  xor     eax, eax
0x180014f22  mov     rbx, [rsp+28h+arg_0]
0x180014f27  add     rsp, 20h
0x180014f2b  pop     rdi
0x180014f2c  retn
```
