# __scrt_dllmain_uninitialize_c

- ea: `0x180001a68`
- end: `0x180001a98`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800016d8`

## callees

- `0x180001a68`
- `0x180002154`
- `0x1800021ba`
- `0x1800021de`
- `0x18001c390`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  ATL::CRegObject *v0; // rcx
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = ATL::CRegObject::Release(v0);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180001a68  sub     rsp, 28h
0x180001a6c  call    __scrt_is_ucrt_dll_in_use
0x180001a71  test    eax, eax
0x180001a73  jz      short loc_180001A85
0x180001a75  lea     rcx, Table; Table
0x180001a7c  add     rsp, 28h
0x180001a80  jmp     _execute_onexit_table
0x180001a85  call    ?Release@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::Release(void)
0x180001a8a  test    eax, eax
0x180001a8c  jnz     short loc_180001A93
0x180001a8e  call    _o__cexit_0
0x180001a93  add     rsp, 28h
0x180001a97  retn
```
