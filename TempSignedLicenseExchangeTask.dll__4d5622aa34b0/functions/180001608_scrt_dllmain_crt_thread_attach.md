# __scrt_dllmain_crt_thread_attach

- ea: `0x180001608`
- end: `0x180001630`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001090`

## callees

- `0x180001608`
- `0x180001fcc`

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
0x180001608  sub     rsp, 28h
0x18000160c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001611  test    al, al
0x180001613  jnz     short loc_180001619
0x180001615  xor     al, al
0x180001617  jmp     short loc_18000162B
0x180001619  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000161e  test    al, al
0x180001620  jnz     short loc_180001629
0x180001622  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001627  jmp     short loc_180001615
0x180001629  mov     al, 1
0x18000162b  add     rsp, 28h
0x18000162f  retn
```
