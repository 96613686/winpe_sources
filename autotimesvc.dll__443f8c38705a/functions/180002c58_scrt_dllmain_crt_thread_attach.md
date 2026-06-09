# __scrt_dllmain_crt_thread_attach

- ea: `0x180002c58`
- end: `0x180002c80`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002700`

## callees

- `0x180002c58`
- `0x1800037e0`

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
0x180002c58  sub     rsp, 28h
0x180002c5c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002c61  test    al, al
0x180002c63  jnz     short loc_180002C69
0x180002c65  xor     al, al
0x180002c67  jmp     short loc_180002C7B
0x180002c69  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002c6e  test    al, al
0x180002c70  jnz     short loc_180002C79
0x180002c72  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002c77  jmp     short loc_180002C65
0x180002c79  mov     al, 1
0x180002c7b  add     rsp, 28h
0x180002c7f  retn
```
