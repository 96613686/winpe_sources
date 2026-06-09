# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180013f98`
- end: `0x180014009`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001584c`
- `0x180015988`

## callees

- `0x180013f98`
- `0x1800156f0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180013fd6`
- `msvcrt!memcpy_s` at `0x180013fd6`

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
0x180013f98  mov     [rsp+arg_0], rbx
0x180013f9d  mov     [rsp+arg_8], rsi
0x180013fa2  push    rdi
0x180013fa3  sub     rsp, 20h
0x180013fa7  mov     rbx, r9
0x180013faa  mov     rdi, rcx
0x180013fad  cmp     rcx, rdx
0x180013fb0  jz      short loc_180013FEA
0x180013fb2  test    r8, r8
0x180013fb5  jz      short loc_180013FEA
0x180013fb7  cmp     byte ptr [r8], 0
0x180013fbb  jz      short loc_180013FEA
0x180013fbd  mov     rcx, r8; this
0x180013fc0  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180013fc5  sub     rdx, rdi; DestinationSize
0x180013fc8  mov     rsi, rax
0x180013fcb  cmp     rdx, rax
0x180013fce  jb      short loc_180013FEA
0x180013fd0  mov     r9, rax; SourceSize
0x180013fd3  mov     rcx, rdi; Destination
0x180013fd6  call    cs:__imp_memcpy_s
0x180013fdc  test    rbx, rbx
0x180013fdf  jz      short loc_180013FE4
0x180013fe1  mov     [rbx], rdi
0x180013fe4  lea     rax, [rsi+rdi]
0x180013fe8  jmp     short loc_180013FF9
0x180013fea  test    rbx, rbx
0x180013fed  jz      short loc_180013FF6
0x180013fef  mov     qword ptr [r9], 0
0x180013ff6  mov     rax, rdi
0x180013ff9  mov     rbx, [rsp+28h+arg_0]
0x180013ffe  mov     rsi, [rsp+28h+arg_8]
0x180014003  add     rsp, 20h
0x180014007  pop     rdi
0x180014008  retn
```
