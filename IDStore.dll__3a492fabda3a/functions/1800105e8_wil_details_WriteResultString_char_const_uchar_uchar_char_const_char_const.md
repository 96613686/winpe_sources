# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x1800105e8`
- end: `0x180010659`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011bf4`

## callees

- `0x1800105e8`
- `0x180011b90`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180010626`
- `msvcrt!memcpy_s` at `0x180010626`

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
0x1800105e8  mov     [rsp+arg_0], rbx
0x1800105ed  mov     [rsp+arg_8], rsi
0x1800105f2  push    rdi
0x1800105f3  sub     rsp, 20h
0x1800105f7  mov     rbx, r9
0x1800105fa  mov     rdi, rcx
0x1800105fd  cmp     rcx, rdx
0x180010600  jz      short loc_18001063A
0x180010602  test    r8, r8
0x180010605  jz      short loc_18001063A
0x180010607  cmp     byte ptr [r8], 0
0x18001060b  jz      short loc_18001063A
0x18001060d  mov     rcx, r8; this
0x180010610  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180010615  sub     rdx, rdi; DestinationSize
0x180010618  mov     rsi, rax
0x18001061b  cmp     rdx, rax
0x18001061e  jb      short loc_18001063A
0x180010620  mov     r9, rax; SourceSize
0x180010623  mov     rcx, rdi; Destination
0x180010626  call    cs:__imp_memcpy_s
0x18001062c  test    rbx, rbx
0x18001062f  jz      short loc_180010634
0x180010631  mov     [rbx], rdi
0x180010634  lea     rax, [rsi+rdi]
0x180010638  jmp     short loc_180010649
0x18001063a  test    rbx, rbx
0x18001063d  jz      short loc_180010646
0x18001063f  mov     qword ptr [r9], 0
0x180010646  mov     rax, rdi
0x180010649  mov     rbx, [rsp+28h+arg_0]
0x18001064e  mov     rsi, [rsp+28h+arg_8]
0x180010653  add     rsp, 20h
0x180010657  pop     rdi
0x180010658  retn
```
