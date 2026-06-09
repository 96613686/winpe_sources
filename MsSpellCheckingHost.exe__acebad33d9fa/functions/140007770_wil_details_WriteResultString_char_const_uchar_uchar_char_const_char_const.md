# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x140007770`
- end: `0x1400077e5`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: `char *__fastcall(char *, char *, _BYTE *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d498`
- `0x14000d89c`

## callees

- `0x140007770`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1400077b2`
- `msvcrt!memcpy_s` at `0x1400077b2`

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
0x140007770  mov     [rsp+arg_0], rbx
0x140007775  mov     [rsp+arg_8], rsi
0x14000777a  push    rdi
0x14000777b  sub     rsp, 20h
0x14000777f  mov     rbx, r9
0x140007782  mov     rdi, rcx
0x140007785  cmp     rcx, rdx
0x140007788  jz      short loc_1400077C6
0x14000778a  test    r8, r8
0x14000778d  jz      short loc_1400077C6
0x14000778f  cmp     byte ptr [r8], 0
0x140007793  jz      short loc_1400077C6
0x140007795  or      rax, 0FFFFFFFFFFFFFFFFh
0x140007799  inc     rax
0x14000779c  cmp     byte ptr [r8+rax], 0
0x1400077a1  jnz     short loc_140007799
0x1400077a3  lea     rsi, [rax+1]
0x1400077a7  sub     rdx, rdi; DestinationSize
0x1400077aa  cmp     rdx, rsi
0x1400077ad  jb      short loc_1400077C6
0x1400077af  mov     r9, rsi; SourceSize
0x1400077b2  call    cs:__imp_memcpy_s
0x1400077b8  test    rbx, rbx
0x1400077bb  jz      short loc_1400077C0
0x1400077bd  mov     [rbx], rdi
0x1400077c0  lea     rax, [rsi+rdi]
0x1400077c4  jmp     short loc_1400077D5
0x1400077c6  test    rbx, rbx
0x1400077c9  jz      short loc_1400077D2
0x1400077cb  mov     qword ptr [r9], 0
0x1400077d2  mov     rax, rdi
0x1400077d5  mov     rbx, [rsp+28h+arg_0]
0x1400077da  mov     rsi, [rsp+28h+arg_8]
0x1400077df  add     rsp, 20h
0x1400077e3  pop     rdi
0x1400077e4  retn
```
