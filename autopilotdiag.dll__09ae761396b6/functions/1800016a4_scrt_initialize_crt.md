# __scrt_initialize_crt

- ea: `0x1800016a4`
- end: `0x1800016de`
- name: `__scrt_initialize_crt`
- size: `58`
- prototype: `char __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800010e8`

## callees

- `0x1800016a4`
- `0x180001918`
- `0x180001c60`

## pseudocode

```c
char __fastcall _scrt_initialize_crt(int a1)
{
  __int64 v1; // rcx
  __int64 v2; // rcx

  if ( !a1 )
    byte_1800040F1 = 1;
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
0x1800016a4  sub     rsp, 28h
0x1800016a8  test    ecx, ecx
0x1800016aa  jnz     short loc_1800016B3
0x1800016ac  mov     cs:byte_1800040F1, 1
0x1800016b3  call    __isa_available_init
0x1800016b8  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016bd  test    al, al
0x1800016bf  jnz     short loc_1800016C5
0x1800016c1  xor     al, al
0x1800016c3  jmp     short loc_1800016D9
0x1800016c5  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016ca  test    al, al
0x1800016cc  jnz     short loc_1800016D7
0x1800016ce  xor     ecx, ecx
0x1800016d0  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016d5  jmp     short loc_1800016C1
0x1800016d7  mov     al, 1
0x1800016d9  add     rsp, 28h
0x1800016dd  retn
```
