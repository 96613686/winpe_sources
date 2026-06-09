# __scrt_dllmain_crt_thread_attach

- ea: `0x18002ac84`
- end: `0x18002acac`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002a750`

## callees

- `0x18002ac84`
- `0x18002b5d8`

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
0x18002ac84  sub     rsp, 28h
0x18002ac88  call    __scrt_stub_for_acrt_uninitialize_critical
0x18002ac8d  test    al, al
0x18002ac8f  jnz     short loc_18002AC95
0x18002ac91  xor     al, al
0x18002ac93  jmp     short loc_18002ACA7
0x18002ac95  call    __scrt_stub_for_acrt_uninitialize_critical
0x18002ac9a  test    al, al
0x18002ac9c  jnz     short loc_18002ACA5
0x18002ac9e  call    __scrt_stub_for_acrt_uninitialize_critical
0x18002aca3  jmp     short loc_18002AC91
0x18002aca5  mov     al, 1
0x18002aca7  add     rsp, 28h
0x18002acab  retn
```
