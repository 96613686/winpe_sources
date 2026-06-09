# __scrt_dllmain_crt_thread_attach

- ea: `0x180003740`
- end: `0x180003768`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003060`

## callees

- `0x180003740`
- `0x180005ee0`

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
0x180003740  sub     rsp, 28h
0x180003744  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003749  test    al, al
0x18000374b  jnz     short loc_180003751
0x18000374d  xor     al, al
0x18000374f  jmp     short loc_180003763
0x180003751  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003756  test    al, al
0x180003758  jnz     short loc_180003761
0x18000375a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000375f  jmp     short loc_18000374D
0x180003761  mov     al, 1
0x180003763  add     rsp, 28h
0x180003767  retn
```
