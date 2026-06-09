# __dcrt_get_or_create_wide_environment_nolock

- ea: `0x180005a44`
- end: `0x180005a7f`
- name: `__dcrt_get_or_create_wide_environment_nolock`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000be18`
- `0x18000c4c4`

## callees

- `0x1800051a8`
- `0x180005634`
- `0x180005a44`

## pseudocode

```c
void *_dcrt_get_or_create_wide_environment_nolock()
{
  void *result; // rax

  result = wenviron_table;
  if ( !wenviron_table )
  {
    if ( !environ_table
      || (unsigned int)common_initialize_environment_nolock_wchar_t_()
      && (unsigned int)initialize_environment_by_cloning_nolock_wchar_t_() )
    {
      return 0;
    }
    else
    {
      return wenviron_table;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005a44  sub     rsp, 28h
0x180005a48  mov     rax, cs:_wenviron_table
0x180005a4f  test    rax, rax
0x180005a52  jnz     short loc_180005A7A
0x180005a54  cmp     cs:_environ_table, rax
0x180005a5b  jnz     short loc_180005A61
0x180005a5d  xor     eax, eax
0x180005a5f  jmp     short loc_180005A7A
0x180005a61  call    common_initialize_environment_nolock_wchar_t_
0x180005a66  test    eax, eax
0x180005a68  jz      short loc_180005A73
0x180005a6a  call    initialize_environment_by_cloning_nolock_wchar_t_
0x180005a6f  test    eax, eax
0x180005a71  jnz     short loc_180005A5D
0x180005a73  mov     rax, cs:_wenviron_table
0x180005a7a  add     rsp, 28h
0x180005a7e  retn
```
