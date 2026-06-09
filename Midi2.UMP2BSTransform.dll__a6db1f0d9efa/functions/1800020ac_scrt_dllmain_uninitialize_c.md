# __scrt_dllmain_uninitialize_c

- ea: `0x1800020ac`
- end: `0x1800020dc`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001cc8`

## callees

- `0x1800020ac`
- `0x180002824`
- `0x1800028ae`
- `0x1800028d2`
- `0x180005030`

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
0x1800020ac  sub     rsp, 28h
0x1800020b0  call    __scrt_is_ucrt_dll_in_use
0x1800020b5  test    eax, eax
0x1800020b7  jz      short loc_1800020C9
0x1800020b9  lea     rcx, Table; Table
0x1800020c0  add     rsp, 28h
0x1800020c4  jmp     _execute_onexit_table
0x1800020c9  call    ?Release@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::Release(void)
0x1800020ce  test    eax, eax
0x1800020d0  jnz     short loc_1800020D7
0x1800020d2  call    _o__cexit_0
0x1800020d7  add     rsp, 28h
0x1800020db  retn
```
