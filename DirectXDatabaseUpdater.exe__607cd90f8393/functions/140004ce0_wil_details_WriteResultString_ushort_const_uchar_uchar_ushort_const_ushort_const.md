# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x140004ce0`
- end: `0x140004d47`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a590`
- `0x14000a7b8`

## callees

- `0x140004ce0`
- `0x14000a3d8`
- `0x14000eff0`

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
0x140004ce0  push    rbx
0x140004ce2  push    rbp
0x140004ce3  push    rsi
0x140004ce4  push    rdi
0x140004ce5  sub     rsp, 28h
0x140004ce9  xor     ebp, ebp
0x140004ceb  mov     rbx, r9
0x140004cee  mov     r10, rdx
0x140004cf1  mov     rdi, rcx
0x140004cf4  cmp     rcx, rdx
0x140004cf7  jz      short loc_140004D33
0x140004cf9  test    r8, r8
0x140004cfc  jz      short loc_140004D33
0x140004cfe  cmp     [r8], bp
0x140004d02  jz      short loc_140004D33
0x140004d04  mov     rcx, r8; this
0x140004d07  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x140004d0c  sub     r10, rdi
0x140004d0f  mov     rsi, rax
0x140004d12  cmp     r10, rax
0x140004d15  jb      short loc_140004D33
0x140004d17  mov     r9, rax; SourceSize
0x140004d1a  mov     rdx, r10; DestinationSize
0x140004d1d  mov     rcx, rdi; Destination
0x140004d20  call    memcpy_s
0x140004d25  test    rbx, rbx
0x140004d28  jz      short loc_140004D2D
0x140004d2a  mov     [rbx], rdi
0x140004d2d  lea     rax, [rsi+rdi]
0x140004d31  jmp     short loc_140004D3E
0x140004d33  test    rbx, rbx
0x140004d36  jz      short loc_140004D3B
0x140004d38  mov     [r9], rbp
0x140004d3b  mov     rax, rdi
0x140004d3e  add     rsp, 28h
0x140004d42  pop     rdi
0x140004d43  pop     rsi
0x140004d44  pop     rbp
0x140004d45  pop     rbx
0x140004d46  retn
```
