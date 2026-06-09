# __scrt_initialize_crt

- ea: `0x1800016a8`
- end: `0x1800016e2`
- name: `__scrt_initialize_crt`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800010e8`

## callees

- `0x1800016a8`
- `0x180001940`
- `0x180001d1c`

## pseudocode

```c
char __fastcall _scrt_initialize_crt(int a1)
{
  if ( !a1 )
    byte_180020131 = 1;
  _isa_available_init();
  if ( !_scrt_stub_for_acrt_uninitialize_critical() )
    return 0;
  if ( !_scrt_stub_for_acrt_uninitialize_critical() )
  {
    _scrt_stub_for_acrt_uninitialize_critical();
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800016a8  sub     rsp, 28h
0x1800016ac  test    ecx, ecx
0x1800016ae  jnz     short loc_1800016B7
0x1800016b0  mov     cs:byte_180020131, 1
0x1800016b7  call    __isa_available_init
0x1800016bc  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016c1  test    al, al
0x1800016c3  jnz     short loc_1800016C9
0x1800016c5  xor     al, al
0x1800016c7  jmp     short loc_1800016DD
0x1800016c9  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016ce  test    al, al
0x1800016d0  jnz     short loc_1800016DB
0x1800016d2  xor     ecx, ecx
0x1800016d4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016d9  jmp     short loc_1800016C5
0x1800016db  mov     al, 1
0x1800016dd  add     rsp, 28h
0x1800016e1  retn
```
