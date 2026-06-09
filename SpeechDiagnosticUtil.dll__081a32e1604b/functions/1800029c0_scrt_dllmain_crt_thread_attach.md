# __scrt_dllmain_crt_thread_attach

- ea: `0x1800029c0`
- end: `0x1800029e8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800025a0`

## callees

- `0x1800029c0`
- `0x180003580`

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
0x1800029c0  sub     rsp, 28h
0x1800029c4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800029c9  test    al, al
0x1800029cb  jnz     short loc_1800029D1
0x1800029cd  xor     al, al
0x1800029cf  jmp     short loc_1800029E3
0x1800029d1  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800029d6  test    al, al
0x1800029d8  jnz     short loc_1800029E1
0x1800029da  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800029df  jmp     short loc_1800029CD
0x1800029e1  mov     al, 1
0x1800029e3  add     rsp, 28h
0x1800029e7  retn
```
