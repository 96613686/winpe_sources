# common_vsprintf___crt_stdio_output::format_validation_base_char_

- ea: `0x180033cc4`
- end: `0x180033e73`
- name: `common_vsprintf___crt_stdio_output::format_validation_base_char_`
- size: `431`
- prototype: `__int64 __fastcall(int, int, int, int, __crt_cached_ptd_host *, __int64)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180033ac0`
- `0x180034734`
- `0x180056548`
- `0x180056bdc`

## callees

- `0x180002810`
- `0x180007b48`
- `0x180008040`
- `0x180033cc4`
- `0x180044548`

## pseudocode

```c
__int64 __fastcall common_vsprintf___crt_stdio_output::format_validation_base_char_(
        __int64 a1,
        _BYTE *a2,
        unsigned __int64 a3,
        __int64 a4,
        __crt_cached_ptd_host *a5,
        __int64 a6)
{
  char v8; // r15
  int v10; // eax
  unsigned __int64 v11; // rbx
  __int64 v12; // rax
  _QWORD v13[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v14; // [rsp+40h] [rbp-C0h]
  char v15; // [rsp+48h] [rbp-B8h]
  int v16; // [rsp+49h] [rbp-B7h]
  __int16 v17; // [rsp+4Dh] [rbp-B3h]
  char v18; // [rsp+4Fh] [rbp-B1h]
  _QWORD v19[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v20; // [rsp+70h] [rbp-90h]
  char v21; // [rsp+74h] [rbp-8Ch]
  __int64 v22; // [rsp+78h] [rbp-88h]
  int v23; // [rsp+80h] [rbp-80h]
  __int16 v24; // [rsp+88h] [rbp-78h]
  int v25; // [rsp+98h] [rbp-68h]
  char v26; // [rsp+9Ch] [rbp-64h]
  void *Block[2]; // [rsp+4A0h] [rbp+3A0h]
  _QWORD *v28; // [rsp+4B0h] [rbp+3B0h]
  int v29; // [rsp+4B8h] [rbp+3B8h]

  v8 = a1;
  if ( !a4 || a3 && !a2 )
  {
    *((_BYTE *)a5 + 48) = 1;
    *((_DWORD *)a5 + 11) = 22;
    invalid_parameter_internal(0, 0, 0, 0, 0, a5);
    return 0xFFFFFFFFLL;
  }
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v13[0] = a2;
  v13[1] = a3;
  v14 = 0;
  if ( (a1 & 2) != 0 || (v15 = 0, !a2) )
    v15 = 1;
  v19[1] = a5;
  v20 = 0;
  v28 = v13;
  v19[3] = a6;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  *(_OWORD *)Block = 0;
  v19[0] = a1;
  v19[2] = a4;
  v29 = 0;
  v10 = __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::format_validation_base<char,__crt_stdio_output::string_output_adapter<char>>>::process(v19);
  v11 = v10;
  if ( a2 )
  {
    if ( (v8 & 1) != 0 )
    {
      if ( !a3 && v10 )
        goto LABEL_12;
      v12 = v14;
      if ( v14 == a3 )
      {
        if ( (v11 & 0x80000000) != 0LL || v11 <= a3 )
          goto LABEL_23;
        goto LABEL_12;
      }
      goto LABEL_22;
    }
    if ( (v8 & 2) != 0 )
    {
      if ( !a3 )
        goto LABEL_23;
      if ( v10 < 0 )
      {
        *a2 = 0;
        goto LABEL_23;
      }
      v12 = v14;
      if ( v14 != a3 )
        goto LABEL_22;
    }
    else
    {
      if ( !a3 )
      {
LABEL_12:
        LODWORD(v11) = -1;
        goto LABEL_23;
      }
      v12 = v14;
      if ( v14 != a3 )
      {
LABEL_22:
        a2[v12] = 0;
        goto LABEL_23;
      }
      LODWORD(v11) = -2;
    }
    a2[a3 - 1] = 0;
  }
LABEL_23:
  free_base(Block[1]);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180033cc4  push    rbp
0x180033cc6  push    rbx
0x180033cc7  push    rsi
0x180033cc8  push    rdi
0x180033cc9  push    r12
0x180033ccb  push    r14
0x180033ccd  push    r15
0x180033ccf  lea     rbp, [rsp-3D0h]
0x180033cd7  sub     rsp, 4D0h
0x180033cde  mov     rax, cs:__security_cookie
0x180033ce5  xor     rax, rsp
0x180033ce8  mov     [rbp+400h+var_40], rax
0x180033cef  mov     rax, [rbp+400h+arg_20]
0x180033cf6  xor     r12d, r12d
0x180033cf9  mov     rdi, r8
0x180033cfc  mov     rsi, rdx
0x180033cff  mov     r15, rcx
0x180033d02  test    r9, r9
0x180033d05  jnz     short loc_180033D33
0x180033d07  mov     byte ptr [rax+30h], 1
0x180033d0b  xor     r9d, r9d; LineNo
0x180033d0e  mov     [rsp+500h+var_4D8], rax; __crt_cached_ptd_host *
0x180033d13  xor     r8d, r8d; FileName
0x180033d16  xor     edx, edx; FunctionName
0x180033d18  mov     dword ptr [rax+2Ch], 16h
0x180033d1f  xor     ecx, ecx; Expression
0x180033d21  mov     [rsp+500h+var_4E0], r12; uintptr_t
0x180033d26  call    _invalid_parameter_internal
0x180033d2b  or      eax, 0FFFFFFFFh
0x180033d2e  jmp     loc_180033E37
0x180033d33  test    rdi, rdi
0x180033d36  jz      short loc_180033D3D
0x180033d38  test    rsi, rsi
0x180033d3b  jz      short loc_180033D07
0x180033d3d  mov     r14, r15
0x180033d40  mov     [rsp+500h+var_4B7], r12d
0x180033d45  mov     [rsp+500h+var_4B3], r12w
0x180033d4b  mov     [rsp+500h+var_4B1], r12b
0x180033d50  mov     [rsp+500h+var_4D0], rsi
0x180033d55  mov     [rsp+500h+var_4C8], rdi
0x180033d5a  mov     [rsp+500h+var_4C0], r12
0x180033d5f  and     r14d, 2
0x180033d63  jnz     short loc_180033D6F
0x180033d65  mov     [rsp+500h+var_4B8], r12b
0x180033d6a  test    rsi, rsi
0x180033d6d  jnz     short loc_180033D74
0x180033d6f  mov     [rsp+500h+var_4B8], 1
0x180033d74  mov     [rsp+500h+var_4A8], rax
0x180033d79  lea     rcx, [rsp+500h+var_4B0]
0x180033d7e  lea     rax, [rsp+500h+var_4D0]
0x180033d83  mov     [rsp+500h+var_490], r12d
0x180033d88  mov     [rbp+400h+var_50], rax
0x180033d8f  xorps   xmm0, xmm0
0x180033d92  mov     rax, [rbp+400h+arg_28]
0x180033d99  mov     [rsp+500h+var_498], rax
0x180033d9e  mov     [rsp+500h+var_48C], r12b
0x180033da3  mov     [rsp+500h+var_488], r12
0x180033da8  mov     [rbp+400h+var_480], r12d
0x180033dac  mov     [rbp+400h+var_478], r12w
0x180033db1  mov     [rbp+400h+var_468], r12d
0x180033db5  mov     [rbp+400h+var_464], r12b
0x180033db9  movdqa  xmmword ptr [rbp+400h+Block], xmm0
0x180033dc1  mov     [rsp+500h+var_4B0], r15
0x180033dc6  mov     [rsp+500h+var_4A0], r9
0x180033dcb  mov     [rbp+400h+var_48], r12d
0x180033dd2  call    ?process@?$output_processor@DV?$string_output_adapter@D@__crt_stdio_output@@V?$format_validation_base@DV?$string_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@QEAAHXZ; __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::format_validation_base<char,__crt_stdio_output::string_output_adapter<char>>>::process(void)
0x180033dd7  movsxd  rbx, eax
0x180033dda  test    rsi, rsi
0x180033ddd  jz      short loc_180033E29
0x180033ddf  test    r15b, 1
0x180033de3  jz      short loc_180033E08
0x180033de5  test    rdi, rdi
0x180033de8  jnz     short loc_180033DF3
0x180033dea  test    eax, eax
0x180033dec  jz      short loc_180033DF3
0x180033dee  or      ebx, 0FFFFFFFFh
0x180033df1  jmp     short loc_180033E29
0x180033df3  mov     rax, [rsp+500h+var_4C0]
0x180033df8  cmp     rax, rdi
0x180033dfb  jnz     short loc_180033E25
0x180033dfd  test    ebx, ebx
0x180033dff  js      short loc_180033E29
0x180033e01  cmp     rbx, rdi
0x180033e04  jbe     short loc_180033E29
0x180033e06  jmp     short loc_180033DEE
0x180033e08  test    r14, r14
0x180033e0b  jz      short loc_180033E58
0x180033e0d  test    rdi, rdi
0x180033e10  jz      short loc_180033E29
0x180033e12  test    eax, eax
0x180033e14  jns     short loc_180033E1B
0x180033e16  mov     [rsi], r12b
0x180033e19  jmp     short loc_180033E29
0x180033e1b  mov     rax, [rsp+500h+var_4C0]
0x180033e20  cmp     rax, rdi
0x180033e23  jz      short loc_180033E6C
0x180033e25  mov     [rsi+rax], r12b
0x180033e29  mov     rcx, [rbp+400h+Block+8]; Block
0x180033e30  call    _free_base
0x180033e35  mov     eax, ebx
0x180033e37  mov     rcx, [rbp+400h+var_40]
0x180033e3e  xor     rcx, rsp; StackCookie
0x180033e41  call    __security_check_cookie
0x180033e46  add     rsp, 4D0h
0x180033e4d  pop     r15
0x180033e4f  pop     r14
0x180033e51  pop     r12
0x180033e53  pop     rdi
0x180033e54  pop     rsi
0x180033e55  pop     rbx
0x180033e56  pop     rbp
0x180033e57  retn
0x180033e58  test    rdi, rdi
0x180033e5b  jz      short loc_180033DEE
0x180033e5d  mov     rax, [rsp+500h+var_4C0]
0x180033e62  cmp     rax, rdi
0x180033e65  jnz     short loc_180033E25
0x180033e67  mov     ebx, 0FFFFFFFEh
0x180033e6c  mov     [rsi+rdi-1], r12b
0x180033e71  jmp     short loc_180033E29
```
