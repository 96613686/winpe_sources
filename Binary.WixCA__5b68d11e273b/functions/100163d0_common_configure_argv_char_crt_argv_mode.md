# common_configure_argv<char>(_crt_argv_mode)

- ea: `0x100163d0`
- end: `0x10016508`
- name: `??$common_configure_argv@D@@YAHW4_crt_argv_mode@@@Z`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x100166d0`

## callees

- `0x10015cbc`
- `0x10015d79`
- `0x100163d0`
- `0x10016508`
- `0x10016681`
- `0x1001770e`
- `0x1001952a`
- `0x10019637`
- `0x10019bea`

## pseudocode

```c
int __cdecl common_configure_argv<char>(int a1)
{
  int v2; // edi
  int *v3; // eax
  char *buffer_for_argv; // esi
  void *v5; // eax
  int v6; // ebx
  void *v7; // eax
  void *v8; // edx
  int v9; // ecx
  _DWORD *i; // eax
  int *v11; // [esp+4h] [ebp-10h]
  int v12; // [esp+8h] [ebp-Ch] BYREF
  void *Block; // [esp+Ch] [ebp-8h] BYREF
  int v14; // [esp+10h] [ebp-4h] BYREF

  if ( !a1 )
    return 0;
  if ( a1 != 2 && a1 != 1 )
  {
    *_errno() = 22;
    _invalid_parameter_noinfo();
    return 22;
  }
  __acrt_initialize_multibyte();
  v2 = 0;
  __acrt_GetModuleFileNameA(0, (int)dword_10034DD8, 260);
  v3 = (int *)dword_100352B0;
  dword_100352A0 = (int)dword_10034DD8;
  v11 = (int *)dword_100352B0;
  if ( !dword_100352B0 || !*(_BYTE *)dword_100352B0 )
  {
    v3 = dword_10034DD8;
    v11 = dword_10034DD8;
  }
  v14 = 0;
  v12 = 0;
  parse_command_line<char>(v3, 0, 0, &v14, &v12);
  buffer_for_argv = (char *)__acrt_allocate_buffer_for_argv(v14, v12, 1);
  if ( buffer_for_argv )
  {
    parse_command_line<char>(v11, buffer_for_argv, &buffer_for_argv[4 * v14], &v14, &v12);
    if ( a1 != 1 )
    {
      Block = 0;
      v6 = __acrt_expand_narrow_argv_wildcards(buffer_for_argv, &Block);
      if ( v6 )
      {
        v7 = Block;
      }
      else
      {
        v8 = Block;
        v9 = 0;
        for ( i = Block; *i; ++v9 )
          ++i;
        v7 = 0;
        dword_100352A4 = v9;
        Block = 0;
        v6 = 0;
        dword_100352A8 = v8;
      }
      _free_base(v7);
      Block = 0;
      goto LABEL_20;
    }
    dword_100352A4 = v14 - 1;
    v5 = buffer_for_argv;
    buffer_for_argv = 0;
    dword_100352A8 = v5;
  }
  else
  {
    v2 = 12;
    *_errno() = 12;
  }
  v6 = v2;
LABEL_20:
  _free_base(buffer_for_argv);
  return v6;
}

