# __scrt_dllmain_crt_thread_attach

- ea: `0x18000add4`
- end: `0x18000adfc`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a820`

## callees

- `0x18000add4`
- `0x18006ade4`

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
0x18000add4  sub     rsp, 28h
0x18000add8  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000addd  test    al, al
0x18000addf  jnz     short loc_18000ADE5
0x18000ade1  xor     al, al
0x18000ade3  jmp     short loc_18000ADF7
0x18000ade5  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000adea  test    al, al
0x18000adec  jnz     short loc_18000ADF5
0x18000adee  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000adf3  jmp     short loc_18000ADE1
0x18000adf5  mov     al, 1
0x18000adf7  add     rsp, 28h
0x18000adfb  retn
```
