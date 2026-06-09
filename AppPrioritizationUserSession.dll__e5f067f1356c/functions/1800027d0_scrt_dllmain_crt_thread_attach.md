# __scrt_dllmain_crt_thread_attach

- ea: `0x1800027d0`
- end: `0x1800027f8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800022e0`

## callees

- `0x1800027d0`
- `0x180003444`

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
0x1800027d0  sub     rsp, 28h
0x1800027d4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800027d9  test    al, al
0x1800027db  jnz     short loc_1800027E1
0x1800027dd  xor     al, al
0x1800027df  jmp     short loc_1800027F3
0x1800027e1  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800027e6  test    al, al
0x1800027e8  jnz     short loc_1800027F1
0x1800027ea  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800027ef  jmp     short loc_1800027DD
0x1800027f1  mov     al, 1
0x1800027f3  add     rsp, 28h
0x1800027f7  retn
```
