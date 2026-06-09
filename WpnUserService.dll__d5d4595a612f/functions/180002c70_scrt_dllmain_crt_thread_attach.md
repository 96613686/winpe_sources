# __scrt_dllmain_crt_thread_attach

- ea: `0x180002c70`
- end: `0x180002c98`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002850`

## callees

- `0x180002c70`
- `0x1800037ec`

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
0x180002c70  sub     rsp, 28h
0x180002c74  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002c79  test    al, al
0x180002c7b  jnz     short loc_180002C81
0x180002c7d  xor     al, al
0x180002c7f  jmp     short loc_180002C93
0x180002c81  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002c86  test    al, al
0x180002c88  jnz     short loc_180002C91
0x180002c8a  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002c8f  jmp     short loc_180002C7D
0x180002c91  mov     al, 1
0x180002c93  add     rsp, 28h
0x180002c97  retn
```
