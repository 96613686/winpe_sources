# __scrt_initialize_crt

- ea: `0x140001cf8`
- end: `0x140001d32`
- name: `__scrt_initialize_crt`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140001ac0`

## callees

- `0x1400011c0`
- `0x140001cf8`
- `0x140001d34`

## pseudocode

```c
char __fastcall _scrt_initialize_crt(int a1)
{
  if ( !a1 )
    byte_140005188 = 1;
  _isa_available_init();
  if ( !(unsigned __int8)((__int64 (*)(void))_scrt_stub_for_acrt_uninitialize)() )
    return 0;
  if ( !(unsigned __int8)((__int64 (*)(void))_scrt_stub_for_acrt_uninitialize)() )
  {
    _scrt_stub_for_acrt_uninitialize(0);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x140001cf8  sub     rsp, 28h
0x140001cfc  test    ecx, ecx
0x140001cfe  jnz     short loc_140001D07
0x140001d00  mov     cs:byte_140005188, 1
0x140001d07  call    __isa_available_init
0x140001d0c  call    __scrt_stub_for_acrt_uninitialize
0x140001d11  test    al, al
0x140001d13  jnz     short loc_140001D19
0x140001d15  xor     al, al
0x140001d17  jmp     short loc_140001D2D
0x140001d19  call    __scrt_stub_for_acrt_uninitialize
0x140001d1e  test    al, al
0x140001d20  jnz     short loc_140001D2B
0x140001d22  xor     ecx, ecx
0x140001d24  call    __scrt_stub_for_acrt_uninitialize
0x140001d29  jmp     short loc_140001D15
0x140001d2b  mov     al, 1
0x140001d2d  add     rsp, 28h
0x140001d31  retn
```
