# __scrt_dllmain_uninitialize_c

- ea: `0x180001650`
- end: `0x180001680`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800011e8`

## callees

- `0x180001650`
- `0x180001bb0`
- `0x180001c0a`
- `0x180001c22`
- `0x180001c6c`

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
0x180001650  sub     rsp, 28h
0x180001654  call    __scrt_is_ucrt_dll_in_use
0x180001659  test    eax, eax
0x18000165b  jz      short loc_18000166D
0x18000165d  lea     rcx, Table; Table
0x180001664  add     rsp, 28h
0x180001668  jmp     _execute_onexit_table
0x18000166d  call    __scrt_stub_for_is_c_termination_complete
0x180001672  test    eax, eax
0x180001674  jnz     short loc_18000167B
0x180001676  call    _o__cexit_0
0x18000167b  add     rsp, 28h
0x18000167f  retn
```
