# __scrt_dllmain_uninitialize_c

- ea: `0x1800018c0`
- end: `0x1800018f0`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001508`

## callees

- `0x1800018c0`
- `0x180002190`
- `0x180002246`
- `0x18000226a`
- `0x180002550`

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
0x1800018c0  sub     rsp, 28h
0x1800018c4  call    __scrt_is_ucrt_dll_in_use
0x1800018c9  test    eax, eax
0x1800018cb  jz      short loc_1800018DD
0x1800018cd  lea     rcx, Table; Table
0x1800018d4  add     rsp, 28h
0x1800018d8  jmp     _execute_onexit_table
0x1800018dd  call    __scrt_stub_for_is_c_termination_complete
0x1800018e2  test    eax, eax
0x1800018e4  jnz     short loc_1800018EB
0x1800018e6  call    _o__cexit_0
0x1800018eb  add     rsp, 28h
0x1800018ef  retn
```
