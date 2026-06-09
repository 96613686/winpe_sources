# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180010a60`
- end: `0x180010adc`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180015184`
- `0x1800155a4`

## callees

- `0x180010a60`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180010aa2`
- `msvcrt!memcpy_s` at `0x180010aa2`

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
0x180010a60  mov     [rsp+arg_0], rbx
0x180010a65  mov     [rsp+arg_8], rsi
0x180010a6a  push    rdi
0x180010a6b  sub     rsp, 20h
0x180010a6f  mov     rbx, r9
0x180010a72  mov     rdi, rcx
0x180010a75  cmp     rcx, rdx
0x180010a78  jz      short loc_180010ABC
0x180010a7a  test    r8, r8
0x180010a7d  jz      short loc_180010ABC
0x180010a7f  cmp     byte ptr [r8], 0
0x180010a83  jz      short loc_180010ABC
0x180010a85  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010a89  inc     rax
0x180010a8c  cmp     byte ptr [r8+rax], 0
0x180010a91  jnz     short loc_180010A89
0x180010a93  lea     rsi, [rax+1]
0x180010a97  sub     rdx, rdi; DestinationSize
0x180010a9a  cmp     rdx, rsi
0x180010a9d  jb      short loc_180010ABC
0x180010a9f  mov     r9, rsi; SourceSize
0x180010aa2  call    cs:__imp_memcpy_s
0x180010aa9  nop     dword ptr [rax+rax+00h]
0x180010aae  test    rbx, rbx
0x180010ab1  jz      short loc_180010AB6
0x180010ab3  mov     [rbx], rdi
0x180010ab6  lea     rax, [rsi+rdi]
0x180010aba  jmp     short loc_180010ACB
0x180010abc  test    rbx, rbx
0x180010abf  jz      short loc_180010AC8
0x180010ac1  mov     qword ptr [r9], 0
0x180010ac8  mov     rax, rdi
0x180010acb  mov     rbx, [rsp+28h+arg_0]
0x180010ad0  mov     rsi, [rsp+28h+arg_8]
0x180010ad5  add     rsp, 20h
0x180010ad9  pop     rdi
0x180010ada  retn
```
