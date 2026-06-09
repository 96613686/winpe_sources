# common_initialize_environment_nolock_wchar_t_

- ea: `0x140012684`
- end: `0x1400126f2`
- name: `common_initialize_environment_nolock_wchar_t_`
- size: `110`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001294c`
- `0x1400129cc`
- `0x140012a1c`

## callees

- `0x140012684`
- `0x1400126f4`
- `0x140013e10`
- `0x140017194`

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
    environment_wchar_t = create_environment_wchar_t_(wide_environment_from_os);
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
0x140012684  mov     [rsp+arg_0], rbx
0x140012689  push    rdi
0x14001268a  sub     rsp, 20h
0x14001268e  xor     edi, edi
0x140012690  cmp     cs:_wenviron_table, rdi
0x140012697  jz      short loc_14001269D
0x140012699  xor     eax, eax
0x14001269b  jmp     short loc_1400126E7
0x14001269d  call    __dcrt_get_wide_environment_from_os
0x1400126a2  mov     rbx, rax
0x1400126a5  test    rax, rax
0x1400126a8  jnz     short loc_1400126B6
0x1400126aa  xor     ecx, ecx; Block
0x1400126ac  call    _free_base
0x1400126b1  or      eax, 0FFFFFFFFh
0x1400126b4  jmp     short loc_1400126E7
0x1400126b6  mov     rcx, rbx; Source
0x1400126b9  call    create_environment_wchar_t_
0x1400126be  test    rax, rax
0x1400126c1  jnz     short loc_1400126C8
0x1400126c3  or      edi, 0FFFFFFFFh
0x1400126c6  jmp     short loc_1400126D6
0x1400126c8  mov     cs:__dcrt_initial_wide_environment, rax
0x1400126cf  mov     cs:_wenviron_table, rax
0x1400126d6  xor     ecx, ecx; Block
0x1400126d8  call    _free_base
0x1400126dd  mov     rcx, rbx; Block
0x1400126e0  call    _free_base
0x1400126e5  mov     eax, edi
0x1400126e7  mov     rbx, [rsp+28h+arg_0]
0x1400126ec  add     rsp, 20h
0x1400126f0  pop     rdi
0x1400126f1  retn
```
