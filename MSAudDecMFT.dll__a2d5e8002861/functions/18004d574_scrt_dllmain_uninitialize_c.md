# __scrt_dllmain_uninitialize_c

- ea: `0x18004d574`
- end: `0x18004d5a4`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004d108`

## callees

- `0x18004d574`
- `0x18004db58`
- `0x18004dc0a`
- `0x18004dc2e`
- `0x1800556a0`

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
0x18004d574  sub     rsp, 28h
0x18004d578  call    __scrt_is_ucrt_dll_in_use
0x18004d57d  test    eax, eax
0x18004d57f  jz      short loc_18004D591
0x18004d581  lea     rcx, Table; Table
0x18004d588  add     rsp, 28h
0x18004d58c  jmp     _execute_onexit_table
0x18004d591  call    __scrt_stub_for_is_c_termination_complete
0x18004d596  test    eax, eax
0x18004d598  jnz     short loc_18004D59F
0x18004d59a  call    _o__cexit_0
0x18004d59f  add     rsp, 28h
0x18004d5a3  retn
```
