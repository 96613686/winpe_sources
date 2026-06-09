# __scrt_dllmain_crt_thread_attach

- ea: `0x180002418`
- end: `0x180002440`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001f90`

## callees

- `0x180002418`
- `0x180002ed0`

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
0x180002418  sub     rsp, 28h
0x18000241c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002421  test    al, al
0x180002423  jnz     short loc_180002429
0x180002425  xor     al, al
0x180002427  jmp     short loc_18000243B
0x180002429  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000242e  test    al, al
0x180002430  jnz     short loc_180002439
0x180002432  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002437  jmp     short loc_180002425
0x180002439  mov     al, 1
0x18000243b  add     rsp, 28h
0x18000243f  retn
```
