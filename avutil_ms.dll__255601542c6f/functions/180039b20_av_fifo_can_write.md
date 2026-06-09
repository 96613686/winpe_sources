# av_fifo_can_write

- ea: `0x180039b20`
- end: `0x180039b3b`
- name: `av_fifo_can_write`
- size: `27`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002aad0`
- `0x180051cf0`

## callees

- `0x180039af0`

## pseudocode

```c
__int64 __fastcall av_fifo_can_write(__int64 a1)
{
  __int64 v1; // rbx

  v1 = *(_QWORD *)(a1 + 16);
  return v1 - av_fifo_can_read(a1);
}

```

## disassembly

```asm
0x180039b20  push    rbx
0x180039b22  sub     rsp, 20h
0x180039b26  mov     rbx, [rcx+10h]
0x180039b2a  call    av_fifo_can_read
0x180039b2f  sub     rbx, rax
0x180039b32  mov     rax, rbx
0x180039b35  add     rsp, 20h
0x180039b39  pop     rbx
0x180039b3a  retn
```
