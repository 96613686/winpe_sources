# __scrt_dllmain_uninitialize_c

- ea: `0x18000440c`
- end: `0x18000443c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180003f58`

## callees

- `0x18000440c`
- `0x180004eb0`
- `0x180004f3e`
- `0x180004f62`
- `0x180007910`

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
0x18000440c  sub     rsp, 28h
0x180004410  call    __scrt_is_ucrt_dll_in_use
0x180004415  test    eax, eax
0x180004417  jz      short loc_180004429
0x180004419  lea     rcx, Table; Table
0x180004420  add     rsp, 28h
0x180004424  jmp     _execute_onexit_table
0x180004429  call    ?Release@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::Release(void)
0x18000442e  test    eax, eax
0x180004430  jnz     short loc_180004437
0x180004432  call    _o__cexit_0
0x180004437  add     rsp, 28h
0x18000443b  retn
```
