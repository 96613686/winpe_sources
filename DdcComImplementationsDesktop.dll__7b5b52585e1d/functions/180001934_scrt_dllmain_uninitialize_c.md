# __scrt_dllmain_uninitialize_c

- ea: `0x180001934`
- end: `0x180001964`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001488`

## callees

- `0x180001934`
- `0x180001f5c`
- `0x180002088`
- `0x1800020ac`
- `0x1800022bc`

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
0x180001934  sub     rsp, 28h
0x180001938  call    __scrt_is_ucrt_dll_in_use
0x18000193d  test    eax, eax
0x18000193f  jz      short loc_180001951
0x180001941  lea     rcx, Table; Table
0x180001948  add     rsp, 28h
0x18000194c  jmp     _execute_onexit_table
0x180001951  call    __scrt_stub_for_is_c_termination_complete
0x180001956  test    eax, eax
0x180001958  jnz     short loc_18000195F
0x18000195a  call    _o__cexit_0
0x18000195f  add     rsp, 28h
0x180001963  retn
```
