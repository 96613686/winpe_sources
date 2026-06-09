# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180002c10`
- end: `0x180002c85`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: `char *__fastcall(char *, char *, _BYTE *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004b24`
- `0x180004f28`

## callees

- `0x180002c10`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180002c52`
- `msvcrt!memcpy_s` at `0x180002c52`

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
0x180002c10  mov     [rsp+arg_0], rbx
0x180002c15  mov     [rsp+arg_8], rsi
0x180002c1a  push    rdi
0x180002c1b  sub     rsp, 20h
0x180002c1f  mov     rbx, r9
0x180002c22  mov     rdi, rcx
0x180002c25  cmp     rcx, rdx
0x180002c28  jz      short loc_180002C66
0x180002c2a  test    r8, r8
0x180002c2d  jz      short loc_180002C66
0x180002c2f  cmp     byte ptr [r8], 0
0x180002c33  jz      short loc_180002C66
0x180002c35  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002c39  inc     rax
0x180002c3c  cmp     byte ptr [r8+rax], 0
0x180002c41  jnz     short loc_180002C39
0x180002c43  lea     rsi, [rax+1]
0x180002c47  sub     rdx, rdi; DestinationSize
0x180002c4a  cmp     rdx, rsi
0x180002c4d  jb      short loc_180002C66
0x180002c4f  mov     r9, rsi; SourceSize
0x180002c52  call    cs:__imp_memcpy_s
0x180002c58  test    rbx, rbx
0x180002c5b  jz      short loc_180002C60
0x180002c5d  mov     [rbx], rdi
0x180002c60  lea     rax, [rsi+rdi]
0x180002c64  jmp     short loc_180002C75
0x180002c66  test    rbx, rbx
0x180002c69  jz      short loc_180002C72
0x180002c6b  mov     qword ptr [r9], 0
0x180002c72  mov     rax, rdi
0x180002c75  mov     rbx, [rsp+28h+arg_0]
0x180002c7a  mov     rsi, [rsp+28h+arg_8]
0x180002c7f  add     rsp, 20h
0x180002c83  pop     rdi
0x180002c84  retn
```
