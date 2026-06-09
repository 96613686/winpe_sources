# _configure_wide_argv

- ea: `0x140012508`
- end: `0x140012681`
- name: `_configure_wide_argv`
- size: `377`
- prototype: `errno_t __cdecl(_crt_argv_mode mode)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005980`

## callees

- `0x14000bf5c`
- `0x1400120dc`
- `0x140012304`
- `0x1400124a8`
- `0x140012508`
- `0x140013e10`
- `0x14001701c`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x140012558`
- `KERNEL32!GetModuleFileNameW` at `0x140012558`

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
0x140012508  mov     [rsp-28h+arg_0], rbx
0x14001250d  push    rbp
0x14001250e  push    rsi
0x14001250f  push    rdi
0x140012510  push    r14
0x140012512  push    r15
0x140012514  mov     rbp, rsp
0x140012517  sub     rsp, 30h
0x14001251b  xor     edi, edi
0x14001251d  mov     r14d, ecx
0x140012520  test    ecx, ecx
0x140012522  jz      loc_14001266E
0x140012528  lea     eax, [rcx-1]
0x14001252b  cmp     eax, 1
0x14001252e  jbe     short loc_140012546
0x140012530  call    _errno
0x140012535  mov     edi, 16h
0x14001253a  mov     [rax], edi
0x14001253c  call    _invalid_parameter_noinfo
0x140012541  jmp     loc_14001266E
0x140012546  lea     rbx, Filename
0x14001254d  mov     r8d, 104h; nSize
0x140012553  mov     rdx, rbx; lpFilename
0x140012556  xor     ecx, ecx; hModule
0x140012558  call    cs:__imp_GetModuleFileNameW
0x14001255e  mov     rsi, cs:_wcmdln
0x140012565  mov     cs:_wpgmptr, rbx
0x14001256c  test    rsi, rsi
0x14001256f  jz      short loc_140012576
0x140012571  cmp     [rsi], di
0x140012574  jnz     short loc_140012579
0x140012576  mov     rsi, rbx
0x140012579  lea     rax, [rbp+arg_18]
0x14001257d  mov     [rbp+arg_10], rdi
0x140012581  lea     r9, [rbp+arg_10]
0x140012585  mov     [rsp+30h+var_10], rax
0x14001258a  xor     r8d, r8d
0x14001258d  mov     [rbp+arg_18], rdi
0x140012591  xor     edx, edx
0x140012593  mov     rcx, rsi
0x140012596  call    parse_command_line_wchar_t_
0x14001259b  mov     r15, [rbp+arg_10]
0x14001259f  mov     r8d, 2
0x1400125a5  mov     rdx, [rbp+arg_18]
0x1400125a9  mov     rcx, r15
0x1400125ac  call    __acrt_allocate_buffer_for_argv
0x1400125b1  mov     rbx, rax
0x1400125b4  test    rax, rax
0x1400125b7  jnz     short loc_1400125CA
0x1400125b9  call    _errno
0x1400125be  lea     edi, [rbx+0Ch]
0x1400125c1  mov     [rax], edi
0x1400125c3  xor     ecx, ecx
0x1400125c5  jmp     loc_140012669
0x1400125ca  lea     r8, [rax+r15*8]
0x1400125ce  mov     rdx, rbx
0x1400125d1  lea     rax, [rbp+arg_18]
0x1400125d5  mov     rcx, rsi
0x1400125d8  lea     r9, [rbp+arg_10]
0x1400125dc  mov     [rsp+30h+var_10], rax
0x1400125e1  call    parse_command_line_wchar_t_
0x1400125e6  cmp     r14d, 1
0x1400125ea  jnz     short loc_140012600
0x1400125ec  mov     eax, dword ptr [rbp+arg_10]
0x1400125ef  dec     eax
0x1400125f1  mov     cs:__wargv, rbx
0x1400125f8  mov     cs:__argc, eax
0x1400125fe  jmp     short loc_1400125C3
0x140012600  lea     rdx, [rbp+Block]
0x140012604  mov     [rbp+Block], rdi
0x140012608  mov     rcx, rbx
0x14001260b  call    __acrt_expand_wide_argv_wildcards
0x140012610  mov     esi, eax
0x140012612  test    eax, eax
0x140012614  jz      short loc_14001262F
0x140012616  mov     rcx, [rbp+Block]; Block
0x14001261a  call    _free_base
0x14001261f  mov     rcx, rbx; Block
0x140012622  mov     [rbp+Block], rdi
0x140012626  call    _free_base
0x14001262b  mov     edi, esi
0x14001262d  jmp     short loc_14001266E
0x14001262f  mov     rdx, [rbp+Block]
0x140012633  mov     rcx, rdi
0x140012636  mov     rax, rdx
0x140012639  cmp     [rdx], rdi
0x14001263c  jz      short loc_14001264A
0x14001263e  lea     rax, [rax+8]
0x140012642  inc     rcx
0x140012645  cmp     [rax], rdi
0x140012648  jnz     short loc_14001263E
0x14001264a  mov     cs:__argc, ecx
0x140012650  xor     ecx, ecx; Block
0x140012652  mov     [rbp+Block], rdi
0x140012656  mov     cs:__wargv, rdx
0x14001265d  call    _free_base
0x140012662  mov     rcx, rbx; Block
0x140012665  mov     [rbp+Block], rdi
0x140012669  call    _free_base
0x14001266e  mov     rbx, [rsp+30h+arg_0]
0x140012673  mov     eax, edi
0x140012675  add     rsp, 30h
0x140012679  pop     r15
0x14001267b  pop     r14
0x14001267d  pop     rdi
0x14001267e  pop     rsi
0x14001267f  pop     rbp
0x140012680  retn
```
