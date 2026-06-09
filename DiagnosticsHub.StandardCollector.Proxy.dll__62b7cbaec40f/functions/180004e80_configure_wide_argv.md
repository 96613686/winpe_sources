# _configure_wide_argv

- ea: `0x180004e80`
- end: `0x180004ff9`
- name: `_configure_wide_argv`
- size: `377`
- prototype: `errno_t __cdecl(_crt_argv_mode mode)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004948`
- `0x180004ca0`
- `0x180004e80`
- `0x180007c00`
- `0x180007ee8`
- `0x180008040`
- `0x180009d8c`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x180004ed0`
- `KERNEL32!GetModuleFileNameW` at `0x180004ed0`

## pseudocode

```c
errno_t __cdecl configure_wide_argv(_crt_argv_mode mode)
{
  errno_t v1; // edi
  WCHAR *v3; // rsi
  int v4; // r15d
  __int64 buffer_for_argv; // rax
  void *v6; // rbx
  void *v7; // rcx
  errno_t v8; // esi
  wchar_t **v9; // rdx
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
    GetModuleFileNameW(0, &Filename, 0x104u);
    LODWORD(v3) = (_DWORD)wcmdln;
    wpgmptr = &Filename;
    if ( !wcmdln || !*wcmdln )
      v3 = &Filename;
    v14 = 0;
    v15 = 0;
    parse_command_line_wchar_t_((_DWORD)v3, 0, 0, (unsigned int)&v14, (__int64)&v15);
    v4 = v14;
    buffer_for_argv = _acrt_allocate_buffer_for_argv(v14, v15, 2);
    v6 = (void *)buffer_for_argv;
    if ( buffer_for_argv )
    {
      parse_command_line_wchar_t_(
        (_DWORD)v3,
        buffer_for_argv,
        buffer_for_argv + 8 * v4,
        (unsigned int)&v14,
        (__int64)&v15);
      if ( mode != _crt_argv_unexpanded_arguments )
      {
        Block = 0;
        v8 = _acrt_expand_wide_argv_wildcards(v6, &Block);
        if ( v8 )
        {
          free_base(Block);
          Block = 0;
          free_base(v6);
          return v8;
        }
        v9 = (wchar_t **)Block;
        v10 = 0;
        for ( i = Block; *i; ++v10 )
          ++i;
        _argc = v10;
        Block = 0;
        _wargv = v9;
        free_base(0);
        v7 = v6;
        Block = 0;
LABEL_17:
        free_base(v7);
        return v1;
      }
      _wargv = (wchar_t **)v6;
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
0x180004e80  mov     [rsp-28h+arg_0], rbx
0x180004e85  push    rbp
0x180004e86  push    rsi
0x180004e87  push    rdi
0x180004e88  push    r14
0x180004e8a  push    r15
0x180004e8c  mov     rbp, rsp
0x180004e8f  sub     rsp, 30h
0x180004e93  xor     edi, edi
0x180004e95  mov     r14d, ecx
0x180004e98  test    ecx, ecx
0x180004e9a  jz      loc_180004FE6
0x180004ea0  lea     eax, [rcx-1]
0x180004ea3  cmp     eax, 1
0x180004ea6  jbe     short loc_180004EBE
0x180004ea8  call    _errno
0x180004ead  mov     edi, 16h
0x180004eb2  mov     [rax], edi
0x180004eb4  call    _invalid_parameter_noinfo
0x180004eb9  jmp     loc_180004FE6
0x180004ebe  lea     rbx, Filename
0x180004ec5  mov     r8d, 104h; nSize
0x180004ecb  mov     rdx, rbx; lpFilename
0x180004ece  xor     ecx, ecx; hModule
0x180004ed0  call    cs:__imp_GetModuleFileNameW
0x180004ed6  mov     rsi, cs:_wcmdln
0x180004edd  mov     cs:_wpgmptr, rbx
0x180004ee4  test    rsi, rsi
0x180004ee7  jz      short loc_180004EEE
0x180004ee9  cmp     [rsi], di
0x180004eec  jnz     short loc_180004EF1
0x180004eee  mov     rsi, rbx
0x180004ef1  lea     rax, [rbp+arg_18]
0x180004ef5  mov     [rbp+arg_10], rdi
0x180004ef9  lea     r9, [rbp+arg_10]
0x180004efd  mov     [rsp+30h+var_10], rax
0x180004f02  xor     r8d, r8d
0x180004f05  mov     [rbp+arg_18], rdi
0x180004f09  xor     edx, edx
0x180004f0b  mov     rcx, rsi
0x180004f0e  call    parse_command_line_wchar_t_
0x180004f13  mov     r15, [rbp+arg_10]
0x180004f17  mov     r8d, 2
0x180004f1d  mov     rdx, [rbp+arg_18]
0x180004f21  mov     rcx, r15
0x180004f24  call    __acrt_allocate_buffer_for_argv
0x180004f29  mov     rbx, rax
0x180004f2c  test    rax, rax
0x180004f2f  jnz     short loc_180004F42
0x180004f31  call    _errno
0x180004f36  lea     edi, [rbx+0Ch]
0x180004f39  mov     [rax], edi
0x180004f3b  xor     ecx, ecx
0x180004f3d  jmp     loc_180004FE1
0x180004f42  lea     r8, [rax+r15*8]
0x180004f46  mov     rdx, rbx
0x180004f49  lea     rax, [rbp+arg_18]
0x180004f4d  mov     rcx, rsi
0x180004f50  lea     r9, [rbp+arg_10]
0x180004f54  mov     [rsp+30h+var_10], rax
0x180004f59  call    parse_command_line_wchar_t_
0x180004f5e  cmp     r14d, 1
0x180004f62  jnz     short loc_180004F78
0x180004f64  mov     eax, dword ptr [rbp+arg_10]
0x180004f67  dec     eax
0x180004f69  mov     cs:__wargv, rbx
0x180004f70  mov     cs:__argc, eax
0x180004f76  jmp     short loc_180004F3B
0x180004f78  lea     rdx, [rbp+Block]
0x180004f7c  mov     [rbp+Block], rdi
0x180004f80  mov     rcx, rbx
0x180004f83  call    __acrt_expand_wide_argv_wildcards
0x180004f88  mov     esi, eax
0x180004f8a  test    eax, eax
0x180004f8c  jz      short loc_180004FA7
0x180004f8e  mov     rcx, [rbp+Block]; Block
0x180004f92  call    _free_base
0x180004f97  mov     rcx, rbx; Block
0x180004f9a  mov     [rbp+Block], rdi
0x180004f9e  call    _free_base
0x180004fa3  mov     edi, esi
0x180004fa5  jmp     short loc_180004FE6
0x180004fa7  mov     rdx, [rbp+Block]
0x180004fab  mov     rcx, rdi
0x180004fae  mov     rax, rdx
0x180004fb1  cmp     [rdx], rdi
0x180004fb4  jz      short loc_180004FC2
0x180004fb6  lea     rax, [rax+8]
0x180004fba  inc     rcx
0x180004fbd  cmp     [rax], rdi
0x180004fc0  jnz     short loc_180004FB6
0x180004fc2  mov     cs:__argc, ecx
0x180004fc8  xor     ecx, ecx; Block
0x180004fca  mov     [rbp+Block], rdi
0x180004fce  mov     cs:__wargv, rdx
0x180004fd5  call    _free_base
0x180004fda  mov     rcx, rbx; Block
0x180004fdd  mov     [rbp+Block], rdi
0x180004fe1  call    _free_base
0x180004fe6  mov     rbx, [rsp+30h+arg_0]
0x180004feb  mov     eax, edi
0x180004fed  add     rsp, 30h
0x180004ff1  pop     r15
0x180004ff3  pop     r14
0x180004ff5  pop     rdi
0x180004ff6  pop     rsi
0x180004ff7  pop     rbp
0x180004ff8  retn
```
