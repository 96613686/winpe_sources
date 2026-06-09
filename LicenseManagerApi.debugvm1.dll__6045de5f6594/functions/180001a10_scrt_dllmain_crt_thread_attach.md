# __scrt_dllmain_crt_thread_attach

- ea: `0x180001a10`
- end: `0x180001a38`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800015f0`

## callees

- `0x180001a10`
- `0x1800029ec`

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
0x180001a10  sub     rsp, 28h
0x180001a14  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001a19  test    al, al
0x180001a1b  jnz     short loc_180001A21
0x180001a1d  xor     al, al
0x180001a1f  jmp     short loc_180001A33
0x180001a21  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001a26  test    al, al
0x180001a28  jnz     short loc_180001A31
0x180001a2a  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001a2f  jmp     short loc_180001A1D
0x180001a31  mov     al, 1
0x180001a33  add     rsp, 28h
0x180001a37  retn
```
