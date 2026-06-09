# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180002cd0`
- end: `0x180002d45`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: `char *__fastcall(char *, char *, _BYTE *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008c28`
- `0x18000902c`

## callees

- `0x180002cd0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180002d12`
- `msvcrt!memcpy_s` at `0x180002d12`

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
0x180002cd0  mov     [rsp+arg_0], rbx
0x180002cd5  mov     [rsp+arg_8], rsi
0x180002cda  push    rdi
0x180002cdb  sub     rsp, 20h
0x180002cdf  mov     rbx, r9
0x180002ce2  mov     rdi, rcx
0x180002ce5  cmp     rcx, rdx
0x180002ce8  jz      short loc_180002D26
0x180002cea  test    r8, r8
0x180002ced  jz      short loc_180002D26
0x180002cef  cmp     byte ptr [r8], 0
0x180002cf3  jz      short loc_180002D26
0x180002cf5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002cf9  inc     rax
0x180002cfc  cmp     byte ptr [r8+rax], 0
0x180002d01  jnz     short loc_180002CF9
0x180002d03  lea     rsi, [rax+1]
0x180002d07  sub     rdx, rdi; DestinationSize
0x180002d0a  cmp     rdx, rsi
0x180002d0d  jb      short loc_180002D26
0x180002d0f  mov     r9, rsi; SourceSize
0x180002d12  call    cs:__imp_memcpy_s
0x180002d18  test    rbx, rbx
0x180002d1b  jz      short loc_180002D20
0x180002d1d  mov     [rbx], rdi
0x180002d20  lea     rax, [rsi+rdi]
0x180002d24  jmp     short loc_180002D35
0x180002d26  test    rbx, rbx
0x180002d29  jz      short loc_180002D32
0x180002d2b  mov     qword ptr [r9], 0
0x180002d32  mov     rax, rdi
0x180002d35  mov     rbx, [rsp+28h+arg_0]
0x180002d3a  mov     rsi, [rsp+28h+arg_8]
0x180002d3f  add     rsp, 20h
0x180002d43  pop     rdi
0x180002d44  retn
```
