# __scrt_dllmain_crt_thread_attach

- ea: `0x180001824`
- end: `0x18000184c`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800013b0`

## callees

- `0x180001824`
- `0x18000232c`

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
0x180001824  sub     rsp, 28h
0x180001828  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000182d  test    al, al
0x18000182f  jnz     short loc_180001835
0x180001831  xor     al, al
0x180001833  jmp     short loc_180001847
0x180001835  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000183a  test    al, al
0x18000183c  jnz     short loc_180001845
0x18000183e  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001843  jmp     short loc_180001831
0x180001845  mov     al, 1
0x180001847  add     rsp, 28h
0x18000184b  retn
```
