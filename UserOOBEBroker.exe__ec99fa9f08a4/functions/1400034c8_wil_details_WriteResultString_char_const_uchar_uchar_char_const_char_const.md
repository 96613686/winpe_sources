# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x1400034c8`
- end: `0x14000353d`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140005564`
- `0x140005968`

## callees

- `0x1400034c8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000350a`
- `msvcrt!memcpy_s` at `0x14000350a`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<char const *>(char *a1, char *a2, _BYTE *a3, _QWORD *a4)
{
  __int64 v6; // rax
  __int64 v7; // rsi
  rsize_t v8; // rdx

  if ( a1 == a2 )
    goto LABEL_10;
  if ( !a3 )
    goto LABEL_10;
  if ( !*a3 )
    goto LABEL_10;
  v6 = -1;
  do
    ++v6;
  while ( a3[v6] );
  v7 = v6 + 1;
  v8 = a2 - a1;
  if ( v8 >= v6 + 1 )
  {
    memcpy_s(a1, v8, a3, v6 + 1);
    if ( a4 )
      *a4 = a1;
    return &a1[v7];
  }
  else
  {
LABEL_10:
    if ( a4 )
      *a4 = 0;
    return a1;
  }
}

```

## disassembly

```asm
0x1400034c8  mov     [rsp+arg_0], rbx
0x1400034cd  mov     [rsp+arg_8], rsi
0x1400034d2  push    rdi
0x1400034d3  sub     rsp, 20h
0x1400034d7  mov     rbx, r9
0x1400034da  mov     rdi, rcx
0x1400034dd  cmp     rcx, rdx
0x1400034e0  jz      short loc_14000351E
0x1400034e2  test    r8, r8
0x1400034e5  jz      short loc_14000351E
0x1400034e7  cmp     byte ptr [r8], 0
0x1400034eb  jz      short loc_14000351E
0x1400034ed  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400034f1  inc     rax
0x1400034f4  cmp     byte ptr [r8+rax], 0
0x1400034f9  jnz     short loc_1400034F1
0x1400034fb  lea     rsi, [rax+1]
0x1400034ff  sub     rdx, rdi; DestinationSize
0x140003502  cmp     rdx, rsi
0x140003505  jb      short loc_14000351E
0x140003507  mov     r9, rsi; SourceSize
0x14000350a  call    cs:__imp_memcpy_s
0x140003510  test    rbx, rbx
0x140003513  jz      short loc_140003518
0x140003515  mov     [rbx], rdi
0x140003518  lea     rax, [rsi+rdi]
0x14000351c  jmp     short loc_14000352D
0x14000351e  test    rbx, rbx
0x140003521  jz      short loc_14000352A
0x140003523  mov     qword ptr [r9], 0
0x14000352a  mov     rax, rdi
0x14000352d  mov     rbx, [rsp+28h+arg_0]
0x140003532  mov     rsi, [rsp+28h+arg_8]
0x140003537  add     rsp, 20h
0x14000353b  pop     rdi
0x14000353c  retn
```
