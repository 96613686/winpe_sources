# __scrt_dllmain_crt_thread_attach

- ea: `0x180001630`
- end: `0x180001658`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800010d0`

## callees

- `0x180001630`
- `0x180001d24`

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
0x180001630  sub     rsp, 28h
0x180001634  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001639  test    al, al
0x18000163b  jnz     short loc_180001641
0x18000163d  xor     al, al
0x18000163f  jmp     short loc_180001653
0x180001641  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001646  test    al, al
0x180001648  jnz     short loc_180001651
0x18000164a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000164f  jmp     short loc_18000163D
0x180001651  mov     al, 1
0x180001653  add     rsp, 28h
0x180001657  retn
```
