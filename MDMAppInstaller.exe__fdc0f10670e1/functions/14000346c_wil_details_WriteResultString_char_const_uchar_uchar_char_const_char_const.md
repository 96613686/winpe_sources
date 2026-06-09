# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x14000346c`
- end: `0x1400034dd`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140005750`
- `0x14000588c`

## callees

- `0x14000346c`
- `0x14000561c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1400034aa`
- `msvcrt!memcpy_s` at `0x1400034aa`

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
0x14000346c  mov     [rsp+arg_0], rbx
0x140003471  mov     [rsp+arg_8], rsi
0x140003476  push    rdi
0x140003477  sub     rsp, 20h
0x14000347b  mov     rbx, r9
0x14000347e  mov     rdi, rcx
0x140003481  cmp     rcx, rdx
0x140003484  jz      short loc_1400034BE
0x140003486  test    r8, r8
0x140003489  jz      short loc_1400034BE
0x14000348b  cmp     byte ptr [r8], 0
0x14000348f  jz      short loc_1400034BE
0x140003491  mov     rcx, r8; this
0x140003494  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140003499  sub     rdx, rdi; DestinationSize
0x14000349c  mov     rsi, rax
0x14000349f  cmp     rdx, rax
0x1400034a2  jb      short loc_1400034BE
0x1400034a4  mov     r9, rax; SourceSize
0x1400034a7  mov     rcx, rdi; Destination
0x1400034aa  call    cs:__imp_memcpy_s
0x1400034b0  test    rbx, rbx
0x1400034b3  jz      short loc_1400034B8
0x1400034b5  mov     [rbx], rdi
0x1400034b8  lea     rax, [rsi+rdi]
0x1400034bc  jmp     short loc_1400034CD
0x1400034be  test    rbx, rbx
0x1400034c1  jz      short loc_1400034CA
0x1400034c3  mov     qword ptr [r9], 0
0x1400034ca  mov     rax, rdi
0x1400034cd  mov     rbx, [rsp+28h+arg_0]
0x1400034d2  mov     rsi, [rsp+28h+arg_8]
0x1400034d7  add     rsp, 20h
0x1400034db  pop     rdi
0x1400034dc  retn
```
