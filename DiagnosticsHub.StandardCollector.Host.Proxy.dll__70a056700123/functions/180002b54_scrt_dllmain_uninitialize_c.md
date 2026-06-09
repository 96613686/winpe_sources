# __scrt_dllmain_uninitialize_c

- ea: `0x180002b54`
- end: `0x180002b84`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002608`

## callees

- `0x180002b54`
- `0x1800035c4`
- `0x180003c8c`
- `0x180003ca8`
- `0x18000595c`

## pseudocode

```c
void _scrt_dllmain_uninitialize_c()
{
  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    execute_onexit_table(&Table);
  }
  else if ( !is_c_termination_complete() )
  {
    cexit();
  }
}

```

## disassembly

```asm
0x180002b54  sub     rsp, 28h
0x180002b58  call    __scrt_is_ucrt_dll_in_use
0x180002b5d  test    eax, eax
0x180002b5f  jz      short loc_180002B71
0x180002b61  lea     rcx, Table
0x180002b68  add     rsp, 28h
0x180002b6c  jmp     _execute_onexit_table
0x180002b71  call    _is_c_termination_complete
0x180002b76  test    eax, eax
0x180002b78  jnz     short loc_180002B7F
0x180002b7a  call    _cexit
0x180002b7f  add     rsp, 28h
0x180002b83  retn
```
