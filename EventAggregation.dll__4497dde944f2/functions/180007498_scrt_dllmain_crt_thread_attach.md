# __scrt_dllmain_crt_thread_attach

- ea: `0x180007498`
- end: `0x1800074c0`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006f70`

## callees

- `0x180007498`
- `0x180007bf8`

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
0x180007498  sub     rsp, 28h
0x18000749c  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800074a1  test    al, al
0x1800074a3  jnz     short loc_1800074A9
0x1800074a5  xor     al, al
0x1800074a7  jmp     short loc_1800074BB
0x1800074a9  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800074ae  test    al, al
0x1800074b0  jnz     short loc_1800074B9
0x1800074b2  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800074b7  jmp     short loc_1800074A5
0x1800074b9  mov     al, 1
0x1800074bb  add     rsp, 28h
0x1800074bf  retn
```
