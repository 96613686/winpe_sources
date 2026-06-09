# __scrt_dllmain_uninitialize_c

- ea: `0x180003ed4`
- end: `0x180003f04`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003a68`

## callees

- `0x180003ed4`
- `0x1800044b8`
- `0x18000452a`
- `0x18000454e`
- `0x1800058ec`

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
0x180003ed4  sub     rsp, 28h
0x180003ed8  call    __scrt_is_ucrt_dll_in_use
0x180003edd  test    eax, eax
0x180003edf  jz      short loc_180003EF1
0x180003ee1  lea     rcx, Table; Table
0x180003ee8  add     rsp, 28h
0x180003eec  jmp     _execute_onexit_table
0x180003ef1  call    __scrt_stub_for_is_c_termination_complete
0x180003ef6  test    eax, eax
0x180003ef8  jnz     short loc_180003EFF
0x180003efa  call    _o__cexit_0
0x180003eff  add     rsp, 28h
0x180003f03  retn
```
