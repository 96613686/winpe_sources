# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x18001878c`
- end: `0x1800187fd`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001aa3c`

## callees

- `0x18001878c`
- `0x18001a96c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800187ca`
- `msvcrt!memcpy_s` at `0x1800187ca`

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
0x18001878c  mov     [rsp+arg_0], rbx
0x180018791  mov     [rsp+arg_8], rsi
0x180018796  push    rdi
0x180018797  sub     rsp, 20h
0x18001879b  mov     rbx, r9
0x18001879e  mov     rdi, rcx
0x1800187a1  cmp     rcx, rdx
0x1800187a4  jz      short loc_1800187DE
0x1800187a6  test    r8, r8
0x1800187a9  jz      short loc_1800187DE
0x1800187ab  cmp     byte ptr [r8], 0
0x1800187af  jz      short loc_1800187DE
0x1800187b1  mov     rcx, r8; this
0x1800187b4  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800187b9  sub     rdx, rdi; DestinationSize
0x1800187bc  mov     rsi, rax
0x1800187bf  cmp     rdx, rax
0x1800187c2  jb      short loc_1800187DE
0x1800187c4  mov     r9, rax; SourceSize
0x1800187c7  mov     rcx, rdi; Destination
0x1800187ca  call    cs:__imp_memcpy_s
0x1800187d0  test    rbx, rbx
0x1800187d3  jz      short loc_1800187D8
0x1800187d5  mov     [rbx], rdi
0x1800187d8  lea     rax, [rsi+rdi]
0x1800187dc  jmp     short loc_1800187ED
0x1800187de  test    rbx, rbx
0x1800187e1  jz      short loc_1800187EA
0x1800187e3  mov     qword ptr [r9], 0
0x1800187ea  mov     rax, rdi
0x1800187ed  mov     rbx, [rsp+28h+arg_0]
0x1800187f2  mov     rsi, [rsp+28h+arg_8]
0x1800187f7  add     rsp, 20h
0x1800187fb  pop     rdi
0x1800187fc  retn
```
