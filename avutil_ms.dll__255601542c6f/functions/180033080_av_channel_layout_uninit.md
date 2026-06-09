# av_channel_layout_uninit

- ea: `0x180033080`
- end: `0x1800330aa`
- name: `av_channel_layout_uninit`
- size: `42`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180032150`
- `0x180032620`
- `0x180032d00`
- `0x18003bd20`
- `0x1800465b0`
- `0x180047710`
- `0x180048e4c`
- `0x180049c20`

## callees

- `0x180033080`
- `0x1800449d0`
- `0x18007b020`

## pseudocode

```c
__m128i *__fastcall av_channel_layout_uninit(__int64 a1)
{
  if ( *(_DWORD *)a1 == 2 )
    av_freep((__m128i *)(a1 + 8));
  return sub_18007B020((__m128i *)a1, 0, 0x18u);
}

```

## disassembly

```asm
0x180033080  push    rbx
0x180033082  sub     rsp, 20h
0x180033086  cmp     dword ptr [rcx], 2
0x180033089  mov     rbx, rcx
0x18003308c  jnz     short loc_180033097
0x18003308e  add     rcx, 8
0x180033092  call    av_freep
0x180033097  xor     edx, edx
0x180033099  mov     rcx, rbx
0x18003309c  lea     r8d, [rdx+18h]
0x1800330a0  add     rsp, 20h
0x1800330a4  pop     rbx
0x1800330a5  jmp     sub_18007B020
```
