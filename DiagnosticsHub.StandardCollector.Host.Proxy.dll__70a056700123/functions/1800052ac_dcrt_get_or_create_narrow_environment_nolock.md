# __dcrt_get_or_create_narrow_environment_nolock

- ea: `0x1800052ac`
- end: `0x1800052e7`
- name: `__dcrt_get_or_create_narrow_environment_nolock`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b360`
- `0x18000bd5c`

## callees

- `0x1800049d8`
- `0x180004df8`
- `0x1800052ac`

## pseudocode

```c
void *_dcrt_get_or_create_narrow_environment_nolock()
{
  void *result; // rax

  result = environ_table;
  if ( !environ_table )
  {
    if ( !wenviron_table
      || (unsigned int)common_initialize_environment_nolock_char_()
      && (unsigned int)initialize_environment_by_cloning_nolock_char_() )
    {
      return 0;
    }
    else
    {
      return environ_table;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800052ac  sub     rsp, 28h
0x1800052b0  mov     rax, cs:_environ_table
0x1800052b7  test    rax, rax
0x1800052ba  jnz     short loc_1800052E2
0x1800052bc  cmp     cs:_wenviron_table, rax
0x1800052c3  jnz     short loc_1800052C9
0x1800052c5  xor     eax, eax
0x1800052c7  jmp     short loc_1800052E2
0x1800052c9  call    common_initialize_environment_nolock_char_
0x1800052ce  test    eax, eax
0x1800052d0  jz      short loc_1800052DB
0x1800052d2  call    initialize_environment_by_cloning_nolock_char_
0x1800052d7  test    eax, eax
0x1800052d9  jnz     short loc_1800052C5
0x1800052db  mov     rax, cs:_environ_table
0x1800052e2  add     rsp, 28h
0x1800052e6  retn
```
