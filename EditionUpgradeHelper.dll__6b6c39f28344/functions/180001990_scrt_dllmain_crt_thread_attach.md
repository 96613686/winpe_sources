# __scrt_dllmain_crt_thread_attach

- ea: `0x180001990`
- end: `0x1800019b8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001570`

## callees

- `0x180001990`
- `0x180002540`

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
0x180001990  sub     rsp, 28h
0x180001994  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001999  test    al, al
0x18000199b  jnz     short loc_1800019A1
0x18000199d  xor     al, al
0x18000199f  jmp     short loc_1800019B3
0x1800019a1  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800019a6  test    al, al
0x1800019a8  jnz     short loc_1800019B1
0x1800019aa  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800019af  jmp     short loc_18000199D
0x1800019b1  mov     al, 1
0x1800019b3  add     rsp, 28h
0x1800019b7  retn
```
