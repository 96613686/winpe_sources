# _configure_narrow_argv

- ea: `0x180004d00`
- end: `0x180004e7d`
- name: `_configure_narrow_argv`
- size: `381`
- prototype: `errno_t __cdecl(_crt_argv_mode mode)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800030d4`
- `0x1800031b4`

## callees

- `0x180004788`
- `0x180004ca0`
- `0x180004d00`
- `0x180007c00`
- `0x180007ee8`
- `0x180008040`
- `0x180009d84`
- `0x180009fac`
- `0x18000aba0`

## pseudocode

```c
errno_t __cdecl configure_narrow_argv(_crt_argv_mode mode)
{
  errno_t v1; // edi
  __int64 *v3; // rsi
  int v4; // r15d
  __int64 buffer_for_argv; // rax
  void *v6; // rbx
  void *v7; // rcx
  errno_t v8; // esi
  char **v9; // rdx
  int v10; // ecx
  _QWORD *i; // rax
  void *Block; // [rsp+68h] [rbp+38h] BYREF
  __int64 v14; // [rsp+70h] [rbp+40h] BYREF
  __int64 v15; // [rsp+78h] [rbp+48h] BYREF

  v1 = 0;
  if ( mode )
  {
    if ( (unsigned int)(mode - 1) > 1 )
    {
      v1 = 22;
      *errno() = 22;
      invalid_parameter_noinfo();
      return v1;
    }
    _acrt_initialize_multibyte();
    _acrt_GetModuleFileNameA(0, qword_18007B8E0, 260);
    LODWORD(v3) = (_DWORD)acmdln;
    pgmptr = (char *)qword_18007B8E0;
    if ( !acmdln || !*acmdln )
      v3 = qword_18007B8E0;
    v14 = 0;
    v15 = 0;
    parse_command_line_char_((_DWORD)v3, 0, 0, (unsigned int)&v14, (__int64)&v15);
    v4 = v14;
    buffer_for_argv = _acrt_allocate_buffer_for_argv(v14, v15, 1);
    v6 = (void *)buffer_for_argv;
    if ( buffer_for_argv )
    {
      parse_command_line_char_((_DWORD)v3, buffer_for_argv, buffer_for_argv + 8 * v4, (unsigned int)&v14, (__int64)&v15);
      if ( mode != _crt_argv_unexpanded_arguments )
      {
        Block = 0;
        v8 = _acrt_expand_narrow_argv_wildcards(v6, &Block);
        if ( v8 )
        {
          free_base(Block);
          Block = 0;
          free_base(v6);
          return v8;
        }
        v9 = (char **)Block;
        v10 = 0;
        for ( i = Block; *i; ++v10 )
          ++i;
        _argc = v10;
        Block = 0;
        _argv = v9;
        free_base(0);
        v7 = v6;
        Block = 0;
LABEL_17:
        free_base(v7);
        return v1;
      }
      _argv = (char **)v6;
      _argc = v14 - 1;
    }
    else
    {
      v1 = 12;
      *errno() = 12;
    }
    v7 = 0;
    goto LABEL_17;
  }
  return v1;
}

```

## disassembly

