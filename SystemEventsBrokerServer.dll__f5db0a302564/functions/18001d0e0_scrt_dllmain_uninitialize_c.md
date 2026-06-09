# __scrt_dllmain_uninitialize_c

- ea: `0x18001d0e0`
- end: `0x18001d110`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001cd38`

## callees

- `0x18001d0e0`
- `0x18001d858`
- `0x18001d8ea`
- `0x18001d90e`
- `0x18001e120`

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
0x18001d0e0  sub     rsp, 28h
0x18001d0e4  call    __scrt_is_ucrt_dll_in_use
0x18001d0e9  test    eax, eax
0x18001d0eb  jz      short loc_18001D0FD
0x18001d0ed  lea     rcx, Table; Table
0x18001d0f4  add     rsp, 28h
0x18001d0f8  jmp     _execute_onexit_table
0x18001d0fd  call    __scrt_stub_for_is_c_termination_complete
0x18001d102  test    eax, eax
0x18001d104  jnz     short loc_18001D10B
0x18001d106  call    _o__cexit_0
0x18001d10b  add     rsp, 28h
0x18001d10f  retn
```
