# __scrt_dllmain_uninitialize_c

- ea: `0x180001a2c`
- end: `0x180001a5c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800016c8`

## callees

- `0x180001a2c`
- `0x180002198`
- `0x18000242a`
- `0x18000244e`
- `0x18000b480`

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
0x180001a2c  sub     rsp, 28h
0x180001a30  call    __scrt_is_ucrt_dll_in_use
0x180001a35  test    eax, eax
0x180001a37  jz      short loc_180001A49
0x180001a39  lea     rcx, Table; Table
0x180001a40  add     rsp, 28h
0x180001a44  jmp     _execute_onexit_table
0x180001a49  call    __scrt_stub_for_is_c_termination_complete
0x180001a4e  test    eax, eax
0x180001a50  jnz     short loc_180001A57
0x180001a52  call    _o__cexit_0
0x180001a57  add     rsp, 28h
0x180001a5b  retn
```
