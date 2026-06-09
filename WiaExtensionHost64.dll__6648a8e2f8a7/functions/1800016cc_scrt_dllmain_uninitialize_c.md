# __scrt_dllmain_uninitialize_c

- ea: `0x1800016cc`
- end: `0x1800016fc`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001228`

## callees

- `0x1800016cc`
- `0x180001c54`
- `0x180001cb6`
- `0x180001cce`
- `0x180001d30`

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
0x1800016cc  sub     rsp, 28h
0x1800016d0  call    __scrt_is_ucrt_dll_in_use
0x1800016d5  test    eax, eax
0x1800016d7  jz      short loc_1800016E9
0x1800016d9  lea     rcx, Table; Table
0x1800016e0  add     rsp, 28h
0x1800016e4  jmp     _execute_onexit_table
0x1800016e9  call    __scrt_stub_for_is_c_termination_complete
0x1800016ee  test    eax, eax
0x1800016f0  jnz     short loc_1800016F7
0x1800016f2  call    _o__cexit_0
0x1800016f7  add     rsp, 28h
0x1800016fb  retn
```
