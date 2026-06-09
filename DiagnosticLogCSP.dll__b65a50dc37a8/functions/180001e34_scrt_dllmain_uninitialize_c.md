# __scrt_dllmain_uninitialize_c

- ea: `0x180001e34`
- end: `0x180001e64`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001978`

## callees

- `0x180001e34`
- `0x180002484`
- `0x18000256a`
- `0x18000258e`
- `0x180002eac`

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
0x180001e34  sub     rsp, 28h
0x180001e38  call    __scrt_is_ucrt_dll_in_use
0x180001e3d  test    eax, eax
0x180001e3f  jz      short loc_180001E51
0x180001e41  lea     rcx, Table; Table
0x180001e48  add     rsp, 28h
0x180001e4c  jmp     _execute_onexit_table
0x180001e51  call    __scrt_stub_for_is_c_termination_complete
0x180001e56  test    eax, eax
0x180001e58  jnz     short loc_180001E5F
0x180001e5a  call    _o__cexit_0
0x180001e5f  add     rsp, 28h
0x180001e63  retn
```
