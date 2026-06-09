# __scrt_dllmain_uninitialize_c

- ea: `0x1800016d4`
- end: `0x180001704`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800011e8`

## callees

- `0x1800016d4`
- `0x180001cb4`
- `0x180001f6c`
- `0x180001f84`
- `0x180002008`

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
0x1800016d4  sub     rsp, 28h
0x1800016d8  call    __scrt_is_ucrt_dll_in_use
0x1800016dd  test    eax, eax
0x1800016df  jz      short loc_1800016F1
0x1800016e1  lea     rcx, Table; Table
0x1800016e8  add     rsp, 28h
0x1800016ec  jmp     _execute_onexit_table
0x1800016f1  call    __scrt_stub_for_is_c_termination_complete
0x1800016f6  test    eax, eax
0x1800016f8  jnz     short loc_1800016FF
0x1800016fa  call    _o__cexit_0
0x1800016ff  add     rsp, 28h
0x180001703  retn
```
