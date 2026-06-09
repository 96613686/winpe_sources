# __scrt_uninitialize_crt

- ea: `0x1800018c8`
- end: `0x1800018f1`
- name: `__scrt_uninitialize_crt`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001268`

## callees

- `0x1800018c8`
- `0x180001dac`

## pseudocode

```c
char __fastcall _scrt_uninitialize_crt(__int64 a1, char a2)
{
  if ( !byte_1800B33B1 || !a2 )
  {
    _scrt_stub_for_acrt_uninitialize_critical();
    _scrt_stub_for_acrt_uninitialize_critical();
  }
  return 1;
}

```

## disassembly

```asm
0x1800018c8  push    rbx
0x1800018ca  sub     rsp, 20h
0x1800018ce  cmp     cs:byte_1800B33B1, 0
0x1800018d5  mov     bl, cl
0x1800018d7  jz      short loc_1800018DD
0x1800018d9  test    dl, dl
0x1800018db  jnz     short loc_1800018E9
0x1800018dd  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800018e2  mov     cl, bl
0x1800018e4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800018e9  mov     al, 1
0x1800018eb  add     rsp, 20h
0x1800018ef  pop     rbx
0x1800018f0  retn
```
