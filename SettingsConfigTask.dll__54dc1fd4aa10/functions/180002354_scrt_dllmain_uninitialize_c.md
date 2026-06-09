# __scrt_dllmain_uninitialize_c

- ea: `0x180002354`
- end: `0x180002384`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001fb8`

## callees

- `0x180002354`
- `0x180002a94`
- `0x180002b6e`
- `0x180002b92`
- `0x18000339c`

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
0x180002354  sub     rsp, 28h
0x180002358  call    __scrt_is_ucrt_dll_in_use
0x18000235d  test    eax, eax
0x18000235f  jz      short loc_180002371
0x180002361  lea     rcx, Table; Table
0x180002368  add     rsp, 28h
0x18000236c  jmp     _execute_onexit_table
0x180002371  call    __scrt_stub_for_is_c_termination_complete
0x180002376  test    eax, eax
0x180002378  jnz     short loc_18000237F
0x18000237a  call    _o__cexit_0
0x18000237f  add     rsp, 28h
0x180002383  retn
```
