# __scrt_dllmain_crt_thread_attach

- ea: `0x180003e38`
- end: `0x180003e60`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003910`

## callees

- `0x180003e38`
- `0x1800058e0`

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
0x180003e38  sub     rsp, 28h
0x180003e3c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003e41  test    al, al
0x180003e43  jnz     short loc_180003E49
0x180003e45  xor     al, al
0x180003e47  jmp     short loc_180003E5B
0x180003e49  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003e4e  test    al, al
0x180003e50  jnz     short loc_180003E59
0x180003e52  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003e57  jmp     short loc_180003E45
0x180003e59  mov     al, 1
0x180003e5b  add     rsp, 28h
0x180003e5f  retn
```
