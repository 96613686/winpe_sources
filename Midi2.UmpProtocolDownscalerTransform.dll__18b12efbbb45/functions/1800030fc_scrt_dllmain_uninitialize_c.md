# __scrt_dllmain_uninitialize_c

- ea: `0x1800030fc`
- end: `0x18000312c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002c48`

## callees

- `0x1800030fc`
- `0x1800038d0`
- `0x18000395e`
- `0x180003982`
- `0x180006210`

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
0x1800030fc  sub     rsp, 28h
0x180003100  call    __scrt_is_ucrt_dll_in_use
0x180003105  test    eax, eax
0x180003107  jz      short loc_180003119
0x180003109  lea     rcx, Table; Table
0x180003110  add     rsp, 28h
0x180003114  jmp     _execute_onexit_table
0x180003119  call    ?Release@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::Release(void)
0x18000311e  test    eax, eax
0x180003120  jnz     short loc_180003127
0x180003122  call    _o__cexit_0
0x180003127  add     rsp, 28h
0x18000312b  retn
```
