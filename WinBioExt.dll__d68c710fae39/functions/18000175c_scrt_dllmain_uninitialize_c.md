# __scrt_dllmain_uninitialize_c

- ea: `0x18000175c`
- end: `0x18000178c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800013f8`

## callees

- `0x18000175c`
- `0x180001ea8`
- `0x180001fd2`
- `0x180001ff6`
- `0x1800023c8`

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
0x18000175c  sub     rsp, 28h
0x180001760  call    __scrt_is_ucrt_dll_in_use
0x180001765  test    eax, eax
0x180001767  jz      short loc_180001779
0x180001769  lea     rcx, Table; Table
0x180001770  add     rsp, 28h
0x180001774  jmp     _execute_onexit_table
0x180001779  call    __scrt_stub_for_is_c_termination_complete
0x18000177e  test    eax, eax
0x180001780  jnz     short loc_180001787
0x180001782  call    _o__cexit_0
0x180001787  add     rsp, 28h
0x18000178b  retn
```
