# __scrt_dllmain_uninitialize_c

- ea: `0x180001dcc`
- end: `0x180001dfc`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001a58`

## callees

- `0x180001dcc`
- `0x180002670`
- `0x18000275a`
- `0x18000277e`
- `0x180002eb8`

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
0x180001dcc  sub     rsp, 28h
0x180001dd0  call    __scrt_is_ucrt_dll_in_use
0x180001dd5  test    eax, eax
0x180001dd7  jz      short loc_180001DE9
0x180001dd9  lea     rcx, Table; Table
0x180001de0  add     rsp, 28h
0x180001de4  jmp     _execute_onexit_table
0x180001de9  call    __scrt_stub_for_is_c_termination_complete
0x180001dee  test    eax, eax
0x180001df0  jnz     short loc_180001DF7
0x180001df2  call    _o__cexit_0
0x180001df7  add     rsp, 28h
0x180001dfb  retn
```
