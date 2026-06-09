# __scrt_dllmain_crt_thread_attach

- ea: `0x18000189c`
- end: `0x1800018c4`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800013a0`

## callees

- `0x18000189c`
- `0x180002758`

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
0x18000189c  sub     rsp, 28h
0x1800018a0  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800018a5  test    al, al
0x1800018a7  jnz     short loc_1800018AD
0x1800018a9  xor     al, al
0x1800018ab  jmp     short loc_1800018BF
0x1800018ad  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800018b2  test    al, al
0x1800018b4  jnz     short loc_1800018BD
0x1800018b6  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800018bb  jmp     short loc_1800018A9
0x1800018bd  mov     al, 1
0x1800018bf  add     rsp, 28h
0x1800018c3  retn
```
