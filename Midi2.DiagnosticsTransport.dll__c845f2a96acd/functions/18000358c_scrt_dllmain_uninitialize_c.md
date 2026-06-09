# __scrt_dllmain_uninitialize_c

- ea: `0x18000358c`
- end: `0x1800035bc`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800031a8`

## callees

- `0x18000358c`
- `0x180004018`
- `0x1800040ae`
- `0x1800040d2`
- `0x180006850`

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
0x18000358c  sub     rsp, 28h
0x180003590  call    __scrt_is_ucrt_dll_in_use
0x180003595  test    eax, eax
0x180003597  jz      short loc_1800035A9
0x180003599  lea     rcx, Table; Table
0x1800035a0  add     rsp, 28h
0x1800035a4  jmp     _execute_onexit_table
0x1800035a9  call    ?Release@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::Release(void)
0x1800035ae  test    eax, eax
0x1800035b0  jnz     short loc_1800035B7
0x1800035b2  call    _o__cexit_0
0x1800035b7  add     rsp, 28h
0x1800035bb  retn
```
