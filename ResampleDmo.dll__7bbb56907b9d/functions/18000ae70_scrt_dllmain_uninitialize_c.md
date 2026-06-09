# __scrt_dllmain_uninitialize_c

- ea: `0x18000ae70`
- end: `0x18000aea0`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000a978`

## callees

- `0x18000ae70`
- `0x18000b5d0`
- `0x18000b686`
- `0x18000b6aa`
- `0x18006aec0`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  C1in1outDMO *v0; // rcx
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = C1in1outDMO::Discontinuity(v0);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x18000ae70  sub     rsp, 28h
0x18000ae74  call    __scrt_is_ucrt_dll_in_use
0x18000ae79  test    eax, eax
0x18000ae7b  jz      short loc_18000AE8D
0x18000ae7d  lea     rcx, Table; Table
0x18000ae84  add     rsp, 28h
0x18000ae88  jmp     _execute_onexit_table
0x18000ae8d  call    ?Discontinuity@C1in1outDMO@@MEAAJXZ; C1in1outDMO::Discontinuity(void)
0x18000ae92  test    eax, eax
0x18000ae94  jnz     short loc_18000AE9B
0x18000ae96  call    _o__cexit_0
0x18000ae9b  add     rsp, 28h
0x18000ae9f  retn
```
