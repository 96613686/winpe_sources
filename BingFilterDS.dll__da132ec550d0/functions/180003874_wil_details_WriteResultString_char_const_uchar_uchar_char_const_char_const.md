# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180003874`
- end: `0x1800038e9`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: `char *__fastcall(char *, char *, _BYTE *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800062f0`
- `0x1800066f4`

## callees

- `0x180003874`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800038b6`
- `msvcrt!memcpy_s` at `0x1800038b6`

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
0x180003874  mov     [rsp+arg_0], rbx
0x180003879  mov     [rsp+arg_8], rsi
0x18000387e  push    rdi
0x18000387f  sub     rsp, 20h
0x180003883  mov     rbx, r9
0x180003886  mov     rdi, rcx
0x180003889  cmp     rcx, rdx
0x18000388c  jz      short loc_1800038CA
0x18000388e  test    r8, r8
0x180003891  jz      short loc_1800038CA
0x180003893  cmp     byte ptr [r8], 0
0x180003897  jz      short loc_1800038CA
0x180003899  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000389d  inc     rax
0x1800038a0  cmp     byte ptr [r8+rax], 0
0x1800038a5  jnz     short loc_18000389D
0x1800038a7  lea     rsi, [rax+1]
0x1800038ab  sub     rdx, rdi; DestinationSize
0x1800038ae  cmp     rdx, rsi
0x1800038b1  jb      short loc_1800038CA
0x1800038b3  mov     r9, rsi; SourceSize
0x1800038b6  call    cs:__imp_memcpy_s
0x1800038bc  test    rbx, rbx
0x1800038bf  jz      short loc_1800038C4
0x1800038c1  mov     [rbx], rdi
0x1800038c4  lea     rax, [rsi+rdi]
0x1800038c8  jmp     short loc_1800038D9
0x1800038ca  test    rbx, rbx
0x1800038cd  jz      short loc_1800038D6
0x1800038cf  mov     qword ptr [r9], 0
0x1800038d6  mov     rax, rdi
0x1800038d9  mov     rbx, [rsp+28h+arg_0]
0x1800038de  mov     rsi, [rsp+28h+arg_8]
0x1800038e3  add     rsp, 20h
0x1800038e7  pop     rdi
0x1800038e8  retn
```
