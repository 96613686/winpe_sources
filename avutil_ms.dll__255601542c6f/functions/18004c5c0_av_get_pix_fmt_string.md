# av_get_pix_fmt_string

- ea: `0x18004c5c0`
- end: `0x18004c63b`
- name: `av_get_pix_fmt_string`
- size: `123`
- prototype: `__int64 __fastcall(char *Buffer)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180036514`
- `0x18004c3a0`
- `0x18004c5c0`

## string_xrefs

- `0x18004c5da`: `name nb_components nb_bits`

## pseudocode

```c
char *__fastcall av_get_pix_fmt_string(char *Buffer, int a2, int a3)
{
  size_t v3; // rsi

  v3 = a2;
  if ( a3 >= 0 )
  {
    _mm_lfence();
    av_get_bits_per_pixel(&(&off_18008A690)[14 * a3]);
    sub_180036514(Buffer, v3, "%-11s %7d %10d");
  }
  else
  {
    sub_180036514(Buffer, a2, "name nb_components nb_bits");
  }
  return Buffer;
}

```

## disassembly

```asm
0x18004c5c0  mov     [rsp+arg_0], rbx
0x18004c5c5  mov     [rsp+arg_8], rsi
0x18004c5ca  push    rdi
0x18004c5cb  sub     rsp, 30h
0x18004c5cf  movsxd  rsi, edx
0x18004c5d2  mov     rdi, rcx
0x18004c5d5  test    r8d, r8d
0x18004c5d8  jns     short loc_18004C5EB
0x18004c5da  lea     r8, aNameNbComponen; "name nb_components nb_bits"
0x18004c5e1  mov     rdx, rsi; BufferCount
0x18004c5e4  call    sub_180036514
0x18004c5e9  jmp     short loc_18004C628
0x18004c5eb  lfence
0x18004c5ee  movsxd  rax, r8d
0x18004c5f1  imul    rbx, rax, 70h ; 'p'
0x18004c5f5  lea     rax, off_18008A690; "yuv420p"
0x18004c5fc  add     rbx, rax
0x18004c5ff  mov     rcx, rbx
0x18004c602  call    av_get_bits_per_pixel
0x18004c607  movzx   ecx, byte ptr [rbx+8]
0x18004c60b  lea     r8, a11s7d10d; "%-11s %7d %10d"
0x18004c612  mov     r9, [rbx]
0x18004c615  mov     rdx, rsi; BufferCount
0x18004c618  mov     [rsp+38h+var_10], eax
0x18004c61c  mov     [rsp+38h+var_18], ecx
0x18004c620  mov     rcx, rdi; Buffer
0x18004c623  call    sub_180036514
0x18004c628  mov     rbx, [rsp+38h+arg_0]
0x18004c62d  mov     rax, rdi
0x18004c630  mov     rsi, [rsp+38h+arg_8]
0x18004c635  add     rsp, 30h
0x18004c639  pop     rdi
0x18004c63a  retn
```
