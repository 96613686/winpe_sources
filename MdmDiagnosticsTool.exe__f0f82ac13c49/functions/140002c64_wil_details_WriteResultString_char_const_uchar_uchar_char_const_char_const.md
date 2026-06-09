# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x140002c64`
- end: `0x140002cd5`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400062cc`
- `0x140006408`

## callees

- `0x140002c64`
- `0x1400061c8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140002ca2`
- `msvcrt!memcpy_s` at `0x140002ca2`

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
0x140002c64  mov     [rsp+arg_0], rbx
0x140002c69  mov     [rsp+arg_8], rsi
0x140002c6e  push    rdi
0x140002c6f  sub     rsp, 20h
0x140002c73  mov     rbx, r9
0x140002c76  mov     rdi, rcx
0x140002c79  cmp     rcx, rdx
0x140002c7c  jz      short loc_140002CB6
0x140002c7e  test    r8, r8
0x140002c81  jz      short loc_140002CB6
0x140002c83  cmp     byte ptr [r8], 0
0x140002c87  jz      short loc_140002CB6
0x140002c89  mov     rcx, r8; this
0x140002c8c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140002c91  sub     rdx, rdi; DestinationSize
0x140002c94  mov     rsi, rax
0x140002c97  cmp     rdx, rax
0x140002c9a  jb      short loc_140002CB6
0x140002c9c  mov     r9, rax; SourceSize
0x140002c9f  mov     rcx, rdi; Destination
0x140002ca2  call    cs:__imp_memcpy_s
0x140002ca8  test    rbx, rbx
0x140002cab  jz      short loc_140002CB0
0x140002cad  mov     [rbx], rdi
0x140002cb0  lea     rax, [rsi+rdi]
0x140002cb4  jmp     short loc_140002CC5
0x140002cb6  test    rbx, rbx
0x140002cb9  jz      short loc_140002CC2
0x140002cbb  mov     qword ptr [r9], 0
0x140002cc2  mov     rax, rdi
0x140002cc5  mov     rbx, [rsp+28h+arg_0]
0x140002cca  mov     rsi, [rsp+28h+arg_8]
0x140002ccf  add     rsp, 20h
0x140002cd3  pop     rdi
0x140002cd4  retn
```
