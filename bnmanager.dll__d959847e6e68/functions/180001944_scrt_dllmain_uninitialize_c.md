# __scrt_dllmain_uninitialize_c

- ea: `0x180001944`
- end: `0x180001974`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800015a8`

## callees

- `0x180001944`
- `0x18000212c`
- `0x1800021d2`
- `0x1800021f6`
- `0x180002350`

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
0x180001944  sub     rsp, 28h
0x180001948  call    __scrt_is_ucrt_dll_in_use
0x18000194d  test    eax, eax
0x18000194f  jz      short loc_180001961
0x180001951  lea     rcx, Table; Table
0x180001958  add     rsp, 28h
0x18000195c  jmp     _execute_onexit_table
0x180001961  call    __scrt_stub_for_is_c_termination_complete
0x180001966  test    eax, eax
0x180001968  jnz     short loc_18000196F
0x18000196a  call    _o__cexit_0
0x18000196f  add     rsp, 28h
0x180001973  retn
```
