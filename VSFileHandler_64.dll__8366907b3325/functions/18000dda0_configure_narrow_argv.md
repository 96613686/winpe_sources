# _configure_narrow_argv

- ea: `0x18000dda0`
- end: `0x18000df26`
- name: `_configure_narrow_argv`
- size: `390`
- prototype: `errno_t __cdecl(_crt_argv_mode mode)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000775c`

## callees

- `0x18000be9c`
- `0x18000bfbc`
- `0x18000db80`
- `0x18000dd40`
- `0x18000dda0`
- `0x18000fe3c`
- `0x180012aec`
- `0x180012c08`
- `0x180013450`

## pseudocode

```c
errno_t __cdecl configure_narrow_argv(_crt_argv_mode mode)
{
  errno_t v1; // edi
  errno_t v3; // ebx
  void *v4; // rsi
  int v5; // r15d
  __int64 buffer_for_argv; // rax
  char **v7; // rbx
  char **v8; // rcx
  errno_t v9; // esi
  char **v10; // rdx
  int v11; // ecx
  _QWORD *i; // rax
  void *Block; // [rsp+68h] [rbp+38h] BYREF
  __int64 v15; // [rsp+70h] [rbp+40h] BYREF
  __int64 v16; // [rsp+78h] [rbp+48h] BYREF

  v1 = 0;
  if ( mode )
  {
    if ( (unsigned int)(mode - 1) <= 1 )
    {
      _acrt_initialize_multibyte();
      _acrt_GetModuleFileNameA(0, &unk_18003E320, 260);
      LODWORD(v4) = (_DWORD)acmdln;
      pgmptr = (char *)&unk_18003E320;
      if ( !acmdln || !*acmdln )
        v4 = &unk_18003E320;
      v15 = 0;
      v16 = 0;
      parse_command_line_char_((_DWORD)v4, 0, 0, (unsigned int)&v15, (__int64)&v16);
      v5 = v15;
      buffer_for_argv = _acrt_allocate_buffer_for_argv(v15, v16, 1);
      v7 = (char **)buffer_for_argv;
      if ( buffer_for_argv )
      {
        parse_command_line_char_(
          (_DWORD)v4,
          buffer_for_argv,
          buffer_for_argv + 8 * v5,
          (unsigned int)&v15,
          (__int64)&v16);
        if ( mode == _crt_argv_unexpanded_arguments )
        {
          _argv = v7;
          _argc = v15 - 1;
          v8 = 0;
        }
        else
        {
          Block = 0;
          v9 = _acrt_expand_narrow_argv_wildcards(v7, &Block);
          if ( v9 )
          {
            free_base(Block);
            Block = 0;
            free_base(v7);
            return v9;
          }
          v10 = (char **)Block;
          v11 = 0;
          for ( i = Block; *i; ++v11 )
            ++i;
          _argc = v11;
          Block = 0;
          _argv = v10;
          free_base(0);
          v8 = v7;
          Block = 0;
        }
        free_base(v8);
        return v1;
      }
      v3 = 12;
      *errno() = 12;
      free_base(0);
    }
    else
    {
      v3 = 22;
      *errno() = 22;
      invalid_parameter_noinfo();
    }
    return v3;
  }
  return v1;
}

```

## disassembly

