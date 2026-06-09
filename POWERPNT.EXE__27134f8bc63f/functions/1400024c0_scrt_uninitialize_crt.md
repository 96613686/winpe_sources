# __scrt_uninitialize_crt

- ea: `0x1400024c0`
- end: `0x1400024e9`
- name: `__scrt_uninitialize_crt`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001ac0`

## callees

- `0x140001d34`
- `0x1400024c0`

## pseudocode

```c
char __fastcall _scrt_uninitialize_crt(__int64 a1, char a2)
{
  if ( !byte_140005188 || !a2 )
  {
    _scrt_stub_for_acrt_uninitialize();
    _scrt_stub_for_acrt_uninitialize();
  }
  return 1;
}

```

## disassembly

```asm
0x1400024c0  push    rbx
0x1400024c2  sub     rsp, 20h
0x1400024c6  cmp     cs:byte_140005188, 0
0x1400024cd  mov     bl, cl
0x1400024cf  jz      short loc_1400024D5
0x1400024d1  test    dl, dl
0x1400024d3  jnz     short loc_1400024E1
0x1400024d5  call    __scrt_stub_for_acrt_uninitialize
0x1400024da  mov     cl, bl
0x1400024dc  call    __scrt_stub_for_acrt_uninitialize
0x1400024e1  mov     al, 1
0x1400024e3  add     rsp, 20h
0x1400024e7  pop     rbx
0x1400024e8  retn
```
