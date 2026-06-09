# __scrt_dllmain_uninitialize_c

- ea: `0x180001938`
- end: `0x180001968`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800014f8`

## callees

- `0x180001938`
- `0x18000207c`
- `0x18000211a`
- `0x18000213e`
- `0x18000aff0`

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
0x180001938  sub     rsp, 28h
0x18000193c  call    __scrt_is_ucrt_dll_in_use
0x180001941  test    eax, eax
0x180001943  jz      short loc_180001955
0x180001945  lea     rcx, Table; Table
0x18000194c  add     rsp, 28h
0x180001950  jmp     _execute_onexit_table
0x180001955  call    ?Release@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::Release(void)
0x18000195a  test    eax, eax
0x18000195c  jnz     short loc_180001963
0x18000195e  call    _o__cexit_0
0x180001963  add     rsp, 28h
0x180001967  retn
```
