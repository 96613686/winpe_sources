# __scrt_dllmain_crt_thread_attach

- ea: `0x180001dfc`
- end: `0x180001e24`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800019d0`

## callees

- `0x180001dfc`
- `0x18000a120`

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
0x180001dfc  sub     rsp, 28h
0x180001e00  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001e05  test    al, al
0x180001e07  jnz     short loc_180001E0D
0x180001e09  xor     al, al
0x180001e0b  jmp     short loc_180001E1F
0x180001e0d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001e12  test    al, al
0x180001e14  jnz     short loc_180001E1D
0x180001e16  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001e1b  jmp     short loc_180001E09
0x180001e1d  mov     al, 1
0x180001e1f  add     rsp, 28h
0x180001e23  retn
```
