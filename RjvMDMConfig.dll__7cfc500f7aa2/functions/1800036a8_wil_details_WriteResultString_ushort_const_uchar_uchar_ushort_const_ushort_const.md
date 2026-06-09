# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x1800036a8`
- end: `0x180003710`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180004f04`
- `0x18000f650`

## callees

- `0x1800036a8`
- `0x180004d1c`
- `0x18000596c`

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
0x1800036a8  push    rbx
0x1800036aa  push    rbp
0x1800036ab  push    rsi
0x1800036ac  push    rdi
0x1800036ad  sub     rsp, 28h
0x1800036b1  xor     ebp, ebp
0x1800036b3  mov     rbx, r9
0x1800036b6  mov     r10, rdx
0x1800036b9  mov     rdi, rcx
0x1800036bc  cmp     rcx, rdx
0x1800036bf  jz      short loc_1800036FB
0x1800036c1  test    r8, r8
0x1800036c4  jz      short loc_1800036FB
0x1800036c6  cmp     [r8], bp
0x1800036ca  jz      short loc_1800036FB
0x1800036cc  mov     rcx, r8; this
0x1800036cf  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800036d4  sub     r10, rdi
0x1800036d7  mov     rsi, rax
0x1800036da  cmp     r10, rax
0x1800036dd  jb      short loc_1800036FB
0x1800036df  mov     r9, rax; SourceSize
0x1800036e2  mov     rdx, r10; DestinationSize
0x1800036e5  mov     rcx, rdi; Destination
0x1800036e8  call    memcpy_s
0x1800036ed  test    rbx, rbx
0x1800036f0  jz      short loc_1800036F5
0x1800036f2  mov     [rbx], rdi
0x1800036f5  lea     rax, [rsi+rdi]
0x1800036f9  jmp     short loc_180003706
0x1800036fb  test    rbx, rbx
0x1800036fe  jz      short loc_180003703
0x180003700  mov     [r9], rbp
0x180003703  mov     rax, rdi
0x180003706  add     rsp, 28h
0x18000370a  pop     rdi
0x18000370b  pop     rsi
0x18000370c  pop     rbp
0x18000370d  pop     rbx
0x18000370e  retn
```
