# __scrt_dllmain_uninitialize_c

- ea: `0x1800016ac`
- end: `0x1800016dc`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001338`

## callees

- `0x1800016ac`
- `0x180001dc8`
- `0x180001e62`
- `0x180001e86`
- `0x1800021a8`

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
0x1800016ac  sub     rsp, 28h
0x1800016b0  call    __scrt_is_ucrt_dll_in_use
0x1800016b5  test    eax, eax
0x1800016b7  jz      short loc_1800016C9
0x1800016b9  lea     rcx, Table; Table
0x1800016c0  add     rsp, 28h
0x1800016c4  jmp     _execute_onexit_table
0x1800016c9  call    __scrt_stub_for_is_c_termination_complete
0x1800016ce  test    eax, eax
0x1800016d0  jnz     short loc_1800016D7
0x1800016d2  call    _o__cexit_0
0x1800016d7  add     rsp, 28h
0x1800016db  retn
```
