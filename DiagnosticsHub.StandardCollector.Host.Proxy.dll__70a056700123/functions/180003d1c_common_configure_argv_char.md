# common_configure_argv_char_

- ea: `0x180003d1c`
- end: `0x180003e96`
- name: `common_configure_argv_char_`
- size: `378`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003d1c`
- `0x18000402c`
- `0x180004544`
- `0x1800074a0`
- `0x180007788`
- `0x1800078e0`
- `0x180009624`
- `0x18000984c`
- `0x18000a440`

## pseudocode

```c
__int64 __fastcall common_configure_argv_char_(int a1)
{
  unsigned int v1; // edi
  __int64 *v4; // rsi
  int v5; // r15d
  __int64 buffer_for_argv; // rax
  char **v7; // rbx
  unsigned int v8; // esi
  char **v9; // rdx
  int v10; // ecx
  _QWORD *i; // rax
  void *Block; // [rsp+68h] [rbp+38h] BYREF
  __int64 v13; // [rsp+70h] [rbp+40h] BYREF
  __int64 v14; // [rsp+78h] [rbp+48h] BYREF

  v1 = 0;
  if ( !a1 )
    return 0;
  if ( (unsigned int)(a1 - 1) > 1 )
  {
    *errno() = 22;
    invalid_parameter_noinfo();
    return 22;
  }
  _acrt_initialize_multibyte();
  _acrt_GetModuleFileNameA(0, qword_180077E30, 260);
  LODWORD(v4) = (_DWORD)acmdln;
  pgmptr = (char *)qword_180077E30;
  if ( !acmdln || !*acmdln )
    v4 = qword_180077E30;
  v13 = 0;
  v14 = 0;
  parse_command_line_char_((_DWORD)v4, 0, 0, (unsigned int)&v13, (__int64)&v14);
  v5 = v13;
  buffer_for_argv = _acrt_allocate_buffer_for_argv(v13, v14, 1);
  v7 = (char **)buffer_for_argv;
  if ( !buffer_for_argv )
  {
    v1 = 12;
    *errno() = 12;
LABEL_12:
    free_base(0);
    return v1;
  }
  parse_command_line_char_((_DWORD)v4, buffer_for_argv, buffer_for_argv + 8 * v5, (unsigned int)&v13, (__int64)&v14);
  if ( a1 == 1 )
  {
    _argv = v7;
    _argc = v13 - 1;
    goto LABEL_12;
  }
  Block = 0;
  v8 = _acrt_expand_narrow_argv_wildcards(v7, &Block);
  if ( v8 )
  {
    free_base(Block);
  }
  else
  {
    v9 = (char **)Block;
    v10 = 0;
    for ( i = Block; *i; ++v10 )
      ++i;
    _argc = v10;
    Block = 0;
    _argv = v9;
    free_base(0);
    v8 = 0;
  }
  Block = 0;
  free_base(v7);
  return v8;
}

