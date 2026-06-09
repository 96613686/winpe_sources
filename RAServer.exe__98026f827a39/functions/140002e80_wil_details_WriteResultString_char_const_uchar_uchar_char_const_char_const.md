# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x140002e80`
- end: `0x140002ef1`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a288`
- `0x14000a4b0`

## callees

- `0x140002e80`
- `0x14000a0a4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140002ebe`
- `msvcrt!memcpy_s` at `0x140002ebe`

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
0x140002e80  mov     [rsp+arg_0], rbx
0x140002e85  mov     [rsp+arg_8], rsi
0x140002e8a  push    rdi
0x140002e8b  sub     rsp, 20h
0x140002e8f  mov     rbx, r9
0x140002e92  mov     rdi, rcx
0x140002e95  cmp     rcx, rdx
0x140002e98  jz      short loc_140002ED2
0x140002e9a  test    r8, r8
0x140002e9d  jz      short loc_140002ED2
0x140002e9f  cmp     byte ptr [r8], 0
0x140002ea3  jz      short loc_140002ED2
0x140002ea5  mov     rcx, r8; this
0x140002ea8  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140002ead  sub     rdx, rdi; DestinationSize
0x140002eb0  mov     rsi, rax
0x140002eb3  cmp     rdx, rax
0x140002eb6  jb      short loc_140002ED2
0x140002eb8  mov     r9, rax; SourceSize
0x140002ebb  mov     rcx, rdi; Destination
0x140002ebe  call    cs:__imp_memcpy_s
0x140002ec4  test    rbx, rbx
0x140002ec7  jz      short loc_140002ECC
0x140002ec9  mov     [rbx], rdi
0x140002ecc  lea     rax, [rsi+rdi]
0x140002ed0  jmp     short loc_140002EE1
0x140002ed2  test    rbx, rbx
0x140002ed5  jz      short loc_140002EDE
0x140002ed7  mov     qword ptr [r9], 0
0x140002ede  mov     rax, rdi
0x140002ee1  mov     rbx, [rsp+28h+arg_0]
0x140002ee6  mov     rsi, [rsp+28h+arg_8]
0x140002eeb  add     rsp, 20h
0x140002eef  pop     rdi
0x140002ef0  retn
```
