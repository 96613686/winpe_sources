# __scrt_dllmain_crt_thread_attach

- ea: `0x180001ef4`
- end: `0x180001f1c`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001a90`

## callees

- `0x180001ef4`
- `0x1800028c4`

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
0x180001ef4  sub     rsp, 28h
0x180001ef8  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001efd  test    al, al
0x180001eff  jnz     short loc_180001F05
0x180001f01  xor     al, al
0x180001f03  jmp     short loc_180001F17
0x180001f05  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001f0a  test    al, al
0x180001f0c  jnz     short loc_180001F15
0x180001f0e  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001f13  jmp     short loc_180001F01
0x180001f15  mov     al, 1
0x180001f17  add     rsp, 28h
0x180001f1b  retn
```
