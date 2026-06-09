# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180006c50`
- end: `0x180006cc0`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800091a0`
- `0x1800092dc`

## callees

- `0x1800034d8`
- `0x180006c50`
- `0x180009078`

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
0x180006c50  mov     [rsp+arg_0], rbx
0x180006c55  mov     [rsp+arg_8], rsi
0x180006c5a  push    rdi
0x180006c5b  sub     rsp, 20h
0x180006c5f  mov     rbx, r9
0x180006c62  mov     rdi, rcx
0x180006c65  cmp     rcx, rdx
0x180006c68  jz      short loc_180006CA1
0x180006c6a  test    r8, r8
0x180006c6d  jz      short loc_180006CA1
0x180006c6f  cmp     byte ptr [r8], 0
0x180006c73  jz      short loc_180006CA1
0x180006c75  mov     rcx, r8; this
0x180006c78  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180006c7d  sub     rdx, rdi; DestinationSize
0x180006c80  mov     rsi, rax
0x180006c83  cmp     rdx, rax
0x180006c86  jb      short loc_180006CA1
0x180006c88  mov     r9, rax; SourceSize
0x180006c8b  mov     rcx, rdi; Destination
0x180006c8e  call    memcpy_s
0x180006c93  test    rbx, rbx
0x180006c96  jz      short loc_180006C9B
0x180006c98  mov     [rbx], rdi
0x180006c9b  lea     rax, [rsi+rdi]
0x180006c9f  jmp     short loc_180006CB0
0x180006ca1  test    rbx, rbx
0x180006ca4  jz      short loc_180006CAD
0x180006ca6  mov     qword ptr [r9], 0
0x180006cad  mov     rax, rdi
0x180006cb0  mov     rbx, [rsp+28h+arg_0]
0x180006cb5  mov     rsi, [rsp+28h+arg_8]
0x180006cba  add     rsp, 20h
0x180006cbe  pop     rdi
0x180006cbf  retn
```
