# __scrt_dllmain_crt_thread_attach

- ea: `0x180008b30`
- end: `0x180008b58`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008710`

## callees

- `0x180008b30`
- `0x18000970c`

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
0x180008b30  sub     rsp, 28h
0x180008b34  call    __scrt_stub_for_acrt_uninitialize_critical
0x180008b39  test    al, al
0x180008b3b  jnz     short loc_180008B41
0x180008b3d  xor     al, al
0x180008b3f  jmp     short loc_180008B53
0x180008b41  call    __scrt_stub_for_acrt_uninitialize_critical
0x180008b46  test    al, al
0x180008b48  jnz     short loc_180008B51
0x180008b4a  call    __scrt_stub_for_acrt_uninitialize_critical
0x180008b4f  jmp     short loc_180008B3D
0x180008b51  mov     al, 1
0x180008b53  add     rsp, 28h
0x180008b57  retn
```
