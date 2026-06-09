# __scrt_dllmain_uninitialize_c

- ea: `0x180016be4`
- end: `0x180016c14`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016828`

## callees

- `0x180016be4`
- `0x1800172b0`
- `0x18001735e`
- `0x180017382`
- `0x180017a6c`

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
0x180016be4  sub     rsp, 28h
0x180016be8  call    __scrt_is_ucrt_dll_in_use
0x180016bed  test    eax, eax
0x180016bef  jz      short loc_180016C01
0x180016bf1  lea     rcx, Table; Table
0x180016bf8  add     rsp, 28h
0x180016bfc  jmp     _execute_onexit_table
0x180016c01  call    __scrt_stub_for_is_c_termination_complete
0x180016c06  test    eax, eax
0x180016c08  jnz     short loc_180016C0F
0x180016c0a  call    _o__cexit_0
0x180016c0f  add     rsp, 28h
0x180016c13  retn
```
