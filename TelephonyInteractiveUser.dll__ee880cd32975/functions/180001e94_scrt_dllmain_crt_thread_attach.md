# __scrt_dllmain_crt_thread_attach

- ea: `0x180001e94`
- end: `0x180001ebc`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001a50`

## callees

- `0x180001e94`
- `0x180011680`

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
0x180001e94  sub     rsp, 28h
0x180001e98  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001e9d  test    al, al
0x180001e9f  jnz     short loc_180001EA5
0x180001ea1  xor     al, al
0x180001ea3  jmp     short loc_180001EB7
0x180001ea5  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001eaa  test    al, al
0x180001eac  jnz     short loc_180001EB5
0x180001eae  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001eb3  jmp     short loc_180001EA1
0x180001eb5  mov     al, 1
0x180001eb7  add     rsp, 28h
0x180001ebb  retn
```
