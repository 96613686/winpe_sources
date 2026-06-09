# __scrt_dllmain_uninitialize_c

- ea: `0x18000286c`
- end: `0x18000289c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002438`

## callees

- `0x18000286c`
- `0x18000310c`
- `0x1800031f2`
- `0x180003216`
- `0x180003450`

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
0x18000286c  sub     rsp, 28h
0x180002870  call    __scrt_is_ucrt_dll_in_use
0x180002875  test    eax, eax
0x180002877  jz      short loc_180002889
0x180002879  lea     rcx, Table; Table
0x180002880  add     rsp, 28h
0x180002884  jmp     _execute_onexit_table
0x180002889  call    __scrt_stub_for_is_c_termination_complete
0x18000288e  test    eax, eax
0x180002890  jnz     short loc_180002897
0x180002892  call    _o__cexit_0
0x180002897  add     rsp, 28h
0x18000289b  retn
```
