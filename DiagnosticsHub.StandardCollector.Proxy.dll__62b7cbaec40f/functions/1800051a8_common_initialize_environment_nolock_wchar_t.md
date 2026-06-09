# common_initialize_environment_nolock_wchar_t_

- ea: `0x1800051a8`
- end: `0x180005216`
- name: `common_initialize_environment_nolock_wchar_t_`
- size: `110`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000506c`
- `0x1800050f8`
- `0x180005a44`
- `0x180005b24`
- `0x180005b7c`

## callees

- `0x1800051a8`
- `0x18000539c`
- `0x180008040`
- `0x18000ba24`

## pseudocode

```c
__int64 common_initialize_environment_nolock_wchar_t_()
{
  unsigned int v0; // edi
  wchar_t *wide_environment_from_os; // rax
  wchar_t *v3; // rbx
  void *environment_wchar_t; // rax

  v0 = 0;
  if ( wenviron_table )
    return 0;
  wide_environment_from_os = (wchar_t *)_dcrt_get_wide_environment_from_os();
  v3 = wide_environment_from_os;
  if ( wide_environment_from_os )
  {
    environment_wchar_t = (void *)create_environment_wchar_t_(wide_environment_from_os);
    if ( environment_wchar_t )
    {
      _dcrt_initial_wide_environment = environment_wchar_t;
      wenviron_table = environment_wchar_t;
    }
    else
    {
      v0 = -1;
    }
    free_base(0);
    free_base(v3);
    return v0;
  }
  else
  {
    free_base(0);
    return 0xFFFFFFFFLL;
  }
}

```

## disassembly

```asm
0x1800051a8  mov     [rsp+arg_0], rbx
0x1800051ad  push    rdi
0x1800051ae  sub     rsp, 20h
0x1800051b2  xor     edi, edi
0x1800051b4  cmp     cs:_wenviron_table, rdi
0x1800051bb  jz      short loc_1800051C1
0x1800051bd  xor     eax, eax
0x1800051bf  jmp     short loc_18000520B
0x1800051c1  call    __dcrt_get_wide_environment_from_os
0x1800051c6  mov     rbx, rax
0x1800051c9  test    rax, rax
0x1800051cc  jnz     short loc_1800051DA
0x1800051ce  xor     ecx, ecx; Block
0x1800051d0  call    _free_base
0x1800051d5  or      eax, 0FFFFFFFFh
0x1800051d8  jmp     short loc_18000520B
0x1800051da  mov     rcx, rbx; Source
0x1800051dd  call    create_environment_wchar_t_
0x1800051e2  test    rax, rax
0x1800051e5  jnz     short loc_1800051EC
0x1800051e7  or      edi, 0FFFFFFFFh
0x1800051ea  jmp     short loc_1800051FA
0x1800051ec  mov     cs:__dcrt_initial_wide_environment, rax
0x1800051f3  mov     cs:_wenviron_table, rax
0x1800051fa  xor     ecx, ecx; Block
0x1800051fc  call    _free_base
0x180005201  mov     rcx, rbx; Block
0x180005204  call    _free_base
0x180005209  mov     eax, edi
0x18000520b  mov     rbx, [rsp+28h+arg_0]
0x180005210  add     rsp, 20h
0x180005214  pop     rdi
0x180005215  retn
```
