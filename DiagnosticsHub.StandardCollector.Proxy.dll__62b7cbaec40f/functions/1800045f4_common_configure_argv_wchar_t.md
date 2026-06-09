# common_configure_argv_wchar_t_

- ea: `0x1800045f4`
- end: `0x18000476a`
- name: `common_configure_argv_wchar_t_`
- size: `374`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800045f4`
- `0x180004948`
- `0x180004ca0`
- `0x180007c00`
- `0x180007ee8`
- `0x180008040`
- `0x180009d8c`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x180004649`
- `KERNEL32!GetModuleFileNameW` at `0x180004649`

## pseudocode

```c
__int64 __fastcall common_configure_argv_wchar_t_(int a1)
{
  unsigned int v1; // edi
  WCHAR *v4; // rsi
  int v5; // r15d
  __int64 buffer_for_argv; // rax
  wchar_t **v7; // rbx
  unsigned int v8; // esi
  wchar_t **v9; // rdx
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
  GetModuleFileNameW(0, &Filename, 0x104u);
  LODWORD(v4) = (_DWORD)wcmdln;
  wpgmptr = &Filename;
  if ( !wcmdln || !*wcmdln )
    v4 = &Filename;
  v13 = 0;
  v14 = 0;
  parse_command_line_wchar_t_((_DWORD)v4, 0, 0, (unsigned int)&v13, (__int64)&v14);
  v5 = v13;
  buffer_for_argv = _acrt_allocate_buffer_for_argv(v13, v14, 2);
  v7 = (wchar_t **)buffer_for_argv;
  if ( !buffer_for_argv )
  {
    v1 = 12;
    *errno() = 12;
LABEL_12:
    free_base(0);
    return v1;
  }
  parse_command_line_wchar_t_((_DWORD)v4, buffer_for_argv, buffer_for_argv + 8 * v5, (unsigned int)&v13, (__int64)&v14);
  if ( a1 == 1 )
  {
    _wargv = v7;
    _argc = v13 - 1;
    goto LABEL_12;
  }
  Block = 0;
  v8 = _acrt_expand_wide_argv_wildcards(v7, &Block);
  if ( v8 )
  {
    free_base(Block);
  }
  else
  {
    v9 = (wchar_t **)Block;
    v10 = 0;
    for ( i = Block; *i; ++v10 )
      ++i;
    _argc = v10;
    Block = 0;
    _wargv = v9;
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
0x1800045f4  mov     [rsp-28h+arg_0], rbx
0x1800045f9  push    rbp
0x1800045fa  push    rsi
0x1800045fb  push    rdi
0x1800045fc  push    r14
0x1800045fe  push    r15
0x180004600  mov     rbp, rsp
0x180004603  sub     rsp, 30h
0x180004607  xor     edi, edi
0x180004609  mov     r14d, ecx
0x18000460c  test    ecx, ecx
0x18000460e  jnz     short loc_180004617
0x180004610  xor     eax, eax
0x180004612  jmp     loc_180004759
0x180004617  lea     eax, [rcx-1]
0x18000461a  cmp     eax, 1
0x18000461d  jbe     short loc_180004637
0x18000461f  call    _errno
0x180004624  mov     ebx, 16h
0x180004629  mov     [rax], ebx
0x18000462b  call    _invalid_parameter_noinfo
0x180004630  mov     eax, ebx
0x180004632  jmp     loc_180004759
0x180004637  lea     rbx, Filename
0x18000463e  mov     r8d, 104h; nSize
0x180004644  mov     rdx, rbx; lpFilename
0x180004647  xor     ecx, ecx; hModule
0x180004649  call    cs:__imp_GetModuleFileNameW
0x18000464f  mov     rsi, cs:_wcmdln
0x180004656  mov     cs:_wpgmptr, rbx
0x18000465d  test    rsi, rsi
0x180004660  jz      short loc_180004667
0x180004662  cmp     [rsi], di
0x180004665  jnz     short loc_18000466A
0x180004667  mov     rsi, rbx
0x18000466a  lea     rax, [rbp+arg_18]
0x18000466e  mov     [rbp+arg_10], rdi
0x180004672  lea     r9, [rbp+arg_10]
0x180004676  mov     [rsp+30h+var_10], rax
0x18000467b  xor     r8d, r8d
0x18000467e  mov     [rbp+arg_18], rdi
0x180004682  xor     edx, edx
0x180004684  mov     rcx, rsi
0x180004687  call    parse_command_line_wchar_t_
0x18000468c  mov     r15, [rbp+arg_10]
0x180004690  mov     r8d, 2
0x180004696  mov     rdx, [rbp+arg_18]
0x18000469a  mov     rcx, r15
0x18000469d  call    __acrt_allocate_buffer_for_argv
0x1800046a2  mov     rbx, rax
0x1800046a5  test    rax, rax
0x1800046a8  jnz     short loc_1800046B6
0x1800046aa  call    _errno
0x1800046af  lea     edi, [rbx+0Ch]
0x1800046b2  mov     [rax], edi
0x1800046b4  jmp     short loc_1800046EA
0x1800046b6  lea     r8, [rax+r15*8]
0x1800046ba  mov     rdx, rbx
0x1800046bd  lea     rax, [rbp+arg_18]
0x1800046c1  mov     rcx, rsi
0x1800046c4  lea     r9, [rbp+arg_10]
0x1800046c8  mov     [rsp+30h+var_10], rax
0x1800046cd  call    parse_command_line_wchar_t_
0x1800046d2  cmp     r14d, 1
0x1800046d6  jnz     short loc_1800046F5
0x1800046d8  mov     ecx, dword ptr [rbp+arg_10]
0x1800046db  dec     ecx
0x1800046dd  mov     cs:__wargv, rbx
0x1800046e4  mov     cs:__argc, ecx
0x1800046ea  xor     ecx, ecx; Block
0x1800046ec  call    _free_base
0x1800046f1  mov     eax, edi
0x1800046f3  jmp     short loc_180004759
0x1800046f5  lea     rdx, [rbp+Block]
0x1800046f9  mov     [rbp+Block], rdi
0x1800046fd  mov     rcx, rbx
0x180004700  call    __acrt_expand_wide_argv_wildcards
0x180004705  mov     esi, eax
0x180004707  test    eax, eax
0x180004709  jz      short loc_180004716
0x18000470b  mov     rcx, [rbp+Block]; Block
0x18000470f  call    _free_base
0x180004714  jmp     short loc_18000474B
0x180004716  mov     rdx, [rbp+Block]
0x18000471a  mov     rcx, rdi
0x18000471d  mov     rax, rdx
0x180004720  cmp     [rdx], rdi
0x180004723  jz      short loc_180004731
0x180004725  lea     rax, [rax+8]
0x180004729  inc     rcx
0x18000472c  cmp     [rax], rdi
0x18000472f  jnz     short loc_180004725
0x180004731  mov     cs:__argc, ecx
0x180004737  xor     ecx, ecx; Block
0x180004739  mov     [rbp+Block], rdi
0x18000473d  mov     cs:__wargv, rdx
0x180004744  call    _free_base
0x180004749  mov     esi, edi
0x18000474b  mov     rcx, rbx; Block
0x18000474e  mov     [rbp+Block], rdi
0x180004752  call    _free_base
0x180004757  mov     eax, esi
0x180004759  mov     rbx, [rsp+30h+arg_0]
0x18000475e  add     rsp, 30h
0x180004762  pop     r15
0x180004764  pop     r14
0x180004766  pop     rdi
0x180004767  pop     rsi
0x180004768  pop     rbp
0x180004769  retn
```
