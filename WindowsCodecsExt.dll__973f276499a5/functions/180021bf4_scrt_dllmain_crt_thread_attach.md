# __scrt_dllmain_crt_thread_attach

- ea: `0x180021bf4`
- end: `0x180021c1c`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800216c0`

## callees

- `0x180021bf4`
- `0x180022724`

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
0x180021bf4  sub     rsp, 28h
0x180021bf8  call    __scrt_stub_for_acrt_uninitialize_critical
0x180021bfd  test    al, al
0x180021bff  jnz     short loc_180021C05
0x180021c01  xor     al, al
0x180021c03  jmp     short loc_180021C17
0x180021c05  call    __scrt_stub_for_acrt_uninitialize_critical
0x180021c0a  test    al, al
0x180021c0c  jnz     short loc_180021C15
0x180021c0e  call    __scrt_stub_for_acrt_uninitialize_critical
0x180021c13  jmp     short loc_180021C01
0x180021c15  mov     al, 1
0x180021c17  add     rsp, 28h
0x180021c1b  retn
```
