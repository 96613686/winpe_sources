# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180008700`
- end: `0x180008768`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b3cc`
- `0x18000b508`

## callees

- `0x180008700`
- `0x18000b300`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180008740`
- `msvcrt!memcpy_s` at `0x180008740`

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
0x180008700  push    rbx
0x180008702  push    rbp
0x180008703  push    rsi
0x180008704  push    rdi
0x180008705  sub     rsp, 28h
0x180008709  xor     ebp, ebp
0x18000870b  mov     rbx, r9
0x18000870e  mov     r10, rdx
0x180008711  mov     rdi, rcx
0x180008714  cmp     rcx, rdx
0x180008717  jz      short loc_180008754
0x180008719  test    r8, r8
0x18000871c  jz      short loc_180008754
0x18000871e  cmp     [r8], bp
0x180008722  jz      short loc_180008754
0x180008724  mov     rcx, r8; this
0x180008727  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000872c  sub     r10, rdi
0x18000872f  mov     rsi, rax
0x180008732  cmp     r10, rax
0x180008735  jb      short loc_180008754
0x180008737  mov     r9, rax; SourceSize
0x18000873a  mov     rdx, r10; DestinationSize
0x18000873d  mov     rcx, rdi; Destination
0x180008740  call    cs:__imp_memcpy_s
0x180008746  test    rbx, rbx
0x180008749  jz      short loc_18000874E
0x18000874b  mov     [rbx], rdi
0x18000874e  lea     rax, [rsi+rdi]
0x180008752  jmp     short loc_18000875F
0x180008754  test    rbx, rbx
0x180008757  jz      short loc_18000875C
0x180008759  mov     [r9], rbp
0x18000875c  mov     rax, rdi
0x18000875f  add     rsp, 28h
0x180008763  pop     rdi
0x180008764  pop     rsi
0x180008765  pop     rbp
0x180008766  pop     rbx
0x180008767  retn
```
