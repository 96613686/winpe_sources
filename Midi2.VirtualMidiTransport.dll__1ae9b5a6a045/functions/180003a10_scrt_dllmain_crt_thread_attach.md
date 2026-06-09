# __scrt_dllmain_crt_thread_attach

- ea: `0x180003a10`
- end: `0x180003a38`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003570`

## callees

- `0x180003a10`
- `0x1800047cc`

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
0x180003a10  sub     rsp, 28h
0x180003a14  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003a19  test    al, al
0x180003a1b  jnz     short loc_180003A21
0x180003a1d  xor     al, al
0x180003a1f  jmp     short loc_180003A33
0x180003a21  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003a26  test    al, al
0x180003a28  jnz     short loc_180003A31
0x180003a2a  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003a2f  jmp     short loc_180003A1D
0x180003a31  mov     al, 1
0x180003a33  add     rsp, 28h
0x180003a37  retn
```
