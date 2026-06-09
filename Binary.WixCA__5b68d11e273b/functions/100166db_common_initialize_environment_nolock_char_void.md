# common_initialize_environment_nolock<char>(void)

- ea: `0x100166db`
- end: `0x1001672e`
- name: `??$common_initialize_environment_nolock@D@@YAHXZ`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x100168c5`

## callees

- `0x100166db`
- `0x1001672e`
- `0x1001770e`
- `0x10019bea`
- `0x1001a034`

## pseudocode

```c
int common_initialize_environment_nolock<char>()
{
  char *narrow_environment_from_os; // eax
  char *v2; // esi
  int v3; // edi
  void *v4; // eax

  if ( dword_10034EE0 )
    return 0;
  __acrt_initialize_multibyte();
  narrow_environment_from_os = (char *)__dcrt_get_narrow_environment_from_os();
  v2 = narrow_environment_from_os;
  if ( narrow_environment_from_os )
  {
    v4 = create_environment<char>(narrow_environment_from_os);
    if ( v4 )
    {
      dword_10034EEC = v4;
      v3 = 0;
      dword_10034EE0 = (int)v4;
    }
    else
    {
      v3 = -1;
    }
    _free_base(0);
  }
  else
  {
    v3 = -1;
  }
  _free_base(v2);
  return v3;
}

```

## disassembly

```asm
0x100166db  cmp     dword_10034EE0, 0
0x100166e2  jz      short loc_100166E7
0x100166e4  xor     eax, eax
0x100166e6  retn
0x100166e7  push    esi
0x100166e8  push    edi
0x100166e9  call    ___acrt_initialize_multibyte
0x100166ee  call    ___dcrt_get_narrow_environment_from_os
0x100166f3  mov     esi, eax
0x100166f5  test    esi, esi
0x100166f7  jnz     short loc_100166FE
0x100166f9  or      edi, 0FFFFFFFFh
0x100166fc  jmp     short loc_10016722
0x100166fe  push    esi; Source
0x100166ff  call    ??$create_environment@D@@YAQAPADQAD@Z
0x10016704  pop     ecx
0x10016705  test    eax, eax
0x10016707  jnz     short loc_1001670E
0x10016709  or      edi, 0FFFFFFFFh
0x1001670c  jmp     short loc_1001671A
0x1001670e  mov     dword_10034EEC, eax
0x10016713  xor     edi, edi
0x10016715  mov     dword_10034EE0, eax
0x1001671a  push    0; Block
0x1001671c  call    __free_base
0x10016721  pop     ecx
0x10016722  push    esi; Block
0x10016723  call    __free_base
0x10016728  pop     ecx
0x10016729  mov     eax, edi
0x1001672b  pop     edi
0x1001672c  pop     esi
0x1001672d  retn
```
