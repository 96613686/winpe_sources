# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x18000f27c`
- end: `0x18000f2e4`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180011510`
- `0x180011728`

## callees

- `0x18000f27c`
- `0x180011440`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000f2bc`
- `msvcrt!memcpy_s` at `0x18000f2bc`

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
0x18000f27c  push    rbx
0x18000f27e  push    rbp
0x18000f27f  push    rsi
0x18000f280  push    rdi
0x18000f281  sub     rsp, 28h
0x18000f285  xor     ebp, ebp
0x18000f287  mov     rbx, r9
0x18000f28a  mov     r10, rdx
0x18000f28d  mov     rdi, rcx
0x18000f290  cmp     rcx, rdx
0x18000f293  jz      short loc_18000F2D0
0x18000f295  test    r8, r8
0x18000f298  jz      short loc_18000F2D0
0x18000f29a  cmp     [r8], bp
0x18000f29e  jz      short loc_18000F2D0
0x18000f2a0  mov     rcx, r8; this
0x18000f2a3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000f2a8  sub     r10, rdi
0x18000f2ab  mov     rsi, rax
0x18000f2ae  cmp     r10, rax
0x18000f2b1  jb      short loc_18000F2D0
0x18000f2b3  mov     r9, rax; SourceSize
0x18000f2b6  mov     rdx, r10; DestinationSize
0x18000f2b9  mov     rcx, rdi; Destination
0x18000f2bc  call    cs:__imp_memcpy_s
0x18000f2c2  test    rbx, rbx
0x18000f2c5  jz      short loc_18000F2CA
0x18000f2c7  mov     [rbx], rdi
0x18000f2ca  lea     rax, [rsi+rdi]
0x18000f2ce  jmp     short loc_18000F2DB
0x18000f2d0  test    rbx, rbx
0x18000f2d3  jz      short loc_18000F2D8
0x18000f2d5  mov     [r9], rbp
0x18000f2d8  mov     rax, rdi
0x18000f2db  add     rsp, 28h
0x18000f2df  pop     rdi
0x18000f2e0  pop     rsi
0x18000f2e1  pop     rbp
0x18000f2e2  pop     rbx
0x18000f2e3  retn
```
