# common_configure_argv<wchar_t>(_crt_argv_mode)

- ea: `0x40e4a7`
- end: `0x40e5d6`
- name: `??$common_configure_argv@_W@@YAHW4_crt_argv_mode@@@Z`
- size: `303`
- prototype: `int __cdecl(int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x40e7b9`

## callees

- `0x40de54`
- `0x40e4a7`
- `0x40e5d6`
- `0x40e76a`
- `0x40ffa9`
- `0x41001a`
- `0x410571`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x40e4ee`
- `KERNEL32!GetModuleFileNameW` at `0x40e4ee`

## pseudocode

```c
int __cdecl common_configure_argv<wchar_t>(int a1)
{
  int v2; // edi
  WCHAR *v3; // eax
  char *buffer_for_argv; // esi
  void *v5; // eax
  int v6; // ebx
  void *v7; // eax
  void *v8; // edx
  int v9; // ecx
  _DWORD *i; // eax
  WCHAR *v11; // [esp+4h] [ebp-10h]
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
  v2 = 0;
  GetModuleFileNameW(0, &Filename, 0x104u);
  v3 = (WCHAR *)dword_4181A4;
  dword_418190 = (int)&Filename;
  v11 = (WCHAR *)dword_4181A4;
  if ( !dword_4181A4 || !*(_WORD *)dword_4181A4 )
  {
    v3 = &Filename;
    v11 = &Filename;
  }
  v14 = 0;
  v12 = 0;
  parse_command_line<wchar_t>(v3, 0, 0, &v14, &v12);
  buffer_for_argv = (char *)__acrt_allocate_buffer_for_argv(v14, v12, 2);
  if ( buffer_for_argv )
  {
    parse_command_line<wchar_t>(v11, buffer_for_argv, &buffer_for_argv[4 * v14], &v14, &v12);
    if ( a1 != 1 )
    {
      Block = 0;
      v6 = __acrt_expand_wide_argv_wildcards(buffer_for_argv, &Block);
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
        dword_418194 = v9;
        Block = 0;
        v6 = 0;
        dword_41819C = v8;
      }
      _free_base(v7);
      Block = 0;
      goto LABEL_20;
    }
    dword_418194 = v14 - 1;
    v5 = buffer_for_argv;
    buffer_for_argv = 0;
    dword_41819C = v5;
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
0x40e4a7  mov     edi, edi
0x40e4a9  push    ebp
0x40e4aa  mov     ebp, esp
0x40e4ac  sub     esp, 10h
0x40e4af  push    ebx
0x40e4b0  mov     ebx, [ebp+arg_0]
0x40e4b3  test    ebx, ebx
0x40e4b5  jnz     short loc_40E4BE
0x40e4b7  xor     eax, eax
0x40e4b9  jmp     loc_40E5D3
0x40e4be  push    esi
0x40e4bf  cmp     ebx, 2
0x40e4c2  jz      short loc_40E4DF
0x40e4c4  cmp     ebx, 1
0x40e4c7  jz      short loc_40E4DF
0x40e4c9  call    __errno
0x40e4ce  push    16h
0x40e4d0  pop     esi
0x40e4d1  mov     [eax], esi
0x40e4d3  call    __invalid_parameter_noinfo
0x40e4d8  mov     eax, esi
0x40e4da  jmp     loc_40E5D2
0x40e4df  push    edi
0x40e4e0  push    104h; nSize
0x40e4e5  mov     esi, offset Filename
0x40e4ea  xor     edi, edi
0x40e4ec  push    esi; lpFilename
0x40e4ed  push    edi; hModule
0x40e4ee  call    ds:GetModuleFileNameW
0x40e4f4  mov     eax, dword_4181A4
0x40e4f9  mov     dword_418190, esi
0x40e4ff  mov     [ebp+var_10], eax
0x40e502  test    eax, eax
0x40e504  jz      short loc_40E50B
0x40e506  cmp     [eax], di
0x40e509  jnz     short loc_40E510
0x40e50b  mov     eax, esi
0x40e50d  mov     [ebp+var_10], esi
0x40e510  lea     ecx, [ebp+var_C]
0x40e513  mov     [ebp+var_4], edi
0x40e516  push    ecx
0x40e517  lea     ecx, [ebp+var_4]
0x40e51a  mov     [ebp+var_C], edi
0x40e51d  push    ecx
0x40e51e  push    edi
0x40e51f  push    edi
0x40e520  push    eax
0x40e521  call    ??$parse_command_line@_W@@YAXPA_WPAPA_W0PAI2@Z
0x40e526  push    2
0x40e528  push    [ebp+var_C]
0x40e52b  push    [ebp+var_4]
0x40e52e  call    ___acrt_allocate_buffer_for_argv
0x40e533  mov     esi, eax
0x40e535  add     esp, 20h
0x40e538  test    esi, esi
0x40e53a  jnz     short loc_40E548
0x40e53c  call    __errno
0x40e541  push    0Ch
0x40e543  pop     edi
0x40e544  mov     [eax], edi
0x40e546  jmp     short loc_40E57A
0x40e548  lea     eax, [ebp+var_C]
0x40e54b  push    eax
0x40e54c  lea     eax, [ebp+var_4]
0x40e54f  push    eax
0x40e550  mov     eax, [ebp+var_4]
0x40e553  lea     eax, [esi+eax*4]
0x40e556  push    eax
0x40e557  push    esi
0x40e558  push    [ebp+var_10]
0x40e55b  call    ??$parse_command_line@_W@@YAXPA_WPAPA_W0PAI2@Z
0x40e560  add     esp, 14h
0x40e563  cmp     ebx, 1
0x40e566  jnz     short loc_40E57E
0x40e568  mov     eax, [ebp+var_4]
0x40e56b  dec     eax
0x40e56c  mov     dword_418194, eax
0x40e571  mov     eax, esi
0x40e573  mov     esi, edi
0x40e575  mov     dword_41819C, eax
0x40e57a  mov     ebx, edi
0x40e57c  jmp     short loc_40E5C8
0x40e57e  lea     eax, [ebp+Block]
0x40e581  mov     [ebp+Block], edi
0x40e584  push    eax
0x40e585  push    esi
0x40e586  call    ___acrt_expand_wide_argv_wildcards
0x40e58b  mov     ebx, eax
0x40e58d  pop     ecx
0x40e58e  pop     ecx
0x40e58f  test    ebx, ebx
0x40e591  jz      short loc_40E598
0x40e593  mov     eax, [ebp+Block]
0x40e596  jmp     short loc_40E5BE
0x40e598  mov     edx, [ebp+Block]
0x40e59b  mov     ecx, edi
0x40e59d  mov     eax, edx
0x40e59f  cmp     [edx], edi
0x40e5a1  jz      short loc_40E5AB
0x40e5a3  lea     eax, [eax+4]
0x40e5a6  inc     ecx
0x40e5a7  cmp     [eax], edi
0x40e5a9  jnz     short loc_40E5A3
0x40e5ab  mov     eax, edi
0x40e5ad  mov     dword_418194, ecx
0x40e5b3  mov     [ebp+Block], eax
0x40e5b6  mov     ebx, edi
0x40e5b8  mov     dword_41819C, edx
0x40e5be  push    eax; Block
0x40e5bf  call    __free_base
0x40e5c4  pop     ecx
0x40e5c5  mov     [ebp+Block], edi
0x40e5c8  push    esi; Block
0x40e5c9  call    __free_base
0x40e5ce  pop     ecx
0x40e5cf  mov     eax, ebx
0x40e5d1  pop     edi
0x40e5d2  pop     esi
0x40e5d3  pop     ebx
0x40e5d4  leave
0x40e5d5  retn
```
