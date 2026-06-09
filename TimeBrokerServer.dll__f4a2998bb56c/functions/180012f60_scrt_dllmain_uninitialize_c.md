# __scrt_dllmain_uninitialize_c

- ea: `0x180012f60`
- end: `0x180012f90`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012bb8`

## callees

- `0x180012f60`
- `0x180013818`
- `0x1800138b2`
- `0x1800138d6`
- `0x1800146d0`

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
0x180012f60  sub     rsp, 28h
0x180012f64  call    __scrt_is_ucrt_dll_in_use
0x180012f69  test    eax, eax
0x180012f6b  jz      short loc_180012F7D
0x180012f6d  lea     rcx, Table; Table
0x180012f74  add     rsp, 28h
0x180012f78  jmp     _execute_onexit_table
0x180012f7d  call    __scrt_stub_for_is_c_termination_complete
0x180012f82  test    eax, eax
0x180012f84  jnz     short loc_180012F8B
0x180012f86  call    _o__cexit_0
0x180012f8b  add     rsp, 28h
0x180012f8f  retn
```
