# common_vsprintf___crt_stdio_output::format_validation_base_char_

- ea: `0x1800339e4`
- end: `0x180033b93`
- name: `common_vsprintf___crt_stdio_output::format_validation_base_char_`
- size: `431`
- prototype: `__int64 __fastcall(int, int, int, int, __crt_cached_ptd_host *, __int64)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800337e0`
- `0x180034454`
- `0x180056268`
- `0x1800568fc`

## callees

- `0x1800073e8`
- `0x1800078e0`
- `0x180032370`
- `0x1800339e4`
- `0x180044268`

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
0x1800339e4  push    rbp
0x1800339e6  push    rbx
0x1800339e7  push    rsi
0x1800339e8  push    rdi
0x1800339e9  push    r12
0x1800339eb  push    r14
0x1800339ed  push    r15
0x1800339ef  lea     rbp, [rsp-3D0h]
0x1800339f7  sub     rsp, 4D0h
0x1800339fe  mov     rax, cs:__security_cookie
0x180033a05  xor     rax, rsp
0x180033a08  mov     [rbp+400h+var_40], rax
0x180033a0f  mov     rax, [rbp+400h+arg_20]
0x180033a16  xor     r12d, r12d
0x180033a19  mov     rdi, r8
0x180033a1c  mov     rsi, rdx
0x180033a1f  mov     r15, rcx
0x180033a22  test    r9, r9
0x180033a25  jnz     short loc_180033A53
0x180033a27  mov     byte ptr [rax+30h], 1
0x180033a2b  xor     r9d, r9d; LineNo
0x180033a2e  mov     [rsp+500h+var_4D8], rax; __crt_cached_ptd_host *
0x180033a33  xor     r8d, r8d; FileName
0x180033a36  xor     edx, edx; FunctionName
0x180033a38  mov     dword ptr [rax+2Ch], 16h
0x180033a3f  xor     ecx, ecx; Expression
0x180033a41  mov     [rsp+500h+var_4E0], r12; uintptr_t
0x180033a46  call    _invalid_parameter_internal
0x180033a4b  or      eax, 0FFFFFFFFh
0x180033a4e  jmp     loc_180033B57
0x180033a53  test    rdi, rdi
0x180033a56  jz      short loc_180033A5D
0x180033a58  test    rsi, rsi
0x180033a5b  jz      short loc_180033A27
0x180033a5d  mov     r14, r15
0x180033a60  mov     [rsp+500h+var_4B7], r12d
0x180033a65  mov     [rsp+500h+var_4B3], r12w
0x180033a6b  mov     [rsp+500h+var_4B1], r12b
0x180033a70  mov     [rsp+500h+var_4D0], rsi
0x180033a75  mov     [rsp+500h+var_4C8], rdi
0x180033a7a  mov     [rsp+500h+var_4C0], r12
0x180033a7f  and     r14d, 2
0x180033a83  jnz     short loc_180033A8F
0x180033a85  mov     [rsp+500h+var_4B8], r12b
0x180033a8a  test    rsi, rsi
0x180033a8d  jnz     short loc_180033A94
0x180033a8f  mov     [rsp+500h+var_4B8], 1
0x180033a94  mov     [rsp+500h+var_4A8], rax
0x180033a99  lea     rcx, [rsp+500h+var_4B0]
0x180033a9e  lea     rax, [rsp+500h+var_4D0]
0x180033aa3  mov     [rsp+500h+var_490], r12d
0x180033aa8  mov     [rbp+400h+var_50], rax
0x180033aaf  xorps   xmm0, xmm0
0x180033ab2  mov     rax, [rbp+400h+arg_28]
0x180033ab9  mov     [rsp+500h+var_498], rax
0x180033abe  mov     [rsp+500h+var_48C], r12b
0x180033ac3  mov     [rsp+500h+var_488], r12
0x180033ac8  mov     [rbp+400h+var_480], r12d
0x180033acc  mov     [rbp+400h+var_478], r12w
0x180033ad1  mov     [rbp+400h+var_468], r12d
0x180033ad5  mov     [rbp+400h+var_464], r12b
0x180033ad9  movdqa  xmmword ptr [rbp+400h+Block], xmm0
0x180033ae1  mov     [rsp+500h+var_4B0], r15
0x180033ae6  mov     [rsp+500h+var_4A0], r9
0x180033aeb  mov     [rbp+400h+var_48], r12d
0x180033af2  call    ?process@?$output_processor@DV?$string_output_adapter@D@__crt_stdio_output@@V?$format_validation_base@DV?$string_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@QEAAHXZ; __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::format_validation_base<char,__crt_stdio_output::string_output_adapter<char>>>::process(void)
0x180033af7  movsxd  rbx, eax
0x180033afa  test    rsi, rsi
0x180033afd  jz      short loc_180033B49
0x180033aff  test    r15b, 1
0x180033b03  jz      short loc_180033B28
0x180033b05  test    rdi, rdi
0x180033b08  jnz     short loc_180033B13
0x180033b0a  test    eax, eax
0x180033b0c  jz      short loc_180033B13
0x180033b0e  or      ebx, 0FFFFFFFFh
0x180033b11  jmp     short loc_180033B49
0x180033b13  mov     rax, [rsp+500h+var_4C0]
0x180033b18  cmp     rax, rdi
0x180033b1b  jnz     short loc_180033B45
0x180033b1d  test    ebx, ebx
0x180033b1f  js      short loc_180033B49
0x180033b21  cmp     rbx, rdi
0x180033b24  jbe     short loc_180033B49
0x180033b26  jmp     short loc_180033B0E
0x180033b28  test    r14, r14
0x180033b2b  jz      short loc_180033B78
0x180033b2d  test    rdi, rdi
0x180033b30  jz      short loc_180033B49
0x180033b32  test    eax, eax
0x180033b34  jns     short loc_180033B3B
0x180033b36  mov     [rsi], r12b
0x180033b39  jmp     short loc_180033B49
0x180033b3b  mov     rax, [rsp+500h+var_4C0]
0x180033b40  cmp     rax, rdi
0x180033b43  jz      short loc_180033B8C
0x180033b45  mov     [rsi+rax], r12b
0x180033b49  mov     rcx, [rbp+400h+Block+8]; Block
0x180033b50  call    _free_base
0x180033b55  mov     eax, ebx
0x180033b57  mov     rcx, [rbp+400h+var_40]
0x180033b5e  xor     rcx, rsp; StackCookie
0x180033b61  call    __security_check_cookie
0x180033b66  add     rsp, 4D0h
0x180033b6d  pop     r15
0x180033b6f  pop     r14
0x180033b71  pop     r12
0x180033b73  pop     rdi
0x180033b74  pop     rsi
0x180033b75  pop     rbx
0x180033b76  pop     rbp
0x180033b77  retn
0x180033b78  test    rdi, rdi
0x180033b7b  jz      short loc_180033B0E
0x180033b7d  mov     rax, [rsp+500h+var_4C0]
0x180033b82  cmp     rax, rdi
0x180033b85  jnz     short loc_180033B45
0x180033b87  mov     ebx, 0FFFFFFFEh
0x180033b8c  mov     [rsi+rdi-1], r12b
0x180033b91  jmp     short loc_180033B49
```
