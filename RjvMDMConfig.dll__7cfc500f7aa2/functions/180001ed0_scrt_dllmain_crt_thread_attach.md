# __scrt_dllmain_crt_thread_attach

- ea: `0x180001ed0`
- end: `0x180001ef8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800018f0`

## callees

- `0x180001ed0`
- `0x180002d6c`

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
0x180001ed0  sub     rsp, 28h
0x180001ed4  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001ed9  test    al, al
0x180001edb  jnz     short loc_180001EE1
0x180001edd  xor     al, al
0x180001edf  jmp     short loc_180001EF3
0x180001ee1  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001ee6  test    al, al
0x180001ee8  jnz     short loc_180001EF1
0x180001eea  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001eef  jmp     short loc_180001EDD
0x180001ef1  mov     al, 1
0x180001ef3  add     rsp, 28h
0x180001ef7  retn
```
