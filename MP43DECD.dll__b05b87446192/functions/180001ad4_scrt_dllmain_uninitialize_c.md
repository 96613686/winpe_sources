# __scrt_dllmain_uninitialize_c

- ea: `0x180001ad4`
- end: `0x180001b04`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001668`

## callees

- `0x180001ad4`
- `0x180002058`
- `0x1800020b2`
- `0x1800020ca`
- `0x180002bd0`

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
0x180001ad4  sub     rsp, 28h
0x180001ad8  call    __scrt_is_ucrt_dll_in_use
0x180001add  test    eax, eax
0x180001adf  jz      short loc_180001AF1
0x180001ae1  lea     rcx, Table; Table
0x180001ae8  add     rsp, 28h
0x180001aec  jmp     _execute_onexit_table
0x180001af1  call    ?decode@CVideoObject@@UEAAJXZ; CVideoObject::decode(void)
0x180001af6  test    eax, eax
0x180001af8  jnz     short loc_180001AFF
0x180001afa  call    _o__cexit_0
0x180001aff  add     rsp, 28h
0x180001b03  retn
```
