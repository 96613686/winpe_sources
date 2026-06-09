# __scrt_dllmain_uninitialize_c

- ea: `0x180002064`
- end: `0x180002094`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001cc8`

## callees

- `0x180002064`
- `0x180002730`
- `0x18000278e`
- `0x1800027b2`
- `0x180021eb0`

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
0x180002064  sub     rsp, 28h
0x180002068  call    __scrt_is_ucrt_dll_in_use
0x18000206d  test    eax, eax
0x18000206f  jz      short loc_180002081
0x180002071  lea     rcx, Table; Table
0x180002078  add     rsp, 28h
0x18000207c  jmp     _execute_onexit_table
0x180002081  call    __scrt_stub_for_is_c_termination_complete
0x180002086  test    eax, eax
0x180002088  jnz     short loc_18000208F
0x18000208a  call    _o__cexit_0
0x18000208f  add     rsp, 28h
0x180002093  retn
```
