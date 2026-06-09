# __scrt_uninitialize_crt

- ea: `0x180001898`
- end: `0x1800018c1`
- name: `__scrt_uninitialize_crt`
- size: `41`
- prototype: `char __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800011e8`

## callees

- `0x180001898`
- `0x180001fcc`

## pseudocode

```c
char __fastcall _scrt_uninitialize_crt(__int64 a1, char a2)
{
  if ( !byte_180013491 || !a2 )
  {
    _scrt_stub_for_acrt_uninitialize_critical();
    _scrt_stub_for_acrt_uninitialize_critical();
  }
  return 1;
}

```

## disassembly

```asm
0x180001898  push    rbx
0x18000189a  sub     rsp, 20h
0x18000189e  cmp     cs:byte_180013491, 0
0x1800018a5  mov     bl, cl
0x1800018a7  jz      short loc_1800018AD
0x1800018a9  test    dl, dl
0x1800018ab  jnz     short loc_1800018B9
0x1800018ad  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800018b2  mov     cl, bl
0x1800018b4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800018b9  mov     al, 1
0x1800018bb  add     rsp, 20h
0x1800018bf  pop     rbx
0x1800018c0  retn
```
