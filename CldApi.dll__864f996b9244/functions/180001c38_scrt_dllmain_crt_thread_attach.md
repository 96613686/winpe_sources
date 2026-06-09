# __scrt_dllmain_crt_thread_attach

- ea: `0x180001c38`
- end: `0x180001c60`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001710`

## callees

- `0x180001c38`
- `0x1800025d4`

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
0x180001c38  sub     rsp, 28h
0x180001c3c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001c41  test    al, al
0x180001c43  jnz     short loc_180001C49
0x180001c45  xor     al, al
0x180001c47  jmp     short loc_180001C5B
0x180001c49  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001c4e  test    al, al
0x180001c50  jnz     short loc_180001C59
0x180001c52  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001c57  jmp     short loc_180001C45
0x180001c59  mov     al, 1
0x180001c5b  add     rsp, 28h
0x180001c5f  retn
```
