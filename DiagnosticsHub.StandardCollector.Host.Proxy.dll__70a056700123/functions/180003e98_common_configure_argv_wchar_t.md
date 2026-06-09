# common_configure_argv_wchar_t_

- ea: `0x180003e98`
- end: `0x18000400e`
- name: `common_configure_argv_wchar_t_`
- size: `374`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003e98`
- `0x1800041ec`
- `0x180004544`
- `0x1800074a0`
- `0x180007788`
- `0x1800078e0`
- `0x18000962c`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x180003eed`
- `KERNEL32!GetModuleFileNameW` at `0x180003eed`

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
0x180003e98  mov     [rsp-28h+arg_0], rbx
0x180003e9d  push    rbp
0x180003e9e  push    rsi
0x180003e9f  push    rdi
0x180003ea0  push    r14
0x180003ea2  push    r15
0x180003ea4  mov     rbp, rsp
0x180003ea7  sub     rsp, 30h
0x180003eab  xor     edi, edi
0x180003ead  mov     r14d, ecx
0x180003eb0  test    ecx, ecx
0x180003eb2  jnz     short loc_180003EBB
0x180003eb4  xor     eax, eax
0x180003eb6  jmp     loc_180003FFD
0x180003ebb  lea     eax, [rcx-1]
0x180003ebe  cmp     eax, 1
0x180003ec1  jbe     short loc_180003EDB
0x180003ec3  call    _errno
0x180003ec8  mov     ebx, 16h
0x180003ecd  mov     [rax], ebx
0x180003ecf  call    _invalid_parameter_noinfo
0x180003ed4  mov     eax, ebx
0x180003ed6  jmp     loc_180003FFD
0x180003edb  lea     rbx, Filename
0x180003ee2  mov     r8d, 104h; nSize
0x180003ee8  mov     rdx, rbx; lpFilename
0x180003eeb  xor     ecx, ecx; hModule
0x180003eed  call    cs:__imp_GetModuleFileNameW
0x180003ef3  mov     rsi, cs:_wcmdln
0x180003efa  mov     cs:_wpgmptr, rbx
0x180003f01  test    rsi, rsi
0x180003f04  jz      short loc_180003F0B
0x180003f06  cmp     [rsi], di
0x180003f09  jnz     short loc_180003F0E
0x180003f0b  mov     rsi, rbx
0x180003f0e  lea     rax, [rbp+arg_18]
0x180003f12  mov     [rbp+arg_10], rdi
0x180003f16  lea     r9, [rbp+arg_10]
0x180003f1a  mov     [rsp+30h+var_10], rax
0x180003f1f  xor     r8d, r8d
0x180003f22  mov     [rbp+arg_18], rdi
0x180003f26  xor     edx, edx
0x180003f28  mov     rcx, rsi
0x180003f2b  call    parse_command_line_wchar_t_
0x180003f30  mov     r15, [rbp+arg_10]
0x180003f34  mov     r8d, 2
0x180003f3a  mov     rdx, [rbp+arg_18]
0x180003f3e  mov     rcx, r15
0x180003f41  call    __acrt_allocate_buffer_for_argv
0x180003f46  mov     rbx, rax
0x180003f49  test    rax, rax
0x180003f4c  jnz     short loc_180003F5A
0x180003f4e  call    _errno
0x180003f53  lea     edi, [rbx+0Ch]
0x180003f56  mov     [rax], edi
0x180003f58  jmp     short loc_180003F8E
0x180003f5a  lea     r8, [rax+r15*8]
0x180003f5e  mov     rdx, rbx
0x180003f61  lea     rax, [rbp+arg_18]
0x180003f65  mov     rcx, rsi
0x180003f68  lea     r9, [rbp+arg_10]
0x180003f6c  mov     [rsp+30h+var_10], rax
0x180003f71  call    parse_command_line_wchar_t_
0x180003f76  cmp     r14d, 1
0x180003f7a  jnz     short loc_180003F99
0x180003f7c  mov     ecx, dword ptr [rbp+arg_10]
0x180003f7f  dec     ecx
0x180003f81  mov     cs:__wargv, rbx
0x180003f88  mov     cs:__argc, ecx
0x180003f8e  xor     ecx, ecx; Block
0x180003f90  call    _free_base
0x180003f95  mov     eax, edi
0x180003f97  jmp     short loc_180003FFD
0x180003f99  lea     rdx, [rbp+Block]
0x180003f9d  mov     [rbp+Block], rdi
0x180003fa1  mov     rcx, rbx
0x180003fa4  call    __acrt_expand_wide_argv_wildcards
0x180003fa9  mov     esi, eax
0x180003fab  test    eax, eax
0x180003fad  jz      short loc_180003FBA
0x180003faf  mov     rcx, [rbp+Block]; Block
0x180003fb3  call    _free_base
0x180003fb8  jmp     short loc_180003FEF
0x180003fba  mov     rdx, [rbp+Block]
0x180003fbe  mov     rcx, rdi
0x180003fc1  mov     rax, rdx
0x180003fc4  cmp     [rdx], rdi
0x180003fc7  jz      short loc_180003FD5
0x180003fc9  lea     rax, [rax+8]
0x180003fcd  inc     rcx
0x180003fd0  cmp     [rax], rdi
0x180003fd3  jnz     short loc_180003FC9
0x180003fd5  mov     cs:__argc, ecx
0x180003fdb  xor     ecx, ecx; Block
0x180003fdd  mov     [rbp+Block], rdi
0x180003fe1  mov     cs:__wargv, rdx
0x180003fe8  call    _free_base
0x180003fed  mov     esi, edi
0x180003fef  mov     rcx, rbx; Block
0x180003ff2  mov     [rbp+Block], rdi
0x180003ff6  call    _free_base
0x180003ffb  mov     eax, esi
0x180003ffd  mov     rbx, [rsp+30h+arg_0]
0x180004002  add     rsp, 30h
0x180004006  pop     r15
0x180004008  pop     r14
0x18000400a  pop     rdi
0x18000400b  pop     rsi
0x18000400c  pop     rbp
0x18000400d  retn
```
