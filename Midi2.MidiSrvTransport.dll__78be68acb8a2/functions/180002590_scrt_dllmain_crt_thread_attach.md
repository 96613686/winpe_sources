# __scrt_dllmain_crt_thread_attach

- ea: `0x180002590`
- end: `0x1800025b8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800020f0`

## callees

- `0x180002590`
- `0x180003088`

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
0x180002590  sub     rsp, 28h
0x180002594  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002599  test    al, al
0x18000259b  jnz     short loc_1800025A1
0x18000259d  xor     al, al
0x18000259f  jmp     short loc_1800025B3
0x1800025a1  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800025a6  test    al, al
0x1800025a8  jnz     short loc_1800025B1
0x1800025aa  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800025af  jmp     short loc_18000259D
0x1800025b1  mov     al, 1
0x1800025b3  add     rsp, 28h
0x1800025b7  retn
```
