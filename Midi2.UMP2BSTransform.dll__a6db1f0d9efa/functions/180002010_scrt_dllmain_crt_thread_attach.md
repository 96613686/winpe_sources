# __scrt_dllmain_crt_thread_attach

- ea: `0x180002010`
- end: `0x180002038`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001b70`

## callees

- `0x180002010`
- `0x1800029c4`

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
0x180002010  sub     rsp, 28h
0x180002014  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002019  test    al, al
0x18000201b  jnz     short loc_180002021
0x18000201d  xor     al, al
0x18000201f  jmp     short loc_180002033
0x180002021  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002026  test    al, al
0x180002028  jnz     short loc_180002031
0x18000202a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000202f  jmp     short loc_18000201D
0x180002031  mov     al, 1
0x180002033  add     rsp, 28h
0x180002037  retn
```
