# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x1400034e4`
- end: `0x14000354c`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140005750`
- `0x14000588c`

## callees

- `0x1400034e4`
- `0x14000563c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140003524`
- `msvcrt!memcpy_s` at `0x140003524`

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
0x1400034e4  push    rbx
0x1400034e6  push    rbp
0x1400034e7  push    rsi
0x1400034e8  push    rdi
0x1400034e9  sub     rsp, 28h
0x1400034ed  xor     ebp, ebp
0x1400034ef  mov     rbx, r9
0x1400034f2  mov     r10, rdx
0x1400034f5  mov     rdi, rcx
0x1400034f8  cmp     rcx, rdx
0x1400034fb  jz      short loc_140003538
0x1400034fd  test    r8, r8
0x140003500  jz      short loc_140003538
0x140003502  cmp     [r8], bp
0x140003506  jz      short loc_140003538
0x140003508  mov     rcx, r8; this
0x14000350b  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x140003510  sub     r10, rdi
0x140003513  mov     rsi, rax
0x140003516  cmp     r10, rax
0x140003519  jb      short loc_140003538
0x14000351b  mov     r9, rax; SourceSize
0x14000351e  mov     rdx, r10; DestinationSize
0x140003521  mov     rcx, rdi; Destination
0x140003524  call    cs:__imp_memcpy_s
0x14000352a  test    rbx, rbx
0x14000352d  jz      short loc_140003532
0x14000352f  mov     [rbx], rdi
0x140003532  lea     rax, [rsi+rdi]
0x140003536  jmp     short loc_140003543
0x140003538  test    rbx, rbx
0x14000353b  jz      short loc_140003540
0x14000353d  mov     [r9], rbp
0x140003540  mov     rax, rdi
0x140003543  add     rsp, 28h
0x140003547  pop     rdi
0x140003548  pop     rsi
0x140003549  pop     rbp
0x14000354a  pop     rbx
0x14000354b  retn
```
