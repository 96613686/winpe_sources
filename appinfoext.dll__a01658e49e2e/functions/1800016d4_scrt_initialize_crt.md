# __scrt_initialize_crt

- ea: `0x1800016d4`
- end: `0x18000170e`
- name: `__scrt_initialize_crt`
- size: `58`
- prototype: `char __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800010e8`

## callees

- `0x1800016d4`
- `0x180001960`
- `0x180001ca0`

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
0x1800016d4  sub     rsp, 28h
0x1800016d8  test    ecx, ecx
0x1800016da  jnz     short loc_1800016E3
0x1800016dc  mov     cs:byte_1800040F1, 1
0x1800016e3  call    __isa_available_init
0x1800016e8  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016ed  test    al, al
0x1800016ef  jnz     short loc_1800016F5
0x1800016f1  xor     al, al
0x1800016f3  jmp     short loc_180001709
0x1800016f5  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016fa  test    al, al
0x1800016fc  jnz     short loc_180001707
0x1800016fe  xor     ecx, ecx
0x180001700  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001705  jmp     short loc_1800016F1
0x180001707  mov     al, 1
0x180001709  add     rsp, 28h
0x18000170d  retn
```
