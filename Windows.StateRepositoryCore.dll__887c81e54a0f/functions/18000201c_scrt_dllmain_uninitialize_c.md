# __scrt_dllmain_uninitialize_c

- ea: `0x18000201c`
- end: `0x18000204c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001cb8`

## callees

- `0x18000201c`
- `0x180002738`
- `0x1800027d2`
- `0x1800027f6`
- `0x180002c14`

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
0x18000201c  sub     rsp, 28h
0x180002020  call    __scrt_is_ucrt_dll_in_use
0x180002025  test    eax, eax
0x180002027  jz      short loc_180002039
0x180002029  lea     rcx, Table; Table
0x180002030  add     rsp, 28h
0x180002034  jmp     _execute_onexit_table
0x180002039  call    __scrt_stub_for_is_c_termination_complete
0x18000203e  test    eax, eax
0x180002040  jnz     short loc_180002047
0x180002042  call    _o__cexit_0
0x180002047  add     rsp, 28h
0x18000204b  retn
```
