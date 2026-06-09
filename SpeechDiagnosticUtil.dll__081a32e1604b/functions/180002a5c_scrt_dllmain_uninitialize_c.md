# __scrt_dllmain_uninitialize_c

- ea: `0x180002a5c`
- end: `0x180002a8c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800026f8`

## callees

- `0x180002a5c`
- `0x180003148`
- `0x1800031da`
- `0x1800031fe`
- `0x18000358c`

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
0x180002a5c  sub     rsp, 28h
0x180002a60  call    __scrt_is_ucrt_dll_in_use
0x180002a65  test    eax, eax
0x180002a67  jz      short loc_180002A79
0x180002a69  lea     rcx, Table; Table
0x180002a70  add     rsp, 28h
0x180002a74  jmp     _execute_onexit_table
0x180002a79  call    __scrt_stub_for_is_c_termination_complete
0x180002a7e  test    eax, eax
0x180002a80  jnz     short loc_180002A87
0x180002a82  call    _o__cexit_0
0x180002a87  add     rsp, 28h
0x180002a8b  retn
```
