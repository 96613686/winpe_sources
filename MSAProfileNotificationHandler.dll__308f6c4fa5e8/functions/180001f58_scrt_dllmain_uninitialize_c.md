# __scrt_dllmain_uninitialize_c

- ea: `0x180001f58`
- end: `0x180001f88`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001a98`

## callees

- `0x180001f58`
- `0x180002594`
- `0x180002848`
- `0x18000286c`
- `0x180002968`

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
0x180001f58  sub     rsp, 28h
0x180001f5c  call    __scrt_is_ucrt_dll_in_use
0x180001f61  test    eax, eax
0x180001f63  jz      short loc_180001F75
0x180001f65  lea     rcx, Table; Table
0x180001f6c  add     rsp, 28h
0x180001f70  jmp     _execute_onexit_table
0x180001f75  call    __scrt_stub_for_is_c_termination_complete
0x180001f7a  test    eax, eax
0x180001f7c  jnz     short loc_180001F83
0x180001f7e  call    _o__cexit_0
0x180001f83  add     rsp, 28h
0x180001f87  retn
```
