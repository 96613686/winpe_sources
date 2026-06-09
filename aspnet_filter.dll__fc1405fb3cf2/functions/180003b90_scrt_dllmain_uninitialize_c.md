# __scrt_dllmain_uninitialize_c

- ea: `0x180003b90`
- end: `0x180003bc0`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800033f8`

## callees

- `0x180003b90`
- `0x1800042e4`
- `0x180004350`
- `0x18000435c`
- `0x180004394`

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
0x180003b90  sub     rsp, 28h
0x180003b94  call    __scrt_is_ucrt_dll_in_use
0x180003b99  test    eax, eax
0x180003b9b  jz      short loc_180003BAD
0x180003b9d  lea     rcx, Table; Table
0x180003ba4  add     rsp, 28h
0x180003ba8  jmp     _execute_onexit_table_0
0x180003bad  call    __scrt_stub_for_is_c_termination_complete
0x180003bb2  test    eax, eax
0x180003bb4  jnz     short loc_180003BBB
0x180003bb6  call    _cexit_0
0x180003bbb  add     rsp, 28h
0x180003bbf  retn
```
