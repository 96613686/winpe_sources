# __scrt_dllmain_crt_thread_attach

- ea: `0x180002120`
- end: `0x180002148`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001c80`

## callees

- `0x180002120`
- `0x180002ad4`

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
0x180002120  sub     rsp, 28h
0x180002124  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002129  test    al, al
0x18000212b  jnz     short loc_180002131
0x18000212d  xor     al, al
0x18000212f  jmp     short loc_180002143
0x180002131  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002136  test    al, al
0x180002138  jnz     short loc_180002141
0x18000213a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000213f  jmp     short loc_18000212D
0x180002141  mov     al, 1
0x180002143  add     rsp, 28h
0x180002147  retn
```
