# av_buffer_unref

- ea: `0x18002f210`
- end: `0x18002f22b`
- name: `av_buffer_unref`
- size: `27`
- prototype: ``
- caller_count: `18`
- callee_count: `2`
- tags: ``

## callers

- `0x180035c90`
- `0x18003b750`
- `0x18003ba10`
- `0x18003bd20`
- `0x18003bfe0`
- `0x18003f090`
- `0x18003f0e0`
- `0x18003f2d0`
- `0x18003f3e0`
- `0x18003f600`
- `0x18003fa00`
- `0x180050760`
- `0x180050880`
- `0x180050b50`
- `0x180050d58`
- `0x180050d8c`
- `0x1800778d0`
- `0x1800779d0`

## callees

- `0x18002f210`
- `0x18002f2e8`

## pseudocode

```c
__int64 __fastcall av_buffer_unref(_QWORD *a1)
{
  __int64 result; // rax

  if ( a1 )
  {
    if ( *a1 )
      return sub_18002F2E8(a1, 0);
  }
  return result;
}

```

## disassembly

```asm
0x18002f210  sub     rsp, 28h
0x18002f214  test    rcx, rcx
0x18002f217  jz      short loc_18002F226
0x18002f219  cmp     qword ptr [rcx], 0
0x18002f21d  jz      short loc_18002F226
0x18002f21f  xor     edx, edx
0x18002f221  call    sub_18002F2E8
0x18002f226  add     rsp, 28h
0x18002f22a  retn
```
