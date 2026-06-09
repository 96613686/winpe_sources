# __scrt_dllmain_uninitialize_c

- ea: `0x1800037a4`
- end: `0x1800037d4`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003308`

## callees

- `0x1800037a4`
- `0x180003fac`
- `0x18000403e`
- `0x180004062`
- `0x18000a3c0`

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
0x1800037a4  sub     rsp, 28h
0x1800037a8  call    __scrt_is_ucrt_dll_in_use
0x1800037ad  test    eax, eax
0x1800037af  jz      short loc_1800037C1
0x1800037b1  lea     rcx, Table; Table
0x1800037b8  add     rsp, 28h
0x1800037bc  jmp     _execute_onexit_table
0x1800037c1  call    __scrt_stub_for_is_c_termination_complete
0x1800037c6  test    eax, eax
0x1800037c8  jnz     short loc_1800037CF
0x1800037ca  call    _o__cexit_0
0x1800037cf  add     rsp, 28h
0x1800037d3  retn
```