```asm
0x180004d00  mov     [rsp-28h+arg_0], rbx
0x180004d05  push    rbp
0x180004d06  push    rsi
0x180004d07  push    rdi
0x180004d08  push    r14
0x180004d0a  push    r15
0x180004d0c  mov     rbp, rsp
0x180004d0f  sub     rsp, 30h
0x180004d13  xor     edi, edi
0x180004d15  mov     r14d, ecx
0x180004d18  test    ecx, ecx
0x180004d1a  jz      loc_180004E6A
0x180004d20  lea     eax, [rcx-1]
0x180004d23  cmp     eax, 1
0x180004d26  jbe     short loc_180004D3E
0x180004d28  call    _errno
0x180004d2d  mov     edi, 16h
0x180004d32  mov     [rax], edi
0x180004d34  call    _invalid_parameter_noinfo
0x180004d39  jmp     loc_180004E6A
0x180004d3e  call    __acrt_initialize_multibyte
0x180004d43  lea     rbx, qword_18007B8E0
0x180004d4a  mov     r8d, 104h
0x180004d50  mov     rdx, rbx
0x180004d53  xor     ecx, ecx
0x180004d55  call    __acrt_GetModuleFileNameA
0x180004d5a  mov     rsi, cs:_acmdln
0x180004d61  mov     cs:_pgmptr, rbx
0x180004d68  test    rsi, rsi
0x180004d6b  jz      short loc_180004D72
0x180004d6d  cmp     [rsi], dil
0x180004d70  jnz     short loc_180004D75
0x180004d72  mov     rsi, rbx
0x180004d75  lea     rax, [rbp+arg_18]
0x180004d79  mov     [rbp+arg_10], rdi
0x180004d7d  lea     r9, [rbp+arg_10]
0x180004d81  mov     [rsp+30h+var_10], rax
0x180004d86  xor     r8d, r8d
0x180004d89  mov     [rbp+arg_18], rdi
0x180004d8d  xor     edx, edx
0x180004d8f  mov     rcx, rsi
0x180004d92  call    parse_command_line_char_
0x180004d97  mov     r15, [rbp+arg_10]
0x180004d9b  mov     r8d, 1
0x180004da1  mov     rdx, [rbp+arg_18]
0x180004da5  mov     rcx, r15
0x180004da8  call    __acrt_allocate_buffer_for_argv
0x180004dad  mov     rbx, rax
0x180004db0  test    rax, rax
0x180004db3  jnz     short loc_180004DC6
0x180004db5  call    _errno
0x180004dba  lea     edi, [rbx+0Ch]
0x180004dbd  mov     [rax], edi
0x180004dbf  xor     ecx, ecx
0x180004dc1  jmp     loc_180004E65
0x180004dc6  lea     r8, [rax+r15*8]
0x180004dca  mov     rdx, rbx
0x180004dcd  lea     rax, [rbp+arg_18]
0x180004dd1  mov     rcx, rsi
0x180004dd4  lea     r9, [rbp+arg_10]
0x180004dd8  mov     [rsp+30h+var_10], rax
0x180004ddd  call    parse_command_line_char_
0x180004de2  cmp     r14d, 1
0x180004de6  jnz     short loc_180004DFC
0x180004de8  mov     eax, dword ptr [rbp+arg_10]
0x180004deb  dec     eax
0x180004ded  mov     cs:__argv, rbx
0x180004df4  mov     cs:__argc, eax
0x180004dfa  jmp     short loc_180004DBF
0x180004dfc  lea     rdx, [rbp+Block]
0x180004e00  mov     [rbp+Block], rdi
0x180004e04  mov     rcx, rbx
0x180004e07  call    __acrt_expand_narrow_argv_wildcards
0x180004e0c  mov     esi, eax
0x180004e0e  test    eax, eax
0x180004e10  jz      short loc_180004E2B
0x180004e12  mov     rcx, [rbp+Block]; Block
0x180004e16  call    _free_base
0x180004e1b  mov     rcx, rbx; Block
0x180004e1e  mov     [rbp+Block], rdi
0x180004e22  call    _free_base
0x180004e27  mov     edi, esi
0x180004e29  jmp     short loc_180004E6A
0x180004e2b  mov     rdx, [rbp+Block]
0x180004e2f  mov     rcx, rdi
0x180004e32  mov     rax, rdx
0x180004e35  cmp     [rdx], rdi
0x180004e38  jz      short loc_180004E46
0x180004e3a  lea     rax, [rax+8]
0x180004e3e  inc     rcx
0x180004e41  cmp     [rax], rdi
0x180004e44  jnz     short loc_180004E3A
0x180004e46  mov     cs:__argc, ecx
0x180004e4c  xor     ecx, ecx; Block
0x180004e4e  mov     [rbp+Block], rdi
0x180004e52  mov     cs:__argv, rdx
0x180004e59  call    _free_base
0x180004e5e  mov     rcx, rbx; Block
0x180004e61  mov     [rbp+Block], rdi
0x180004e65  call    _free_base
0x180004e6a  mov     rbx, [rsp+30h+arg_0]
0x180004e6f  mov     eax, edi
0x180004e71  add     rsp, 30h
0x180004e75  pop     r15
0x180004e77  pop     r14
0x180004e79  pop     rdi
0x180004e7a  pop     rsi
0x180004e7b  pop     rbp
0x180004e7c  retn
```
