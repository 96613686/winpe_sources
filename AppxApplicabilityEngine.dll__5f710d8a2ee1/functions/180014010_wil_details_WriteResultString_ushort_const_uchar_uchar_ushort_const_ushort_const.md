# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180014010`
- end: `0x180014078`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001584c`
- `0x180015988`

## callees

- `0x180014010`
- `0x180015710`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180014050`
- `msvcrt!memcpy_s` at `0x180014050`

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
0x180014010  push    rbx
0x180014012  push    rbp
0x180014013  push    rsi
0x180014014  push    rdi
0x180014015  sub     rsp, 28h
0x180014019  xor     ebp, ebp
0x18001401b  mov     rbx, r9
0x18001401e  mov     r10, rdx
0x180014021  mov     rdi, rcx
0x180014024  cmp     rcx, rdx
0x180014027  jz      short loc_180014064
0x180014029  test    r8, r8
0x18001402c  jz      short loc_180014064
0x18001402e  cmp     [r8], bp
0x180014032  jz      short loc_180014064
0x180014034  mov     rcx, r8; this
0x180014037  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18001403c  sub     r10, rdi
0x18001403f  mov     rsi, rax
0x180014042  cmp     r10, rax
0x180014045  jb      short loc_180014064
0x180014047  mov     r9, rax; SourceSize
0x18001404a  mov     rdx, r10; DestinationSize
0x18001404d  mov     rcx, rdi; Destination
0x180014050  call    cs:__imp_memcpy_s
0x180014056  test    rbx, rbx
0x180014059  jz      short loc_18001405E
0x18001405b  mov     [rbx], rdi
0x18001405e  lea     rax, [rsi+rdi]
0x180014062  jmp     short loc_18001406F
0x180014064  test    rbx, rbx
0x180014067  jz      short loc_18001406C
0x180014069  mov     [r9], rbp
0x18001406c  mov     rax, rdi
0x18001406f  add     rsp, 28h
0x180014073  pop     rdi
0x180014074  pop     rsi
0x180014075  pop     rbp
0x180014076  pop     rbx
0x180014077  retn
```
