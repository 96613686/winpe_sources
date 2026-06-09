# __scrt_dllmain_crt_thread_attach

- ea: `0x1800016d0`
- end: `0x1800016f8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800012b0`

## callees

- `0x1800016d0`
- `0x180002884`

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
0x1800016d0  sub     rsp, 28h
0x1800016d4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016d9  test    al, al
0x1800016db  jnz     short loc_1800016E1
0x1800016dd  xor     al, al
0x1800016df  jmp     short loc_1800016F3
0x1800016e1  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016e6  test    al, al
0x1800016e8  jnz     short loc_1800016F1
0x1800016ea  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016ef  jmp     short loc_1800016DD
0x1800016f1  mov     al, 1
0x1800016f3  add     rsp, 28h
0x1800016f7  retn
```
