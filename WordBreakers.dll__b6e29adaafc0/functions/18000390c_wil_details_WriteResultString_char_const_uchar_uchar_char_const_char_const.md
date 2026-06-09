# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x18000390c`
- end: `0x180003981`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: `char *__fastcall(char *, char *, _BYTE *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800059c4`
- `0x180005dc8`

## callees

- `0x18000390c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000394e`
- `msvcrt!memcpy_s` at `0x18000394e`

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
0x18000390c  mov     [rsp+arg_0], rbx
0x180003911  mov     [rsp+arg_8], rsi
0x180003916  push    rdi
0x180003917  sub     rsp, 20h
0x18000391b  mov     rbx, r9
0x18000391e  mov     rdi, rcx
0x180003921  cmp     rcx, rdx
0x180003924  jz      short loc_180003962
0x180003926  test    r8, r8
0x180003929  jz      short loc_180003962
0x18000392b  cmp     byte ptr [r8], 0
0x18000392f  jz      short loc_180003962
0x180003931  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003935  inc     rax
0x180003938  cmp     byte ptr [r8+rax], 0
0x18000393d  jnz     short loc_180003935
0x18000393f  lea     rsi, [rax+1]
0x180003943  sub     rdx, rdi; DestinationSize
0x180003946  cmp     rdx, rsi
0x180003949  jb      short loc_180003962
0x18000394b  mov     r9, rsi; SourceSize
0x18000394e  call    cs:__imp_memcpy_s
0x180003954  test    rbx, rbx
0x180003957  jz      short loc_18000395C
0x180003959  mov     [rbx], rdi
0x18000395c  lea     rax, [rsi+rdi]
0x180003960  jmp     short loc_180003971
0x180003962  test    rbx, rbx
0x180003965  jz      short loc_18000396E
0x180003967  mov     qword ptr [r9], 0
0x18000396e  mov     rax, rdi
0x180003971  mov     rbx, [rsp+28h+arg_0]
0x180003976  mov     rsi, [rsp+28h+arg_8]
0x18000397b  add     rsp, 20h
0x18000397f  pop     rdi
0x180003980  retn
```
