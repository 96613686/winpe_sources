# __scrt_dllmain_crt_thread_attach

- ea: `0x1800019cc`
- end: `0x1800019f4`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001580`

## callees

- `0x1800019cc`
- `0x18001b03c`

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
0x1800019cc  sub     rsp, 28h
0x1800019d0  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800019d5  test    al, al
0x1800019d7  jnz     short loc_1800019DD
0x1800019d9  xor     al, al
0x1800019db  jmp     short loc_1800019EF
0x1800019dd  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800019e2  test    al, al
0x1800019e4  jnz     short loc_1800019ED
0x1800019e6  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800019eb  jmp     short loc_1800019D9
0x1800019ed  mov     al, 1
0x1800019ef  add     rsp, 28h
0x1800019f3  retn
```
