# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180016fc8`
- end: `0x180017039`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a404`

## callees

- `0x180016fc8`
- `0x18001a284`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180017006`
- `msvcrt!memcpy_s` at `0x180017006`

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
0x180016fc8  mov     [rsp+arg_0], rbx
0x180016fcd  mov     [rsp+arg_8], rsi
0x180016fd2  push    rdi
0x180016fd3  sub     rsp, 20h
0x180016fd7  mov     rbx, r9
0x180016fda  mov     rdi, rcx
0x180016fdd  cmp     rcx, rdx
0x180016fe0  jz      short loc_18001701A
0x180016fe2  test    r8, r8
0x180016fe5  jz      short loc_18001701A
0x180016fe7  cmp     byte ptr [r8], 0
0x180016feb  jz      short loc_18001701A
0x180016fed  mov     rcx, r8; this
0x180016ff0  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180016ff5  sub     rdx, rdi; DestinationSize
0x180016ff8  mov     rsi, rax
0x180016ffb  cmp     rdx, rax
0x180016ffe  jb      short loc_18001701A
0x180017000  mov     r9, rax; SourceSize
0x180017003  mov     rcx, rdi; Destination
0x180017006  call    cs:__imp_memcpy_s
0x18001700c  test    rbx, rbx
0x18001700f  jz      short loc_180017014
0x180017011  mov     [rbx], rdi
0x180017014  lea     rax, [rsi+rdi]
0x180017018  jmp     short loc_180017029
0x18001701a  test    rbx, rbx
0x18001701d  jz      short loc_180017026
0x18001701f  mov     qword ptr [r9], 0
0x180017026  mov     rax, rdi
0x180017029  mov     rbx, [rsp+28h+arg_0]
0x18001702e  mov     rsi, [rsp+28h+arg_8]
0x180017033  add     rsp, 20h
0x180017037  pop     rdi
0x180017038  retn
```
