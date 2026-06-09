# __scrt_dllmain_uninitialize_c

- ea: `0x1800029f0`
- end: `0x180002a20`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002670`

## callees

- `0x1800029f0`
- `0x180003454`
- `0x18000353a`
- `0x18000355e`
- `0x180006fa0`

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
0x1800029f0  sub     rsp, 28h
0x1800029f4  call    __scrt_is_ucrt_dll_in_use
0x1800029f9  test    eax, eax
0x1800029fb  jz      short loc_180002A0D
0x1800029fd  lea     rcx, Table; Table
0x180002a04  add     rsp, 28h
0x180002a08  jmp     _execute_onexit_table
0x180002a0d  call    __scrt_stub_for_is_c_termination_complete
0x180002a12  test    eax, eax
0x180002a14  jnz     short loc_180002A1B
0x180002a16  call    _o__cexit_0
0x180002a1b  add     rsp, 28h
0x180002a1f  retn
```
