# __scrt_dllmain_crt_thread_attach

- ea: `0x180003bec`
- end: `0x180003c14`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003f80`

## callees

- `0x180003bec`
- `0x1800049bc`

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
0x180003bec  sub     rsp, 28h
0x180003bf0  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003bf5  test    al, al
0x180003bf7  jnz     short loc_180003BFD
0x180003bf9  xor     al, al
0x180003bfb  jmp     short loc_180003C0F
0x180003bfd  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003c02  test    al, al
0x180003c04  jnz     short loc_180003C0D
0x180003c06  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003c0b  jmp     short loc_180003BF9
0x180003c0d  mov     al, 1
0x180003c0f  add     rsp, 28h
0x180003c13  retn
```
