# __dcrt_get_or_create_wide_environment_nolock

- ea: `0x1800052e8`
- end: `0x180005323`
- name: `__dcrt_get_or_create_wide_environment_nolock`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b6b8`
- `0x18000bd64`

## callees

- `0x180004a4c`
- `0x180004ed8`
- `0x1800052e8`

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
0x1800052e8  sub     rsp, 28h
0x1800052ec  mov     rax, cs:_wenviron_table
0x1800052f3  test    rax, rax
0x1800052f6  jnz     short loc_18000531E
0x1800052f8  cmp     cs:_environ_table, rax
0x1800052ff  jnz     short loc_180005305
0x180005301  xor     eax, eax
0x180005303  jmp     short loc_18000531E
0x180005305  call    common_initialize_environment_nolock_wchar_t_
0x18000530a  test    eax, eax
0x18000530c  jz      short loc_180005317
0x18000530e  call    initialize_environment_by_cloning_nolock_wchar_t_
0x180005313  test    eax, eax
0x180005315  jnz     short loc_180005301
0x180005317  mov     rax, cs:_wenviron_table
0x18000531e  add     rsp, 28h
0x180005322  retn
```
