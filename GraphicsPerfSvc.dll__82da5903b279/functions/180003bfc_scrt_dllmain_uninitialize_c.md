# __scrt_dllmain_uninitialize_c

- ea: `0x180003bfc`
- end: `0x180003c2c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003898`

## callees

- `0x180003bfc`
- `0x18000464c`
- `0x18000473a`
- `0x18000475e`
- `0x18000d720`

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
0x180003bfc  sub     rsp, 28h
0x180003c00  call    __scrt_is_ucrt_dll_in_use
0x180003c05  test    eax, eax
0x180003c07  jz      short loc_180003C19
0x180003c09  lea     rcx, Table; Table
0x180003c10  add     rsp, 28h
0x180003c14  jmp     _execute_onexit_table
0x180003c19  call    __scrt_stub_for_is_c_termination_complete
0x180003c1e  test    eax, eax
0x180003c20  jnz     short loc_180003C27
0x180003c22  call    _o__cexit_0
0x180003c27  add     rsp, 28h
0x180003c2b  retn
```
