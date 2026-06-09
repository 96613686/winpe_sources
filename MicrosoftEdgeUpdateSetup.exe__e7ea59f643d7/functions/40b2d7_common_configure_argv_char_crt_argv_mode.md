# common_configure_argv<char>(_crt_argv_mode)

- ea: `0x40b2d7`
- end: `0x40b40d`
- name: `??$common_configure_argv@D@@YAHW4_crt_argv_mode@@@Z`
- size: `310`
- prototype: `int __cdecl(int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x40b5d0`

## callees

- `0x40b2d7`
- `0x40b40d`
- `0x40b581`
- `0x40ec26`
- `0x40ece3`
- `0x40ed53`
- `0x40f5b7`
- `0x40f6c4`
- `0x40fc80`

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
  __acrt_GetModuleFileNameA(0, (int)dword_426D40, 260);
  v3 = (int *)dword_426EB4;
  dword_426EA4 = (int)dword_426D40;
  v11 = (int *)dword_426EB4;
  if ( !dword_426EB4 || !*(_BYTE *)dword_426EB4 )
  {
    v3 = dword_426D40;
    v11 = dword_426D40;
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
        dword_426EA8 = v9;
        Block = 0;
        v6 = 0;
        dword_426EAC = v8;
      }
      _free_base(v7);
      Block = 0;
      goto LABEL_20;
    }
    dword_426EA8 = v14 - 1;
    v5 = buffer_for_argv;
    buffer_for_argv = 0;
    dword_426EAC = v5;
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
0x40b2d7  mov     edi, edi
0x40b2d9  push    ebp
0x40b2da  mov     ebp, esp
0x40b2dc  sub     esp, 10h
0x40b2df  push    ebx
0x40b2e0  mov     ebx, [ebp+arg_0]
0x40b2e3  test    ebx, ebx
0x40b2e5  jnz     short loc_40B2EE
0x40b2e7  xor     eax, eax
0x40b2e9  jmp     loc_40B40A
0x40b2ee  push    esi
0x40b2ef  cmp     ebx, 2
0x40b2f2  jz      short loc_40B30F
0x40b2f4  cmp     ebx, 1
0x40b2f7  jz      short loc_40B30F
0x40b2f9  call    __errno
0x40b2fe  push    16h
0x40b300  pop     esi
0x40b301  mov     [eax], esi
0x40b303  call    __invalid_parameter_noinfo
0x40b308  mov     eax, esi
0x40b30a  jmp     loc_40B409
0x40b30f  push    edi
0x40b310  call    ___acrt_initialize_multibyte
0x40b315  push    104h; int
0x40b31a  mov     esi, offset dword_426D40
0x40b31f  xor     edi, edi
0x40b321  push    esi; int
0x40b322  push    edi; hModule
0x40b323  call    ___acrt_GetModuleFileNameA
0x40b328  mov     eax, dword_426EB4
0x40b32d  add     esp, 0Ch
0x40b330  mov     dword_426EA4, esi
0x40b336  mov     [ebp+var_10], eax
0x40b339  test    eax, eax
0x40b33b  jz      short loc_40B342
0x40b33d  cmp     byte ptr [eax], 0
0x40b340  jnz     short loc_40B347
0x40b342  mov     eax, esi
0x40b344  mov     [ebp+var_10], esi
0x40b347  lea     ecx, [ebp+var_C]
0x40b34a  mov     [ebp+var_4], edi
0x40b34d  push    ecx
0x40b34e  lea     ecx, [ebp+var_4]
0x40b351  mov     [ebp+var_C], edi
0x40b354  push    ecx
0x40b355  push    edi
0x40b356  push    edi
0x40b357  push    eax
0x40b358  call    ??$parse_command_line@D@@YAXPADPAPAD0PAI2@Z
0x40b35d  push    1
0x40b35f  push    [ebp+var_C]
0x40b362  push    [ebp+var_4]
0x40b365  call    ___acrt_allocate_buffer_for_argv
0x40b36a  mov     esi, eax
0x40b36c  add     esp, 20h
0x40b36f  test    esi, esi
0x40b371  jnz     short loc_40B37F
0x40b373  call    __errno
0x40b378  push    0Ch
0x40b37a  pop     edi
0x40b37b  mov     [eax], edi
0x40b37d  jmp     short loc_40B3B1
0x40b37f  lea     eax, [ebp+var_C]
0x40b382  push    eax
0x40b383  lea     eax, [ebp+var_4]
0x40b386  push    eax
0x40b387  mov     eax, [ebp+var_4]
0x40b38a  lea     eax, [esi+eax*4]
0x40b38d  push    eax
0x40b38e  push    esi
0x40b38f  push    [ebp+var_10]
0x40b392  call    ??$parse_command_line@D@@YAXPADPAPAD0PAI2@Z
0x40b397  add     esp, 14h
0x40b39a  cmp     ebx, 1
0x40b39d  jnz     short loc_40B3B5
0x40b39f  mov     eax, [ebp+var_4]
0x40b3a2  dec     eax
0x40b3a3  mov     dword_426EA8, eax
0x40b3a8  mov     eax, esi
0x40b3aa  mov     esi, edi
0x40b3ac  mov     dword_426EAC, eax
0x40b3b1  mov     ebx, edi
0x40b3b3  jmp     short loc_40B3FF
0x40b3b5  lea     eax, [ebp+Block]
0x40b3b8  mov     [ebp+Block], edi
0x40b3bb  push    eax
0x40b3bc  push    esi
0x40b3bd  call    ___acrt_expand_narrow_argv_wildcards
0x40b3c2  mov     ebx, eax
0x40b3c4  pop     ecx
0x40b3c5  pop     ecx
0x40b3c6  test    ebx, ebx
0x40b3c8  jz      short loc_40B3CF
0x40b3ca  mov     eax, [ebp+Block]
0x40b3cd  jmp     short loc_40B3F5
0x40b3cf  mov     edx, [ebp+Block]
0x40b3d2  mov     ecx, edi
0x40b3d4  mov     eax, edx
0x40b3d6  cmp     [edx], edi
0x40b3d8  jz      short loc_40B3E2
0x40b3da  lea     eax, [eax+4]
0x40b3dd  inc     ecx
0x40b3de  cmp     [eax], edi
0x40b3e0  jnz     short loc_40B3DA
0x40b3e2  mov     eax, edi
0x40b3e4  mov     dword_426EA8, ecx
0x40b3ea  mov     [ebp+Block], eax
0x40b3ed  mov     ebx, edi
0x40b3ef  mov     dword_426EAC, edx
0x40b3f5  push    eax; Block
0x40b3f6  call    __free_base
0x40b3fb  pop     ecx
0x40b3fc  mov     [ebp+Block], edi
0x40b3ff  push    esi; Block
0x40b400  call    __free_base
0x40b405  pop     ecx
0x40b406  mov     eax, ebx
0x40b408  pop     edi
0x40b409  pop     esi
0x40b40a  pop     ebx
0x40b40b  leave
0x40b40c  retn
```
