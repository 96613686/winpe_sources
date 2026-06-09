# Pal::DeviceTypeClassifierImplWindows::calculateDeviceTypeFromGraphicsMemoryAndDeviceId(void)

- ea: `0x180015a04`
- end: `0x180015b06`
- name: `?calculateDeviceTypeFromGraphicsMemoryAndDeviceId@DeviceTypeClassifierImplWindows@Pal@@CA?AW4DeviceType@2@XZ`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180015858`

## callees

- `0x1800094a0`
- `0x18000a074`
- `0x180015a04`
- `0x180043010`

## import_xrefs

- `dxgi!CreateDXGIFactory1` at `0x180015a39`
- `dxgi!CreateDXGIFactory1` at `0x180015a39`

## pseudocode

```c
__int64 Pal::DeviceTypeClassifierImplWindows::calculateDeviceTypeFromGraphicsMemoryAndDeviceId()
{
  __int64 v0; // rbx
  unsigned __int64 v1; // rcx
  __int64 result; // rax
  void *ppFactory; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v4; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v5[272]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v6; // [rsp+140h] [rbp+40h]
  __int64 v7; // [rsp+148h] [rbp+48h]
  __int64 v8; // [rsp+150h] [rbp+50h]

  ppFactory = 0;
  if ( CreateDXGIFactory1(&GUID_770aae78_f26f_4dba_a829_253c83d1b387, &ppFactory) < 0 )
    return 2;
  if ( !ppFactory )
    return 2;
  v4 = 0;
  if ( (*(int (__fastcall **)(void *, _QWORD, __int64 *))(*(_QWORD *)ppFactory + 56LL))(ppFactory, 0, &v4) < 0 )
    return 2;
  v0 = v4;
  if ( !v4 )
    return 2;
  memset_0(v5, 0, 0x130u);
  if ( (*(int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v0 + 64LL))(v0, v5) < 0 )
    return 2;
  (*(void (__fastcall **)(void *))(*(_QWORD *)ppFactory + 16LL))(ppFactory);
  v1 = v8 + v7 + v6;
  if ( v1 <= 0x20000000 )
    return 1;
  result = 3;
  if ( v1 <= 0x60000000 )
    return 2;
  return result;
}

```

## disassembly

```asm
0x180015a04  mov     [rsp-8+arg_0], rbx
0x180015a09  push    rbp
0x180015a0a  lea     rbp, [rsp-70h]
0x180015a0f  sub     rsp, 170h
0x180015a16  mov     rax, cs:__security_cookie
0x180015a1d  xor     rax, rsp
0x180015a20  mov     [rbp+70h+var_10], rax
0x180015a24  lea     rdx, [rsp+170h+ppFactory]; ppFactory
0x180015a29  mov     [rsp+170h+ppFactory], 0
0x180015a32  lea     rcx, _GUID_770aae78_f26f_4dba_a829_253c83d1b387; riid
0x180015a39  call    cs:__imp_CreateDXGIFactory1
0x180015a3f  test    eax, eax
0x180015a41  js      loc_180015AE4
0x180015a47  mov     rcx, [rsp+170h+ppFactory]
0x180015a4c  test    rcx, rcx
0x180015a4f  jz      loc_180015AE4
0x180015a55  mov     [rsp+170h+var_148], 0
0x180015a5e  lea     r8, [rsp+170h+var_148]
0x180015a63  mov     rax, [rcx]
0x180015a66  xor     edx, edx
0x180015a68  mov     rax, [rax+38h]
0x180015a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a71  test    eax, eax
0x180015a73  js      short loc_180015AE4
0x180015a75  mov     rbx, [rsp+170h+var_148]
0x180015a7a  test    rbx, rbx
0x180015a7d  jz      short loc_180015AE4
0x180015a7f  xor     edx, edx; Val
0x180015a81  lea     rcx, [rsp+170h+var_140]; void *
0x180015a86  mov     r8d, 130h; Size
0x180015a8c  call    memset_0
0x180015a91  mov     rax, [rbx]
0x180015a94  lea     rdx, [rsp+170h+var_140]
0x180015a99  mov     rcx, rbx
0x180015a9c  mov     rax, [rax+40h]
0x180015aa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015aa5  test    eax, eax
0x180015aa7  js      short loc_180015AE4
0x180015aa9  mov     rcx, [rsp+170h+ppFactory]
0x180015aae  mov     rax, [rcx]
0x180015ab1  mov     rax, [rax+10h]
0x180015ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015aba  mov     rcx, [rbp+70h+var_30]
0x180015abe  add     rcx, [rbp+70h+var_28]
0x180015ac2  add     rcx, [rbp+70h+var_20]
0x180015ac6  cmp     rcx, 20000000h
0x180015acd  ja      short loc_180015AD6
0x180015acf  mov     eax, 1
0x180015ad4  jmp     short loc_180015AE9
0x180015ad6  mov     eax, 3
0x180015adb  cmp     rcx, 60000000h
0x180015ae2  ja      short loc_180015AE9
0x180015ae4  mov     eax, 2
0x180015ae9  mov     rcx, [rbp+70h+var_10]
0x180015aed  xor     rcx, rsp; StackCookie
0x180015af0  call    __security_check_cookie
0x180015af5  mov     rbx, [rsp+170h+arg_0]
0x180015afd  add     rsp, 170h
0x180015b04  pop     rbp
0x180015b05  retn
```
