# __scrt_dllmain_crt_thread_attach

- ea: `0x180001898`
- end: `0x1800018c0`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001330`

## callees

- `0x180001898`
- `0x1800022b0`

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
0x180001898  sub     rsp, 28h
0x18000189c  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800018a1  test    al, al
0x1800018a3  jnz     short loc_1800018A9
0x1800018a5  xor     al, al
0x1800018a7  jmp     short loc_1800018BB
0x1800018a9  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800018ae  test    al, al
0x1800018b0  jnz     short loc_1800018B9
0x1800018b2  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800018b7  jmp     short loc_1800018A5
0x1800018b9  mov     al, 1
0x1800018bb  add     rsp, 28h
0x1800018bf  retn
```
