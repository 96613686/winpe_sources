# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180002c10`
- end: `0x180002c81`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004aac`
- `0x180004be8`

## callees

- `0x180002c10`
- `0x1800049c8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180002c4e`
- `msvcrt!memcpy_s` at `0x180002c4e`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<char const *>(
        char *Destination,
        const char *a2,
        wil::details *a3,
        char **a4)
{
  rsize_t v6; // rax
  const void *v7; // r8
  __int64 v8; // rdx
  rsize_t v9; // rdx
  rsize_t v10; // rsi

  if ( Destination != a2
    && a3
    && *(_BYTE *)a3
    && (v6 = wil::details::ResultStringSize(a3, a2), v9 = v8 - (_QWORD)Destination, v10 = v6, v9 >= v6) )
  {
    memcpy_s(Destination, v9, v7, v6);
    if ( a4 )
      *a4 = Destination;
    return &Destination[v10];
  }
  else
  {
    if ( a4 )
      *a4 = 0;
    return Destination;
  }
}

```

## disassembly

```asm
0x180002c10  mov     [rsp+arg_0], rbx
0x180002c15  mov     [rsp+arg_8], rsi
0x180002c1a  push    rdi
0x180002c1b  sub     rsp, 20h
0x180002c1f  mov     rbx, r9
0x180002c22  mov     rdi, rcx
0x180002c25  cmp     rcx, rdx
0x180002c28  jz      short loc_180002C62
0x180002c2a  test    r8, r8
0x180002c2d  jz      short loc_180002C62
0x180002c2f  cmp     byte ptr [r8], 0
0x180002c33  jz      short loc_180002C62
0x180002c35  mov     rcx, r8; this
0x180002c38  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180002c3d  sub     rdx, rdi; DestinationSize
0x180002c40  mov     rsi, rax
0x180002c43  cmp     rdx, rax
0x180002c46  jb      short loc_180002C62
0x180002c48  mov     r9, rax; SourceSize
0x180002c4b  mov     rcx, rdi; Destination
0x180002c4e  call    cs:__imp_memcpy_s
0x180002c54  test    rbx, rbx
0x180002c57  jz      short loc_180002C5C
0x180002c59  mov     [rbx], rdi
0x180002c5c  lea     rax, [rsi+rdi]
0x180002c60  jmp     short loc_180002C71
0x180002c62  test    rbx, rbx
0x180002c65  jz      short loc_180002C6E
0x180002c67  mov     qword ptr [r9], 0
0x180002c6e  mov     rax, rdi
0x180002c71  mov     rbx, [rsp+28h+arg_0]
0x180002c76  mov     rsi, [rsp+28h+arg_8]
0x180002c7b  add     rsp, 20h
0x180002c7f  pop     rdi
0x180002c80  retn
```
