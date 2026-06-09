# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMapView<HSTRING__ *,uchar>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,uchar> *>>::GetIids(ulong *,_GUID * *)

- ea: `0x180014f50`
- end: `0x180014fbd`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IMapView@PEAUHSTRING__@@E@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@E@Collections@Foundation@Windows@@@567@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014fd0`

## callees

- `0x180014f50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014f72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014f72`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMapView<HSTRING__ *,unsigned char>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,unsigned char> *>>::GetIids(
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
  *v5 = GUID_864c9cdb_725f_5911_b692_cb12e2c56d36;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_2a8cd53f_ffbd_57ea_867c_12a448d00aae;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180014f50  mov     [rsp+arg_0], rbx
0x180014f55  push    rdi
0x180014f56  sub     rsp, 20h
0x180014f5a  mov     qword ptr [r8], 0
0x180014f61  mov     ecx, 30h ; '0'; cb
0x180014f66  mov     dword ptr [rdx], 0
0x180014f6c  mov     rbx, r8
0x180014f6f  mov     rdi, rdx
0x180014f72  call    cs:__imp_CoTaskMemAlloc
0x180014f78  test    rax, rax
0x180014f7b  jnz     short loc_180014F84
0x180014f7d  mov     eax, 8007000Eh
0x180014f82  jmp     short loc_180014FB2
0x180014f84  movups  xmm0, xmmword ptr cs:_GUID_864c9cdb_725f_5911_b692_cb12e2c56d36.Data1
0x180014f8b  movdqu  xmmword ptr [rax], xmm0
0x180014f8f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180014f96  movdqu  xmmword ptr [rax+10h], xmm1
0x180014f9b  movups  xmm0, xmmword ptr cs:_GUID_2a8cd53f_ffbd_57ea_867c_12a448d00aae.Data1
0x180014fa2  movdqu  xmmword ptr [rax+20h], xmm0
0x180014fa7  mov     dword ptr [rdi], 3
0x180014fad  mov     [rbx], rax
0x180014fb0  xor     eax, eax
0x180014fb2  mov     rbx, [rsp+28h+arg_0]
0x180014fb7  add     rsp, 20h
0x180014fbb  pop     rdi
0x180014fbc  retn
```
