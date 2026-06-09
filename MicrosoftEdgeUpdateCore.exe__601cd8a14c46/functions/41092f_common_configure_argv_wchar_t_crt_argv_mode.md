# common_configure_argv<wchar_t>(_crt_argv_mode)

- ea: `0x41092f`
- end: `0x410a5e`
- name: `??$common_configure_argv@_W@@YAHW4_crt_argv_mode@@@Z`
- size: `303`
- prototype: `int __cdecl(int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x410c41`

## callees

- `0x410369`
- `0x410443`
- `0x41092f`
- `0x410a5e`
- `0x410bf2`
- `0x4136b2`
- `0x414391`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x410976`
- `KERNEL32!GetModuleFileNameW` at `0x410976`

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
  v3 = (WCHAR *)dword_43E4A4;
  dword_43E490 = (int)&Filename;
  v11 = (WCHAR *)dword_43E4A4;
  if ( !dword_43E4A4 || !*(_WORD *)dword_43E4A4 )
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
        dword_43E494 = v9;
        Block = 0;
        v6 = 0;
        dword_43E49C = v8;
      }
      _free_base(v7);
      Block = 0;
      goto LABEL_20;
    }
    dword_43E494 = v14 - 1;
    v5 = buffer_for_argv;
    buffer_for_argv = 0;
    dword_43E49C = v5;
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
0x41092f  mov     edi, edi
0x410931  push    ebp
0x410932  mov     ebp, esp
0x410934  sub     esp, 10h
0x410937  push    ebx
0x410938  mov     ebx, [ebp+arg_0]
0x41093b  test    ebx, ebx
0x41093d  jnz     short loc_410946
0x41093f  xor     eax, eax
0x410941  jmp     loc_410A5B
0x410946  push    esi
0x410947  cmp     ebx, 2
0x41094a  jz      short loc_410967
0x41094c  cmp     ebx, 1
0x41094f  jz      short loc_410967
0x410951  call    __errno
0x410956  push    16h
0x410958  pop     esi
0x410959  mov     [eax], esi
0x41095b  call    __invalid_parameter_noinfo
0x410960  mov     eax, esi
0x410962  jmp     loc_410A5A
0x410967  push    edi
0x410968  push    104h; nSize
0x41096d  mov     esi, offset Filename
0x410972  xor     edi, edi
0x410974  push    esi; lpFilename
0x410975  push    edi; hModule
0x410976  call    ds:GetModuleFileNameW
0x41097c  mov     eax, dword_43E4A4
0x410981  mov     dword_43E490, esi
0x410987  mov     [ebp+var_10], eax
0x41098a  test    eax, eax
0x41098c  jz      short loc_410993
0x41098e  cmp     [eax], di
0x410991  jnz     short loc_410998
0x410993  mov     eax, esi
0x410995  mov     [ebp+var_10], esi
0x410998  lea     ecx, [ebp+var_C]
0x41099b  mov     [ebp+var_4], edi
0x41099e  push    ecx
0x41099f  lea     ecx, [ebp+var_4]
0x4109a2  mov     [ebp+var_C], edi
0x4109a5  push    ecx
0x4109a6  push    edi
0x4109a7  push    edi
0x4109a8  push    eax
0x4109a9  call    ??$parse_command_line@_W@@YAXPA_WPAPA_W0PAI2@Z
0x4109ae  push    2
0x4109b0  push    [ebp+var_C]
0x4109b3  push    [ebp+var_4]
0x4109b6  call    ___acrt_allocate_buffer_for_argv
0x4109bb  mov     esi, eax
0x4109bd  add     esp, 20h
0x4109c0  test    esi, esi
0x4109c2  jnz     short loc_4109D0
0x4109c4  call    __errno
0x4109c9  push    0Ch
0x4109cb  pop     edi
0x4109cc  mov     [eax], edi
0x4109ce  jmp     short loc_410A02
0x4109d0  lea     eax, [ebp+var_C]
0x4109d3  push    eax
0x4109d4  lea     eax, [ebp+var_4]
0x4109d7  push    eax
0x4109d8  mov     eax, [ebp+var_4]
0x4109db  lea     eax, [esi+eax*4]
0x4109de  push    eax
0x4109df  push    esi
0x4109e0  push    [ebp+var_10]
0x4109e3  call    ??$parse_command_line@_W@@YAXPA_WPAPA_W0PAI2@Z
0x4109e8  add     esp, 14h
0x4109eb  cmp     ebx, 1
0x4109ee  jnz     short loc_410A06
0x4109f0  mov     eax, [ebp+var_4]
0x4109f3  dec     eax
0x4109f4  mov     dword_43E494, eax
0x4109f9  mov     eax, esi
0x4109fb  mov     esi, edi
0x4109fd  mov     dword_43E49C, eax
0x410a02  mov     ebx, edi
0x410a04  jmp     short loc_410A50
0x410a06  lea     eax, [ebp+Block]
0x410a09  mov     [ebp+Block], edi
0x410a0c  push    eax
0x410a0d  push    esi
0x410a0e  call    ___acrt_expand_wide_argv_wildcards
0x410a13  mov     ebx, eax
0x410a15  pop     ecx
0x410a16  pop     ecx
0x410a17  test    ebx, ebx
0x410a19  jz      short loc_410A20
0x410a1b  mov     eax, [ebp+Block]
0x410a1e  jmp     short loc_410A46
0x410a20  mov     edx, [ebp+Block]
0x410a23  mov     ecx, edi
0x410a25  mov     eax, edx
0x410a27  cmp     [edx], edi
0x410a29  jz      short loc_410A33
0x410a2b  lea     eax, [eax+4]
0x410a2e  inc     ecx
0x410a2f  cmp     [eax], edi
0x410a31  jnz     short loc_410A2B
0x410a33  mov     eax, edi
0x410a35  mov     dword_43E494, ecx
0x410a3b  mov     [ebp+Block], eax
0x410a3e  mov     ebx, edi
0x410a40  mov     dword_43E49C, edx
0x410a46  push    eax; Block
0x410a47  call    __free_base
0x410a4c  pop     ecx
0x410a4d  mov     [ebp+Block], edi
0x410a50  push    esi; Block
0x410a51  call    __free_base
0x410a56  pop     ecx
0x410a57  mov     eax, ebx
0x410a59  pop     edi
0x410a5a  pop     esi
0x410a5b  pop     ebx
0x410a5c  leave
0x410a5d  retn
```
