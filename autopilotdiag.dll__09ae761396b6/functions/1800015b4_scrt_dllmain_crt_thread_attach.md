# __scrt_dllmain_crt_thread_attach

- ea: `0x1800015b4`
- end: `0x1800015dc`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001090`

## callees

- `0x1800015b4`
- `0x180001c60`

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
0x1800015b4  sub     rsp, 28h
0x1800015b8  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800015bd  test    al, al
0x1800015bf  jnz     short loc_1800015C5
0x1800015c1  xor     al, al
0x1800015c3  jmp     short loc_1800015D7
0x1800015c5  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800015ca  test    al, al
0x1800015cc  jnz     short loc_1800015D5
0x1800015ce  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800015d3  jmp     short loc_1800015C1
0x1800015d5  mov     al, 1
0x1800015d7  add     rsp, 28h
0x1800015db  retn
```
