# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x18000691c`
- end: `0x180006983`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000923c`
- `0x180009378`

## callees

- `0x18000691c`
- `0x180009158`
- `0x18000af04`

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
0x18000691c  push    rbx
0x18000691e  push    rbp
0x18000691f  push    rsi
0x180006920  push    rdi
0x180006921  sub     rsp, 28h
0x180006925  xor     ebp, ebp
0x180006927  mov     rbx, r9
0x18000692a  mov     r10, rdx
0x18000692d  mov     rdi, rcx
0x180006930  cmp     rcx, rdx
0x180006933  jz      short loc_18000696F
0x180006935  test    r8, r8
0x180006938  jz      short loc_18000696F
0x18000693a  cmp     [r8], bp
0x18000693e  jz      short loc_18000696F
0x180006940  mov     rcx, r8; this
0x180006943  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180006948  sub     r10, rdi
0x18000694b  mov     rsi, rax
0x18000694e  cmp     r10, rax
0x180006951  jb      short loc_18000696F
0x180006953  mov     r9, rax; SourceSize
0x180006956  mov     rdx, r10; DestinationSize
0x180006959  mov     rcx, rdi; Destination
0x18000695c  call    memcpy_s
0x180006961  test    rbx, rbx
0x180006964  jz      short loc_180006969
0x180006966  mov     [rbx], rdi
0x180006969  lea     rax, [rsi+rdi]
0x18000696d  jmp     short loc_18000697A
0x18000696f  test    rbx, rbx
0x180006972  jz      short loc_180006977
0x180006974  mov     [r9], rbp
0x180006977  mov     rax, rdi
0x18000697a  add     rsp, 28h
0x18000697e  pop     rdi
0x18000697f  pop     rsi
0x180006980  pop     rbp
0x180006981  pop     rbx
0x180006982  retn
```
