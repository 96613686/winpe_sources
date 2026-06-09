# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180004998`
- end: `0x180004a09`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000684c`

## callees

- `0x180004998`
- `0x180006784`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800049d6`
- `msvcrt!memcpy_s` at `0x1800049d6`

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
0x180004998  mov     [rsp+arg_0], rbx
0x18000499d  mov     [rsp+arg_8], rsi
0x1800049a2  push    rdi
0x1800049a3  sub     rsp, 20h
0x1800049a7  mov     rbx, r9
0x1800049aa  mov     rdi, rcx
0x1800049ad  cmp     rcx, rdx
0x1800049b0  jz      short loc_1800049EA
0x1800049b2  test    r8, r8
0x1800049b5  jz      short loc_1800049EA
0x1800049b7  cmp     byte ptr [r8], 0
0x1800049bb  jz      short loc_1800049EA
0x1800049bd  mov     rcx, r8; this
0x1800049c0  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800049c5  sub     rdx, rdi; DestinationSize
0x1800049c8  mov     rsi, rax
0x1800049cb  cmp     rdx, rax
0x1800049ce  jb      short loc_1800049EA
0x1800049d0  mov     r9, rax; SourceSize
0x1800049d3  mov     rcx, rdi; Destination
0x1800049d6  call    cs:__imp_memcpy_s
0x1800049dc  test    rbx, rbx
0x1800049df  jz      short loc_1800049E4
0x1800049e1  mov     [rbx], rdi
0x1800049e4  lea     rax, [rsi+rdi]
0x1800049e8  jmp     short loc_1800049F9
0x1800049ea  test    rbx, rbx
0x1800049ed  jz      short loc_1800049F6
0x1800049ef  mov     qword ptr [r9], 0
0x1800049f6  mov     rax, rdi
0x1800049f9  mov     rbx, [rsp+28h+arg_0]
0x1800049fe  mov     rsi, [rsp+28h+arg_8]
0x180004a03  add     rsp, 20h
0x180004a07  pop     rdi
0x180004a08  retn
```
