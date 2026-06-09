# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x18000ab50`
- end: `0x18000abc1`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c39c`
- `0x18000c4d8`

## callees

- `0x1800056d0`
- `0x18000ab50`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000ab8e`
- `msvcrt!memcpy_s` at `0x18000ab8e`

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
0x18000ab50  mov     [rsp+arg_0], rbx
0x18000ab55  mov     [rsp+arg_8], rsi
0x18000ab5a  push    rdi
0x18000ab5b  sub     rsp, 20h
0x18000ab5f  mov     rbx, r9
0x18000ab62  mov     rdi, rcx
0x18000ab65  cmp     rcx, rdx
0x18000ab68  jz      short loc_18000ABA2
0x18000ab6a  test    r8, r8
0x18000ab6d  jz      short loc_18000ABA2
0x18000ab6f  cmp     byte ptr [r8], 0
0x18000ab73  jz      short loc_18000ABA2
0x18000ab75  mov     rcx, r8; this
0x18000ab78  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000ab7d  sub     rdx, rdi; DestinationSize
0x18000ab80  mov     rsi, rax
0x18000ab83  cmp     rdx, rax
0x18000ab86  jb      short loc_18000ABA2
0x18000ab88  mov     r9, rax; SourceSize
0x18000ab8b  mov     rcx, rdi; Destination
0x18000ab8e  call    cs:__imp_memcpy_s
0x18000ab94  test    rbx, rbx
0x18000ab97  jz      short loc_18000AB9C
0x18000ab99  mov     [rbx], rdi
0x18000ab9c  lea     rax, [rsi+rdi]
0x18000aba0  jmp     short loc_18000ABB1
0x18000aba2  test    rbx, rbx
0x18000aba5  jz      short loc_18000ABAE
0x18000aba7  mov     qword ptr [r9], 0
0x18000abae  mov     rax, rdi
0x18000abb1  mov     rbx, [rsp+28h+arg_0]
0x18000abb6  mov     rsi, [rsp+28h+arg_8]
0x18000abbb  add     rsp, 20h
0x18000abbf  pop     rdi
0x18000abc0  retn
```