```

## disassembly

```asm
0x100163d0  mov     edi, edi
0x100163d2  push    ebp
0x100163d3  mov     ebp, esp
0x100163d5  sub     esp, 10h
0x100163d8  push    ebx
0x100163d9  mov     ebx, [ebp+arg_0]
0x100163dc  test    ebx, ebx
0x100163de  jnz     short loc_100163E7
0x100163e0  xor     eax, eax
0x100163e2  jmp     loc_10016503
0x100163e7  push    esi
0x100163e8  cmp     ebx, 2
0x100163eb  jz      short loc_10016408
0x100163ed  cmp     ebx, 1
0x100163f0  jz      short loc_10016408
0x100163f2  call    __errno
0x100163f7  push    16h
0x100163f9  pop     esi
0x100163fa  mov     [eax], esi
0x100163fc  call    __invalid_parameter_noinfo
0x10016401  mov     eax, esi
0x10016403  jmp     loc_10016502
0x10016408  push    edi
0x10016409  call    ___acrt_initialize_multibyte
0x1001640e  push    104h; int
0x10016413  mov     esi, offset dword_10034DD8
0x10016418  xor     edi, edi
0x1001641a  push    esi; int
0x1001641b  push    edi; hModule
0x1001641c  call    ___acrt_GetModuleFileNameA
0x10016421  mov     eax, dword_100352B0
0x10016426  add     esp, 0Ch
0x10016429  mov     dword_100352A0, esi
0x1001642f  mov     [ebp+var_10], eax
0x10016432  test    eax, eax
0x10016434  jz      short loc_1001643B
0x10016436  cmp     byte ptr [eax], 0
0x10016439  jnz     short loc_10016440
0x1001643b  mov     eax, esi
0x1001643d  mov     [ebp+var_10], esi
0x10016440  lea     ecx, [ebp+var_C]
0x10016443  mov     [ebp+var_4], edi
0x10016446  push    ecx
0x10016447  lea     ecx, [ebp+var_4]
0x1001644a  mov     [ebp+var_C], edi
0x1001644d  push    ecx
0x1001644e  push    edi
0x1001644f  push    edi
0x10016450  push    eax
0x10016451  call    ??$parse_command_line@D@@YAXPADPAPAD0PAI2@Z
0x10016456  push    1
0x10016458  push    [ebp+var_C]
0x1001645b  push    [ebp+var_4]
0x1001645e  call    ___acrt_allocate_buffer_for_argv
0x10016463  mov     esi, eax
0x10016465  add     esp, 20h
0x10016468  test    esi, esi
0x1001646a  jnz     short loc_10016478
0x1001646c  call    __errno
0x10016471  push    0Ch
0x10016473  pop     edi
0x10016474  mov     [eax], edi
0x10016476  jmp     short loc_100164AA
0x10016478  lea     eax, [ebp+var_C]
0x1001647b  push    eax
0x1001647c  lea     eax, [ebp+var_4]
0x1001647f  push    eax
0x10016480  mov     eax, [ebp+var_4]
0x10016483  lea     eax, [esi+eax*4]
0x10016486  push    eax
0x10016487  push    esi
0x10016488  push    [ebp+var_10]
0x1001648b  call    ??$parse_command_line@D@@YAXPADPAPAD0PAI2@Z
0x10016490  add     esp, 14h
0x10016493  cmp     ebx, 1
0x10016496  jnz     short loc_100164AE
0x10016498  mov     eax, [ebp+var_4]
0x1001649b  dec     eax
0x1001649c  mov     dword_100352A4, eax
0x100164a1  mov     eax, esi
0x100164a3  mov     esi, edi
0x100164a5  mov     dword_100352A8, eax
0x100164aa  mov     ebx, edi
0x100164ac  jmp     short loc_100164F8
0x100164ae  lea     eax, [ebp+Block]
0x100164b1  mov     [ebp+Block], edi
0x100164b4  push    eax
0x100164b5  push    esi
0x100164b6  call    ___acrt_expand_narrow_argv_wildcards
0x100164bb  mov     ebx, eax
0x100164bd  pop     ecx
0x100164be  pop     ecx
0x100164bf  test    ebx, ebx
0x100164c1  jz      short loc_100164C8
0x100164c3  mov     eax, [ebp+Block]
0x100164c6  jmp     short loc_100164EE
0x100164c8  mov     edx, [ebp+Block]
0x100164cb  mov     ecx, edi
0x100164cd  mov     eax, edx
0x100164cf  cmp     [edx], edi
0x100164d1  jz      short loc_100164DB
0x100164d3  lea     eax, [eax+4]
0x100164d6  inc     ecx
0x100164d7  cmp     [eax], edi
0x100164d9  jnz     short loc_100164D3
0x100164db  mov     eax, edi
0x100164dd  mov     dword_100352A4, ecx
0x100164e3  mov     [ebp+Block], eax
0x100164e6  mov     ebx, edi
0x100164e8  mov     dword_100352A8, edx
0x100164ee  push    eax; Block
0x100164ef  call    __free_base
0x100164f4  pop     ecx
0x100164f5  mov     [ebp+Block], edi
0x100164f8  push    esi; Block
0x100164f9  call    __free_base
0x100164fe  pop     ecx
0x100164ff  mov     eax, ebx
0x10016501  pop     edi
0x10016502  pop     esi
0x10016503  pop     ebx
0x10016504  mov     esp, ebp
0x10016506  pop     ebp
0x10016507  retn
```
