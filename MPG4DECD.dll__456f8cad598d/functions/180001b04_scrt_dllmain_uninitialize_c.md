# __scrt_dllmain_uninitialize_c

- ea: `0x180001b04`
- end: `0x180001b34`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001698`

## callees

- `0x180001b04`
- `0x180002088`
- `0x1800020e2`
- `0x1800020fa`
- `0x180002c90`

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
0x180001b04  sub     rsp, 28h
0x180001b08  call    __scrt_is_ucrt_dll_in_use
0x180001b0d  test    eax, eax
0x180001b0f  jz      short loc_180001B21
0x180001b11  lea     rcx, Table; Table
0x180001b18  add     rsp, 28h
0x180001b1c  jmp     _execute_onexit_table
0x180001b21  call    ?decode@CVideoObject@@UEAAJXZ; CVideoObject::decode(void)
0x180001b26  test    eax, eax
0x180001b28  jnz     short loc_180001B2F
0x180001b2a  call    _o__cexit_0
0x180001b2f  add     rsp, 28h
0x180001b33  retn
```
