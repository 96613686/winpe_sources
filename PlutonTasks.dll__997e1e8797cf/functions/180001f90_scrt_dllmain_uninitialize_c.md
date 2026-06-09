# __scrt_dllmain_uninitialize_c

- ea: `0x180001f90`
- end: `0x180001fc0`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001be8`

## callees

- `0x180001f90`
- `0x180002720`
- `0x1800027b2`
- `0x1800027d6`
- `0x1800028d0`

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
0x180001f90  sub     rsp, 28h
0x180001f94  call    __scrt_is_ucrt_dll_in_use
0x180001f99  test    eax, eax
0x180001f9b  jz      short loc_180001FAD
0x180001f9d  lea     rcx, Table; Table
0x180001fa4  add     rsp, 28h
0x180001fa8  jmp     _execute_onexit_table
0x180001fad  call    __scrt_stub_for_is_c_termination_complete
0x180001fb2  test    eax, eax
0x180001fb4  jnz     short loc_180001FBB
0x180001fb6  call    _o__cexit_0
0x180001fbb  add     rsp, 28h
0x180001fbf  retn
```
