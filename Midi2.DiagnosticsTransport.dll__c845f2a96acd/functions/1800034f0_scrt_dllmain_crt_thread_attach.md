# __scrt_dllmain_crt_thread_attach

- ea: `0x1800034f0`
- end: `0x180003518`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003050`

## callees

- `0x1800034f0`
- `0x1800041e8`

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
0x1800034f0  sub     rsp, 28h
0x1800034f4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800034f9  test    al, al
0x1800034fb  jnz     short loc_180003501
0x1800034fd  xor     al, al
0x1800034ff  jmp     short loc_180003513
0x180003501  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003506  test    al, al
0x180003508  jnz     short loc_180003511
0x18000350a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000350f  jmp     short loc_1800034FD
0x180003511  mov     al, 1
0x180003513  add     rsp, 28h
0x180003517  retn
```
