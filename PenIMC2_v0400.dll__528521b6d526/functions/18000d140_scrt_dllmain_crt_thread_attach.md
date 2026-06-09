# __scrt_dllmain_crt_thread_attach

- ea: `0x18000d140`
- end: `0x18000d168`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d730`

## callees

- `0x18000d140`
- `0x18000e318`

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
0x18000d140  sub     rsp, 28h
0x18000d144  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000d149  test    al, al
0x18000d14b  jnz     short loc_18000D151
0x18000d14d  xor     al, al
0x18000d14f  jmp     short loc_18000D163
0x18000d151  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000d156  test    al, al
0x18000d158  jnz     short loc_18000D161
0x18000d15a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000d15f  jmp     short loc_18000D14D
0x18000d161  mov     al, 1
0x18000d163  add     rsp, 28h
0x18000d167  retn
```
