# __scrt_dllmain_uninitialize_c

- ea: `0x180007418`
- end: `0x180007448`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `void()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007808`

## callees

- `0x180005f60`
- `0x180007418`
- `0x180007ec8`
- `0x18000b5e0`
- `0x18000b5ec`

## pseudocode

```c
void _scrt_dllmain_uninitialize_c()
{
  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    execute_onexit_table_0(&Table);
  }
  else if ( !(unsigned int)_scrt_stub_for_is_c_termination_complete() )
  {
    cexit_0();
  }
}

```

## disassembly

```asm
0x180007418  sub     rsp, 28h
0x18000741c  call    __scrt_is_ucrt_dll_in_use
0x180007421  test    eax, eax
0x180007423  jz      short loc_180007435
0x180007425  lea     rcx, Table; Table
0x18000742c  add     rsp, 28h
0x180007430  jmp     _execute_onexit_table_0
0x180007435  call    __scrt_stub_for_is_c_termination_complete
0x18000743a  test    eax, eax
0x18000743c  jnz     short loc_180007443
0x18000743e  call    _cexit_0
0x180007443  add     rsp, 28h
0x180007447  retn
```
