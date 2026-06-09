# __scrt_dllmain_uninitialize_c

- ea: `0x1800017f4`
- end: `0x180001824`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001448`

## callees

- `0x1800017f4`
- `0x180001f00`
- `0x180001f82`
- `0x180001fa6`
- `0x1800022b8`

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
0x1800017f4  sub     rsp, 28h
0x1800017f8  call    __scrt_is_ucrt_dll_in_use
0x1800017fd  test    eax, eax
0x1800017ff  jz      short loc_180001811
0x180001801  lea     rcx, Table; Table
0x180001808  add     rsp, 28h
0x18000180c  jmp     _execute_onexit_table
0x180001811  call    __scrt_stub_for_is_c_termination_complete
0x180001816  test    eax, eax
0x180001818  jnz     short loc_18000181F
0x18000181a  call    _o__cexit_0
0x18000181f  add     rsp, 28h
0x180001823  retn
```
