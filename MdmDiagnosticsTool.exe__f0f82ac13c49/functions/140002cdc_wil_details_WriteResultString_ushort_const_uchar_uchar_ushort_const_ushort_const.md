# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x140002cdc`
- end: `0x140002d44`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400062cc`
- `0x140006408`

## callees

- `0x140002cdc`
- `0x1400061e8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140002d1c`
- `msvcrt!memcpy_s` at `0x140002d1c`

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
0x140002cdc  push    rbx
0x140002cde  push    rbp
0x140002cdf  push    rsi
0x140002ce0  push    rdi
0x140002ce1  sub     rsp, 28h
0x140002ce5  xor     ebp, ebp
0x140002ce7  mov     rbx, r9
0x140002cea  mov     r10, rdx
0x140002ced  mov     rdi, rcx
0x140002cf0  cmp     rcx, rdx
0x140002cf3  jz      short loc_140002D30
0x140002cf5  test    r8, r8
0x140002cf8  jz      short loc_140002D30
0x140002cfa  cmp     [r8], bp
0x140002cfe  jz      short loc_140002D30
0x140002d00  mov     rcx, r8; this
0x140002d03  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x140002d08  sub     r10, rdi
0x140002d0b  mov     rsi, rax
0x140002d0e  cmp     r10, rax
0x140002d11  jb      short loc_140002D30
0x140002d13  mov     r9, rax; SourceSize
0x140002d16  mov     rdx, r10; DestinationSize
0x140002d19  mov     rcx, rdi; Destination
0x140002d1c  call    cs:__imp_memcpy_s
0x140002d22  test    rbx, rbx
0x140002d25  jz      short loc_140002D2A
0x140002d27  mov     [rbx], rdi
0x140002d2a  lea     rax, [rsi+rdi]
0x140002d2e  jmp     short loc_140002D3B
0x140002d30  test    rbx, rbx
0x140002d33  jz      short loc_140002D38
0x140002d35  mov     [r9], rbp
0x140002d38  mov     rax, rdi
0x140002d3b  add     rsp, 28h
0x140002d3f  pop     rdi
0x140002d40  pop     rsi
0x140002d41  pop     rbp
0x140002d42  pop     rbx
0x140002d43  retn
```
