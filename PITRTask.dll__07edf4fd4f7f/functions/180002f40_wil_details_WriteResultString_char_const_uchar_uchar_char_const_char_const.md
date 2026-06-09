# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180002f40`
- end: `0x180002fb5`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: `char *__fastcall(char *, char *, _BYTE *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008e78`
- `0x18000927c`

## callees

- `0x180002f40`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180002f82`
- `msvcrt!memcpy_s` at `0x180002f82`

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
0x180002f40  mov     [rsp+arg_0], rbx
0x180002f45  mov     [rsp+arg_8], rsi
0x180002f4a  push    rdi
0x180002f4b  sub     rsp, 20h
0x180002f4f  mov     rbx, r9
0x180002f52  mov     rdi, rcx
0x180002f55  cmp     rcx, rdx
0x180002f58  jz      short loc_180002F96
0x180002f5a  test    r8, r8
0x180002f5d  jz      short loc_180002F96
0x180002f5f  cmp     byte ptr [r8], 0
0x180002f63  jz      short loc_180002F96
0x180002f65  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002f69  inc     rax
0x180002f6c  cmp     byte ptr [r8+rax], 0
0x180002f71  jnz     short loc_180002F69
0x180002f73  lea     rsi, [rax+1]
0x180002f77  sub     rdx, rdi; DestinationSize
0x180002f7a  cmp     rdx, rsi
0x180002f7d  jb      short loc_180002F96
0x180002f7f  mov     r9, rsi; SourceSize
0x180002f82  call    cs:__imp_memcpy_s
0x180002f88  test    rbx, rbx
0x180002f8b  jz      short loc_180002F90
0x180002f8d  mov     [rbx], rdi
0x180002f90  lea     rax, [rsi+rdi]
0x180002f94  jmp     short loc_180002FA5
0x180002f96  test    rbx, rbx
0x180002f99  jz      short loc_180002FA2
0x180002f9b  mov     qword ptr [r9], 0
0x180002fa2  mov     rax, rdi
0x180002fa5  mov     rbx, [rsp+28h+arg_0]
0x180002faa  mov     rsi, [rsp+28h+arg_8]
0x180002faf  add     rsp, 20h
0x180002fb3  pop     rdi
0x180002fb4  retn
```
