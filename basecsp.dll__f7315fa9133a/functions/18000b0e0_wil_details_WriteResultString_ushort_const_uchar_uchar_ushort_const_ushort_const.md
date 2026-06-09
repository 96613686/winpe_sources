# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x18000b0e0`
- end: `0x18000b148`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180016770`
- `0x1800169a4`

## callees

- `0x18000b0e0`
- `0x180016608`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000b120`
- `msvcrt!memcpy_s` at `0x18000b120`

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
0x18000b0e0  push    rbx
0x18000b0e2  push    rbp
0x18000b0e3  push    rsi
0x18000b0e4  push    rdi
0x18000b0e5  sub     rsp, 28h
0x18000b0e9  xor     ebp, ebp
0x18000b0eb  mov     rbx, r9
0x18000b0ee  mov     r10, rdx
0x18000b0f1  mov     rdi, rcx
0x18000b0f4  cmp     rcx, rdx
0x18000b0f7  jz      short loc_18000B134
0x18000b0f9  test    r8, r8
0x18000b0fc  jz      short loc_18000B134
0x18000b0fe  cmp     [r8], bp
0x18000b102  jz      short loc_18000B134
0x18000b104  mov     rcx, r8; this
0x18000b107  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000b10c  sub     r10, rdi
0x18000b10f  mov     rsi, rax
0x18000b112  cmp     r10, rax
0x18000b115  jb      short loc_18000B134
0x18000b117  mov     r9, rax; SourceSize
0x18000b11a  mov     rdx, r10; DestinationSize
0x18000b11d  mov     rcx, rdi; Destination
0x18000b120  call    cs:__imp_memcpy_s
0x18000b126  test    rbx, rbx
0x18000b129  jz      short loc_18000B12E
0x18000b12b  mov     [rbx], rdi
0x18000b12e  lea     rax, [rsi+rdi]
0x18000b132  jmp     short loc_18000B13F
0x18000b134  test    rbx, rbx
0x18000b137  jz      short loc_18000B13C
0x18000b139  mov     [r9], rbp
0x18000b13c  mov     rax, rdi
0x18000b13f  add     rsp, 28h
0x18000b143  pop     rdi
0x18000b144  pop     rsi
0x18000b145  pop     rbp
0x18000b146  pop     rbx
0x18000b147  retn
```
