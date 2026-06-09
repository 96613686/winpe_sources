# __scrt_dllmain_uninitialize_c

- ea: `0x180002d0c`
- end: `0x180002d3c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800029a8`

## callees

- `0x180002d0c`
- `0x180003428`
- `0x1800034b6`
- `0x1800034da`
- `0x180009a10`

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
0x180002d0c  sub     rsp, 28h
0x180002d10  call    __scrt_is_ucrt_dll_in_use
0x180002d15  test    eax, eax
0x180002d17  jz      short loc_180002D29
0x180002d19  lea     rcx, Table; Table
0x180002d20  add     rsp, 28h
0x180002d24  jmp     _execute_onexit_table
0x180002d29  call    __scrt_stub_for_is_c_termination_complete
0x180002d2e  test    eax, eax
0x180002d30  jnz     short loc_180002D37
0x180002d32  call    _o__cexit_0
0x180002d37  add     rsp, 28h
0x180002d3b  retn
```
