# __scrt_dllmain_crt_thread_attach

- ea: `0x180003750`
- end: `0x180003778`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003330`

## callees

- `0x180003750`
- `0x18000438c`

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
0x180003750  sub     rsp, 28h
0x180003754  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003759  test    al, al
0x18000375b  jnz     short loc_180003761
0x18000375d  xor     al, al
0x18000375f  jmp     short loc_180003773
0x180003761  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003766  test    al, al
0x180003768  jnz     short loc_180003771
0x18000376a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000376f  jmp     short loc_18000375D
0x180003771  mov     al, 1
0x180003773  add     rsp, 28h
0x180003777  retn
```
