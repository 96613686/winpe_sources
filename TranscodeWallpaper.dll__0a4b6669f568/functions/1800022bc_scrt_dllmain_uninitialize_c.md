# __scrt_dllmain_uninitialize_c

- ea: `0x1800022bc`
- end: `0x1800022ec`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001f58`

## callees

- `0x1800022bc`
- `0x180002a68`
- `0x180002c02`
- `0x180002c26`
- `0x18000c7b0`

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
0x1800022bc  sub     rsp, 28h
0x1800022c0  call    __scrt_is_ucrt_dll_in_use
0x1800022c5  test    eax, eax
0x1800022c7  jz      short loc_1800022D9
0x1800022c9  lea     rcx, Table; Table
0x1800022d0  add     rsp, 28h
0x1800022d4  jmp     _execute_onexit_table
0x1800022d9  call    __scrt_stub_for_is_c_termination_complete
0x1800022de  test    eax, eax
0x1800022e0  jnz     short loc_1800022E7
0x1800022e2  call    _o__cexit_0
0x1800022e7  add     rsp, 28h
0x1800022eb  retn
```
