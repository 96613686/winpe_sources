# __scrt_uninitialize_crt

- ea: `0x1800018b4`
- end: `0x1800018dd`
- name: `__scrt_uninitialize_crt`
- size: `41`
- prototype: `char __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001248`

## callees

- `0x1800018b4`
- `0x180001d8c`

## pseudocode

```c
char __fastcall _scrt_uninitialize_crt(__int64 a1, char a2)
{
  if ( !byte_1800070F1 || !a2 )
  {
    _scrt_stub_for_acrt_uninitialize_critical();
    _scrt_stub_for_acrt_uninitialize_critical();
  }
  return 1;
}

```

## disassembly

```asm
0x1800018b4  push    rbx
0x1800018b6  sub     rsp, 20h
0x1800018ba  cmp     cs:byte_1800070F1, 0
0x1800018c1  mov     bl, cl
0x1800018c3  jz      short loc_1800018C9
0x1800018c5  test    dl, dl
0x1800018c7  jnz     short loc_1800018D5
0x1800018c9  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800018ce  mov     cl, bl
0x1800018d0  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800018d5  mov     al, 1
0x1800018d7  add     rsp, 20h
0x1800018db  pop     rbx
0x1800018dc  retn
```
