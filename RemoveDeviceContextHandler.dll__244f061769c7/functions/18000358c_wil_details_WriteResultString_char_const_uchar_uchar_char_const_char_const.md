# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x18000358c`
- end: `0x180003601`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: `char *__fastcall(char *, char *, _BYTE *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004e50`
- `0x18000a728`

## callees

- `0x18000358c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800035ce`
- `msvcrt!memcpy_s` at `0x1800035ce`

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
0x18000358c  mov     [rsp+arg_0], rbx
0x180003591  mov     [rsp+arg_8], rsi
0x180003596  push    rdi
0x180003597  sub     rsp, 20h
0x18000359b  mov     rbx, r9
0x18000359e  mov     rdi, rcx
0x1800035a1  cmp     rcx, rdx
0x1800035a4  jz      short loc_1800035E2
0x1800035a6  test    r8, r8
0x1800035a9  jz      short loc_1800035E2
0x1800035ab  cmp     byte ptr [r8], 0
0x1800035af  jz      short loc_1800035E2
0x1800035b1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800035b5  inc     rax
0x1800035b8  cmp     byte ptr [r8+rax], 0
0x1800035bd  jnz     short loc_1800035B5
0x1800035bf  lea     rsi, [rax+1]
0x1800035c3  sub     rdx, rdi; DestinationSize
0x1800035c6  cmp     rdx, rsi
0x1800035c9  jb      short loc_1800035E2
0x1800035cb  mov     r9, rsi; SourceSize
0x1800035ce  call    cs:__imp_memcpy_s
0x1800035d4  test    rbx, rbx
0x1800035d7  jz      short loc_1800035DC
0x1800035d9  mov     [rbx], rdi
0x1800035dc  lea     rax, [rsi+rdi]
0x1800035e0  jmp     short loc_1800035F1
0x1800035e2  test    rbx, rbx
0x1800035e5  jz      short loc_1800035EE
0x1800035e7  mov     qword ptr [r9], 0
0x1800035ee  mov     rax, rdi
0x1800035f1  mov     rbx, [rsp+28h+arg_0]
0x1800035f6  mov     rsi, [rsp+28h+arg_8]
0x1800035fb  add     rsp, 20h
0x1800035ff  pop     rdi
0x180003600  retn
```
