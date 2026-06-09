# common_initialize_environment_nolock<wchar_t>(void)

- ea: `0x410c4c`
- end: `0x410c9a`
- name: `??$common_initialize_environment_nolock@_W@@YAHXZ`
- size: `78`
- prototype: `int()`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x410e72`

## callees

- `0x410c4c`
- `0x410c9a`
- `0x4136b2`
- `0x414d77`

## pseudocode

```c
int common_initialize_environment_nolock<wchar_t>()
{
  wchar_t *wide_environment_from_os; // eax
  wchar_t *v2; // esi
  int v3; // edi
  void *v4; // eax

  if ( dword_43E2E8 )
    return 0;
  wide_environment_from_os = (wchar_t *)__dcrt_get_wide_environment_from_os();
  v2 = wide_environment_from_os;
  if ( wide_environment_from_os )
  {
    v4 = (void *)create_environment<wchar_t>(wide_environment_from_os);
    if ( v4 )
    {
      dword_43E2EC = v4;
      v3 = 0;
      dword_43E2E8 = (int)v4;
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
0x410c4c  cmp     dword_43E2E8, 0
0x410c53  jz      short loc_410C58
0x410c55  xor     eax, eax
0x410c57  retn
0x410c58  push    esi
0x410c59  push    edi
0x410c5a  call    ___dcrt_get_wide_environment_from_os
0x410c5f  mov     esi, eax
0x410c61  test    esi, esi
0x410c63  jnz     short loc_410C6A
0x410c65  or      edi, 0FFFFFFFFh
0x410c68  jmp     short loc_410C8E
0x410c6a  push    esi; Source
0x410c6b  call    ??$create_environment@_W@@YAQAPA_WQA_W@Z
0x410c70  pop     ecx
0x410c71  test    eax, eax
0x410c73  jnz     short loc_410C7A
0x410c75  or      edi, 0FFFFFFFFh
0x410c78  jmp     short loc_410C86
0x410c7a  mov     dword_43E2EC, eax
0x410c7f  xor     edi, edi
0x410c81  mov     dword_43E2E8, eax
0x410c86  push    0; Block
0x410c88  call    __free_base
0x410c8d  pop     ecx
0x410c8e  push    esi; Block
0x410c8f  call    __free_base
0x410c94  pop     ecx
0x410c95  mov     eax, edi
0x410c97  pop     edi
0x410c98  pop     esi
0x410c99  retn
```
