# __scrt_dllmain_uninitialize_c

- ea: `0x180003c90`
- end: `0x180003cc0`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800040fc`

## callees

- `0x180003c90`
- `0x180004670`
- `0x180004996`
- `0x1800049a2`
- `0x1800049c0`

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
0x180003c90  sub     rsp, 28h
0x180003c94  call    __scrt_is_ucrt_dll_in_use
0x180003c99  test    eax, eax
0x180003c9b  jz      short loc_180003CAD
0x180003c9d  lea     rcx, Table; Table
0x180003ca4  add     rsp, 28h
0x180003ca8  jmp     _execute_onexit_table_0
0x180003cad  call    __scrt_stub_for_is_c_termination_complete
0x180003cb2  test    eax, eax
0x180003cb4  jnz     short loc_180003CBB
0x180003cb6  call    _cexit_0
0x180003cbb  add     rsp, 28h
0x180003cbf  retn
```
