# __scrt_dllmain_uninitialize_c

- ea: `0x180005374`
- end: `0x1800053a4`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004ed8`

## callees

- `0x180005374`
- `0x180005b20`
- `0x180005bae`
- `0x180005bd2`
- `0x1800167d0`

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
0x180005374  sub     rsp, 28h
0x180005378  call    __scrt_is_ucrt_dll_in_use
0x18000537d  test    eax, eax
0x18000537f  jz      short loc_180005391
0x180005381  lea     rcx, Table; Table
0x180005388  add     rsp, 28h
0x18000538c  jmp     _execute_onexit_table
0x180005391  call    __scrt_stub_for_is_c_termination_complete
0x180005396  test    eax, eax
0x180005398  jnz     short loc_18000539F
0x18000539a  call    _o__cexit_0
0x18000539f  add     rsp, 28h
0x1800053a3  retn
```
