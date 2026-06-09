# __scrt_uninitialize_crt

- ea: `0x140001564`
- end: `0x14000158d`
- name: `__scrt_uninitialize_crt`
- size: `41`
- prototype: `char __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001180`

## callees

- `0x140001564`
- `0x1400016dc`

## pseudocode

```c
char __fastcall _scrt_uninitialize_crt(__int64 a1, char a2)
{
  if ( !byte_140006191 || !a2 )
  {
    _scrt_stub_for_acrt_uninitialize();
    _scrt_stub_for_acrt_uninitialize();
  }
  return 1;
}

```

## disassembly

```asm
0x140001564  push    rbx
0x140001566  sub     rsp, 20h
0x14000156a  cmp     cs:byte_140006191, 0
0x140001571  mov     bl, cl
0x140001573  jz      short loc_140001579
0x140001575  test    dl, dl
0x140001577  jnz     short loc_140001585
0x140001579  call    __scrt_stub_for_acrt_uninitialize
0x14000157e  mov     cl, bl
0x140001580  call    __scrt_stub_for_acrt_uninitialize
0x140001585  mov     al, 1
0x140001587  add     rsp, 20h
0x14000158b  pop     rbx
0x14000158c  retn
```
