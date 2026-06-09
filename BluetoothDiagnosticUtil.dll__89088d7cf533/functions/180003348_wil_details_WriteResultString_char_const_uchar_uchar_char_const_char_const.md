# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180003348`
- end: `0x1800033c4`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800072cc`
- `0x1800076ec`

## callees

- `0x180003348`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000338a`
- `msvcrt!memcpy_s` at `0x18000338a`

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
0x180003348  mov     [rsp+arg_0], rbx
0x18000334d  mov     [rsp+arg_8], rsi
0x180003352  push    rdi
0x180003353  sub     rsp, 20h
0x180003357  mov     rbx, r9
0x18000335a  mov     rdi, rcx
0x18000335d  cmp     rcx, rdx
0x180003360  jz      short loc_1800033A4
0x180003362  test    r8, r8
0x180003365  jz      short loc_1800033A4
0x180003367  cmp     byte ptr [r8], 0
0x18000336b  jz      short loc_1800033A4
0x18000336d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003371  inc     rax
0x180003374  cmp     byte ptr [r8+rax], 0
0x180003379  jnz     short loc_180003371
0x18000337b  lea     rsi, [rax+1]
0x18000337f  sub     rdx, rdi; DestinationSize
0x180003382  cmp     rdx, rsi
0x180003385  jb      short loc_1800033A4
0x180003387  mov     r9, rsi; SourceSize
0x18000338a  call    cs:__imp_memcpy_s
0x180003391  nop     dword ptr [rax+rax+00h]
0x180003396  test    rbx, rbx
0x180003399  jz      short loc_18000339E
0x18000339b  mov     [rbx], rdi
0x18000339e  lea     rax, [rsi+rdi]
0x1800033a2  jmp     short loc_1800033B3
0x1800033a4  test    rbx, rbx
0x1800033a7  jz      short loc_1800033B0
0x1800033a9  mov     qword ptr [r9], 0
0x1800033b0  mov     rax, rdi
0x1800033b3  mov     rbx, [rsp+28h+arg_0]
0x1800033b8  mov     rsi, [rsp+28h+arg_8]
0x1800033bd  add     rsp, 20h
0x1800033c1  pop     rdi
0x1800033c2  retn
```
