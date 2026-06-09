# __scrt_dllmain_crt_thread_attach

- ea: `0x180001e34`
- end: `0x180001e5c`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800019f0`

## callees

- `0x180001e34`
- `0x180002cbc`

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
0x180001e34  sub     rsp, 28h
0x180001e38  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001e3d  test    al, al
0x180001e3f  jnz     short loc_180001E45
0x180001e41  xor     al, al
0x180001e43  jmp     short loc_180001E57
0x180001e45  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001e4a  test    al, al
0x180001e4c  jnz     short loc_180001E55
0x180001e4e  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001e53  jmp     short loc_180001E41
0x180001e55  mov     al, 1
0x180001e57  add     rsp, 28h
0x180001e5b  retn
```
