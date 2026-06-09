# __scrt_dllmain_crt_thread_attach

- ea: `0x1800022b0`
- end: `0x1800022d8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001e90`

## callees

- `0x1800022b0`
- `0x180002ff4`

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
0x1800022b0  sub     rsp, 28h
0x1800022b4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800022b9  test    al, al
0x1800022bb  jnz     short loc_1800022C1
0x1800022bd  xor     al, al
0x1800022bf  jmp     short loc_1800022D3
0x1800022c1  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800022c6  test    al, al
0x1800022c8  jnz     short loc_1800022D1
0x1800022ca  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800022cf  jmp     short loc_1800022BD
0x1800022d1  mov     al, 1
0x1800022d3  add     rsp, 28h
0x1800022d7  retn
```
