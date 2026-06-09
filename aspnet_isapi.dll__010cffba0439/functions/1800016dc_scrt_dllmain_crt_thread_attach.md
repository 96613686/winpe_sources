# __scrt_dllmain_crt_thread_attach

- ea: `0x1800016dc`
- end: `0x180001704`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001150`

## callees

- `0x1800016dc`
- `0x180001ee4`

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
0x1800016dc  sub     rsp, 28h
0x1800016e0  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016e5  test    al, al
0x1800016e7  jnz     short loc_1800016ED
0x1800016e9  xor     al, al
0x1800016eb  jmp     short loc_1800016FF
0x1800016ed  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016f2  test    al, al
0x1800016f4  jnz     short loc_1800016FD
0x1800016f6  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016fb  jmp     short loc_1800016E9
0x1800016fd  mov     al, 1
0x1800016ff  add     rsp, 28h
0x180001703  retn
```
