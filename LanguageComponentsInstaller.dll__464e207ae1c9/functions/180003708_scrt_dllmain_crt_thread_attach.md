# __scrt_dllmain_crt_thread_attach

- ea: `0x180003708`
- end: `0x180003730`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800031b0`

## callees

- `0x180003708`
- `0x180015680`

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
0x180003708  sub     rsp, 28h
0x18000370c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003711  test    al, al
0x180003713  jnz     short loc_180003719
0x180003715  xor     al, al
0x180003717  jmp     short loc_18000372B
0x180003719  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000371e  test    al, al
0x180003720  jnz     short loc_180003729
0x180003722  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003727  jmp     short loc_180003715
0x180003729  mov     al, 1
0x18000372b  add     rsp, 28h
0x18000372f  retn
```
