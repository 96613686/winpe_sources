# __scrt_uninitialize_crt

- ea: `0x180001844`
- end: `0x18000186d`
- name: `__scrt_uninitialize_crt`
- size: `41`
- prototype: `char __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800011e8`

## callees

- `0x180001844`
- `0x180001c60`

## pseudocode

```c
char __fastcall _scrt_uninitialize_crt(__int64 a1, char a2)
{
  if ( !byte_1800040F1 || !a2 )
  {
    _scrt_stub_for_acrt_uninitialize_critical();
    _scrt_stub_for_acrt_uninitialize_critical();
  }
  return 1;
}

```

## disassembly

```asm
0x180001844  push    rbx
0x180001846  sub     rsp, 20h
0x18000184a  cmp     cs:byte_1800040F1, 0
0x180001851  mov     bl, cl
0x180001853  jz      short loc_180001859
0x180001855  test    dl, dl
0x180001857  jnz     short loc_180001865
0x180001859  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000185e  mov     cl, bl
0x180001860  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001865  mov     al, 1
0x180001867  add     rsp, 20h
0x18000186b  pop     rbx
0x18000186c  retn
```
