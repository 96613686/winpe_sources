# __scrt_dllmain_crt_thread_attach

- ea: `0x180003af0`
- end: `0x180003b18`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003290`

## callees

- `0x180003af0`
- `0x180004390`

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
0x180003af0  sub     rsp, 28h
0x180003af4  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003af9  test    al, al
0x180003afb  jnz     short loc_180003B01
0x180003afd  xor     al, al
0x180003aff  jmp     short loc_180003B13
0x180003b01  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003b06  test    al, al
0x180003b08  jnz     short loc_180003B11
0x180003b0a  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003b0f  jmp     short loc_180003AFD
0x180003b11  mov     al, 1
0x180003b13  add     rsp, 28h
0x180003b17  retn
```
