# MpConfigGetValueDword

- ea: `0x140020a14`
- end: `0x140020aaa`
- name: `MpConfigGetValueDword`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400208f4`

## callees

- `0x140005c20`
- `0x140020a14`

## import_xrefs

- `MpClient!MpConfigGetValue` at `0x140020a6e`
- `MpClient!MpConfigGetValue` at `0x140020a6e`

## pseudocode

```c
__int64 __fastcall MpConfigGetValueDword(__int64 a1, __int64 a2, _DWORD *a3, __int64 a4)
{
  int v4; // ebx
  __int64 result; // rax
  unsigned int v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+34h] [rbp-24h] BYREF
  int v9; // [rsp+38h] [rbp-20h] BYREF

  v4 = 0;
  v8 = 4;
  v7 = 0;
  v9 = 0;
  if ( !a3 )
    return 2147942487LL;
  result = MpConfigGetValue(a1, L"EnableCACS", &v7, &v8, &v9, a4);
  if ( (int)result >= 0 )
  {
    if ( v7 <= 1 )
    {
      if ( v8 )
        v4 = v9;
      *a3 = v4;
    }
    else
    {
      return 2147944029LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140020a14  mov     [rsp+arg_8], rbx
0x140020a19  push    rdi
0x140020a1a  sub     rsp, 50h
0x140020a1e  mov     rax, cs:__security_cookie
0x140020a25  xor     rax, rsp
0x140020a28  mov     [rsp+58h+var_18], rax
0x140020a2d  xor     ebx, ebx
0x140020a2f  mov     [rsp+58h+var_24], 4
0x140020a37  mov     [rsp+58h+var_28], ebx
0x140020a3b  mov     rdi, r8
0x140020a3e  mov     [rsp+58h+var_20], ebx
0x140020a42  test    r8, r8
0x140020a45  jnz     short loc_140020A4E
0x140020a47  mov     eax, 80070057h
0x140020a4c  jmp     short loc_140020A92
0x140020a4e  mov     [rsp+58h+var_30], r9
0x140020a53  lea     rax, [rsp+58h+var_20]
0x140020a58  lea     r9, [rsp+58h+var_24]
0x140020a5d  mov     [rsp+58h+var_38], rax
0x140020a62  lea     r8, [rsp+58h+var_28]
0x140020a67  lea     rdx, aEnablecacs; "EnableCACS"
0x140020a6e  call    cs:__imp_MpConfigGetValue
0x140020a74  test    eax, eax
0x140020a76  js      short loc_140020A92
0x140020a78  cmp     [rsp+58h+var_28], 1
0x140020a7d  jbe     short loc_140020A86
0x140020a7f  mov     eax, 8007065Dh
0x140020a84  jmp     short loc_140020A92
0x140020a86  cmp     [rsp+58h+var_24], ebx
0x140020a8a  jz      short loc_140020A90
0x140020a8c  mov     ebx, [rsp+58h+var_20]
0x140020a90  mov     [rdi], ebx
0x140020a92  mov     rcx, [rsp+58h+var_18]
0x140020a97  xor     rcx, rsp; StackCookie
0x140020a9a  call    __security_check_cookie
0x140020a9f  mov     rbx, [rsp+58h+arg_8]
0x140020aa4  add     rsp, 50h
0x140020aa8  pop     rdi
0x140020aa9  retn
```
