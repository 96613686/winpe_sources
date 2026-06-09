# __scrt_dllmain_uninitialize_c

- ea: `0x1800016c0`
- end: `0x1800016f0`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001338`

## callees

- `0x1800016c0`
- `0x180001dfc`
- `0x1800020b4`
- `0x1800020d8`
- `0x1800021d0`

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
0x1800016c0  sub     rsp, 28h
0x1800016c4  call    __scrt_is_ucrt_dll_in_use
0x1800016c9  test    eax, eax
0x1800016cb  jz      short loc_1800016DD
0x1800016cd  lea     rcx, Table; Table
0x1800016d4  add     rsp, 28h
0x1800016d8  jmp     _execute_onexit_table
0x1800016dd  call    __scrt_stub_for_is_c_termination_complete
0x1800016e2  test    eax, eax
0x1800016e4  jnz     short loc_1800016EB
0x1800016e6  call    _o__cexit_0
0x1800016eb  add     rsp, 28h
0x1800016ef  retn
```
