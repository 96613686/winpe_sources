# __scrt_dllmain_crt_thread_attach

- ea: `0x1800016e4`
- end: `0x18000170c`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800011b0`

## callees

- `0x1800016e4`
- `0x18000209c`

## pseudocode

```c
char _scrt_dllmain_crt_thread_attach()
{
  if ( !(unsigned __int8)_scrt_stub_for_acrt_uninitialize_critical() )
    return 0;
  if ( !(unsigned __int8)_scrt_stub_for_acrt_uninitialize_critical() )
  {
    _scrt_stub_for_acrt_uninitialize_critical();
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800016e4  sub     rsp, 28h
0x1800016e8  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016ed  test    al, al
0x1800016ef  jnz     short loc_1800016F5
0x1800016f1  xor     al, al
0x1800016f3  jmp     short loc_180001707
0x1800016f5  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016fa  test    al, al
0x1800016fc  jnz     short loc_180001705
0x1800016fe  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001703  jmp     short loc_1800016F1
0x180001705  mov     al, 1
0x180001707  add     rsp, 28h
0x18000170b  retn
```
