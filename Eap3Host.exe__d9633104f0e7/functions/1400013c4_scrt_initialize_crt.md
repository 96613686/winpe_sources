# __scrt_initialize_crt

- ea: `0x1400013c4`
- end: `0x1400013fe`
- name: `__scrt_initialize_crt`
- size: `58`
- prototype: `char __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140001180`

## callees

- `0x1400013c4`
- `0x1400016dc`
- `0x140001970`

## pseudocode

```c
char __fastcall _scrt_initialize_crt(int a1)
{
  if ( !a1 )
    byte_140006191 = 1;
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
0x1400013c4  sub     rsp, 28h
0x1400013c8  test    ecx, ecx
0x1400013ca  jnz     short loc_1400013D3
0x1400013cc  mov     cs:byte_140006191, 1
0x1400013d3  call    __isa_available_init
0x1400013d8  call    __scrt_stub_for_acrt_uninitialize
0x1400013dd  test    al, al
0x1400013df  jnz     short loc_1400013E5
0x1400013e1  xor     al, al
0x1400013e3  jmp     short loc_1400013F9
0x1400013e5  call    __scrt_stub_for_acrt_uninitialize
0x1400013ea  test    al, al
0x1400013ec  jnz     short loc_1400013F7
0x1400013ee  xor     ecx, ecx
0x1400013f0  call    __scrt_stub_for_acrt_uninitialize
0x1400013f5  jmp     short loc_1400013E1
0x1400013f7  mov     al, 1
0x1400013f9  add     rsp, 28h
0x1400013fd  retn
```
