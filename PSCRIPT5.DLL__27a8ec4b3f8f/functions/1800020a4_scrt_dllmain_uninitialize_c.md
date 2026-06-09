# __scrt_dllmain_uninitialize_c

- ea: `0x1800020a4`
- end: `0x1800020d4`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001d08`

## callees

- `0x1800020a4`
- `0x18000277c`
- `0x1800027ee`
- `0x180002812`
- `0x180002a28`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  int result; // eax

  if ( _scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = _scrt_stub_for_is_c_termination_complete();
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x1800020a4  sub     rsp, 28h
0x1800020a8  call    __scrt_is_ucrt_dll_in_use
0x1800020ad  test    eax, eax
0x1800020af  jz      short loc_1800020C1
0x1800020b1  lea     rcx, Table; Table
0x1800020b8  add     rsp, 28h
0x1800020bc  jmp     _execute_onexit_table
0x1800020c1  call    __scrt_stub_for_is_c_termination_complete
0x1800020c6  test    eax, eax
0x1800020c8  jnz     short loc_1800020CF
0x1800020ca  call    _o__cexit_0
0x1800020cf  add     rsp, 28h
0x1800020d3  retn
```
