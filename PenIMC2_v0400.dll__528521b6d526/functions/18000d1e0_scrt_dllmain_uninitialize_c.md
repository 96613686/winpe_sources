# __scrt_dllmain_uninitialize_c

- ea: `0x18000d1e0`
- end: `0x18000d210`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000d898`

## callees

- `0x180001a90`
- `0x18000d1e0`
- `0x18000dc34`
- `0x18000e114`
- `0x18000e120`

## pseudocode

```c
void _scrt_dllmain_uninitialize_c()
{
  ATL::CRegObject *v0; // rcx

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    execute_onexit_table_0(&Table);
  }
  else if ( !ATL::CRegObject::Release(v0) )
  {
    cexit_0();
  }
}

```

## disassembly

```asm
0x18000d1e0  sub     rsp, 28h
0x18000d1e4  call    __scrt_is_ucrt_dll_in_use
0x18000d1e9  test    eax, eax
0x18000d1eb  jz      short loc_18000D1FD
0x18000d1ed  lea     rcx, Table; Table
0x18000d1f4  add     rsp, 28h
0x18000d1f8  jmp     _execute_onexit_table_0
0x18000d1fd  call    ?Release@CRegObject@ATL@@UEAAKXZ
0x18000d202  test    eax, eax
0x18000d204  jnz     short loc_18000D20B
0x18000d206  call    _cexit_0
0x18000d20b  add     rsp, 28h
0x18000d20f  retn
```
