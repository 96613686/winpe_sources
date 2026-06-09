# __scrt_dllmain_crt_thread_attach

- ea: `0x180009a08`
- end: `0x180009a30`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800094e0`

## callees

- `0x180009a08`
- `0x18000af24`

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
0x180009a08  sub     rsp, 28h
0x180009a0c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180009a11  test    al, al
0x180009a13  jnz     short loc_180009A19
0x180009a15  xor     al, al
0x180009a17  jmp     short loc_180009A2B
0x180009a19  call    __scrt_stub_for_acrt_uninitialize_critical
0x180009a1e  test    al, al
0x180009a20  jnz     short loc_180009A29
0x180009a22  call    __scrt_stub_for_acrt_uninitialize_critical
0x180009a27  jmp     short loc_180009A15
0x180009a29  mov     al, 1
0x180009a2b  add     rsp, 28h
0x180009a2f  retn
```
