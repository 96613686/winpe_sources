# __scrt_dllmain_crt_thread_attach

- ea: `0x180001728`
- end: `0x180001750`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800010f0`

## callees

- `0x180001728`
- `0x180001f68`

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
0x180001728  sub     rsp, 28h
0x18000172c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001731  test    al, al
0x180001733  jnz     short loc_180001739
0x180001735  xor     al, al
0x180001737  jmp     short loc_18000174B
0x180001739  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000173e  test    al, al
0x180001740  jnz     short loc_180001749
0x180001742  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001747  jmp     short loc_180001735
0x180001749  mov     al, 1
0x18000174b  add     rsp, 28h
0x18000174f  retn
```
