# __scrt_dllmain_crt_thread_attach

- ea: `0x180001810`
- end: `0x180001838`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800013f0`

## callees

- `0x180001810`
- `0x18000223c`

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
0x180001810  sub     rsp, 28h
0x180001814  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001819  test    al, al
0x18000181b  jnz     short loc_180001821
0x18000181d  xor     al, al
0x18000181f  jmp     short loc_180001833
0x180001821  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001826  test    al, al
0x180001828  jnz     short loc_180001831
0x18000182a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000182f  jmp     short loc_18000181D
0x180001831  mov     al, 1
0x180001833  add     rsp, 28h
0x180001837  retn
```
