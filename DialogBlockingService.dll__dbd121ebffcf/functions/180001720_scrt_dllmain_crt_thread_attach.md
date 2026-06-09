# __scrt_dllmain_crt_thread_attach

- ea: `0x180001720`
- end: `0x180001748`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800012b0`

## callees

- `0x180001720`
- `0x180002160`

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
0x180001720  sub     rsp, 28h
0x180001724  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001729  test    al, al
0x18000172b  jnz     short loc_180001731
0x18000172d  xor     al, al
0x18000172f  jmp     short loc_180001743
0x180001731  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001736  test    al, al
0x180001738  jnz     short loc_180001741
0x18000173a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000173f  jmp     short loc_18000172D
0x180001741  mov     al, 1
0x180001743  add     rsp, 28h
0x180001747  retn
```
