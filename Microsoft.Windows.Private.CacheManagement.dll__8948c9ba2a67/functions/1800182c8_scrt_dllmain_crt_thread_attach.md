# __scrt_dllmain_crt_thread_attach

- ea: `0x1800182c8`
- end: `0x1800182f0`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800185d0`

## callees

- `0x1800182c8`
- `0x180019ce8`
- `0x180019cfc`
- `0x18001c79c`

## pseudocode

```c
char _scrt_dllmain_crt_thread_attach()
{
  if ( !_vcrt_thread_attach() )
    return 0;
  if ( !(unsigned __int8)_scrt_stub_for_acrt_uninitialize_critical() )
  {
    _vcrt_thread_detach();
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800182c8  sub     rsp, 28h
0x1800182cc  call    __vcrt_thread_attach
0x1800182d1  test    al, al
0x1800182d3  jnz     short loc_1800182D9
0x1800182d5  xor     al, al
0x1800182d7  jmp     short loc_1800182EB
0x1800182d9  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800182de  test    al, al
0x1800182e0  jnz     short loc_1800182E9
0x1800182e2  call    __vcrt_thread_detach
0x1800182e7  jmp     short loc_1800182D5
0x1800182e9  mov     al, 1
0x1800182eb  add     rsp, 28h
0x1800182ef  retn
```
