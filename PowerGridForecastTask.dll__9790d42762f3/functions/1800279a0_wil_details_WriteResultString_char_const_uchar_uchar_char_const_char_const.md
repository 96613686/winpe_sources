# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x1800279a0`
- end: `0x180027a15`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: `char *__fastcall(char *, char *, _BYTE *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002dec8`
- `0x18002e2cc`

## callees

- `0x1800279a0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800279e2`
- `msvcrt!memcpy_s` at `0x1800279e2`

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
0x1800279a0  mov     [rsp+arg_0], rbx
0x1800279a5  mov     [rsp+arg_8], rsi
0x1800279aa  push    rdi
0x1800279ab  sub     rsp, 20h
0x1800279af  mov     rbx, r9
0x1800279b2  mov     rdi, rcx
0x1800279b5  cmp     rcx, rdx
0x1800279b8  jz      short loc_1800279F6
0x1800279ba  test    r8, r8
0x1800279bd  jz      short loc_1800279F6
0x1800279bf  cmp     byte ptr [r8], 0
0x1800279c3  jz      short loc_1800279F6
0x1800279c5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800279c9  inc     rax
0x1800279cc  cmp     byte ptr [r8+rax], 0
0x1800279d1  jnz     short loc_1800279C9
0x1800279d3  lea     rsi, [rax+1]
0x1800279d7  sub     rdx, rdi; DestinationSize
0x1800279da  cmp     rdx, rsi
0x1800279dd  jb      short loc_1800279F6
0x1800279df  mov     r9, rsi; SourceSize
0x1800279e2  call    cs:__imp_memcpy_s
0x1800279e8  test    rbx, rbx
0x1800279eb  jz      short loc_1800279F0
0x1800279ed  mov     [rbx], rdi
0x1800279f0  lea     rax, [rsi+rdi]
0x1800279f4  jmp     short loc_180027A05
0x1800279f6  test    rbx, rbx
0x1800279f9  jz      short loc_180027A02
0x1800279fb  mov     qword ptr [r9], 0
0x180027a02  mov     rax, rdi
0x180027a05  mov     rbx, [rsp+28h+arg_0]
0x180027a0a  mov     rsi, [rsp+28h+arg_8]
0x180027a0f  add     rsp, 20h
0x180027a13  pop     rdi
0x180027a14  retn
```
