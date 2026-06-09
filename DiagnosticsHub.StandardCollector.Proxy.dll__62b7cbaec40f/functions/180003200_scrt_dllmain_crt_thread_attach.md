# __scrt_dllmain_crt_thread_attach

- ea: `0x180003200`
- end: `0x180003228`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002830`

## callees

- `0x180003200`
- `0x1800063f8`
- `0x180022c98`
- `0x180022cac`

## pseudocode

```c
char _scrt_dllmain_crt_thread_attach()
{
  if ( !_vcrt_thread_attach() )
    return 0;
  if ( !_acrt_thread_attach() )
  {
    _vcrt_thread_detach();
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180003200  sub     rsp, 28h
0x180003204  call    __vcrt_thread_attach
0x180003209  test    al, al
0x18000320b  jnz     short loc_180003211
0x18000320d  xor     al, al
0x18000320f  jmp     short loc_180003223
0x180003211  call    __acrt_thread_attach
0x180003216  test    al, al
0x180003218  jnz     short loc_180003221
0x18000321a  call    __vcrt_thread_detach
0x18000321f  jmp     short loc_18000320D
0x180003221  mov     al, 1
0x180003223  add     rsp, 28h
0x180003227  retn
```
