# __scrt_dllmain_crt_thread_attach

- ea: `0x180003060`
- end: `0x180003088`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002af0`

## callees

- `0x180003060`
- `0x180003b4c`

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
0x180003060  sub     rsp, 28h
0x180003064  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003069  test    al, al
0x18000306b  jnz     short loc_180003071
0x18000306d  xor     al, al
0x18000306f  jmp     short loc_180003083
0x180003071  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003076  test    al, al
0x180003078  jnz     short loc_180003081
0x18000307a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000307f  jmp     short loc_18000306D
0x180003081  mov     al, 1
0x180003083  add     rsp, 28h
0x180003087  retn
```
