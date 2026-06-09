# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180003b14`
- end: `0x180003b7b`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000629c`

## callees

- `0x180003b14`
- `0x1800061e0`
- `0x180006c80`

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
    memcpy_s_0(Destination, v9, v7, v6);
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
0x180003b14  push    rbx
0x180003b16  push    rbp
0x180003b17  push    rsi
0x180003b18  push    rdi
0x180003b19  sub     rsp, 28h
0x180003b1d  xor     ebp, ebp
0x180003b1f  mov     rbx, r9
0x180003b22  mov     r10, rdx
0x180003b25  mov     rdi, rcx
0x180003b28  cmp     rcx, rdx
0x180003b2b  jz      short loc_180003B67
0x180003b2d  test    r8, r8
0x180003b30  jz      short loc_180003B67
0x180003b32  cmp     [r8], bp
0x180003b36  jz      short loc_180003B67
0x180003b38  mov     rcx, r8; this
0x180003b3b  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180003b40  sub     r10, rdi
0x180003b43  mov     rsi, rax
0x180003b46  cmp     r10, rax
0x180003b49  jb      short loc_180003B67
0x180003b4b  mov     r9, rax; SourceSize
0x180003b4e  mov     rdx, r10; DestinationSize
0x180003b51  mov     rcx, rdi; Destination
0x180003b54  call    memcpy_s_0
0x180003b59  test    rbx, rbx
0x180003b5c  jz      short loc_180003B61
0x180003b5e  mov     [rbx], rdi
0x180003b61  lea     rax, [rsi+rdi]
0x180003b65  jmp     short loc_180003B72
0x180003b67  test    rbx, rbx
0x180003b6a  jz      short loc_180003B6F
0x180003b6c  mov     [r9], rbp
0x180003b6f  mov     rax, rdi
0x180003b72  add     rsp, 28h
0x180003b76  pop     rdi
0x180003b77  pop     rsi
0x180003b78  pop     rbp
0x180003b79  pop     rbx
0x180003b7a  retn
```
