# __scrt_dllmain_crt_thread_attach

- ea: `0x180001a38`
- end: `0x180001a60`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001510`

## callees

- `0x180001a38`
- `0x1800022d8`

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
0x180001a38  sub     rsp, 28h
0x180001a3c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001a41  test    al, al
0x180001a43  jnz     short loc_180001A49
0x180001a45  xor     al, al
0x180001a47  jmp     short loc_180001A5B
0x180001a49  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001a4e  test    al, al
0x180001a50  jnz     short loc_180001A59
0x180001a52  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001a57  jmp     short loc_180001A45
0x180001a59  mov     al, 1
0x180001a5b  add     rsp, 28h
0x180001a5f  retn
```
