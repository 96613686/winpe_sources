# __scrt_dllmain_uninitialize_c

- ea: `0x18000177c`
- end: `0x1800017ac`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800012b8`

## callees

- `0x18000177c`
- `0x180001e94`
- `0x180001ed6`
- `0x180001edc`
- `0x180001ee8`

## pseudocode

```c
void _scrt_dllmain_uninitialize_c()
{
  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    execute_onexit_table_0(&Table);
  }
  else if ( !(unsigned int)_scrt_stub_for_is_c_termination_complete() )
  {
    cexit_0();
  }
}

```

## disassembly

```asm
0x18000177c  sub     rsp, 28h
0x180001780  call    __scrt_is_ucrt_dll_in_use
0x180001785  test    eax, eax
0x180001787  jz      short loc_180001799
0x180001789  lea     rcx, Table; Table
0x180001790  add     rsp, 28h
0x180001794  jmp     _execute_onexit_table_0
0x180001799  call    __scrt_stub_for_is_c_termination_complete
0x18000179e  test    eax, eax
0x1800017a0  jnz     short loc_1800017A7
0x1800017a2  call    _cexit_0
0x1800017a7  add     rsp, 28h
0x1800017ab  retn
```
