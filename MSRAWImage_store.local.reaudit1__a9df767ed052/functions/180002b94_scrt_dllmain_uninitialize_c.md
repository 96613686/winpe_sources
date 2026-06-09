# __scrt_dllmain_uninitialize_c

- ea: `0x180002b94`
- end: `0x180002bc4`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800027f0`

## callees

- `0x180002b94`
- `0x180003330`
- `0x180005c97`
- `0x180005caf`
- `0x18009539c`

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
0x180002b94  sub     rsp, 28h
0x180002b98  call    __scrt_is_ucrt_dll_in_use
0x180002b9d  test    eax, eax
0x180002b9f  jz      short loc_180002BB1
0x180002ba1  lea     rcx, Table; Table
0x180002ba8  add     rsp, 28h
0x180002bac  jmp     _execute_onexit_table_0
0x180002bb1  call    __scrt_stub_for_is_c_termination_complete
0x180002bb6  test    eax, eax
0x180002bb8  jnz     short loc_180002BBF
0x180002bba  call    _cexit_0
0x180002bbf  add     rsp, 28h
0x180002bc3  retn
```
