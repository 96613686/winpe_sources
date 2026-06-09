# __scrt_dllmain_uninitialize_c

- ea: `0x1800021b0`
- end: `0x1800021e0`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001e08`

## callees

- `0x1800021b0`
- `0x180002a18`
- `0x180002aa2`
- `0x180002ac6`
- `0x18000cfe0`

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
0x1800021b0  sub     rsp, 28h
0x1800021b4  call    __scrt_is_ucrt_dll_in_use
0x1800021b9  test    eax, eax
0x1800021bb  jz      short loc_1800021CD
0x1800021bd  lea     rcx, Table; Table
0x1800021c4  add     rsp, 28h
0x1800021c8  jmp     _execute_onexit_table
0x1800021cd  call    __scrt_stub_for_is_c_termination_complete
0x1800021d2  test    eax, eax
0x1800021d4  jnz     short loc_1800021DB
0x1800021d6  call    _o__cexit_0
0x1800021db  add     rsp, 28h
0x1800021df  retn
```
