# __scrt_dllmain_crt_thread_attach

- ea: `0x180001f80`
- end: `0x180001fa8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001b60`

## callees

- `0x180001f80`
- `0x180002c08`

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
0x180001f80  sub     rsp, 28h
0x180001f84  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001f89  test    al, al
0x180001f8b  jnz     short loc_180001F91
0x180001f8d  xor     al, al
0x180001f8f  jmp     short loc_180001FA3
0x180001f91  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001f96  test    al, al
0x180001f98  jnz     short loc_180001FA1
0x180001f9a  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001f9f  jmp     short loc_180001F8D
0x180001fa1  mov     al, 1
0x180001fa3  add     rsp, 28h
0x180001fa7  retn
```
