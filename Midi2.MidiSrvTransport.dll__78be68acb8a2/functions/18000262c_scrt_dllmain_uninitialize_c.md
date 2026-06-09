# __scrt_dllmain_uninitialize_c

- ea: `0x18000262c`
- end: `0x18000265c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002248`

## callees

- `0x18000262c`
- `0x180002ec0`
- `0x180002f4e`
- `0x180002f72`
- `0x1800056f0`

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
0x18000262c  sub     rsp, 28h
0x180002630  call    __scrt_is_ucrt_dll_in_use
0x180002635  test    eax, eax
0x180002637  jz      short loc_180002649
0x180002639  lea     rcx, Table; Table
0x180002640  add     rsp, 28h
0x180002644  jmp     _execute_onexit_table
0x180002649  call    ?Release@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::Release(void)
0x18000264e  test    eax, eax
0x180002650  jnz     short loc_180002657
0x180002652  call    _o__cexit_0
0x180002657  add     rsp, 28h
0x18000265b  retn
```
