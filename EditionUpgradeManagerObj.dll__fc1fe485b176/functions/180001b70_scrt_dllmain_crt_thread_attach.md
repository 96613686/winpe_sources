# __scrt_dllmain_crt_thread_attach

- ea: `0x180001b70`
- end: `0x180001b98`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001750`

## callees

- `0x180001b70`
- `0x180002830`

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
0x180001b70  sub     rsp, 28h
0x180001b74  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001b79  test    al, al
0x180001b7b  jnz     short loc_180001B81
0x180001b7d  xor     al, al
0x180001b7f  jmp     short loc_180001B93
0x180001b81  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001b86  test    al, al
0x180001b88  jnz     short loc_180001B91
0x180001b8a  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001b8f  jmp     short loc_180001B7D
0x180001b91  mov     al, 1
0x180001b93  add     rsp, 28h
0x180001b97  retn
```
