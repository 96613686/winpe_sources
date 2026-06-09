# __scrt_initialize_crt

- ea: `0x180001914`
- end: `0x18000194e`
- name: `__scrt_initialize_crt`
- size: `58`
- prototype: `char __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001408`

## callees

- `0x180001914`
- `0x180001ef8`
- `0x18000232c`

## pseudocode

```c
char __fastcall _scrt_initialize_crt(int a1)
{
  __int64 v1; // rcx
  __int64 v2; // rcx

  if ( !a1 )
    byte_180007211 = 1;
  _isa_available_init();
  if ( !(unsigned __int8)_scrt_stub_for_acrt_uninitialize_critical(v1) )
    return 0;
  if ( !(unsigned __int8)_scrt_stub_for_acrt_uninitialize_critical(v2) )
  {
    _scrt_stub_for_acrt_uninitialize_critical(0);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180001914  sub     rsp, 28h
0x180001918  test    ecx, ecx
0x18000191a  jnz     short loc_180001923
0x18000191c  mov     cs:byte_180007211, 1
0x180001923  call    __isa_available_init
0x180001928  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000192d  test    al, al
0x18000192f  jnz     short loc_180001935
0x180001931  xor     al, al
0x180001933  jmp     short loc_180001949
0x180001935  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000193a  test    al, al
0x18000193c  jnz     short loc_180001947
0x18000193e  xor     ecx, ecx
0x180001940  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001945  jmp     short loc_180001931
0x180001947  mov     al, 1
0x180001949  add     rsp, 28h
0x18000194d  retn
```
