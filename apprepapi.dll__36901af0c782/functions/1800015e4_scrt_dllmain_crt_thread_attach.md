# __scrt_dllmain_crt_thread_attach

- ea: `0x1800015e4`
- end: `0x18000160c`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001090`

## callees

- `0x1800015e4`
- `0x180001c90`

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
0x1800015e4  sub     rsp, 28h
0x1800015e8  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800015ed  test    al, al
0x1800015ef  jnz     short loc_1800015F5
0x1800015f1  xor     al, al
0x1800015f3  jmp     short loc_180001607
0x1800015f5  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800015fa  test    al, al
0x1800015fc  jnz     short loc_180001605
0x1800015fe  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001603  jmp     short loc_1800015F1
0x180001605  mov     al, 1
0x180001607  add     rsp, 28h
0x18000160b  retn
```
