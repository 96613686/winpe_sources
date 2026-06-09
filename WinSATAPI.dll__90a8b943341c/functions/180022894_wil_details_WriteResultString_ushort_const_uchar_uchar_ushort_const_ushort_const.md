# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180022894`
- end: `0x18002291a`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `134`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18002732c`
- `0x180027590`

## callees

- `0x180022894`
- `0x180027144`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800228df`
- `msvcrt!memcpy_s` at `0x1800228df`

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
0x180022894  mov     [rsp+arg_0], rbx
0x180022899  mov     [rsp+arg_8], rbp
0x18002289e  mov     [rsp+arg_10], rsi
0x1800228a3  push    rdi
0x1800228a4  sub     rsp, 20h
0x1800228a8  xor     ebp, ebp
0x1800228aa  mov     rbx, r9
0x1800228ad  mov     r10, rdx
0x1800228b0  mov     rdi, rcx
0x1800228b3  cmp     rcx, rdx
0x1800228b6  jz      short loc_1800228F9
0x1800228b8  test    r8, r8
0x1800228bb  jz      short loc_1800228F9
0x1800228bd  cmp     [r8], bp
0x1800228c1  jz      short loc_1800228F9
0x1800228c3  mov     rcx, r8; this
0x1800228c6  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800228cb  sub     r10, rdi
0x1800228ce  mov     rsi, rax
0x1800228d1  cmp     r10, rax
0x1800228d4  jb      short loc_1800228F9
0x1800228d6  mov     r9, rax; SourceSize
0x1800228d9  mov     rdx, r10; DestinationSize
0x1800228dc  mov     rcx, rdi; Destination
0x1800228df  call    cs:__imp_memcpy_s
0x1800228e6  nop     dword ptr [rax+rax+00h]
0x1800228eb  test    rbx, rbx
0x1800228ee  jz      short loc_1800228F3
0x1800228f0  mov     [rbx], rdi
0x1800228f3  lea     rax, [rsi+rdi]
0x1800228f7  jmp     short loc_180022904
0x1800228f9  test    rbx, rbx
0x1800228fc  jz      short loc_180022901
0x1800228fe  mov     [r9], rbp
0x180022901  mov     rax, rdi
0x180022904  mov     rbx, [rsp+28h+arg_0]
0x180022909  mov     rbp, [rsp+28h+arg_8]
0x18002290e  mov     rsi, [rsp+28h+arg_10]
0x180022913  add     rsp, 20h
0x180022917  pop     rdi
0x180022918  retn
```
