# __scrt_uninitialize_crt

- ea: `0x180001954`
- end: `0x18000197d`
- name: `__scrt_uninitialize_crt`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800012b8`

## callees

- `0x180001954`
- `0x180001ee4`

## pseudocode

```c
char __fastcall _scrt_uninitialize_crt(__int64 a1, char a2)
{
  if ( !byte_180003080 || !a2 )
  {
    _scrt_stub_for_acrt_uninitialize_critical();
    _scrt_stub_for_acrt_uninitialize_critical();
  }
  return 1;
}

```

## disassembly

```asm
0x180001954  push    rbx
0x180001956  sub     rsp, 20h
0x18000195a  cmp     cs:byte_180003080, 0
0x180001961  mov     bl, cl
0x180001963  jz      short loc_180001969
0x180001965  test    dl, dl
0x180001967  jnz     short loc_180001975
0x180001969  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000196e  mov     cl, bl
0x180001970  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001975  mov     al, 1
0x180001977  add     rsp, 20h
0x18000197b  pop     rbx
0x18000197c  retn
```
