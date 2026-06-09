# __scrt_dllmain_uninitialize_c

- ea: `0x180001aac`
- end: `0x180001adc`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001748`

## callees

- `0x180001aac`
- `0x1800021c8`
- `0x180002266`
- `0x18000228a`
- `0x1800029f8`

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
0x180001aac  sub     rsp, 28h
0x180001ab0  call    __scrt_is_ucrt_dll_in_use
0x180001ab5  test    eax, eax
0x180001ab7  jz      short loc_180001AC9
0x180001ab9  lea     rcx, Table; Table
0x180001ac0  add     rsp, 28h
0x180001ac4  jmp     _execute_onexit_table
0x180001ac9  call    __scrt_stub_for_is_c_termination_complete
0x180001ace  test    eax, eax
0x180001ad0  jnz     short loc_180001AD7
0x180001ad2  call    _o__cexit_0
0x180001ad7  add     rsp, 28h
0x180001adb  retn
```
