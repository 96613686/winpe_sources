# __scrt_dllmain_uninitialize_c

- ea: `0x1800016a4`
- end: `0x1800016d4`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800011e8`

## callees

- `0x1800016a4`
- `0x180001e20`
- `0x180001ef2`
- `0x180001f0a`
- `0x18000c8c0`

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
0x1800016a4  sub     rsp, 28h
0x1800016a8  call    __scrt_is_ucrt_dll_in_use
0x1800016ad  test    eax, eax
0x1800016af  jz      short loc_1800016C1
0x1800016b1  lea     rcx, Table; Table
0x1800016b8  add     rsp, 28h
0x1800016bc  jmp     _execute_onexit_table
0x1800016c1  call    __scrt_stub_for_is_c_termination_complete
0x1800016c6  test    eax, eax
0x1800016c8  jnz     short loc_1800016CF
0x1800016ca  call    _o__cexit_0
0x1800016cf  add     rsp, 28h
0x1800016d3  retn
```
