# __scrt_initialize_crt

- ea: `0x1800016f8`
- end: `0x180001732`
- name: `__scrt_initialize_crt`
- size: `58`
- prototype: `char __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800010e8`

## callees

- `0x1800016f8`
- `0x180001b88`
- `0x180001fcc`

## pseudocode

```c
char __fastcall _scrt_initialize_crt(int a1)
{
  __int64 v1; // rcx
  __int64 v2; // rcx

  if ( !a1 )
    byte_180013491 = 1;
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
0x1800016f8  sub     rsp, 28h
0x1800016fc  test    ecx, ecx
0x1800016fe  jnz     short loc_180001707
0x180001700  mov     cs:byte_180013491, 1
0x180001707  call    __isa_available_init
0x18000170c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001711  test    al, al
0x180001713  jnz     short loc_180001719
0x180001715  xor     al, al
0x180001717  jmp     short loc_18000172D
0x180001719  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000171e  test    al, al
0x180001720  jnz     short loc_18000172B
0x180001722  xor     ecx, ecx
0x180001724  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001729  jmp     short loc_180001715
0x18000172b  mov     al, 1
0x18000172d  add     rsp, 28h
0x180001731  retn
```
