# __dcrt_get_or_create_narrow_environment_nolock

- ea: `0x180005a08`
- end: `0x180005a43`
- name: `__dcrt_get_or_create_narrow_environment_nolock`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000bac0`
- `0x18000c4bc`

## callees

- `0x180005134`
- `0x180005554`
- `0x180005a08`

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
0x180005a08  sub     rsp, 28h
0x180005a0c  mov     rax, cs:_environ_table
0x180005a13  test    rax, rax
0x180005a16  jnz     short loc_180005A3E
0x180005a18  cmp     cs:_wenviron_table, rax
0x180005a1f  jnz     short loc_180005A25
0x180005a21  xor     eax, eax
0x180005a23  jmp     short loc_180005A3E
0x180005a25  call    common_initialize_environment_nolock_char_
0x180005a2a  test    eax, eax
0x180005a2c  jz      short loc_180005A37
0x180005a2e  call    initialize_environment_by_cloning_nolock_char_
0x180005a33  test    eax, eax
0x180005a35  jnz     short loc_180005A21
0x180005a37  mov     rax, cs:_environ_table
0x180005a3e  add     rsp, 28h
0x180005a42  retn
```
