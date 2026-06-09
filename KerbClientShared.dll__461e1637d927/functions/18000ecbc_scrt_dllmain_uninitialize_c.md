# __scrt_dllmain_uninitialize_c

- ea: `0x18000ecbc`
- end: `0x18000ecec`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e958`

## callees

- `0x18000ecbc`
- `0x18000f3f8`
- `0x18000f446`
- `0x18000f46a`
- `0x18000f92c`

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
0x18000ecbc  sub     rsp, 28h
0x18000ecc0  call    __scrt_is_ucrt_dll_in_use
0x18000ecc5  test    eax, eax
0x18000ecc7  jz      short loc_18000ECD9
0x18000ecc9  lea     rcx, Table; Table
0x18000ecd0  add     rsp, 28h
0x18000ecd4  jmp     _execute_onexit_table
0x18000ecd9  call    __scrt_stub_for_is_c_termination_complete
0x18000ecde  test    eax, eax
0x18000ece0  jnz     short loc_18000ECE7
0x18000ece2  call    _o__cexit_0
0x18000ece7  add     rsp, 28h
0x18000eceb  retn
```
