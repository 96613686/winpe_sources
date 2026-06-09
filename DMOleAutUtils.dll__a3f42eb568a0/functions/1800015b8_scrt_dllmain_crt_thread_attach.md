# __scrt_dllmain_crt_thread_attach

- ea: `0x1800015b8`
- end: `0x1800015e0`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001090`

## callees

- `0x1800015b8`
- `0x180001f74`

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
0x1800015b8  sub     rsp, 28h
0x1800015bc  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800015c1  test    al, al
0x1800015c3  jnz     short loc_1800015C9
0x1800015c5  xor     al, al
0x1800015c7  jmp     short loc_1800015DB
0x1800015c9  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800015ce  test    al, al
0x1800015d0  jnz     short loc_1800015D9
0x1800015d2  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800015d7  jmp     short loc_1800015C5
0x1800015d9  mov     al, 1
0x1800015db  add     rsp, 28h
0x1800015df  retn
```
