# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180003090`
- end: `0x180003105`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: `char *__fastcall(char *, char *, _BYTE *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800056d0`
- `0x180005ad4`

## callees

- `0x180003090`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800030d2`
- `msvcrt!memcpy_s` at `0x1800030d2`

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
0x180003090  mov     [rsp+arg_0], rbx
0x180003095  mov     [rsp+arg_8], rsi
0x18000309a  push    rdi
0x18000309b  sub     rsp, 20h
0x18000309f  mov     rbx, r9
0x1800030a2  mov     rdi, rcx
0x1800030a5  cmp     rcx, rdx
0x1800030a8  jz      short loc_1800030E6
0x1800030aa  test    r8, r8
0x1800030ad  jz      short loc_1800030E6
0x1800030af  cmp     byte ptr [r8], 0
0x1800030b3  jz      short loc_1800030E6
0x1800030b5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800030b9  inc     rax
0x1800030bc  cmp     byte ptr [r8+rax], 0
0x1800030c1  jnz     short loc_1800030B9
0x1800030c3  lea     rsi, [rax+1]
0x1800030c7  sub     rdx, rdi; DestinationSize
0x1800030ca  cmp     rdx, rsi
0x1800030cd  jb      short loc_1800030E6
0x1800030cf  mov     r9, rsi; SourceSize
0x1800030d2  call    cs:__imp_memcpy_s
0x1800030d8  test    rbx, rbx
0x1800030db  jz      short loc_1800030E0
0x1800030dd  mov     [rbx], rdi
0x1800030e0  lea     rax, [rsi+rdi]
0x1800030e4  jmp     short loc_1800030F5
0x1800030e6  test    rbx, rbx
0x1800030e9  jz      short loc_1800030F2
0x1800030eb  mov     qword ptr [r9], 0
0x1800030f2  mov     rax, rdi
0x1800030f5  mov     rbx, [rsp+28h+arg_0]
0x1800030fa  mov     rsi, [rsp+28h+arg_8]
0x1800030ff  add     rsp, 20h
0x180003103  pop     rdi
0x180003104  retn
```
