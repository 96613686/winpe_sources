# av_fifo_read

- ea: `0x180039d60`
- end: `0x180039dab`
- name: `av_fifo_read`
- size: `75`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18002aa30`
- `0x180033790`
- `0x180033850`
- `0x180033900`
- `0x180051c30`

## callees

- `0x180039b40`
- `0x180039e70`

## pseudocode

```c
__int64 __fastcall av_fifo_read(__int64 a1, int a2, __int64 a3)
{
  unsigned int v4; // ebx
  __int64 v6; // [rsp+50h] [rbp+18h] BYREF

  v6 = a3;
  v4 = sub_180039E70(a1, a2, (unsigned int)&v6, 0, 0, 0);
  av_fifo_drain2(a1, v6);
  return v4;
}

```

## disassembly

```asm
0x180039d60  mov     rax, rsp
0x180039d63  mov     [rax+8], rbx
0x180039d67  mov     [rax+18h], r8
0x180039d6b  push    rdi
0x180039d6c  sub     rsp, 30h
0x180039d70  mov     qword ptr [rax-10h], 0
0x180039d78  lea     r8, [rax+18h]
0x180039d7c  xor     r9d, r9d
0x180039d7f  mov     qword ptr [rax-18h], 0
0x180039d87  mov     rdi, rcx
0x180039d8a  call    sub_180039E70
0x180039d8f  mov     rdx, [rsp+38h+arg_10]
0x180039d94  mov     rcx, rdi
0x180039d97  mov     ebx, eax
0x180039d99  call    av_fifo_drain2
0x180039d9e  mov     eax, ebx
0x180039da0  mov     rbx, [rsp+38h+arg_0]
0x180039da5  add     rsp, 30h
0x180039da9  pop     rdi
0x180039daa  retn
```
