# __scrt_dllmain_crt_thread_attach

- ea: `0x18000e8d4`
- end: `0x18000e8fc`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000e3d0`

## callees

- `0x18000e8d4`
- `0x18000f028`

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
0x18000e8d4  sub     rsp, 28h
0x18000e8d8  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000e8dd  test    al, al
0x18000e8df  jnz     short loc_18000E8E5
0x18000e8e1  xor     al, al
0x18000e8e3  jmp     short loc_18000E8F7
0x18000e8e5  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000e8ea  test    al, al
0x18000e8ec  jnz     short loc_18000E8F5
0x18000e8ee  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000e8f3  jmp     short loc_18000E8E1
0x18000e8f5  mov     al, 1
0x18000e8f7  add     rsp, 28h
0x18000e8fb  retn
```
