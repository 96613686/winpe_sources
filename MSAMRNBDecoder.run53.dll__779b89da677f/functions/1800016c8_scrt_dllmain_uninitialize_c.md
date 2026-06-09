# __scrt_dllmain_uninitialize_c

- ea: `0x1800016c8`
- end: `0x1800016f8`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800011e8`

## callees

- `0x1800016c8`
- `0x180001e4c`
- `0x180001eee`
- `0x180001f06`
- `0x18000a590`

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
0x1800016c8  sub     rsp, 28h
0x1800016cc  call    __scrt_is_ucrt_dll_in_use
0x1800016d1  test    eax, eax
0x1800016d3  jz      short loc_1800016E5
0x1800016d5  lea     rcx, Table; Table
0x1800016dc  add     rsp, 28h
0x1800016e0  jmp     _execute_onexit_table
0x1800016e5  call    __scrt_stub_for_is_c_termination_complete
0x1800016ea  test    eax, eax
0x1800016ec  jnz     short loc_1800016F3
0x1800016ee  call    _o__cexit_0
0x1800016f3  add     rsp, 28h
0x1800016f7  retn
```
