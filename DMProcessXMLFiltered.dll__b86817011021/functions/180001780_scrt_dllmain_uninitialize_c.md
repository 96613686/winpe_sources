# __scrt_dllmain_uninitialize_c

- ea: `0x180001780`
- end: `0x1800017b0`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001308`

## callees

- `0x180001780`
- `0x180001d4c`
- `0x180001dd6`
- `0x180001dfa`
- `0x1800020a8`

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
0x180001780  sub     rsp, 28h
0x180001784  call    __scrt_is_ucrt_dll_in_use
0x180001789  test    eax, eax
0x18000178b  jz      short loc_18000179D
0x18000178d  lea     rcx, Table; Table
0x180001794  add     rsp, 28h
0x180001798  jmp     _execute_onexit_table
0x18000179d  call    __scrt_stub_for_is_c_termination_complete
0x1800017a2  test    eax, eax
0x1800017a4  jnz     short loc_1800017AB
0x1800017a6  call    _o__cexit_0
0x1800017ab  add     rsp, 28h
0x1800017af  retn
```
