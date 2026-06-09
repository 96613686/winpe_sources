# common_initialize_environment_nolock<wchar_t>(void)

- ea: `0x40e7c4`
- end: `0x40e812`
- name: `??$common_initialize_environment_nolock@_W@@YAHXZ`
- size: `78`
- prototype: `int()`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x40e9f2`

## callees

- `0x40e7c4`
- `0x40e812`
- `0x41001a`
- `0x410ef3`

## pseudocode

```c
int common_initialize_environment_nolock<wchar_t>()
{
  wchar_t *wide_environment_from_os; // eax
  wchar_t *v2; // esi
  int v3; // edi
  void *v4; // eax

  if ( dword_417FE0 )
    return 0;
  wide_environment_from_os = (wchar_t *)__dcrt_get_wide_environment_from_os();
  v2 = wide_environment_from_os;
  if ( wide_environment_from_os )
  {
    v4 = (void *)create_environment<wchar_t>(wide_environment_from_os);
    if ( v4 )
    {
      dword_417FE4 = v4;
      v3 = 0;
      dword_417FE0 = (int)v4;
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
0x40e7c4  cmp     dword_417FE0, 0
0x40e7cb  jz      short loc_40E7D0
0x40e7cd  xor     eax, eax
0x40e7cf  retn
0x40e7d0  push    esi
0x40e7d1  push    edi
0x40e7d2  call    ___dcrt_get_wide_environment_from_os
0x40e7d7  mov     esi, eax
0x40e7d9  test    esi, esi
0x40e7db  jnz     short loc_40E7E2
0x40e7dd  or      edi, 0FFFFFFFFh
0x40e7e0  jmp     short loc_40E806
0x40e7e2  push    esi; Source
0x40e7e3  call    ??$create_environment@_W@@YAQAPA_WQA_W@Z
0x40e7e8  pop     ecx
0x40e7e9  test    eax, eax
0x40e7eb  jnz     short loc_40E7F2
0x40e7ed  or      edi, 0FFFFFFFFh
0x40e7f0  jmp     short loc_40E7FE
0x40e7f2  mov     dword_417FE4, eax
0x40e7f7  xor     edi, edi
0x40e7f9  mov     dword_417FE0, eax
0x40e7fe  push    0; Block
0x40e800  call    __free_base
0x40e805  pop     ecx
0x40e806  push    esi; Block
0x40e807  call    __free_base
0x40e80c  pop     ecx
0x40e80d  mov     eax, edi
0x40e80f  pop     edi
0x40e810  pop     esi
0x40e811  retn
```
