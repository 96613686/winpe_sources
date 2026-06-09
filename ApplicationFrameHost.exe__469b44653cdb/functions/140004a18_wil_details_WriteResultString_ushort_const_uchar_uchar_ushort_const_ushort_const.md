# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x140004a18`
- end: `0x140004a7f`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400083f0`
- `0x140008608`

## callees

- `0x140004a18`
- `0x1400082bc`
- `0x140009d98`

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
0x140004a18  push    rbx
0x140004a1a  push    rbp
0x140004a1b  push    rsi
0x140004a1c  push    rdi
0x140004a1d  sub     rsp, 28h
0x140004a21  xor     ebp, ebp
0x140004a23  mov     rbx, r9
0x140004a26  mov     r10, rdx
0x140004a29  mov     rdi, rcx
0x140004a2c  cmp     rcx, rdx
0x140004a2f  jz      short loc_140004A6B
0x140004a31  test    r8, r8
0x140004a34  jz      short loc_140004A6B
0x140004a36  cmp     [r8], bp
0x140004a3a  jz      short loc_140004A6B
0x140004a3c  mov     rcx, r8; this
0x140004a3f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x140004a44  sub     r10, rdi
0x140004a47  mov     rsi, rax
0x140004a4a  cmp     r10, rax
0x140004a4d  jb      short loc_140004A6B
0x140004a4f  mov     r9, rax; SourceSize
0x140004a52  mov     rdx, r10; DestinationSize
0x140004a55  mov     rcx, rdi; Destination
0x140004a58  call    memcpy_s
0x140004a5d  test    rbx, rbx
0x140004a60  jz      short loc_140004A65
0x140004a62  mov     [rbx], rdi
0x140004a65  lea     rax, [rsi+rdi]
0x140004a69  jmp     short loc_140004A76
0x140004a6b  test    rbx, rbx
0x140004a6e  jz      short loc_140004A73
0x140004a70  mov     [r9], rbp
0x140004a73  mov     rax, rdi
0x140004a76  add     rsp, 28h
0x140004a7a  pop     rdi
0x140004a7b  pop     rsi
0x140004a7c  pop     rbp
0x140004a7d  pop     rbx
0x140004a7e  retn
```