```asm
0x18000dda0  mov     [rsp-28h+arg_0], rbx
0x18000dda5  push    rbp
0x18000dda6  push    rsi
0x18000dda7  push    rdi
0x18000dda8  push    r14
0x18000ddaa  push    r15
0x18000ddac  mov     rbp, rsp
0x18000ddaf  sub     rsp, 30h
0x18000ddb3  xor     edi, edi
0x18000ddb5  mov     r14d, ecx
0x18000ddb8  test    ecx, ecx
0x18000ddba  jz      loc_18000DF13
0x18000ddc0  lea     eax, [rcx-1]
0x18000ddc3  cmp     eax, 1
0x18000ddc6  jbe     short loc_18000DDDE
0x18000ddc8  call    _errno
0x18000ddcd  lea     ebx, [rdi+16h]
0x18000ddd0  mov     [rax], ebx
0x18000ddd2  call    _invalid_parameter_noinfo
0x18000ddd7  mov     edi, ebx
0x18000ddd9  jmp     loc_18000DF13
0x18000ddde  call    __acrt_initialize_multibyte
0x18000dde3  lea     rbx, unk_18003E320
0x18000ddea  mov     r8d, 104h
0x18000ddf0  mov     rdx, rbx
0x18000ddf3  xor     ecx, ecx
0x18000ddf5  call    __acrt_GetModuleFileNameA
0x18000ddfa  mov     rsi, cs:_acmdln
0x18000de01  mov     cs:_pgmptr, rbx
0x18000de08  test    rsi, rsi
0x18000de0b  jz      short loc_18000DE12
0x18000de0d  cmp     [rsi], dil
0x18000de10  jnz     short loc_18000DE15
0x18000de12  mov     rsi, rbx
0x18000de15  lea     rax, [rbp+arg_18]
0x18000de19  mov     [rbp+arg_10], rdi
0x18000de1d  lea     r9, [rbp+arg_10]
0x18000de21  mov     [rsp+30h+var_10], rax
0x18000de26  xor     r8d, r8d
0x18000de29  mov     [rbp+arg_18], rdi
0x18000de2d  xor     edx, edx
0x18000de2f  mov     rcx, rsi
0x18000de32  call    parse_command_line_char_
0x18000de37  mov     r15, [rbp+arg_10]
0x18000de3b  mov     r8d, 1
0x18000de41  mov     rdx, [rbp+arg_18]
0x18000de45  mov     rcx, r15
0x18000de48  call    __acrt_allocate_buffer_for_argv
0x18000de4d  mov     rbx, rax
0x18000de50  test    rax, rax
0x18000de53  jnz     short loc_18000DE6D
0x18000de55  call    _errno
0x18000de5a  mov     ebx, 0Ch
0x18000de5f  xor     ecx, ecx; Block
0x18000de61  mov     [rax], ebx
0x18000de63  call    _free_base
0x18000de68  jmp     loc_18000DDD7
0x18000de6d  lea     r8, [rax+r15*8]
0x18000de71  mov     rdx, rbx
0x18000de74  lea     rax, [rbp+arg_18]
0x18000de78  mov     rcx, rsi
0x18000de7b  lea     r9, [rbp+arg_10]
0x18000de7f  mov     [rsp+30h+var_10], rax
0x18000de84  call    parse_command_line_char_
0x18000de89  cmp     r14d, 1
0x18000de8d  jnz     short loc_18000DEA5
0x18000de8f  mov     eax, dword ptr [rbp+arg_10]
0x18000de92  dec     eax
0x18000de94  mov     cs:__argv, rbx
0x18000de9b  mov     cs:__argc, eax
0x18000dea1  xor     ecx, ecx
0x18000dea3  jmp     short loc_18000DF0E
0x18000dea5  lea     rdx, [rbp+Block]
0x18000dea9  mov     [rbp+Block], rdi
0x18000dead  mov     rcx, rbx
0x18000deb0  call    __acrt_expand_narrow_argv_wildcards
0x18000deb5  mov     esi, eax
0x18000deb7  test    eax, eax
0x18000deb9  jz      short loc_18000DED4
0x18000debb  mov     rcx, [rbp+Block]; Block
0x18000debf  call    _free_base
0x18000dec4  mov     rcx, rbx; Block
0x18000dec7  mov     [rbp+Block], rdi
0x18000decb  call    _free_base
0x18000ded0  mov     edi, esi
0x18000ded2  jmp     short loc_18000DF13
0x18000ded4  mov     rdx, [rbp+Block]
0x18000ded8  mov     rcx, rdi
0x18000dedb  mov     rax, rdx
0x18000dede  cmp     [rdx], rdi
0x18000dee1  jz      short loc_18000DEEF
0x18000dee3  lea     rax, [rax+8]
0x18000dee7  inc     rcx
0x18000deea  cmp     [rax], rdi
0x18000deed  jnz     short loc_18000DEE3
0x18000deef  mov     cs:__argc, ecx
0x18000def5  xor     ecx, ecx; Block
0x18000def7  mov     [rbp+Block], rdi
0x18000defb  mov     cs:__argv, rdx
0x18000df02  call    _free_base
0x18000df07  mov     rcx, rbx; Block
0x18000df0a  mov     [rbp+Block], rdi
0x18000df0e  call    _free_base
0x18000df13  mov     rbx, [rsp+30h+arg_0]
0x18000df18  mov     eax, edi
0x18000df1a  add     rsp, 30h
0x18000df1e  pop     r15
0x18000df20  pop     r14
0x18000df22  pop     rdi
0x18000df23  pop     rsi
0x18000df24  pop     rbp
0x18000df25  retn
```
