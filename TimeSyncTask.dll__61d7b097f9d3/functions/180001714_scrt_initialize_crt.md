# __scrt_initialize_crt

- ea: `0x180001714`
- end: `0x18000174e`
- name: `__scrt_initialize_crt`
- size: `58`
- prototype: `char __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001148`

## callees

- `0x180001714`
- `0x1800019ac`
- `0x180001d8c`

## pseudocode

```c
char __fastcall _scrt_initialize_crt(int a1)
{
  __int64 v1; // rcx
  __int64 v2; // rcx

  if ( !a1 )
    byte_1800070F1 = 1;
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
0x180001714  sub     rsp, 28h
0x180001718  test    ecx, ecx
0x18000171a  jnz     short loc_180001723
0x18000171c  mov     cs:byte_1800070F1, 1
0x180001723  call    __isa_available_init
0x180001728  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000172d  test    al, al
0x18000172f  jnz     short loc_180001735
0x180001731  xor     al, al
0x180001733  jmp     short loc_180001749
0x180001735  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000173a  test    al, al
0x18000173c  jnz     short loc_180001747
0x18000173e  xor     ecx, ecx
0x180001740  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001745  jmp     short loc_180001731
0x180001747  mov     al, 1
0x180001749  add     rsp, 28h
0x18000174d  retn
```
