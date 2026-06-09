# __scrt_dllmain_uninitialize_c

- ea: `0x180018368`
- end: `0x180018398`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `void()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018738`

## callees

- `0x180008670`
- `0x180018368`
- `0x180018ee8`
- `0x18001c5b5`
- `0x18001c5c1`

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
0x180018368  sub     rsp, 28h
0x18001836c  call    __scrt_is_ucrt_dll_in_use
0x180018371  test    eax, eax
0x180018373  jz      short loc_180018385
0x180018375  lea     rcx, Table; Table
0x18001837c  add     rsp, 28h
0x180018380  jmp     _execute_onexit_table_0
0x180018385  call    __scrt_stub_for_is_c_termination_complete
0x18001838a  test    eax, eax
0x18001838c  jnz     short loc_180018393
0x18001838e  call    _cexit_0
0x180018393  add     rsp, 28h
0x180018397  retn
```
