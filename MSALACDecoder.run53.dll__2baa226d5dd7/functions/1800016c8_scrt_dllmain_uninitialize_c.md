# __scrt_dllmain_uninitialize_c

- ea: `0x1800016c8`
- end: `0x1800016f8`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001338`

## callees

- `0x1800016c8`
- `0x180001db4`
- `0x180001e1a`
- `0x180001e3e`
- `0x1800035c0`

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
0x1800016c8  sub     rsp, 28h
0x1800016cc  call    __scrt_is_ucrt_dll_in_use
0x1800016d1  test    eax, eax
0x1800016d3  jz      short loc_1800016E5
0x1800016d5  lea     rcx, Table; Table
0x1800016dc  add     rsp, 28h
0x1800016e0  jmp     _execute_onexit_table
0x1800016e5  call    ?Release@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::Release(void)
0x1800016ea  test    eax, eax
0x1800016ec  jnz     short loc_1800016F3
0x1800016ee  call    _o__cexit_0
0x1800016f3  add     rsp, 28h
0x1800016f7  retn
```
