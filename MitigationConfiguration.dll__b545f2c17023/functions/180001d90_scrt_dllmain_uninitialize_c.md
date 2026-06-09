# __scrt_dllmain_uninitialize_c

- ea: `0x180001d90`
- end: `0x180001dc0`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800019e8`

## callees

- `0x180001d90`
- `0x1800024f4`
- `0x1800025a2`
- `0x1800025c6`
- `0x180010ce0`

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
0x180001d90  sub     rsp, 28h
0x180001d94  call    __scrt_is_ucrt_dll_in_use
0x180001d99  test    eax, eax
0x180001d9b  jz      short loc_180001DAD
0x180001d9d  lea     rcx, Table; Table
0x180001da4  add     rsp, 28h
0x180001da8  jmp     _execute_onexit_table
0x180001dad  call    __scrt_stub_for_is_c_termination_complete
0x180001db2  test    eax, eax
0x180001db4  jnz     short loc_180001DBB
0x180001db6  call    _o__cexit_0
0x180001dbb  add     rsp, 28h
0x180001dbf  retn
```
