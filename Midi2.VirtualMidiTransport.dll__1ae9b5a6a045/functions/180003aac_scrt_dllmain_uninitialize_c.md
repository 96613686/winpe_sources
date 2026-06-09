# __scrt_dllmain_uninitialize_c

- ea: `0x180003aac`
- end: `0x180003adc`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800036c8`

## callees

- `0x180003aac`
- `0x180004550`
- `0x1800045de`
- `0x180004602`
- `0x180006ee0`

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
0x180003aac  sub     rsp, 28h
0x180003ab0  call    __scrt_is_ucrt_dll_in_use
0x180003ab5  test    eax, eax
0x180003ab7  jz      short loc_180003AC9
0x180003ab9  lea     rcx, Table; Table
0x180003ac0  add     rsp, 28h
0x180003ac4  jmp     _execute_onexit_table
0x180003ac9  call    ?Release@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::Release(void)
0x180003ace  test    eax, eax
0x180003ad0  jnz     short loc_180003AD7
0x180003ad2  call    _o__cexit_0
0x180003ad7  add     rsp, 28h
0x180003adb  retn
```
