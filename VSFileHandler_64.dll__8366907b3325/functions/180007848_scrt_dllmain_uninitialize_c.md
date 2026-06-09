# __scrt_dllmain_uninitialize_c

- ea: `0x180007848`
- end: `0x180007878`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800074f8`

## callees

- `0x180007848`
- `0x180008344`
- `0x18000db5c`
- `0x18000db78`
- `0x18000e4a8`

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
0x180007848  sub     rsp, 28h
0x18000784c  call    __scrt_is_ucrt_dll_in_use
0x180007851  test    eax, eax
0x180007853  jz      short loc_180007865
0x180007855  lea     rcx, Table
0x18000785c  add     rsp, 28h
0x180007860  jmp     _execute_onexit_table
0x180007865  call    _is_c_termination_complete
0x18000786a  test    eax, eax
0x18000786c  jnz     short loc_180007873
0x18000786e  call    _cexit
0x180007873  add     rsp, 28h
0x180007877  retn
```
