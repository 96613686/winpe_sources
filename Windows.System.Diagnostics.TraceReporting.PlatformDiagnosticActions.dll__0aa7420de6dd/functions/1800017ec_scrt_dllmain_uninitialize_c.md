# __scrt_dllmain_uninitialize_c

- ea: `0x1800017ec`
- end: `0x18000181c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001488`

## callees

- `0x1800017ec`
- `0x180001f08`
- `0x180001fb2`
- `0x180001fd6`
- `0x1800084d0`

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
0x1800017ec  sub     rsp, 28h
0x1800017f0  call    __scrt_is_ucrt_dll_in_use
0x1800017f5  test    eax, eax
0x1800017f7  jz      short loc_180001809
0x1800017f9  lea     rcx, Table; Table
0x180001800  add     rsp, 28h
0x180001804  jmp     _execute_onexit_table
0x180001809  call    __scrt_stub_for_is_c_termination_complete
0x18000180e  test    eax, eax
0x180001810  jnz     short loc_180001817
0x180001812  call    _o__cexit_0
0x180001817  add     rsp, 28h
0x18000181b  retn
```
