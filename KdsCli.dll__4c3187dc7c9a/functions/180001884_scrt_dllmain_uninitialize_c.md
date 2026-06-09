# __scrt_dllmain_uninitialize_c

- ea: `0x180001884`
- end: `0x1800018b4`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001418`

## callees

- `0x180001884`
- `0x180001e68`
- `0x180001ec2`
- `0x180001ee6`
- `0x18000287c`

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
0x180001884  sub     rsp, 28h
0x180001888  call    __scrt_is_ucrt_dll_in_use
0x18000188d  test    eax, eax
0x18000188f  jz      short loc_1800018A1
0x180001891  lea     rcx, Table; Table
0x180001898  add     rsp, 28h
0x18000189c  jmp     _execute_onexit_table
0x1800018a1  call    __scrt_stub_for_is_c_termination_complete
0x1800018a6  test    eax, eax
0x1800018a8  jnz     short loc_1800018AF
0x1800018aa  call    _o__cexit_0
0x1800018af  add     rsp, 28h
0x1800018b3  retn
```
