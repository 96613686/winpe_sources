# __dcrt_get_or_create_wide_environment_nolock

- ea: `0x14001294c`
- end: `0x140012987`
- name: `__dcrt_get_or_create_wide_environment_nolock`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140017230`

## callees

- `0x140012684`
- `0x140012858`
- `0x14001294c`

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
0x14001294c  sub     rsp, 28h
0x140012950  mov     rax, cs:_wenviron_table
0x140012957  test    rax, rax
0x14001295a  jnz     short loc_140012982
0x14001295c  cmp     cs:_environ_table, rax
0x140012963  jnz     short loc_140012969
0x140012965  xor     eax, eax
0x140012967  jmp     short loc_140012982
0x140012969  call    common_initialize_environment_nolock_wchar_t_
0x14001296e  test    eax, eax
0x140012970  jz      short loc_14001297B
0x140012972  call    initialize_environment_by_cloning_nolock_wchar_t_
0x140012977  test    eax, eax
0x140012979  jnz     short loc_140012965
0x14001297b  mov     rax, cs:_wenviron_table
0x140012982  add     rsp, 28h
0x140012986  retn
```
