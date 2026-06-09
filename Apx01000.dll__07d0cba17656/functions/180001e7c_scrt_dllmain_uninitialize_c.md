# __scrt_dllmain_uninitialize_c

- ea: `0x180001e7c`
- end: `0x180001eac`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001b18`

## callees

- `0x180001e7c`
- `0x180002628`
- `0x18000271e`
- `0x180002742`
- `0x1800261c0`

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
0x180001e7c  sub     rsp, 28h
0x180001e80  call    __scrt_is_ucrt_dll_in_use
0x180001e85  test    eax, eax
0x180001e87  jz      short loc_180001E99
0x180001e89  lea     rcx, Table; Table
0x180001e90  add     rsp, 28h
0x180001e94  jmp     _execute_onexit_table
0x180001e99  call    __scrt_stub_for_is_c_termination_complete
0x180001e9e  test    eax, eax
0x180001ea0  jnz     short loc_180001EA7
0x180001ea2  call    _o__cexit_0
0x180001ea7  add     rsp, 28h
0x180001eab  retn
```
