# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x18000349c`
- end: `0x180003511`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: `char *__fastcall(char *, char *, _BYTE *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005d94`
- `0x180006198`

## callees

- `0x18000349c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800034de`
- `msvcrt!memcpy_s` at `0x1800034de`

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
0x18000349c  mov     [rsp+arg_0], rbx
0x1800034a1  mov     [rsp+arg_8], rsi
0x1800034a6  push    rdi
0x1800034a7  sub     rsp, 20h
0x1800034ab  mov     rbx, r9
0x1800034ae  mov     rdi, rcx
0x1800034b1  cmp     rcx, rdx
0x1800034b4  jz      short loc_1800034F2
0x1800034b6  test    r8, r8
0x1800034b9  jz      short loc_1800034F2
0x1800034bb  cmp     byte ptr [r8], 0
0x1800034bf  jz      short loc_1800034F2
0x1800034c1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800034c5  inc     rax
0x1800034c8  cmp     byte ptr [r8+rax], 0
0x1800034cd  jnz     short loc_1800034C5
0x1800034cf  lea     rsi, [rax+1]
0x1800034d3  sub     rdx, rdi; DestinationSize
0x1800034d6  cmp     rdx, rsi
0x1800034d9  jb      short loc_1800034F2
0x1800034db  mov     r9, rsi; SourceSize
0x1800034de  call    cs:__imp_memcpy_s
0x1800034e4  test    rbx, rbx
0x1800034e7  jz      short loc_1800034EC
0x1800034e9  mov     [rbx], rdi
0x1800034ec  lea     rax, [rsi+rdi]
0x1800034f0  jmp     short loc_180003501
0x1800034f2  test    rbx, rbx
0x1800034f5  jz      short loc_1800034FE
0x1800034f7  mov     qword ptr [r9], 0
0x1800034fe  mov     rax, rdi
0x180003501  mov     rbx, [rsp+28h+arg_0]
0x180003506  mov     rsi, [rsp+28h+arg_8]
0x18000350b  add     rsp, 20h
0x18000350f  pop     rdi
0x180003510  retn
```
