# __scrt_dllmain_uninitialize_c

- ea: `0x180001ae8`
- end: `0x180001b18`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001648`

## callees

- `0x180001ae8`
- `0x180002258`
- `0x18000233a`
- `0x18000235e`
- `0x1800046b0`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  void *v0; // rdx
  WMIDPREQUESTCODE v1; // ecx
  ULONG *v2; // r8
  void *v3; // r9
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = _scrt_stub_for_is_c_termination_complete(v1, v0, v2, v3);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180001ae8  sub     rsp, 28h
0x180001aec  call    __scrt_is_ucrt_dll_in_use
0x180001af1  test    eax, eax
0x180001af3  jz      short loc_180001B05
0x180001af5  lea     rcx, Table; Table
0x180001afc  add     rsp, 28h
0x180001b00  jmp     _execute_onexit_table
0x180001b05  call    __scrt_stub_for_is_c_termination_complete
0x180001b0a  test    eax, eax
0x180001b0c  jnz     short loc_180001B13
0x180001b0e  call    _o__cexit_0
0x180001b13  add     rsp, 28h
0x180001b17  retn
```
