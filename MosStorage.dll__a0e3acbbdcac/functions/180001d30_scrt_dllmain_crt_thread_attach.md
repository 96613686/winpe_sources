# __scrt_dllmain_crt_thread_attach

- ea: `0x180001d30`
- end: `0x180001d58`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001900`

## callees

- `0x180001d30`
- `0x180002eac`

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
0x180001d30  sub     rsp, 28h
0x180001d34  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001d39  test    al, al
0x180001d3b  jnz     short loc_180001D41
0x180001d3d  xor     al, al
0x180001d3f  jmp     short loc_180001D53
0x180001d41  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001d46  test    al, al
0x180001d48  jnz     short loc_180001D51
0x180001d4a  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001d4f  jmp     short loc_180001D3D
0x180001d51  mov     al, 1
0x180001d53  add     rsp, 28h
0x180001d57  retn
```
