# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180015e38`
- end: `0x180015ea9`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180017024`

## callees

- `0x180015e38`
- `0x180016f54`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180015e76`
- `msvcrt!memcpy_s` at `0x180015e76`

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
0x180015e38  mov     [rsp+arg_0], rbx
0x180015e3d  mov     [rsp+arg_8], rsi
0x180015e42  push    rdi
0x180015e43  sub     rsp, 20h
0x180015e47  mov     rbx, r9
0x180015e4a  mov     rdi, rcx
0x180015e4d  cmp     rcx, rdx
0x180015e50  jz      short loc_180015E8A
0x180015e52  test    r8, r8
0x180015e55  jz      short loc_180015E8A
0x180015e57  cmp     byte ptr [r8], 0
0x180015e5b  jz      short loc_180015E8A
0x180015e5d  mov     rcx, r8; this
0x180015e60  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180015e65  sub     rdx, rdi; DestinationSize
0x180015e68  mov     rsi, rax
0x180015e6b  cmp     rdx, rax
0x180015e6e  jb      short loc_180015E8A
0x180015e70  mov     r9, rax; SourceSize
0x180015e73  mov     rcx, rdi; Destination
0x180015e76  call    cs:__imp_memcpy_s
0x180015e7c  test    rbx, rbx
0x180015e7f  jz      short loc_180015E84
0x180015e81  mov     [rbx], rdi
0x180015e84  lea     rax, [rsi+rdi]
0x180015e88  jmp     short loc_180015E99
0x180015e8a  test    rbx, rbx
0x180015e8d  jz      short loc_180015E96
0x180015e8f  mov     qword ptr [r9], 0
0x180015e96  mov     rax, rdi
0x180015e99  mov     rbx, [rsp+28h+arg_0]
0x180015e9e  mov     rsi, [rsp+28h+arg_8]
0x180015ea3  add     rsp, 20h
0x180015ea7  pop     rdi
0x180015ea8  retn
```
