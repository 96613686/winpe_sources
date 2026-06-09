# __scrt_dllmain_uninitialize_c

- ea: `0x18001bf78`
- end: `0x18001bfa8`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001bbf8`

## callees

- `0x18001bf78`
- `0x18001c670`
- `0x18001c6fe`
- `0x18001c722`
- `0x18001cc08`

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
0x18001bf78  sub     rsp, 28h
0x18001bf7c  call    __scrt_is_ucrt_dll_in_use
0x18001bf81  test    eax, eax
0x18001bf83  jz      short loc_18001BF95
0x18001bf85  lea     rcx, Table; Table
0x18001bf8c  add     rsp, 28h
0x18001bf90  jmp     _execute_onexit_table
0x18001bf95  call    __scrt_stub_for_is_c_termination_complete
0x18001bf9a  test    eax, eax
0x18001bf9c  jnz     short loc_18001BFA3
0x18001bf9e  call    _o__cexit_0
0x18001bfa3  add     rsp, 28h
0x18001bfa7  retn
```
