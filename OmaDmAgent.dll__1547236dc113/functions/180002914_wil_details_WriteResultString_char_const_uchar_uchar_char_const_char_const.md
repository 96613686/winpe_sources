# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180002914`
- end: `0x18000298c`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `120`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000549c`
- `0x1800055e8`

## callees

- `0x180002914`
- `0x1800053a8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180002952`
- `msvcrt!memcpy_s` at `0x180002952`

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
0x180002914  mov     [rsp+arg_0], rbx
0x180002919  mov     [rsp+arg_8], rsi
0x18000291e  push    rdi
0x18000291f  sub     rsp, 20h
0x180002923  mov     rbx, r9
0x180002926  mov     rdi, rcx
0x180002929  cmp     rcx, rdx
0x18000292c  jz      short loc_18000296C
0x18000292e  test    r8, r8
0x180002931  jz      short loc_18000296C
0x180002933  cmp     byte ptr [r8], 0
0x180002937  jz      short loc_18000296C
0x180002939  mov     rcx, r8; this
0x18000293c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180002941  sub     rdx, rdi; DestinationSize
0x180002944  mov     rsi, rax
0x180002947  cmp     rdx, rax
0x18000294a  jb      short loc_18000296C
0x18000294c  mov     r9, rax; SourceSize
0x18000294f  mov     rcx, rdi; Destination
0x180002952  call    cs:__imp_memcpy_s
0x180002959  nop     dword ptr [rax+rax+00h]
0x18000295e  test    rbx, rbx
0x180002961  jz      short loc_180002966
0x180002963  mov     [rbx], rdi
0x180002966  lea     rax, [rsi+rdi]
0x18000296a  jmp     short loc_18000297B
0x18000296c  test    rbx, rbx
0x18000296f  jz      short loc_180002978
0x180002971  mov     qword ptr [r9], 0
0x180002978  mov     rax, rdi
0x18000297b  mov     rbx, [rsp+28h+arg_0]
0x180002980  mov     rsi, [rsp+28h+arg_8]
0x180002985  add     rsp, 20h
0x180002989  pop     rdi
0x18000298a  retn
```
