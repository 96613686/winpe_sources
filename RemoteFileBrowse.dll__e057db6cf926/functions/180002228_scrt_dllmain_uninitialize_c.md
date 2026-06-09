# __scrt_dllmain_uninitialize_c

- ea: `0x180002228`
- end: `0x180002258`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001e18`

## callees

- `0x180002228`
- `0x180002c7c`
- `0x180002d0e`
- `0x180002d32`
- `0x1800070a0`

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
0x180002228  sub     rsp, 28h
0x18000222c  call    __scrt_is_ucrt_dll_in_use
0x180002231  test    eax, eax
0x180002233  jz      short loc_180002245
0x180002235  lea     rcx, Table; Table
0x18000223c  add     rsp, 28h
0x180002240  jmp     _execute_onexit_table
0x180002245  call    __scrt_stub_for_is_c_termination_complete
0x18000224a  test    eax, eax
0x18000224c  jnz     short loc_180002253
0x18000224e  call    _o__cexit_0
0x180002253  add     rsp, 28h
0x180002257  retn
```
