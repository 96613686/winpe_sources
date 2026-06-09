# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x140004fb8`
- end: `0x140005028`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140006c8c`
- `0x140006dc8`

## callees

- `0x140004fb8`
- `0x140006ba4`
- `0x140007b40`

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
0x140004fb8  mov     [rsp+arg_0], rbx
0x140004fbd  mov     [rsp+arg_8], rsi
0x140004fc2  push    rdi
0x140004fc3  sub     rsp, 20h
0x140004fc7  mov     rbx, r9
0x140004fca  mov     rdi, rcx
0x140004fcd  cmp     rcx, rdx
0x140004fd0  jz      short loc_140005009
0x140004fd2  test    r8, r8
0x140004fd5  jz      short loc_140005009
0x140004fd7  cmp     byte ptr [r8], 0
0x140004fdb  jz      short loc_140005009
0x140004fdd  mov     rcx, r8; this
0x140004fe0  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140004fe5  sub     rdx, rdi; DestinationSize
0x140004fe8  mov     rsi, rax
0x140004feb  cmp     rdx, rax
0x140004fee  jb      short loc_140005009
0x140004ff0  mov     r9, rax; SourceSize
0x140004ff3  mov     rcx, rdi; Destination
0x140004ff6  call    memcpy_s
0x140004ffb  test    rbx, rbx
0x140004ffe  jz      short loc_140005003
0x140005000  mov     [rbx], rdi
0x140005003  lea     rax, [rsi+rdi]
0x140005007  jmp     short loc_140005018
0x140005009  test    rbx, rbx
0x14000500c  jz      short loc_140005015
0x14000500e  mov     qword ptr [r9], 0
0x140005015  mov     rax, rdi
0x140005018  mov     rbx, [rsp+28h+arg_0]
0x14000501d  mov     rsi, [rsp+28h+arg_8]
0x140005022  add     rsp, 20h
0x140005026  pop     rdi
0x140005027  retn
```
