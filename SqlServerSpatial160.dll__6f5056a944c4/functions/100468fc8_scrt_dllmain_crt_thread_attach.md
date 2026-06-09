# __scrt_dllmain_crt_thread_attach

- ea: `0x100468fc8`
- end: `0x100468ff0`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x100468bb4`

## callees

- `0x100468fc8`
- `0x1004698f0`

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
0x100468fc8  sub     rsp, 28h
0x100468fcc  call    __scrt_stub_for_acrt_uninitialize_critical
0x100468fd1  test    al, al
0x100468fd3  jnz     short loc_100468FD9
0x100468fd5  xor     al, al
0x100468fd7  jmp     short loc_100468FEB
0x100468fd9  call    __scrt_stub_for_acrt_uninitialize_critical
0x100468fde  test    al, al
0x100468fe0  jnz     short loc_100468FE9
0x100468fe2  call    __scrt_stub_for_acrt_uninitialize_critical
0x100468fe7  jmp     short loc_100468FD5
0x100468fe9  mov     al, 1
0x100468feb  add     rsp, 28h
0x100468fef  retn
```
