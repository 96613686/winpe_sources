# __scrt_dllmain_crt_thread_attach

- ea: `0x18000162c`
- end: `0x180001654`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800011e0`

## callees

- `0x18000162c`
- `0x180001eb8`

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
0x18000162c  sub     rsp, 28h
0x180001630  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001635  test    al, al
0x180001637  jnz     short loc_18000163D
0x180001639  xor     al, al
0x18000163b  jmp     short loc_18000164F
0x18000163d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001642  test    al, al
0x180001644  jnz     short loc_18000164D
0x180001646  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000164b  jmp     short loc_180001639
0x18000164d  mov     al, 1
0x18000164f  add     rsp, 28h
0x180001653  retn
```
