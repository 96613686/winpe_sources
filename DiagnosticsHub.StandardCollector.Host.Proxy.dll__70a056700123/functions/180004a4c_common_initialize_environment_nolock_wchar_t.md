# common_initialize_environment_nolock_wchar_t_

- ea: `0x180004a4c`
- end: `0x180004aba`
- name: `common_initialize_environment_nolock_wchar_t_`
- size: `110`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004910`
- `0x18000499c`
- `0x1800052e8`
- `0x1800053c8`
- `0x180005420`

## callees

- `0x180004a4c`
- `0x180004c40`
- `0x1800078e0`
- `0x18000b2c4`

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
0x180004a4c  mov     [rsp+arg_0], rbx
0x180004a51  push    rdi
0x180004a52  sub     rsp, 20h
0x180004a56  xor     edi, edi
0x180004a58  cmp     cs:_wenviron_table, rdi
0x180004a5f  jz      short loc_180004A65
0x180004a61  xor     eax, eax
0x180004a63  jmp     short loc_180004AAF
0x180004a65  call    __dcrt_get_wide_environment_from_os
0x180004a6a  mov     rbx, rax
0x180004a6d  test    rax, rax
0x180004a70  jnz     short loc_180004A7E
0x180004a72  xor     ecx, ecx; Block
0x180004a74  call    _free_base
0x180004a79  or      eax, 0FFFFFFFFh
0x180004a7c  jmp     short loc_180004AAF
0x180004a7e  mov     rcx, rbx; Source
0x180004a81  call    create_environment_wchar_t_
0x180004a86  test    rax, rax
0x180004a89  jnz     short loc_180004A90
0x180004a8b  or      edi, 0FFFFFFFFh
0x180004a8e  jmp     short loc_180004A9E
0x180004a90  mov     cs:__dcrt_initial_wide_environment, rax
0x180004a97  mov     cs:_wenviron_table, rax
0x180004a9e  xor     ecx, ecx; Block
0x180004aa0  call    _free_base
0x180004aa5  mov     rcx, rbx; Block
0x180004aa8  call    _free_base
0x180004aad  mov     eax, edi
0x180004aaf  mov     rbx, [rsp+28h+arg_0]
0x180004ab4  add     rsp, 20h
0x180004ab8  pop     rdi
0x180004ab9  retn
```
