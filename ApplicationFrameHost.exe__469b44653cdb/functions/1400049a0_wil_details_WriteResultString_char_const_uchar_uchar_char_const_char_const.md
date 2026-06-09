# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x1400049a0`
- end: `0x140004a10`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400083f0`
- `0x140008608`

## callees

- `0x1400049a0`
- `0x14000829c`
- `0x140009d98`

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
0x1400049a0  mov     [rsp+arg_0], rbx
0x1400049a5  mov     [rsp+arg_8], rsi
0x1400049aa  push    rdi
0x1400049ab  sub     rsp, 20h
0x1400049af  mov     rbx, r9
0x1400049b2  mov     rdi, rcx
0x1400049b5  cmp     rcx, rdx
0x1400049b8  jz      short loc_1400049F1
0x1400049ba  test    r8, r8
0x1400049bd  jz      short loc_1400049F1
0x1400049bf  cmp     byte ptr [r8], 0
0x1400049c3  jz      short loc_1400049F1
0x1400049c5  mov     rcx, r8; this
0x1400049c8  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1400049cd  sub     rdx, rdi; DestinationSize
0x1400049d0  mov     rsi, rax
0x1400049d3  cmp     rdx, rax
0x1400049d6  jb      short loc_1400049F1
0x1400049d8  mov     r9, rax; SourceSize
0x1400049db  mov     rcx, rdi; Destination
0x1400049de  call    memcpy_s
0x1400049e3  test    rbx, rbx
0x1400049e6  jz      short loc_1400049EB
0x1400049e8  mov     [rbx], rdi
0x1400049eb  lea     rax, [rsi+rdi]
0x1400049ef  jmp     short loc_140004A00
0x1400049f1  test    rbx, rbx
0x1400049f4  jz      short loc_1400049FD
0x1400049f6  mov     qword ptr [r9], 0
0x1400049fd  mov     rax, rdi
0x140004a00  mov     rbx, [rsp+28h+arg_0]
0x140004a05  mov     rsi, [rsp+28h+arg_8]
0x140004a0a  add     rsp, 20h
0x140004a0e  pop     rdi
0x140004a0f  retn
```
