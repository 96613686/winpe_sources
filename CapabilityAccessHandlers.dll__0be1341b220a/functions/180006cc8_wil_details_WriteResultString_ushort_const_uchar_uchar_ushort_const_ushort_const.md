# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180006cc8`
- end: `0x180006d2f`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800091a0`
- `0x1800092dc`

## callees

- `0x1800034d8`
- `0x180006cc8`
- `0x180009098`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<unsigned short const *>(
        unsigned __int16 *Destination,
        const unsigned __int16 *a2,
        wil::details *a3,
        unsigned __int16 **a4)
{
  rsize_t v6; // rax
  const void *v7; // r8
  __int64 v8; // r10
  rsize_t v9; // r10
  rsize_t v10; // rsi

  if ( Destination != a2
    && a3
    && *(_WORD *)a3
    && (v6 = wil::details::ResultStringSize(a3, a2), v9 = v8 - (_QWORD)Destination, v10 = v6, v9 >= v6) )
  {
    memcpy_s(Destination, v9, v7, v6);
    if ( a4 )
      *a4 = Destination;
    return (char *)Destination + v10;
  }
  else
  {
    if ( a4 )
      *a4 = 0;
    return (char *)Destination;
  }
}

```

## disassembly

```asm
0x180006cc8  push    rbx
0x180006cca  push    rbp
0x180006ccb  push    rsi
0x180006ccc  push    rdi
0x180006ccd  sub     rsp, 28h
0x180006cd1  xor     ebp, ebp
0x180006cd3  mov     rbx, r9
0x180006cd6  mov     r10, rdx
0x180006cd9  mov     rdi, rcx
0x180006cdc  cmp     rcx, rdx
0x180006cdf  jz      short loc_180006D1B
0x180006ce1  test    r8, r8
0x180006ce4  jz      short loc_180006D1B
0x180006ce6  cmp     [r8], bp
0x180006cea  jz      short loc_180006D1B
0x180006cec  mov     rcx, r8; this
0x180006cef  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180006cf4  sub     r10, rdi
0x180006cf7  mov     rsi, rax
0x180006cfa  cmp     r10, rax
0x180006cfd  jb      short loc_180006D1B
0x180006cff  mov     r9, rax; SourceSize
0x180006d02  mov     rdx, r10; DestinationSize
0x180006d05  mov     rcx, rdi; Destination
0x180006d08  call    memcpy_s
0x180006d0d  test    rbx, rbx
0x180006d10  jz      short loc_180006D15
0x180006d12  mov     [rbx], rdi
0x180006d15  lea     rax, [rsi+rdi]
0x180006d19  jmp     short loc_180006D26
0x180006d1b  test    rbx, rbx
0x180006d1e  jz      short loc_180006D23
0x180006d20  mov     [r9], rbp
0x180006d23  mov     rax, rdi
0x180006d26  add     rsp, 28h
0x180006d2a  pop     rdi
0x180006d2b  pop     rsi
0x180006d2c  pop     rbp
0x180006d2d  pop     rbx
0x180006d2e  retn
```
