# _configure_narrow_argv

- ea: `0x1800045a4`
- end: `0x180004721`
- name: `_configure_narrow_argv`
- size: `381`
- prototype: `errno_t __cdecl(_crt_argv_mode mode)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002988`
- `0x180002a68`

## callees

- `0x18000402c`
- `0x180004544`
- `0x1800045a4`
- `0x1800074a0`
- `0x180007788`
- `0x1800078e0`
- `0x180009624`
- `0x18000984c`
- `0x18000a440`

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
    _acrt_GetModuleFileNameA(0, qword_180077E30, 260);
    LODWORD(v3) = (_DWORD)acmdln;
    pgmptr = (char *)qword_180077E30;
    if ( !acmdln || !*acmdln )
      v3 = qword_180077E30;
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
0x1800045a4  mov     [rsp-28h+arg_0], rbx
0x1800045a9  push    rbp
0x1800045aa  push    rsi
0x1800045ab  push    rdi
0x1800045ac  push    r14
0x1800045ae  push    r15
0x1800045b0  mov     rbp, rsp
0x1800045b3  sub     rsp, 30h
0x1800045b7  xor     edi, edi
0x1800045b9  mov     r14d, ecx
0x1800045bc  test    ecx, ecx
0x1800045be  jz      loc_18000470E
0x1800045c4  lea     eax, [rcx-1]
0x1800045c7  cmp     eax, 1
0x1800045ca  jbe     short loc_1800045E2
0x1800045cc  call    _errno
0x1800045d1  mov     edi, 16h
0x1800045d6  mov     [rax], edi
0x1800045d8  call    _invalid_parameter_noinfo
0x1800045dd  jmp     loc_18000470E
0x1800045e2  call    __acrt_initialize_multibyte
0x1800045e7  lea     rbx, qword_180077E30
0x1800045ee  mov     r8d, 104h
0x1800045f4  mov     rdx, rbx
0x1800045f7  xor     ecx, ecx
0x1800045f9  call    __acrt_GetModuleFileNameA
0x1800045fe  mov     rsi, cs:_acmdln
0x180004605  mov     cs:_pgmptr, rbx
0x18000460c  test    rsi, rsi
0x18000460f  jz      short loc_180004616
0x180004611  cmp     [rsi], dil
0x180004614  jnz     short loc_180004619
0x180004616  mov     rsi, rbx
0x180004619  lea     rax, [rbp+arg_18]
0x18000461d  mov     [rbp+arg_10], rdi
0x180004621  lea     r9, [rbp+arg_10]
0x180004625  mov     [rsp+30h+var_10], rax
0x18000462a  xor     r8d, r8d
0x18000462d  mov     [rbp+arg_18], rdi
0x180004631  xor     edx, edx
0x180004633  mov     rcx, rsi
0x180004636  call    parse_command_line_char_
0x18000463b  mov     r15, [rbp+arg_10]
0x18000463f  mov     r8d, 1
0x180004645  mov     rdx, [rbp+arg_18]
0x180004649  mov     rcx, r15
0x18000464c  call    __acrt_allocate_buffer_for_argv
0x180004651  mov     rbx, rax
0x180004654  test    rax, rax
0x180004657  jnz     short loc_18000466A
0x180004659  call    _errno
0x18000465e  lea     edi, [rbx+0Ch]
0x180004661  mov     [rax], edi
0x180004663  xor     ecx, ecx
0x180004665  jmp     loc_180004709
0x18000466a  lea     r8, [rax+r15*8]
0x18000466e  mov     rdx, rbx
0x180004671  lea     rax, [rbp+arg_18]
0x180004675  mov     rcx, rsi
0x180004678  lea     r9, [rbp+arg_10]
0x18000467c  mov     [rsp+30h+var_10], rax
0x180004681  call    parse_command_line_char_
0x180004686  cmp     r14d, 1
0x18000468a  jnz     short loc_1800046A0
0x18000468c  mov     eax, dword ptr [rbp+arg_10]
0x18000468f  dec     eax
0x180004691  mov     cs:__argv, rbx
0x180004698  mov     cs:__argc, eax
0x18000469e  jmp     short loc_180004663
0x1800046a0  lea     rdx, [rbp+Block]
0x1800046a4  mov     [rbp+Block], rdi
0x1800046a8  mov     rcx, rbx
0x1800046ab  call    __acrt_expand_narrow_argv_wildcards
0x1800046b0  mov     esi, eax
0x1800046b2  test    eax, eax
0x1800046b4  jz      short loc_1800046CF
0x1800046b6  mov     rcx, [rbp+Block]; Block
0x1800046ba  call    _free_base
0x1800046bf  mov     rcx, rbx; Block
0x1800046c2  mov     [rbp+Block], rdi
0x1800046c6  call    _free_base
0x1800046cb  mov     edi, esi
0x1800046cd  jmp     short loc_18000470E
0x1800046cf  mov     rdx, [rbp+Block]
0x1800046d3  mov     rcx, rdi
0x1800046d6  mov     rax, rdx
0x1800046d9  cmp     [rdx], rdi
0x1800046dc  jz      short loc_1800046EA
0x1800046de  lea     rax, [rax+8]
0x1800046e2  inc     rcx
0x1800046e5  cmp     [rax], rdi
0x1800046e8  jnz     short loc_1800046DE
0x1800046ea  mov     cs:__argc, ecx
0x1800046f0  xor     ecx, ecx; Block
0x1800046f2  mov     [rbp+Block], rdi
0x1800046f6  mov     cs:__argv, rdx
0x1800046fd  call    _free_base
0x180004702  mov     rcx, rbx; Block
0x180004705  mov     [rbp+Block], rdi
0x180004709  call    _free_base
0x18000470e  mov     rbx, [rsp+30h+arg_0]
0x180004713  mov     eax, edi
0x180004715  add     rsp, 30h
0x180004719  pop     r15
0x18000471b  pop     r14
0x18000471d  pop     rdi
0x18000471e  pop     rsi
0x18000471f  pop     rbp
0x180004720  retn
```
