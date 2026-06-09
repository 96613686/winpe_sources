# __scrt_dllmain_uninitialize_c

- ea: `0x18000164c`
- end: `0x18000167c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001298`

## callees

- `0x18000164c`
- `0x180001f2c`
- `0x180001fe6`
- `0x18000200a`
- `0x180002144`

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
0x18000164c  sub     rsp, 28h
0x180001650  call    __scrt_is_ucrt_dll_in_use
0x180001655  test    eax, eax
0x180001657  jz      short loc_180001669
0x180001659  lea     rcx, Table; Table
0x180001660  add     rsp, 28h
0x180001664  jmp     _execute_onexit_table
0x180001669  call    __scrt_stub_for_is_c_termination_complete
0x18000166e  test    eax, eax
0x180001670  jnz     short loc_180001677
0x180001672  call    _o__cexit_0
0x180001677  add     rsp, 28h
0x18000167b  retn
```
