# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x1800036e4`
- end: `0x18000374b`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800094b0`
- `0x1800096e4`

## callees

- `0x1800036e4`
- `0x180009348`
- `0x18000b43c`

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
0x1800036e4  push    rbx
0x1800036e6  push    rbp
0x1800036e7  push    rsi
0x1800036e8  push    rdi
0x1800036e9  sub     rsp, 28h
0x1800036ed  xor     ebp, ebp
0x1800036ef  mov     rbx, r9
0x1800036f2  mov     r10, rdx
0x1800036f5  mov     rdi, rcx
0x1800036f8  cmp     rcx, rdx
0x1800036fb  jz      short loc_180003737
0x1800036fd  test    r8, r8
0x180003700  jz      short loc_180003737
0x180003702  cmp     [r8], bp
0x180003706  jz      short loc_180003737
0x180003708  mov     rcx, r8; this
0x18000370b  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180003710  sub     r10, rdi
0x180003713  mov     rsi, rax
0x180003716  cmp     r10, rax
0x180003719  jb      short loc_180003737
0x18000371b  mov     r9, rax; SourceSize
0x18000371e  mov     rdx, r10; DestinationSize
0x180003721  mov     rcx, rdi; Destination
0x180003724  call    memcpy_s
0x180003729  test    rbx, rbx
0x18000372c  jz      short loc_180003731
0x18000372e  mov     [rbx], rdi
0x180003731  lea     rax, [rsi+rdi]
0x180003735  jmp     short loc_180003742
0x180003737  test    rbx, rbx
0x18000373a  jz      short loc_18000373F
0x18000373c  mov     [r9], rbp
0x18000373f  mov     rax, rdi
0x180003742  add     rsp, 28h
0x180003746  pop     rdi
0x180003747  pop     rsi
0x180003748  pop     rbp
0x180003749  pop     rbx
0x18000374a  retn
```
