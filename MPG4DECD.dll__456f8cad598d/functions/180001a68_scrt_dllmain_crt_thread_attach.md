# __scrt_dllmain_crt_thread_attach

- ea: `0x180001a68`
- end: `0x180001a90`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001540`

## callees

- `0x180001a68`
- `0x180002394`

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
0x180001a68  sub     rsp, 28h
0x180001a6c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001a71  test    al, al
0x180001a73  jnz     short loc_180001A79
0x180001a75  xor     al, al
0x180001a77  jmp     short loc_180001A8B
0x180001a79  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001a7e  test    al, al
0x180001a80  jnz     short loc_180001A89
0x180001a82  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001a87  jmp     short loc_180001A75
0x180001a89  mov     al, 1
0x180001a8b  add     rsp, 28h
0x180001a8f  retn
```
