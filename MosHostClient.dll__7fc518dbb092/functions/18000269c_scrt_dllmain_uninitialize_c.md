# __scrt_dllmain_uninitialize_c

- ea: `0x18000269c`
- end: `0x1800026cc`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002328`

## callees

- `0x18000269c`
- `0x180002e28`
- `0x180002f0e`
- `0x180002f32`
- `0x180003228`

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
0x18000269c  sub     rsp, 28h
0x1800026a0  call    __scrt_is_ucrt_dll_in_use
0x1800026a5  test    eax, eax
0x1800026a7  jz      short loc_1800026B9
0x1800026a9  lea     rcx, Table; Table
0x1800026b0  add     rsp, 28h
0x1800026b4  jmp     _execute_onexit_table
0x1800026b9  call    __scrt_stub_for_is_c_termination_complete
0x1800026be  test    eax, eax
0x1800026c0  jnz     short loc_1800026C7
0x1800026c2  call    _o__cexit_0
0x1800026c7  add     rsp, 28h
0x1800026cb  retn
```
