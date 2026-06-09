# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180005a44`
- end: `0x180005ab5`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800047b8`
- `0x18000abd4`

## callees

- `0x180005a44`
- `0x180007458`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180005a82`
- `msvcrt!memcpy_s` at `0x180005a82`

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
0x180005a44  mov     [rsp+arg_0], rbx
0x180005a49  mov     [rsp+arg_8], rsi
0x180005a4e  push    rdi
0x180005a4f  sub     rsp, 20h
0x180005a53  mov     rbx, r9
0x180005a56  mov     rdi, rcx
0x180005a59  cmp     rcx, rdx
0x180005a5c  jz      short loc_180005A96
0x180005a5e  test    r8, r8
0x180005a61  jz      short loc_180005A96
0x180005a63  cmp     byte ptr [r8], 0
0x180005a67  jz      short loc_180005A96
0x180005a69  mov     rcx, r8; this
0x180005a6c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180005a71  sub     rdx, rdi; DestinationSize
0x180005a74  mov     rsi, rax
0x180005a77  cmp     rdx, rax
0x180005a7a  jb      short loc_180005A96
0x180005a7c  mov     r9, rax; SourceSize
0x180005a7f  mov     rcx, rdi; Destination
0x180005a82  call    cs:__imp_memcpy_s
0x180005a88  test    rbx, rbx
0x180005a8b  jz      short loc_180005A90
0x180005a8d  mov     [rbx], rdi
0x180005a90  lea     rax, [rsi+rdi]
0x180005a94  jmp     short loc_180005AA5
0x180005a96  test    rbx, rbx
0x180005a99  jz      short loc_180005AA2
0x180005a9b  mov     qword ptr [r9], 0
0x180005aa2  mov     rax, rdi
0x180005aa5  mov     rbx, [rsp+28h+arg_0]
0x180005aaa  mov     rsi, [rsp+28h+arg_8]
0x180005aaf  add     rsp, 20h
0x180005ab3  pop     rdi
0x180005ab4  retn
```
