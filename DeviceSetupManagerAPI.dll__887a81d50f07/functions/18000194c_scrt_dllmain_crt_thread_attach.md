# __scrt_dllmain_crt_thread_attach

- ea: `0x18000194c`
- end: `0x180001974`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001450`

## callees

- `0x18000194c`
- `0x18000269c`

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
0x18000194c  sub     rsp, 28h
0x180001950  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001955  test    al, al
0x180001957  jnz     short loc_18000195D
0x180001959  xor     al, al
0x18000195b  jmp     short loc_18000196F
0x18000195d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001962  test    al, al
0x180001964  jnz     short loc_18000196D
0x180001966  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000196b  jmp     short loc_180001959
0x18000196d  mov     al, 1
0x18000196f  add     rsp, 28h
0x180001973  retn
```
