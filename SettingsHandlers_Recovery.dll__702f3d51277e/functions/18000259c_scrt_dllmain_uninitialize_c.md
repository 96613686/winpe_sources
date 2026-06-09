# __scrt_dllmain_uninitialize_c

- ea: `0x18000259c`
- end: `0x1800025cc`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002138`

## callees

- `0x18000259c`
- `0x180002d20`
- `0x180002df2`
- `0x180002e16`
- `0x180016080`

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
0x18000259c  sub     rsp, 28h
0x1800025a0  call    __scrt_is_ucrt_dll_in_use
0x1800025a5  test    eax, eax
0x1800025a7  jz      short loc_1800025B9
0x1800025a9  lea     rcx, Table; Table
0x1800025b0  add     rsp, 28h
0x1800025b4  jmp     _execute_onexit_table
0x1800025b9  call    __scrt_stub_for_is_c_termination_complete
0x1800025be  test    eax, eax
0x1800025c0  jnz     short loc_1800025C7
0x1800025c2  call    _o__cexit_0
0x1800025c7  add     rsp, 28h
0x1800025cb  retn
```
