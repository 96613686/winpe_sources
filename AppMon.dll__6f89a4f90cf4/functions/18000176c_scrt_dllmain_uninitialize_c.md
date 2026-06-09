# __scrt_dllmain_uninitialize_c

- ea: `0x18000176c`
- end: `0x18000179c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001408`

## callees

- `0x18000176c`
- `0x180001e7c`
- `0x180001f12`
- `0x180001f36`
- `0x180009d40`

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
0x18000176c  sub     rsp, 28h
0x180001770  call    __scrt_is_ucrt_dll_in_use
0x180001775  test    eax, eax
0x180001777  jz      short loc_180001789
0x180001779  lea     rcx, Table; Table
0x180001780  add     rsp, 28h
0x180001784  jmp     _execute_onexit_table
0x180001789  call    __scrt_stub_for_is_c_termination_complete
0x18000178e  test    eax, eax
0x180001790  jnz     short loc_180001797
0x180001792  call    _o__cexit_0
0x180001797  add     rsp, 28h
0x18000179b  retn
```
