# av_frame_new_side_data_from_buf

- ea: `0x18003b7b0`
- end: `0x18003b7cb`
- name: `av_frame_new_side_data_from_buf`
- size: `27`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180035c90`
- `0x1800778d0`
- `0x1800779d0`

## callees

- `0x180050d2c`

## pseudocode

```c
__int64 __fastcall av_frame_new_side_data_from_buf(__int64 a1, unsigned int a2, __int64 a3)
{
  return sub_180050D2C(a1 + 264, a1 + 272, a2, a3);
}

```

## disassembly

```asm
0x18003b7b0  mov     eax, edx
0x18003b7b2  mov     r9, r8
0x18003b7b5  lea     rdx, [rcx+110h]
0x18003b7bc  mov     r8d, eax
0x18003b7bf  add     rcx, 108h
0x18003b7c6  jmp     sub_180050D2C
```
