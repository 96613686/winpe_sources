# __scrt_dllmain_crt_thread_attach

- ea: `0x180001cf4`
- end: `0x180001d1c`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001890`

## callees

- `0x180001cf4`
- `0x180002a7c`

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
0x180001cf4  sub     rsp, 28h
0x180001cf8  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001cfd  test    al, al
0x180001cff  jnz     short loc_180001D05
0x180001d01  xor     al, al
0x180001d03  jmp     short loc_180001D17
0x180001d05  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001d0a  test    al, al
0x180001d0c  jnz     short loc_180001D15
0x180001d0e  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001d13  jmp     short loc_180001D01
0x180001d15  mov     al, 1
0x180001d17  add     rsp, 28h
0x180001d1b  retn
```
