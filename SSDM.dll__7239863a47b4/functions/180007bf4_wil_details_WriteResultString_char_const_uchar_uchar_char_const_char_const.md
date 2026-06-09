# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180007bf4`
- end: `0x180007c69`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: `char *__fastcall(char *, char *, _BYTE *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180009070`
- `0x180009474`

## callees

- `0x180007bf4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180007c36`
- `msvcrt!memcpy_s` at `0x180007c36`

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
0x180007bf4  mov     [rsp+arg_0], rbx
0x180007bf9  mov     [rsp+arg_8], rsi
0x180007bfe  push    rdi
0x180007bff  sub     rsp, 20h
0x180007c03  mov     rbx, r9
0x180007c06  mov     rdi, rcx
0x180007c09  cmp     rcx, rdx
0x180007c0c  jz      short loc_180007C4A
0x180007c0e  test    r8, r8
0x180007c11  jz      short loc_180007C4A
0x180007c13  cmp     byte ptr [r8], 0
0x180007c17  jz      short loc_180007C4A
0x180007c19  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007c1d  inc     rax
0x180007c20  cmp     byte ptr [r8+rax], 0
0x180007c25  jnz     short loc_180007C1D
0x180007c27  lea     rsi, [rax+1]
0x180007c2b  sub     rdx, rdi; DestinationSize
0x180007c2e  cmp     rdx, rsi
0x180007c31  jb      short loc_180007C4A
0x180007c33  mov     r9, rsi; SourceSize
0x180007c36  call    cs:__imp_memcpy_s
0x180007c3c  test    rbx, rbx
0x180007c3f  jz      short loc_180007C44
0x180007c41  mov     [rbx], rdi
0x180007c44  lea     rax, [rsi+rdi]
0x180007c48  jmp     short loc_180007C59
0x180007c4a  test    rbx, rbx
0x180007c4d  jz      short loc_180007C56
0x180007c4f  mov     qword ptr [r9], 0
0x180007c56  mov     rax, rdi
0x180007c59  mov     rbx, [rsp+28h+arg_0]
0x180007c5e  mov     rsi, [rsp+28h+arg_8]
0x180007c63  add     rsp, 20h
0x180007c67  pop     rdi
0x180007c68  retn
```
