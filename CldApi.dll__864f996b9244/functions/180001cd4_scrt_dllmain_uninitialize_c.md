# __scrt_dllmain_uninitialize_c

- ea: `0x180001cd4`
- end: `0x180001d04`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001868`

## callees

- `0x180001cd4`
- `0x18000224c`
- `0x18000229a`
- `0x1800022b2`
- `0x1800025e0`

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
0x180001cd4  sub     rsp, 28h
0x180001cd8  call    __scrt_is_ucrt_dll_in_use
0x180001cdd  test    eax, eax
0x180001cdf  jz      short loc_180001CF1
0x180001ce1  lea     rcx, Table; Table
0x180001ce8  add     rsp, 28h
0x180001cec  jmp     _execute_onexit_table
0x180001cf1  call    __scrt_stub_for_is_c_termination_complete
0x180001cf6  test    eax, eax
0x180001cf8  jnz     short loc_180001CFF
0x180001cfa  call    _o__cexit_0
0x180001cff  add     rsp, 28h
0x180001d03  retn
```
