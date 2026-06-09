# __scrt_dllmain_crt_thread_attach

- ea: `0x18000287c`
- end: `0x1800028a4`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002370`

## callees

- `0x18000287c`
- `0x18000369c`

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
0x18000287c  sub     rsp, 28h
0x180002880  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002885  test    al, al
0x180002887  jnz     short loc_18000288D
0x180002889  xor     al, al
0x18000288b  jmp     short loc_18000289F
0x18000288d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002892  test    al, al
0x180002894  jnz     short loc_18000289D
0x180002896  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000289b  jmp     short loc_180002889
0x18000289d  mov     al, 1
0x18000289f  add     rsp, 28h
0x1800028a3  retn
```
