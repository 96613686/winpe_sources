# __scrt_dllmain_crt_thread_attach

- ea: `0x18000184c`
- end: `0x180001874`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001350`

## callees

- `0x18000184c`
- `0x1800023ac`

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
0x18000184c  sub     rsp, 28h
0x180001850  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001855  test    al, al
0x180001857  jnz     short loc_18000185D
0x180001859  xor     al, al
0x18000185b  jmp     short loc_18000186F
0x18000185d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001862  test    al, al
0x180001864  jnz     short loc_18000186D
0x180001866  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000186b  jmp     short loc_180001859
0x18000186d  mov     al, 1
0x18000186f  add     rsp, 28h
0x180001873  retn
```
