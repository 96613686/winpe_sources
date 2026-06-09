# __scrt_dllmain_crt_thread_attach

- ea: `0x1800016c0`
- end: `0x1800016e8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800012a0`

## callees

- `0x1800016c0`
- `0x1800023bc`

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
0x1800016c0  sub     rsp, 28h
0x1800016c4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016c9  test    al, al
0x1800016cb  jnz     short loc_1800016D1
0x1800016cd  xor     al, al
0x1800016cf  jmp     short loc_1800016E3
0x1800016d1  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016d6  test    al, al
0x1800016d8  jnz     short loc_1800016E1
0x1800016da  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016df  jmp     short loc_1800016CD
0x1800016e1  mov     al, 1
0x1800016e3  add     rsp, 28h
0x1800016e7  retn
```
