# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180002b10`
- end: `0x180002b8c`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007cb4`
- `0x1800080d4`

## callees

- `0x180002b10`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180002b52`
- `msvcrt!memcpy_s` at `0x180002b52`

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
0x180002b10  mov     [rsp+arg_0], rbx
0x180002b15  mov     [rsp+arg_8], rsi
0x180002b1a  push    rdi
0x180002b1b  sub     rsp, 20h
0x180002b1f  mov     rbx, r9
0x180002b22  mov     rdi, rcx
0x180002b25  cmp     rcx, rdx
0x180002b28  jz      short loc_180002B6C
0x180002b2a  test    r8, r8
0x180002b2d  jz      short loc_180002B6C
0x180002b2f  cmp     byte ptr [r8], 0
0x180002b33  jz      short loc_180002B6C
0x180002b35  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002b39  inc     rax
0x180002b3c  cmp     byte ptr [r8+rax], 0
0x180002b41  jnz     short loc_180002B39
0x180002b43  lea     rsi, [rax+1]
0x180002b47  sub     rdx, rdi; DestinationSize
0x180002b4a  cmp     rdx, rsi
0x180002b4d  jb      short loc_180002B6C
0x180002b4f  mov     r9, rsi; SourceSize
0x180002b52  call    cs:__imp_memcpy_s
0x180002b59  nop     dword ptr [rax+rax+00h]
0x180002b5e  test    rbx, rbx
0x180002b61  jz      short loc_180002B66
0x180002b63  mov     [rbx], rdi
0x180002b66  lea     rax, [rsi+rdi]
0x180002b6a  jmp     short loc_180002B7B
0x180002b6c  test    rbx, rbx
0x180002b6f  jz      short loc_180002B78
0x180002b71  mov     qword ptr [r9], 0
0x180002b78  mov     rax, rdi
0x180002b7b  mov     rbx, [rsp+28h+arg_0]
0x180002b80  mov     rsi, [rsp+28h+arg_8]
0x180002b85  add     rsp, 20h
0x180002b89  pop     rdi
0x180002b8a  retn
```
