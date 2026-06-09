# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180008688`
- end: `0x1800086f9`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b3cc`
- `0x18000b508`

## callees

- `0x180008688`
- `0x18000b2e0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800086c6`
- `msvcrt!memcpy_s` at `0x1800086c6`

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
0x180008688  mov     [rsp+arg_0], rbx
0x18000868d  mov     [rsp+arg_8], rsi
0x180008692  push    rdi
0x180008693  sub     rsp, 20h
0x180008697  mov     rbx, r9
0x18000869a  mov     rdi, rcx
0x18000869d  cmp     rcx, rdx
0x1800086a0  jz      short loc_1800086DA
0x1800086a2  test    r8, r8
0x1800086a5  jz      short loc_1800086DA
0x1800086a7  cmp     byte ptr [r8], 0
0x1800086ab  jz      short loc_1800086DA
0x1800086ad  mov     rcx, r8; this
0x1800086b0  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800086b5  sub     rdx, rdi; DestinationSize
0x1800086b8  mov     rsi, rax
0x1800086bb  cmp     rdx, rax
0x1800086be  jb      short loc_1800086DA
0x1800086c0  mov     r9, rax; SourceSize
0x1800086c3  mov     rcx, rdi; Destination
0x1800086c6  call    cs:__imp_memcpy_s
0x1800086cc  test    rbx, rbx
0x1800086cf  jz      short loc_1800086D4
0x1800086d1  mov     [rbx], rdi
0x1800086d4  lea     rax, [rsi+rdi]
0x1800086d8  jmp     short loc_1800086E9
0x1800086da  test    rbx, rbx
0x1800086dd  jz      short loc_1800086E6
0x1800086df  mov     qword ptr [r9], 0
0x1800086e6  mov     rax, rdi
0x1800086e9  mov     rbx, [rsp+28h+arg_0]
0x1800086ee  mov     rsi, [rsp+28h+arg_8]
0x1800086f3  add     rsp, 20h
0x1800086f7  pop     rdi
0x1800086f8  retn
```