```

## disassembly

```asm
0x180003d1c  mov     [rsp-28h+arg_0], rbx
0x180003d21  push    rbp
0x180003d22  push    rsi
0x180003d23  push    rdi
0x180003d24  push    r14
0x180003d26  push    r15
0x180003d28  mov     rbp, rsp
0x180003d2b  sub     rsp, 30h
0x180003d2f  xor     edi, edi
0x180003d31  mov     r14d, ecx
0x180003d34  test    ecx, ecx
0x180003d36  jnz     short loc_180003D3F
0x180003d38  xor     eax, eax
0x180003d3a  jmp     loc_180003E85
0x180003d3f  lea     eax, [rcx-1]
0x180003d42  cmp     eax, 1
0x180003d45  jbe     short loc_180003D5F
0x180003d47  call    _errno
0x180003d4c  mov     ebx, 16h
0x180003d51  mov     [rax], ebx
0x180003d53  call    _invalid_parameter_noinfo
0x180003d58  mov     eax, ebx
0x180003d5a  jmp     loc_180003E85
0x180003d5f  call    __acrt_initialize_multibyte
0x180003d64  lea     rbx, qword_180077E30
0x180003d6b  mov     r8d, 104h
0x180003d71  mov     rdx, rbx
0x180003d74  xor     ecx, ecx
0x180003d76  call    __acrt_GetModuleFileNameA
0x180003d7b  mov     rsi, cs:_acmdln
0x180003d82  mov     cs:_pgmptr, rbx
0x180003d89  test    rsi, rsi
0x180003d8c  jz      short loc_180003D93
0x180003d8e  cmp     [rsi], dil
0x180003d91  jnz     short loc_180003D96
0x180003d93  mov     rsi, rbx
0x180003d96  lea     rax, [rbp+arg_18]
0x180003d9a  mov     [rbp+arg_10], rdi
0x180003d9e  lea     r9, [rbp+arg_10]
0x180003da2  mov     [rsp+30h+var_10], rax
0x180003da7  xor     r8d, r8d
0x180003daa  mov     [rbp+arg_18], rdi
0x180003dae  xor     edx, edx
0x180003db0  mov     rcx, rsi
0x180003db3  call    parse_command_line_char_
0x180003db8  mov     r15, [rbp+arg_10]
0x180003dbc  mov     r8d, 1
0x180003dc2  mov     rdx, [rbp+arg_18]
0x180003dc6  mov     rcx, r15
0x180003dc9  call    __acrt_allocate_buffer_for_argv
0x180003dce  mov     rbx, rax
0x180003dd1  test    rax, rax
0x180003dd4  jnz     short loc_180003DE2
0x180003dd6  call    _errno
0x180003ddb  lea     edi, [rbx+0Ch]
0x180003dde  mov     [rax], edi
0x180003de0  jmp     short loc_180003E16
0x180003de2  lea     r8, [rax+r15*8]
0x180003de6  mov     rdx, rbx
0x180003de9  lea     rax, [rbp+arg_18]
0x180003ded  mov     rcx, rsi
0x180003df0  lea     r9, [rbp+arg_10]
0x180003df4  mov     [rsp+30h+var_10], rax
0x180003df9  call    parse_command_line_char_
0x180003dfe  cmp     r14d, 1
0x180003e02  jnz     short loc_180003E21
0x180003e04  mov     ecx, dword ptr [rbp+arg_10]
0x180003e07  dec     ecx
0x180003e09  mov     cs:__argv, rbx
0x180003e10  mov     cs:__argc, ecx
0x180003e16  xor     ecx, ecx; Block
0x180003e18  call    _free_base
0x180003e1d  mov     eax, edi
0x180003e1f  jmp     short loc_180003E85
0x180003e21  lea     rdx, [rbp+Block]
0x180003e25  mov     [rbp+Block], rdi
0x180003e29  mov     rcx, rbx
0x180003e2c  call    __acrt_expand_narrow_argv_wildcards
0x180003e31  mov     esi, eax
0x180003e33  test    eax, eax
0x180003e35  jz      short loc_180003E42
0x180003e37  mov     rcx, [rbp+Block]; Block
0x180003e3b  call    _free_base
0x180003e40  jmp     short loc_180003E77
0x180003e42  mov     rdx, [rbp+Block]
0x180003e46  mov     rcx, rdi
0x180003e49  mov     rax, rdx
0x180003e4c  cmp     [rdx], rdi
0x180003e4f  jz      short loc_180003E5D
0x180003e51  lea     rax, [rax+8]
0x180003e55  inc     rcx
0x180003e58  cmp     [rax], rdi
0x180003e5b  jnz     short loc_180003E51
0x180003e5d  mov     cs:__argc, ecx
0x180003e63  xor     ecx, ecx; Block
0x180003e65  mov     [rbp+Block], rdi
0x180003e69  mov     cs:__argv, rdx
0x180003e70  call    _free_base
0x180003e75  mov     esi, edi
0x180003e77  mov     rcx, rbx; Block
0x180003e7a  mov     [rbp+Block], rdi
0x180003e7e  call    _free_base
0x180003e83  mov     eax, esi
0x180003e85  mov     rbx, [rsp+30h+arg_0]
0x180003e8a  add     rsp, 30h
0x180003e8e  pop     r15
0x180003e90  pop     r14
0x180003e92  pop     rdi
0x180003e93  pop     rsi
0x180003e94  pop     rbp
0x180003e95  retn
```
