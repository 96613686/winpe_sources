# __scrt_dllmain_crt_thread_attach

- ea: `0x18003512c`
- end: `0x180035154`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180035500`

## callees

- `0x18003512c`
- `0x180037048`
- `0x18003705c`
- `0x1800398cc`

## pseudocode

```c
char _scrt_dllmain_crt_thread_attach()
{
  if ( !_vcrt_thread_attach() )
    return 0;
  if ( !(unsigned __int8)_scrt_stub_for_acrt_uninitialize_critical() )
  {
    _vcrt_thread_detach();
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18003512c  sub     rsp, 28h
0x180035130  call    __vcrt_thread_attach
0x180035135  test    al, al
0x180035137  jnz     short loc_18003513D
0x180035139  xor     al, al
0x18003513b  jmp     short loc_18003514F
0x18003513d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180035142  test    al, al
0x180035144  jnz     short loc_18003514D
0x180035146  call    __vcrt_thread_detach
0x18003514b  jmp     short loc_180035139
0x18003514d  mov     al, 1
0x18003514f  add     rsp, 28h
0x180035153  retn
```
