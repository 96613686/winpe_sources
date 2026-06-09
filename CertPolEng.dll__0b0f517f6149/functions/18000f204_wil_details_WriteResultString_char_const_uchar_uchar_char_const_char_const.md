# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x18000f204`
- end: `0x18000f275`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180011510`
- `0x180011728`

## callees

- `0x18000f204`
- `0x180011420`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000f242`
- `msvcrt!memcpy_s` at `0x18000f242`

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
0x18000f204  mov     [rsp+arg_0], rbx
0x18000f209  mov     [rsp+arg_8], rsi
0x18000f20e  push    rdi
0x18000f20f  sub     rsp, 20h
0x18000f213  mov     rbx, r9
0x18000f216  mov     rdi, rcx
0x18000f219  cmp     rcx, rdx
0x18000f21c  jz      short loc_18000F256
0x18000f21e  test    r8, r8
0x18000f221  jz      short loc_18000F256
0x18000f223  cmp     byte ptr [r8], 0
0x18000f227  jz      short loc_18000F256
0x18000f229  mov     rcx, r8; this
0x18000f22c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000f231  sub     rdx, rdi; DestinationSize
0x18000f234  mov     rsi, rax
0x18000f237  cmp     rdx, rax
0x18000f23a  jb      short loc_18000F256
0x18000f23c  mov     r9, rax; SourceSize
0x18000f23f  mov     rcx, rdi; Destination
0x18000f242  call    cs:__imp_memcpy_s
0x18000f248  test    rbx, rbx
0x18000f24b  jz      short loc_18000F250
0x18000f24d  mov     [rbx], rdi
0x18000f250  lea     rax, [rsi+rdi]
0x18000f254  jmp     short loc_18000F265
0x18000f256  test    rbx, rbx
0x18000f259  jz      short loc_18000F262
0x18000f25b  mov     qword ptr [r9], 0
0x18000f262  mov     rax, rdi
0x18000f265  mov     rbx, [rsp+28h+arg_0]
0x18000f26a  mov     rsi, [rsp+28h+arg_8]
0x18000f26f  add     rsp, 20h
0x18000f273  pop     rdi
0x18000f274  retn
```
