# __scrt_dllmain_crt_thread_attach

- ea: `0x180001620`
- end: `0x180001648`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001200`

## callees

- `0x180001620`
- `0x1800020a0`

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
0x180001620  sub     rsp, 28h
0x180001624  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001629  test    al, al
0x18000162b  jnz     short loc_180001631
0x18000162d  xor     al, al
0x18000162f  jmp     short loc_180001643
0x180001631  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001636  test    al, al
0x180001638  jnz     short loc_180001641
0x18000163a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000163f  jmp     short loc_18000162D
0x180001641  mov     al, 1
0x180001643  add     rsp, 28h
0x180001647  retn
```
