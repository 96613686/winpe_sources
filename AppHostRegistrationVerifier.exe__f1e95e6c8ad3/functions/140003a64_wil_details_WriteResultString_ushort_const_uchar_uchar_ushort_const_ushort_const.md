# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x140003a64`
- end: `0x140003acb`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140006b50`
- `0x140006c8c`

## callees

- `0x140003a64`
- `0x1400069f8`
- `0x1400080c0`

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
0x140003a64  push    rbx
0x140003a66  push    rbp
0x140003a67  push    rsi
0x140003a68  push    rdi
0x140003a69  sub     rsp, 28h
0x140003a6d  xor     ebp, ebp
0x140003a6f  mov     rbx, r9
0x140003a72  mov     r10, rdx
0x140003a75  mov     rdi, rcx
0x140003a78  cmp     rcx, rdx
0x140003a7b  jz      short loc_140003AB7
0x140003a7d  test    r8, r8
0x140003a80  jz      short loc_140003AB7
0x140003a82  cmp     [r8], bp
0x140003a86  jz      short loc_140003AB7
0x140003a88  mov     rcx, r8; this
0x140003a8b  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x140003a90  sub     r10, rdi
0x140003a93  mov     rsi, rax
0x140003a96  cmp     r10, rax
0x140003a99  jb      short loc_140003AB7
0x140003a9b  mov     r9, rax; SourceSize
0x140003a9e  mov     rdx, r10; DestinationSize
0x140003aa1  mov     rcx, rdi; Destination
0x140003aa4  call    memcpy_s
0x140003aa9  test    rbx, rbx
0x140003aac  jz      short loc_140003AB1
0x140003aae  mov     [rbx], rdi
0x140003ab1  lea     rax, [rsi+rdi]
0x140003ab5  jmp     short loc_140003AC2
0x140003ab7  test    rbx, rbx
0x140003aba  jz      short loc_140003ABF
0x140003abc  mov     [r9], rbp
0x140003abf  mov     rax, rdi
0x140003ac2  add     rsp, 28h
0x140003ac6  pop     rdi
0x140003ac7  pop     rsi
0x140003ac8  pop     rbp
0x140003ac9  pop     rbx
0x140003aca  retn
```
