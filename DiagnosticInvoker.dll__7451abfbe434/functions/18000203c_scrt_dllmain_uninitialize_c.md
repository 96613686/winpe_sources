# __scrt_dllmain_uninitialize_c

- ea: `0x18000203c`
- end: `0x18000206c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001c08`

## callees

- `0x18000203c`
- `0x18000277c`
- `0x1800029fa`
- `0x180002a1e`
- `0x180002da4`

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
0x18000203c  sub     rsp, 28h
0x180002040  call    __scrt_is_ucrt_dll_in_use
0x180002045  test    eax, eax
0x180002047  jz      short loc_180002059
0x180002049  lea     rcx, Table; Table
0x180002050  add     rsp, 28h
0x180002054  jmp     _execute_onexit_table
0x180002059  call    __scrt_stub_for_is_c_termination_complete
0x18000205e  test    eax, eax
0x180002060  jnz     short loc_180002067
0x180002062  call    _o__cexit_0
0x180002067  add     rsp, 28h
0x18000206b  retn
```
