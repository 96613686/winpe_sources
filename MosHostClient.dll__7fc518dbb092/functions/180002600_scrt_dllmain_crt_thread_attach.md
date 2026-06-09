# __scrt_dllmain_crt_thread_attach

- ea: `0x180002600`
- end: `0x180002628`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800021d0`

## callees

- `0x180002600`
- `0x18000321c`

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
0x180002600  sub     rsp, 28h
0x180002604  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002609  test    al, al
0x18000260b  jnz     short loc_180002611
0x18000260d  xor     al, al
0x18000260f  jmp     short loc_180002623
0x180002611  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002616  test    al, al
0x180002618  jnz     short loc_180002621
0x18000261a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000261f  jmp     short loc_18000260D
0x180002621  mov     al, 1
0x180002623  add     rsp, 28h
0x180002627  retn
```
