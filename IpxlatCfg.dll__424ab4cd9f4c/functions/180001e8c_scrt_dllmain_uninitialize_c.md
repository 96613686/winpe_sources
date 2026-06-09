# __scrt_dllmain_uninitialize_c

- ea: `0x180001e8c`
- end: `0x180001ebc`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001b28`

## callees

- `0x180001e8c`
- `0x1800028a8`
- `0x180002982`
- `0x1800029a6`
- `0x18000c1c0`

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
0x180001e8c  sub     rsp, 28h
0x180001e90  call    __scrt_is_ucrt_dll_in_use
0x180001e95  test    eax, eax
0x180001e97  jz      short loc_180001EA9
0x180001e99  lea     rcx, Table; Table
0x180001ea0  add     rsp, 28h
0x180001ea4  jmp     _execute_onexit_table
0x180001ea9  call    __scrt_stub_for_is_c_termination_complete
0x180001eae  test    eax, eax
0x180001eb0  jnz     short loc_180001EB7
0x180001eb2  call    _o__cexit_0
0x180001eb7  add     rsp, 28h
0x180001ebb  retn
```
