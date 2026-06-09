# __scrt_dllmain_uninitialize_c

- ea: `0x18000234c`
- end: `0x18000237c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001fe8`

## callees

- `0x18000234c`
- `0x180002e08`
- `0x180002ee2`
- `0x180002f06`
- `0x180003000`

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
0x18000234c  sub     rsp, 28h
0x180002350  call    __scrt_is_ucrt_dll_in_use
0x180002355  test    eax, eax
0x180002357  jz      short loc_180002369
0x180002359  lea     rcx, Table; Table
0x180002360  add     rsp, 28h
0x180002364  jmp     _execute_onexit_table
0x180002369  call    __scrt_stub_for_is_c_termination_complete
0x18000236e  test    eax, eax
0x180002370  jnz     short loc_180002377
0x180002372  call    _o__cexit_0
0x180002377  add     rsp, 28h
0x18000237b  retn
```
