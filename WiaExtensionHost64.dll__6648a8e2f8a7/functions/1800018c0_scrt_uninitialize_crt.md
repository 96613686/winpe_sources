# __scrt_uninitialize_crt

- ea: `0x1800018c0`
- end: `0x1800018e9`
- name: `__scrt_uninitialize_crt`
- size: `41`
- prototype: `char __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001228`

## callees

- `0x1800018c0`
- `0x180001d24`

## pseudocode

```c
char __fastcall _scrt_uninitialize_crt(__int64 a1, char a2)
{
  if ( !byte_1800050F1 || !a2 )
  {
    _scrt_stub_for_acrt_uninitialize_critical();
    _scrt_stub_for_acrt_uninitialize_critical();
  }
  return 1;
}

```

## disassembly

```asm
0x1800018c0  push    rbx
0x1800018c2  sub     rsp, 20h
0x1800018c6  cmp     cs:byte_1800050F1, 0
0x1800018cd  mov     bl, cl
0x1800018cf  jz      short loc_1800018D5
0x1800018d1  test    dl, dl
0x1800018d3  jnz     short loc_1800018E1
0x1800018d5  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800018da  mov     cl, bl
0x1800018dc  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800018e1  mov     al, 1
0x1800018e3  add     rsp, 20h
0x1800018e7  pop     rbx
0x1800018e8  retn
```
