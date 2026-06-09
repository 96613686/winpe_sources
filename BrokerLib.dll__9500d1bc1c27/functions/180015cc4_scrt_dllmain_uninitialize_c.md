# __scrt_dllmain_uninitialize_c

- ea: `0x180015cc4`
- end: `0x180015cf4`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800158d8`

## callees

- `0x180015cc4`
- `0x1800164a8`
- `0x180016526`
- `0x18001654a`
- `0x1800190c0`

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
0x180015cc4  sub     rsp, 28h
0x180015cc8  call    __scrt_is_ucrt_dll_in_use
0x180015ccd  test    eax, eax
0x180015ccf  jz      short loc_180015CE1
0x180015cd1  lea     rcx, Table; Table
0x180015cd8  add     rsp, 28h
0x180015cdc  jmp     _execute_onexit_table
0x180015ce1  call    __scrt_stub_for_is_c_termination_complete
0x180015ce6  test    eax, eax
0x180015ce8  jnz     short loc_180015CEF
0x180015cea  call    _o__cexit_0
0x180015cef  add     rsp, 28h
0x180015cf3  retn
```
