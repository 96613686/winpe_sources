# _configure_wide_argv

- ea: `0x1400226a8`
- end: `0x14002282a`
- name: `_configure_wide_argv`
- size: `386`
- prototype: `errno_t __cdecl(_crt_argv_mode mode)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001bc80`

## callees

- `0x1400046cc`
- `0x14000fa6c`
- `0x1400107c4`
- `0x1400224a4`
- `0x140022648`
- `0x1400226a8`
- `0x140023b8c`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x1400226f8`
- `KERNEL32!GetModuleFileNameW` at `0x1400226f8`

## pseudocode

```c
errno_t __cdecl configure_wide_argv(_crt_argv_mode mode)
{
  errno_t v1; // edi
  errno_t v3; // ebx
  __int16 *v4; // rsi
  __int64 v5; // r15
  __int16 **buffer_for_argv; // rax
  int v7; // ecx
  __int16 **v8; // rbx
  __int16 **v9; // rcx
  errno_t v10; // esi
  void *v11; // rdx
  int v12; // ecx
  _QWORD *i; // rax
  void *Block; // [rsp+68h] [rbp+38h] BYREF
  __int64 v16; // [rsp+70h] [rbp+40h] BYREF
  __int64 v17; // [rsp+78h] [rbp+48h] BYREF

  v1 = 0;
  if ( mode )
  {
    if ( (unsigned int)(mode - 1) <= 1 )
    {
      GetModuleFileNameW(0, &Filename, 0x104u);
      v4 = (__int16 *)qword_1400D7C00;
      qword_1400D7BD8 = (__int64)&Filename;
      if ( !qword_1400D7C00 || !*(_WORD *)qword_1400D7C00 )
        v4 = (__int16 *)&Filename;
      v16 = 0;
      v17 = 0;
      parse_command_line<wchar_t>(v4, 0, 0, &v16, &v17);
      v5 = v16;
      buffer_for_argv = (__int16 **)_acrt_allocate_buffer_for_argv(v16, v17, 2);
      v8 = buffer_for_argv;
      if ( buffer_for_argv )
      {
        parse_command_line<wchar_t>(v4, buffer_for_argv, (__int16 *)&buffer_for_argv[v5], &v16, &v17);
        if ( mode == _crt_argv_unexpanded_arguments )
        {
          qword_1400D7BF0 = v8;
          dword_1400D7BE0 = v16 - 1;
          v9 = 0;
        }
        else
        {
          Block = 0;
          v10 = common_expand_argv_wildcards<wchar_t>((const wchar_t **)v8, (__int64 *)&Block);
          if ( v10 )
          {
            free_base(Block);
            Block = 0;
            free_base(v8);
            return v10;
          }
          v11 = Block;
          v12 = 0;
          for ( i = Block; *i; ++v12 )
            ++i;
          dword_1400D7BE0 = v12;
          Block = 0;
          qword_1400D7BF0 = v11;
          free_base(0);
          v9 = v8;
          Block = 0;
        }
        free_base(v9);
        return v1;
      }
      v3 = 12;
      *(_DWORD *)sub_14000FA6C(v7) = 12;
      free_base(0);
    }
    else
    {
      v3 = 22;
      *(_DWORD *)sub_14000FA6C(mode) = 22;
      invalid_parameter_noinfo();
    }
    return v3;
  }
  return v1;
}

