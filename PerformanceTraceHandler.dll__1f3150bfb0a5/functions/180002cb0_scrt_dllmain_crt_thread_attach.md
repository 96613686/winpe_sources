# __scrt_dllmain_crt_thread_attach

- ea: `0x180002cb0`
- end: `0x180002cd8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002890`

## callees

- `0x180002cb0`
- `0x1800038a4`

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
0x180002cb0  sub     rsp, 28h
0x180002cb4  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002cb9  test    al, al
0x180002cbb  jnz     short loc_180002CC1
0x180002cbd  xor     al, al
0x180002cbf  jmp     short loc_180002CD3
0x180002cc1  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002cc6  test    al, al
0x180002cc8  jnz     short loc_180002CD1
0x180002cca  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002ccf  jmp     short loc_180002CBD
0x180002cd1  mov     al, 1
0x180002cd3  add     rsp, 28h
0x180002cd7  retn
```
