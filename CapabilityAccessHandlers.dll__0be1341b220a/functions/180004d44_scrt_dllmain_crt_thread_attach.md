# __scrt_dllmain_crt_thread_attach

- ea: `0x180004d44`
- end: `0x180004d6c`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004900`

## callees

- `0x180004d44`
- `0x1800057f0`

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
0x180004d44  sub     rsp, 28h
0x180004d48  call    __scrt_stub_for_acrt_uninitialize_critical
0x180004d4d  test    al, al
0x180004d4f  jnz     short loc_180004D55
0x180004d51  xor     al, al
0x180004d53  jmp     short loc_180004D67
0x180004d55  call    __scrt_stub_for_acrt_uninitialize_critical
0x180004d5a  test    al, al
0x180004d5c  jnz     short loc_180004D65
0x180004d5e  call    __scrt_stub_for_acrt_uninitialize_critical
0x180004d63  jmp     short loc_180004D51
0x180004d65  mov     al, 1
0x180004d67  add     rsp, 28h
0x180004d6b  retn
```
