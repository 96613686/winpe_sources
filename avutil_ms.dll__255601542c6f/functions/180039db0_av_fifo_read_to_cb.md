# av_fifo_read_to_cb

- ea: `0x180039db0`
- end: `0x180039dfa`
- name: `av_fifo_read_to_cb`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180051aa0`

## callees

- `0x180039b40`
- `0x180039e70`

## pseudocode

```c
__int64 __fastcall av_fifo_read_to_cb(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  unsigned int v6; // ebx

  v6 = sub_180039E70(a1, 0, (_DWORD)a4, 0, a2, a3);
  av_fifo_drain2(a1, *a4);
  return v6;
}

```

## disassembly

```asm
0x180039db0  mov     rax, rsp
0x180039db3  mov     [rax+8], rbx
0x180039db7  mov     [rax+10h], rsi
0x180039dbb  push    rdi
0x180039dbc  sub     rsp, 30h
0x180039dc0  mov     rsi, r9
0x180039dc3  mov     [rax-10h], r8
0x180039dc7  mov     [rax-18h], rdx
0x180039dcb  mov     r8, rsi
0x180039dce  xor     edx, edx
0x180039dd0  xor     r9d, r9d
0x180039dd3  mov     rdi, rcx
0x180039dd6  call    sub_180039E70
0x180039ddb  mov     rdx, [rsi]
0x180039dde  mov     rcx, rdi
0x180039de1  mov     ebx, eax
0x180039de3  call    av_fifo_drain2
0x180039de8  mov     rsi, [rsp+38h+arg_8]
0x180039ded  mov     eax, ebx
0x180039def  mov     rbx, [rsp+38h+arg_0]
0x180039df4  add     rsp, 30h
0x180039df8  pop     rdi
0x180039df9  retn
```
