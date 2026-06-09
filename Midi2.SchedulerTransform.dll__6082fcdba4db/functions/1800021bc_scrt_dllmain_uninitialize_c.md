# __scrt_dllmain_uninitialize_c

- ea: `0x1800021bc`
- end: `0x1800021ec`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001dd8`

## callees

- `0x1800021bc`
- `0x180002934`
- `0x1800029be`
- `0x1800029e2`
- `0x180005140`

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
0x1800021bc  sub     rsp, 28h
0x1800021c0  call    __scrt_is_ucrt_dll_in_use
0x1800021c5  test    eax, eax
0x1800021c7  jz      short loc_1800021D9
0x1800021c9  lea     rcx, Table; Table
0x1800021d0  add     rsp, 28h
0x1800021d4  jmp     _execute_onexit_table
0x1800021d9  call    ?Release@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::Release(void)
0x1800021de  test    eax, eax
0x1800021e0  jnz     short loc_1800021E7
0x1800021e2  call    _o__cexit_0
0x1800021e7  add     rsp, 28h
0x1800021eb  retn
```
