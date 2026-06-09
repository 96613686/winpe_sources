# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x140003fa0`
- end: `0x140004011`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140007a74`

## callees

- `0x140003fa0`
- `0x1400078fc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140003fde`
- `msvcrt!memcpy_s` at `0x140003fde`

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
0x140003fa0  mov     [rsp+arg_0], rbx
0x140003fa5  mov     [rsp+arg_8], rsi
0x140003faa  push    rdi
0x140003fab  sub     rsp, 20h
0x140003faf  mov     rbx, r9
0x140003fb2  mov     rdi, rcx
0x140003fb5  cmp     rcx, rdx
0x140003fb8  jz      short loc_140003FF2
0x140003fba  test    r8, r8
0x140003fbd  jz      short loc_140003FF2
0x140003fbf  cmp     byte ptr [r8], 0
0x140003fc3  jz      short loc_140003FF2
0x140003fc5  mov     rcx, r8; this
0x140003fc8  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140003fcd  sub     rdx, rdi; DestinationSize
0x140003fd0  mov     rsi, rax
0x140003fd3  cmp     rdx, rax
0x140003fd6  jb      short loc_140003FF2
0x140003fd8  mov     r9, rax; SourceSize
0x140003fdb  mov     rcx, rdi; Destination
0x140003fde  call    cs:__imp_memcpy_s
0x140003fe4  test    rbx, rbx
0x140003fe7  jz      short loc_140003FEC
0x140003fe9  mov     [rbx], rdi
0x140003fec  lea     rax, [rsi+rdi]
0x140003ff0  jmp     short loc_140004001
0x140003ff2  test    rbx, rbx
0x140003ff5  jz      short loc_140003FFE
0x140003ff7  mov     qword ptr [r9], 0
0x140003ffe  mov     rax, rdi
0x140004001  mov     rbx, [rsp+28h+arg_0]
0x140004006  mov     rsi, [rsp+28h+arg_8]
0x14000400b  add     rsp, 20h
0x14000400f  pop     rdi
0x140004010  retn
```
