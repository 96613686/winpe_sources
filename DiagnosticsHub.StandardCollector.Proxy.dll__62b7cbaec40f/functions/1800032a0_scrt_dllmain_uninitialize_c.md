# __scrt_dllmain_uninitialize_c

- ea: `0x1800032a0`
- end: `0x1800032d0`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002998`

## callees

- `0x1800032a0`
- `0x180003d14`
- `0x1800043e8`
- `0x180004404`
- `0x1800060b8`

## pseudocode

```c
void _scrt_dllmain_uninitialize_c()
{
  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    execute_onexit_table(&Table);
  }
  else if ( !is_c_termination_complete() )
  {
    cexit();
  }
}

```

## disassembly

```asm
0x1800032a0  sub     rsp, 28h
0x1800032a4  call    __scrt_is_ucrt_dll_in_use
0x1800032a9  test    eax, eax
0x1800032ab  jz      short loc_1800032BD
0x1800032ad  lea     rcx, Table
0x1800032b4  add     rsp, 28h
0x1800032b8  jmp     _execute_onexit_table
0x1800032bd  call    _is_c_termination_complete
0x1800032c2  test    eax, eax
0x1800032c4  jnz     short loc_1800032CB
0x1800032c6  call    _cexit
0x1800032cb  add     rsp, 28h
0x1800032cf  retn
```
