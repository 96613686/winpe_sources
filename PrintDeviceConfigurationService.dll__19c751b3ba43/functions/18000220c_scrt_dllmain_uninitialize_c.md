# __scrt_dllmain_uninitialize_c

- ea: `0x18000220c`
- end: `0x18000223c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001ea8`

## callees

- `0x18000220c`
- `0x180002978`
- `0x180002a82`
- `0x180002aa6`
- `0x18000c340`

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
0x18000220c  sub     rsp, 28h
0x180002210  call    __scrt_is_ucrt_dll_in_use
0x180002215  test    eax, eax
0x180002217  jz      short loc_180002229
0x180002219  lea     rcx, Table; Table
0x180002220  add     rsp, 28h
0x180002224  jmp     _execute_onexit_table
0x180002229  call    __scrt_stub_for_is_c_termination_complete
0x18000222e  test    eax, eax
0x180002230  jnz     short loc_180002237
0x180002232  call    _o__cexit_0
0x180002237  add     rsp, 28h
0x18000223b  retn
```
