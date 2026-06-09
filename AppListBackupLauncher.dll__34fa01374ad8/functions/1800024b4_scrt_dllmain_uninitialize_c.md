# __scrt_dllmain_uninitialize_c

- ea: `0x1800024b4`
- end: `0x1800024e4`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800020e8`

## callees

- `0x1800024b4`
- `0x180002c94`
- `0x180002d22`
- `0x180002d46`
- `0x180002edc`

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
0x1800024b4  sub     rsp, 28h
0x1800024b8  call    __scrt_is_ucrt_dll_in_use
0x1800024bd  test    eax, eax
0x1800024bf  jz      short loc_1800024D1
0x1800024c1  lea     rcx, Table; Table
0x1800024c8  add     rsp, 28h
0x1800024cc  jmp     _execute_onexit_table
0x1800024d1  call    __scrt_stub_for_is_c_termination_complete
0x1800024d6  test    eax, eax
0x1800024d8  jnz     short loc_1800024DF
0x1800024da  call    _o__cexit_0
0x1800024df  add     rsp, 28h
0x1800024e3  retn
```
