# __scrt_uninitialize_crt

- ea: `0x180001848`
- end: `0x180001871`
- name: `__scrt_uninitialize_crt`
- size: `41`
- prototype: `char __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800011e8`

## callees

- `0x180001848`
- `0x180001e20`

## pseudocode

```c
char __fastcall _scrt_uninitialize_crt(__int64 a1, char a2)
{
  if ( !byte_1800080F1 || !a2 )
  {
    _scrt_stub_for_acrt_uninitialize_critical();
    _scrt_stub_for_acrt_uninitialize_critical();
  }
  return 1;
}

```

## disassembly

```asm
0x180001848  push    rbx
0x18000184a  sub     rsp, 20h
0x18000184e  cmp     cs:byte_1800080F1, 0
0x180001855  mov     bl, cl
0x180001857  jz      short loc_18000185D
0x180001859  test    dl, dl
0x18000185b  jnz     short loc_180001869
0x18000185d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001862  mov     cl, bl
0x180001864  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001869  mov     al, 1
0x18000186b  add     rsp, 20h
0x18000186f  pop     rbx
0x180001870  retn
```
