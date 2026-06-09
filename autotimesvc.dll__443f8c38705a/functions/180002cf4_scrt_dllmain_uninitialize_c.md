# __scrt_dllmain_uninitialize_c

- ea: `0x180002cf4`
- end: `0x180002d24`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002858`

## callees

- `0x180002cf4`
- `0x1800034f8`
- `0x18000358e`
- `0x1800035b2`
- `0x18000fa90`

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
0x180002cf4  sub     rsp, 28h
0x180002cf8  call    __scrt_is_ucrt_dll_in_use
0x180002cfd  test    eax, eax
0x180002cff  jz      short loc_180002D11
0x180002d01  lea     rcx, Table; Table
0x180002d08  add     rsp, 28h
0x180002d0c  jmp     _execute_onexit_table
0x180002d11  call    __scrt_stub_for_is_c_termination_complete
0x180002d16  test    eax, eax
0x180002d18  jnz     short loc_180002D1F
0x180002d1a  call    _o__cexit_0
0x180002d1f  add     rsp, 28h
0x180002d23  retn
```
