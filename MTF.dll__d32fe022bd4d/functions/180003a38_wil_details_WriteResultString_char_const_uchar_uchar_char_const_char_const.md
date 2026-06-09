# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180003a38`
- end: `0x180003aad`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006164`
- `0x180006568`

## callees

- `0x180003a38`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180003a7a`
- `msvcrt!memcpy_s` at `0x180003a7a`

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
0x180003a38  mov     [rsp+arg_0], rbx
0x180003a3d  mov     [rsp+arg_8], rsi
0x180003a42  push    rdi
0x180003a43  sub     rsp, 20h
0x180003a47  mov     rbx, r9
0x180003a4a  mov     rdi, rcx
0x180003a4d  cmp     rcx, rdx
0x180003a50  jz      short loc_180003A8E
0x180003a52  test    r8, r8
0x180003a55  jz      short loc_180003A8E
0x180003a57  cmp     byte ptr [r8], 0
0x180003a5b  jz      short loc_180003A8E
0x180003a5d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003a61  inc     rax
0x180003a64  cmp     byte ptr [r8+rax], 0
0x180003a69  jnz     short loc_180003A61
0x180003a6b  lea     rsi, [rax+1]
0x180003a6f  sub     rdx, rdi; DestinationSize
0x180003a72  cmp     rdx, rsi
0x180003a75  jb      short loc_180003A8E
0x180003a77  mov     r9, rsi; SourceSize
0x180003a7a  call    cs:__imp_memcpy_s
0x180003a80  test    rbx, rbx
0x180003a83  jz      short loc_180003A88
0x180003a85  mov     [rbx], rdi
0x180003a88  lea     rax, [rsi+rdi]
0x180003a8c  jmp     short loc_180003A9D
0x180003a8e  test    rbx, rbx
0x180003a91  jz      short loc_180003A9A
0x180003a93  mov     qword ptr [r9], 0
0x180003a9a  mov     rax, rdi
0x180003a9d  mov     rbx, [rsp+28h+arg_0]
0x180003aa2  mov     rsi, [rsp+28h+arg_8]
0x180003aa7  add     rsp, 20h
0x180003aab  pop     rdi
0x180003aac  retn
```
