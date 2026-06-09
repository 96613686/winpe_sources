# __scrt_dllmain_uninitialize_c

- ea: `0x180001f6c`
- end: `0x180001f9c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001a48`

## callees

- `0x180001f6c`
- `0x180002580`
- `0x18000263a`
- `0x18000265e`
- `0x180002d78`

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
0x180001f6c  sub     rsp, 28h
0x180001f70  call    __scrt_is_ucrt_dll_in_use
0x180001f75  test    eax, eax
0x180001f77  jz      short loc_180001F89
0x180001f79  lea     rcx, Table; Table
0x180001f80  add     rsp, 28h
0x180001f84  jmp     _execute_onexit_table
0x180001f89  call    __scrt_stub_for_is_c_termination_complete
0x180001f8e  test    eax, eax
0x180001f90  jnz     short loc_180001F97
0x180001f92  call    _o__cexit_0
0x180001f97  add     rsp, 28h
0x180001f9b  retn
```
