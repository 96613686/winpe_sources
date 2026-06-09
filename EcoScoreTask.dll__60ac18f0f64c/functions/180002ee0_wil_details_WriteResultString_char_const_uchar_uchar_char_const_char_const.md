# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180002ee0`
- end: `0x180002f55`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: `char *__fastcall(char *, char *, _BYTE *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005ef0`
- `0x1800063a8`

## callees

- `0x180002ee0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180002f22`
- `msvcrt!memcpy_s` at `0x180002f22`

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
0x180002ee0  mov     [rsp+arg_0], rbx
0x180002ee5  mov     [rsp+arg_8], rsi
0x180002eea  push    rdi
0x180002eeb  sub     rsp, 20h
0x180002eef  mov     rbx, r9
0x180002ef2  mov     rdi, rcx
0x180002ef5  cmp     rcx, rdx
0x180002ef8  jz      short loc_180002F36
0x180002efa  test    r8, r8
0x180002efd  jz      short loc_180002F36
0x180002eff  cmp     byte ptr [r8], 0
0x180002f03  jz      short loc_180002F36
0x180002f05  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002f09  inc     rax
0x180002f0c  cmp     byte ptr [r8+rax], 0
0x180002f11  jnz     short loc_180002F09
0x180002f13  lea     rsi, [rax+1]
0x180002f17  sub     rdx, rdi; DestinationSize
0x180002f1a  cmp     rdx, rsi
0x180002f1d  jb      short loc_180002F36
0x180002f1f  mov     r9, rsi; SourceSize
0x180002f22  call    cs:__imp_memcpy_s
0x180002f28  test    rbx, rbx
0x180002f2b  jz      short loc_180002F30
0x180002f2d  mov     [rbx], rdi
0x180002f30  lea     rax, [rsi+rdi]
0x180002f34  jmp     short loc_180002F45
0x180002f36  test    rbx, rbx
0x180002f39  jz      short loc_180002F42
0x180002f3b  mov     qword ptr [r9], 0
0x180002f42  mov     rax, rdi
0x180002f45  mov     rbx, [rsp+28h+arg_0]
0x180002f4a  mov     rsi, [rsp+28h+arg_8]
0x180002f4f  add     rsp, 20h
0x180002f53  pop     rdi
0x180002f54  retn
```
