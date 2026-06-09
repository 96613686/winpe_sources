# common_configure_argv_char_

- ea: `0x180004478`
- end: `0x1800045f2`
- name: `common_configure_argv_char_`
- size: `378`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004478`
- `0x180004788`
- `0x180004ca0`
- `0x180007c00`
- `0x180007ee8`
- `0x180008040`
- `0x180009d84`
- `0x180009fac`
- `0x18000aba0`

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
  _acrt_GetModuleFileNameA(0, qword_18007B8E0, 260);
  LODWORD(v4) = (_DWORD)acmdln;
  pgmptr = (char *)qword_18007B8E0;
  if ( !acmdln || !*acmdln )
    v4 = qword_18007B8E0;
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
0x180004478  mov     [rsp-28h+arg_0], rbx
0x18000447d  push    rbp
0x18000447e  push    rsi
0x18000447f  push    rdi
0x180004480  push    r14
0x180004482  push    r15
0x180004484  mov     rbp, rsp
0x180004487  sub     rsp, 30h
0x18000448b  xor     edi, edi
0x18000448d  mov     r14d, ecx
0x180004490  test    ecx, ecx
0x180004492  jnz     short loc_18000449B
0x180004494  xor     eax, eax
0x180004496  jmp     loc_1800045E1
0x18000449b  lea     eax, [rcx-1]
0x18000449e  cmp     eax, 1
0x1800044a1  jbe     short loc_1800044BB
0x1800044a3  call    _errno
0x1800044a8  mov     ebx, 16h
0x1800044ad  mov     [rax], ebx
0x1800044af  call    _invalid_parameter_noinfo
0x1800044b4  mov     eax, ebx
0x1800044b6  jmp     loc_1800045E1
0x1800044bb  call    __acrt_initialize_multibyte
0x1800044c0  lea     rbx, qword_18007B8E0
0x1800044c7  mov     r8d, 104h
0x1800044cd  mov     rdx, rbx
0x1800044d0  xor     ecx, ecx
0x1800044d2  call    __acrt_GetModuleFileNameA
0x1800044d7  mov     rsi, cs:_acmdln
0x1800044de  mov     cs:_pgmptr, rbx
0x1800044e5  test    rsi, rsi
0x1800044e8  jz      short loc_1800044EF
0x1800044ea  cmp     [rsi], dil
0x1800044ed  jnz     short loc_1800044F2
0x1800044ef  mov     rsi, rbx
0x1800044f2  lea     rax, [rbp+arg_18]
0x1800044f6  mov     [rbp+arg_10], rdi
0x1800044fa  lea     r9, [rbp+arg_10]
0x1800044fe  mov     [rsp+30h+var_10], rax
0x180004503  xor     r8d, r8d
0x180004506  mov     [rbp+arg_18], rdi
0x18000450a  xor     edx, edx
0x18000450c  mov     rcx, rsi
0x18000450f  call    parse_command_line_char_
0x180004514  mov     r15, [rbp+arg_10]
0x180004518  mov     r8d, 1
0x18000451e  mov     rdx, [rbp+arg_18]
0x180004522  mov     rcx, r15
0x180004525  call    __acrt_allocate_buffer_for_argv
0x18000452a  mov     rbx, rax
0x18000452d  test    rax, rax
0x180004530  jnz     short loc_18000453E
0x180004532  call    _errno
0x180004537  lea     edi, [rbx+0Ch]
0x18000453a  mov     [rax], edi
0x18000453c  jmp     short loc_180004572
0x18000453e  lea     r8, [rax+r15*8]
0x180004542  mov     rdx, rbx
0x180004545  lea     rax, [rbp+arg_18]
0x180004549  mov     rcx, rsi
0x18000454c  lea     r9, [rbp+arg_10]
0x180004550  mov     [rsp+30h+var_10], rax
0x180004555  call    parse_command_line_char_
0x18000455a  cmp     r14d, 1
0x18000455e  jnz     short loc_18000457D
0x180004560  mov     ecx, dword ptr [rbp+arg_10]
0x180004563  dec     ecx
0x180004565  mov     cs:__argv, rbx
0x18000456c  mov     cs:__argc, ecx
0x180004572  xor     ecx, ecx; Block
0x180004574  call    _free_base
0x180004579  mov     eax, edi
0x18000457b  jmp     short loc_1800045E1
0x18000457d  lea     rdx, [rbp+Block]
0x180004581  mov     [rbp+Block], rdi
0x180004585  mov     rcx, rbx
0x180004588  call    __acrt_expand_narrow_argv_wildcards
0x18000458d  mov     esi, eax
0x18000458f  test    eax, eax
0x180004591  jz      short loc_18000459E
0x180004593  mov     rcx, [rbp+Block]; Block
0x180004597  call    _free_base
0x18000459c  jmp     short loc_1800045D3
0x18000459e  mov     rdx, [rbp+Block]
0x1800045a2  mov     rcx, rdi
0x1800045a5  mov     rax, rdx
0x1800045a8  cmp     [rdx], rdi
0x1800045ab  jz      short loc_1800045B9
0x1800045ad  lea     rax, [rax+8]
0x1800045b1  inc     rcx
0x1800045b4  cmp     [rax], rdi
0x1800045b7  jnz     short loc_1800045AD
0x1800045b9  mov     cs:__argc, ecx
0x1800045bf  xor     ecx, ecx; Block
0x1800045c1  mov     [rbp+Block], rdi
0x1800045c5  mov     cs:__argv, rdx
0x1800045cc  call    _free_base
0x1800045d1  mov     esi, edi
0x1800045d3  mov     rcx, rbx; Block
0x1800045d6  mov     [rbp+Block], rdi
0x1800045da  call    _free_base
0x1800045df  mov     eax, esi
0x1800045e1  mov     rbx, [rsp+30h+arg_0]
0x1800045e6  add     rsp, 30h
0x1800045ea  pop     r15
0x1800045ec  pop     r14
0x1800045ee  pop     rdi
0x1800045ef  pop     rsi
0x1800045f0  pop     rbp
0x1800045f1  retn
```
