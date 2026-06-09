# __scrt_dllmain_uninitialize_c

- ea: `0x180002c20`
- end: `0x180002c50`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002878`

## callees

- `0x180002c20`
- `0x180003724`
- `0x1800037b2`
- `0x1800037d6`
- `0x180008aa0`

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
0x180002c20  sub     rsp, 28h
0x180002c24  call    __scrt_is_ucrt_dll_in_use
0x180002c29  test    eax, eax
0x180002c2b  jz      short loc_180002C3D
0x180002c2d  lea     rcx, Table; Table
0x180002c34  add     rsp, 28h
0x180002c38  jmp     _execute_onexit_table
0x180002c3d  call    __scrt_stub_for_is_c_termination_complete
0x180002c42  test    eax, eax
0x180002c44  jnz     short loc_180002C4B
0x180002c46  call    _o__cexit_0
0x180002c4b  add     rsp, 28h
0x180002c4f  retn
```
