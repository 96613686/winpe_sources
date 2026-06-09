# __scrt_dllmain_crt_thread_attach

- ea: `0x180001a4c`
- end: `0x180001a74`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800014f0`

## callees

- `0x180001a4c`
- `0x1800028c0`

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
0x180001a4c  sub     rsp, 28h
0x180001a50  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001a55  test    al, al
0x180001a57  jnz     short loc_180001A5D
0x180001a59  xor     al, al
0x180001a5b  jmp     short loc_180001A6F
0x180001a5d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001a62  test    al, al
0x180001a64  jnz     short loc_180001A6D
0x180001a66  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001a6b  jmp     short loc_180001A59
0x180001a6d  mov     al, 1
0x180001a6f  add     rsp, 28h
0x180001a73  retn
```
