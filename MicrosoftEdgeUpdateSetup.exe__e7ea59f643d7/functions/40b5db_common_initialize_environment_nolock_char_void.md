# common_initialize_environment_nolock<char>(void)

- ea: `0x40b5db`
- end: `0x40b62e`
- name: `??$common_initialize_environment_nolock@D@@YAHXZ`
- size: `83`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x40b7d2`

## callees

- `0x40b5db`
- `0x40b62e`
- `0x40ed53`
- `0x40fc80`
- `0x410143`

## pseudocode

```c
int common_initialize_environment_nolock<char>()
{
  char *narrow_environment_from_os; // eax
  char *v2; // esi
  int v3; // edi
  void *v4; // eax

  if ( dword_426E48 )
    return 0;
  __acrt_initialize_multibyte();
  narrow_environment_from_os = (char *)__dcrt_get_narrow_environment_from_os();
  v2 = narrow_environment_from_os;
  if ( narrow_environment_from_os )
  {
    v4 = (void *)create_environment<char>(narrow_environment_from_os);
    if ( v4 )
    {
      dword_426E54 = v4;
      v3 = 0;
      dword_426E48 = (int)v4;
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
0x40b5db  cmp     dword_426E48, 0
0x40b5e2  jz      short loc_40B5E7
0x40b5e4  xor     eax, eax
0x40b5e6  retn
0x40b5e7  push    esi
0x40b5e8  push    edi
0x40b5e9  call    ___acrt_initialize_multibyte
0x40b5ee  call    ___dcrt_get_narrow_environment_from_os
0x40b5f3  mov     esi, eax
0x40b5f5  test    esi, esi
0x40b5f7  jnz     short loc_40B5FE
0x40b5f9  or      edi, 0FFFFFFFFh
0x40b5fc  jmp     short loc_40B622
0x40b5fe  push    esi; Source
0x40b5ff  call    ??$create_environment@D@@YAQAPADQAD@Z
0x40b604  pop     ecx
0x40b605  test    eax, eax
0x40b607  jnz     short loc_40B60E
0x40b609  or      edi, 0FFFFFFFFh
0x40b60c  jmp     short loc_40B61A
0x40b60e  mov     dword_426E54, eax
0x40b613  xor     edi, edi
0x40b615  mov     dword_426E48, eax
0x40b61a  push    0; Block
0x40b61c  call    __free_base
0x40b621  pop     ecx
0x40b622  push    esi; Block
0x40b623  call    __free_base
0x40b628  pop     ecx
0x40b629  mov     eax, edi
0x40b62b  pop     edi
0x40b62c  pop     esi
0x40b62d  retn
```
