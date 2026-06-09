# __scrt_dllmain_crt_thread_attach

- ea: `0x18001079c`
- end: `0x1800107c4`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180010350`

## callees

- `0x18001079c`
- `0x1800119d0`

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
0x18001079c  sub     rsp, 28h
0x1800107a0  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800107a5  test    al, al
0x1800107a7  jnz     short loc_1800107AD
0x1800107a9  xor     al, al
0x1800107ab  jmp     short loc_1800107BF
0x1800107ad  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800107b2  test    al, al
0x1800107b4  jnz     short loc_1800107BD
0x1800107b6  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800107bb  jmp     short loc_1800107A9
0x1800107bd  mov     al, 1
0x1800107bf  add     rsp, 28h
0x1800107c3  retn
```
