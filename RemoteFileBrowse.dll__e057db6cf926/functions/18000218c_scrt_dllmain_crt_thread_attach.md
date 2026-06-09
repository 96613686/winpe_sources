# __scrt_dllmain_crt_thread_attach

- ea: `0x18000218c`
- end: `0x1800021b4`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001cc0`

## callees

- `0x18000218c`
- `0x180002ee8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000218c  sub     rsp, 28h
0x180002190  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002195  test    al, al
0x180002197  jnz     short loc_18000219D
0x180002199  xor     al, al
0x18000219b  jmp     short loc_1800021AF
0x18000219d  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800021a2  test    al, al
0x1800021a4  jnz     short loc_1800021AD
0x1800021a6  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800021ab  jmp     short loc_180002199
0x1800021ad  mov     al, 1
0x1800021af  add     rsp, 28h
0x1800021b3  retn
```
