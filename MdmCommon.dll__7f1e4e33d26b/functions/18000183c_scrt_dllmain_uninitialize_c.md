# __scrt_dllmain_uninitialize_c

- ea: `0x18000183c`
- end: `0x18000186c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001308`

## callees

- `0x18000183c`
- `0x180001e80`
- `0x180001f22`
- `0x180001f46`
- `0x180002690`

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
0x18000183c  sub     rsp, 28h
0x180001840  call    __scrt_is_ucrt_dll_in_use
0x180001845  test    eax, eax
0x180001847  jz      short loc_180001859
0x180001849  lea     rcx, Table; Table
0x180001850  add     rsp, 28h
0x180001854  jmp     _execute_onexit_table
0x180001859  call    __scrt_stub_for_is_c_termination_complete
0x18000185e  test    eax, eax
0x180001860  jnz     short loc_180001867
0x180001862  call    _o__cexit_0
0x180001867  add     rsp, 28h
0x18000186b  retn
```
