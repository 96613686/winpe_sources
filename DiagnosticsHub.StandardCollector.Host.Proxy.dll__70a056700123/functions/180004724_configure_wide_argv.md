# _configure_wide_argv

- ea: `0x180004724`
- end: `0x18000489d`
- name: `_configure_wide_argv`
- size: `377`
- prototype: `errno_t __cdecl(_crt_argv_mode mode)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800041ec`
- `0x180004544`
- `0x180004724`
- `0x1800074a0`
- `0x180007788`
- `0x1800078e0`
- `0x18000962c`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x180004774`
- `KERNEL32!GetModuleFileNameW` at `0x180004774`

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
0x180004724  mov     [rsp-28h+arg_0], rbx
0x180004729  push    rbp
0x18000472a  push    rsi
0x18000472b  push    rdi
0x18000472c  push    r14
0x18000472e  push    r15
0x180004730  mov     rbp, rsp
0x180004733  sub     rsp, 30h
0x180004737  xor     edi, edi
0x180004739  mov     r14d, ecx
0x18000473c  test    ecx, ecx
0x18000473e  jz      loc_18000488A
0x180004744  lea     eax, [rcx-1]
0x180004747  cmp     eax, 1
0x18000474a  jbe     short loc_180004762
0x18000474c  call    _errno
0x180004751  mov     edi, 16h
0x180004756  mov     [rax], edi
0x180004758  call    _invalid_parameter_noinfo
0x18000475d  jmp     loc_18000488A
0x180004762  lea     rbx, Filename
0x180004769  mov     r8d, 104h; nSize
0x18000476f  mov     rdx, rbx; lpFilename
0x180004772  xor     ecx, ecx; hModule
0x180004774  call    cs:__imp_GetModuleFileNameW
0x18000477a  mov     rsi, cs:_wcmdln
0x180004781  mov     cs:_wpgmptr, rbx
0x180004788  test    rsi, rsi
0x18000478b  jz      short loc_180004792
0x18000478d  cmp     [rsi], di
0x180004790  jnz     short loc_180004795
0x180004792  mov     rsi, rbx
0x180004795  lea     rax, [rbp+arg_18]
0x180004799  mov     [rbp+arg_10], rdi
0x18000479d  lea     r9, [rbp+arg_10]
0x1800047a1  mov     [rsp+30h+var_10], rax
0x1800047a6  xor     r8d, r8d
0x1800047a9  mov     [rbp+arg_18], rdi
0x1800047ad  xor     edx, edx
0x1800047af  mov     rcx, rsi
0x1800047b2  call    parse_command_line_wchar_t_
0x1800047b7  mov     r15, [rbp+arg_10]
0x1800047bb  mov     r8d, 2
0x1800047c1  mov     rdx, [rbp+arg_18]
0x1800047c5  mov     rcx, r15
0x1800047c8  call    __acrt_allocate_buffer_for_argv
0x1800047cd  mov     rbx, rax
0x1800047d0  test    rax, rax
0x1800047d3  jnz     short loc_1800047E6
0x1800047d5  call    _errno
0x1800047da  lea     edi, [rbx+0Ch]
0x1800047dd  mov     [rax], edi
0x1800047df  xor     ecx, ecx
0x1800047e1  jmp     loc_180004885
0x1800047e6  lea     r8, [rax+r15*8]
0x1800047ea  mov     rdx, rbx
0x1800047ed  lea     rax, [rbp+arg_18]
0x1800047f1  mov     rcx, rsi
0x1800047f4  lea     r9, [rbp+arg_10]
0x1800047f8  mov     [rsp+30h+var_10], rax
0x1800047fd  call    parse_command_line_wchar_t_
0x180004802  cmp     r14d, 1
0x180004806  jnz     short loc_18000481C
0x180004808  mov     eax, dword ptr [rbp+arg_10]
0x18000480b  dec     eax
0x18000480d  mov     cs:__wargv, rbx
0x180004814  mov     cs:__argc, eax
0x18000481a  jmp     short loc_1800047DF
0x18000481c  lea     rdx, [rbp+Block]
0x180004820  mov     [rbp+Block], rdi
0x180004824  mov     rcx, rbx
0x180004827  call    __acrt_expand_wide_argv_wildcards
0x18000482c  mov     esi, eax
0x18000482e  test    eax, eax
0x180004830  jz      short loc_18000484B
0x180004832  mov     rcx, [rbp+Block]; Block
0x180004836  call    _free_base
0x18000483b  mov     rcx, rbx; Block
0x18000483e  mov     [rbp+Block], rdi
0x180004842  call    _free_base
0x180004847  mov     edi, esi
0x180004849  jmp     short loc_18000488A
0x18000484b  mov     rdx, [rbp+Block]
0x18000484f  mov     rcx, rdi
0x180004852  mov     rax, rdx
0x180004855  cmp     [rdx], rdi
0x180004858  jz      short loc_180004866
0x18000485a  lea     rax, [rax+8]
0x18000485e  inc     rcx
0x180004861  cmp     [rax], rdi
0x180004864  jnz     short loc_18000485A
0x180004866  mov     cs:__argc, ecx
0x18000486c  xor     ecx, ecx; Block
0x18000486e  mov     [rbp+Block], rdi
0x180004872  mov     cs:__wargv, rdx
0x180004879  call    _free_base
0x18000487e  mov     rcx, rbx; Block
0x180004881  mov     [rbp+Block], rdi
0x180004885  call    _free_base
0x18000488a  mov     rbx, [rsp+30h+arg_0]
0x18000488f  mov     eax, edi
0x180004891  add     rsp, 30h
0x180004895  pop     r15
0x180004897  pop     r14
0x180004899  pop     rdi
0x18000489a  pop     rsi
0x18000489b  pop     rbp
0x18000489c  retn
```
