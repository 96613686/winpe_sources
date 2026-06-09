# __scrt_dllmain_uninitialize_c

- ea: `0x180002d4c`
- end: `0x180002d7c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800029e8`

## callees

- `0x180002d4c`
- `0x180003570`
- `0x18000364e`
- `0x180003672`
- `0x18000c5f0`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = _scrt_stub_for_is_c_termination_complete();
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180002d4c  sub     rsp, 28h
0x180002d50  call    __scrt_is_ucrt_dll_in_use
0x180002d55  test    eax, eax
0x180002d57  jz      short loc_180002D69
0x180002d59  lea     rcx, Table; Table
0x180002d60  add     rsp, 28h
0x180002d64  jmp     _execute_onexit_table
0x180002d69  call    __scrt_stub_for_is_c_termination_complete
0x180002d6e  test    eax, eax
0x180002d70  jnz     short loc_180002D77
0x180002d72  call    _o__cexit_0
0x180002d77  add     rsp, 28h
0x180002d7b  retn
```
