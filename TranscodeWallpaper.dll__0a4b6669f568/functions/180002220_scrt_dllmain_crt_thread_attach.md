# __scrt_dllmain_crt_thread_attach

- ea: `0x180002220`
- end: `0x180002248`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001e00`

## callees

- `0x180002220`
- `0x180002dfc`

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
0x180002220  sub     rsp, 28h
0x180002224  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002229  test    al, al
0x18000222b  jnz     short loc_180002231
0x18000222d  xor     al, al
0x18000222f  jmp     short loc_180002243
0x180002231  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002236  test    al, al
0x180002238  jnz     short loc_180002241
0x18000223a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000223f  jmp     short loc_18000222D
0x180002241  mov     al, 1
0x180002243  add     rsp, 28h
0x180002247  retn
```
