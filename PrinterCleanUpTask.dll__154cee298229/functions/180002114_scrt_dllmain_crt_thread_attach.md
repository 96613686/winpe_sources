# __scrt_dllmain_crt_thread_attach

- ea: `0x180002114`
- end: `0x18000213c`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001cb0`

## callees

- `0x180002114`
- `0x180003438`

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
0x180002114  sub     rsp, 28h
0x180002118  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000211d  test    al, al
0x18000211f  jnz     short loc_180002125
0x180002121  xor     al, al
0x180002123  jmp     short loc_180002137
0x180002125  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000212a  test    al, al
0x18000212c  jnz     short loc_180002135
0x18000212e  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002133  jmp     short loc_180002121
0x180002135  mov     al, 1
0x180002137  add     rsp, 28h
0x18000213b  retn
```
