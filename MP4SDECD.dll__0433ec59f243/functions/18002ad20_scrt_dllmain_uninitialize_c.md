# __scrt_dllmain_uninitialize_c

- ea: `0x18002ad20`
- end: `0x18002ad50`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18002a8a8`

## callees

- `0x18002ad20`
- `0x18002b298`
- `0x18002b2f2`
- `0x18002b30a`
- `0x18002ba70`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  CVideoObject *v0; // rcx
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = CVideoObject::decode(v0);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x18002ad20  sub     rsp, 28h
0x18002ad24  call    __scrt_is_ucrt_dll_in_use
0x18002ad29  test    eax, eax
0x18002ad2b  jz      short loc_18002AD3D
0x18002ad2d  lea     rcx, Table; Table
0x18002ad34  add     rsp, 28h
0x18002ad38  jmp     _execute_onexit_table
0x18002ad3d  call    ?decode@CVideoObject@@UEAAJXZ; CVideoObject::decode(void)
0x18002ad42  test    eax, eax
0x18002ad44  jnz     short loc_18002AD4B
0x18002ad46  call    _o__cexit_0
0x18002ad4b  add     rsp, 28h
0x18002ad4f  retn
```