```

## disassembly

```asm
0x1400226a8  mov     [rsp-28h+arg_0], rbx
0x1400226ad  push    rbp
0x1400226ae  push    rsi
0x1400226af  push    rdi
0x1400226b0  push    r14
0x1400226b2  push    r15
0x1400226b4  mov     rbp, rsp
0x1400226b7  sub     rsp, 30h
0x1400226bb  xor     edi, edi
0x1400226bd  mov     r14d, ecx
0x1400226c0  test    ecx, ecx
0x1400226c2  jz      loc_140022817
0x1400226c8  lea     eax, [rcx-1]
0x1400226cb  cmp     eax, 1
0x1400226ce  jbe     short loc_1400226E6
0x1400226d0  call    sub_14000FA6C
0x1400226d5  lea     ebx, [rdi+16h]
0x1400226d8  mov     [rax], ebx
0x1400226da  call    _invalid_parameter_noinfo
0x1400226df  mov     edi, ebx
0x1400226e1  jmp     loc_140022817
0x1400226e6  lea     rbx, Filename
0x1400226ed  mov     r8d, 104h; nSize
0x1400226f3  mov     rdx, rbx; lpFilename
0x1400226f6  xor     ecx, ecx; hModule
0x1400226f8  call    cs:GetModuleFileNameW
0x1400226fe  mov     rsi, cs:qword_1400D7C00
0x140022705  mov     cs:qword_1400D7BD8, rbx
0x14002270c  test    rsi, rsi
0x14002270f  jz      short loc_140022716
0x140022711  cmp     [rsi], di
0x140022714  jnz     short loc_140022719
0x140022716  mov     rsi, rbx
0x140022719  lea     rax, [rbp+arg_18]
0x14002271d  mov     [rbp+arg_10], rdi
0x140022721  lea     r9, [rbp+arg_10]
0x140022725  mov     [rsp+30h+var_10], rax
0x14002272a  xor     r8d, r8d
0x14002272d  mov     [rbp+arg_18], rdi
0x140022731  xor     edx, edx
0x140022733  mov     rcx, rsi
0x140022736  call    ??$parse_command_line@_W@@YAXPEA_WPEAPEA_W0PEA_K2@Z
0x14002273b  mov     r15, [rbp+arg_10]
0x14002273f  mov     r8d, 2
0x140022745  mov     rdx, [rbp+arg_18]
0x140022749  mov     rcx, r15
0x14002274c  call    __acrt_allocate_buffer_for_argv
0x140022751  mov     rbx, rax
0x140022754  test    rax, rax
0x140022757  jnz     short loc_140022771
0x140022759  call    sub_14000FA6C
0x14002275e  mov     ebx, 0Ch
0x140022763  xor     ecx, ecx; Block
0x140022765  mov     [rax], ebx
0x140022767  call    _free_base
0x14002276c  jmp     loc_1400226DF
0x140022771  lea     r8, [rax+r15*8]
0x140022775  mov     rdx, rbx
0x140022778  lea     rax, [rbp+arg_18]
0x14002277c  mov     rcx, rsi
0x14002277f  lea     r9, [rbp+arg_10]
0x140022783  mov     [rsp+30h+var_10], rax
0x140022788  call    ??$parse_command_line@_W@@YAXPEA_WPEAPEA_W0PEA_K2@Z
0x14002278d  cmp     r14d, 1
0x140022791  jnz     short loc_1400227A9
0x140022793  mov     eax, dword ptr [rbp+arg_10]
0x140022796  dec     eax
0x140022798  mov     cs:qword_1400D7BF0, rbx
0x14002279f  mov     cs:dword_1400D7BE0, eax
0x1400227a5  xor     ecx, ecx
0x1400227a7  jmp     short loc_140022812
0x1400227a9  lea     rdx, [rbp+Block]
0x1400227ad  mov     [rbp+Block], rdi
0x1400227b1  mov     rcx, rbx
0x1400227b4  call    j_??$common_expand_argv_wildcards@_W@@YAHQEAPEA_WQEAPEAPEA_W@Z
0x1400227b9  mov     esi, eax
0x1400227bb  test    eax, eax
0x1400227bd  jz      short loc_1400227D8
0x1400227bf  mov     rcx, [rbp+Block]; Block
0x1400227c3  call    _free_base
0x1400227c8  mov     rcx, rbx; Block
0x1400227cb  mov     [rbp+Block], rdi
0x1400227cf  call    _free_base
0x1400227d4  mov     edi, esi
0x1400227d6  jmp     short loc_140022817
0x1400227d8  mov     rdx, [rbp+Block]
0x1400227dc  mov     rcx, rdi
0x1400227df  mov     rax, rdx
0x1400227e2  cmp     [rdx], rdi
0x1400227e5  jz      short loc_1400227F3
0x1400227e7  lea     rax, [rax+8]
0x1400227eb  inc     rcx
0x1400227ee  cmp     [rax], rdi
0x1400227f1  jnz     short loc_1400227E7
0x1400227f3  mov     cs:dword_1400D7BE0, ecx
0x1400227f9  xor     ecx, ecx; Block
0x1400227fb  mov     [rbp+Block], rdi
0x1400227ff  mov     cs:qword_1400D7BF0, rdx
0x140022806  call    _free_base
0x14002280b  mov     rcx, rbx; Block
0x14002280e  mov     [rbp+Block], rdi
0x140022812  call    _free_base
0x140022817  mov     rbx, [rsp+30h+arg_0]
0x14002281c  mov     eax, edi
0x14002281e  add     rsp, 30h
0x140022822  pop     r15
0x140022824  pop     r14
0x140022826  pop     rdi
0x140022827  pop     rsi
0x140022828  pop     rbp
0x140022829  retn
```
