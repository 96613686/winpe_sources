# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x14000aa04`
- end: `0x14000aa74`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000c664`

## callees

- `0x140006030`
- `0x14000aa04`
- `0x14000c5b4`

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
0x14000aa04  mov     [rsp+arg_0], rbx
0x14000aa09  mov     [rsp+arg_8], rsi
0x14000aa0e  push    rdi
0x14000aa0f  sub     rsp, 20h
0x14000aa13  mov     rbx, r9
0x14000aa16  mov     rdi, rcx
0x14000aa19  cmp     rcx, rdx
0x14000aa1c  jz      short loc_14000AA55
0x14000aa1e  test    r8, r8
0x14000aa21  jz      short loc_14000AA55
0x14000aa23  cmp     byte ptr [r8], 0
0x14000aa27  jz      short loc_14000AA55
0x14000aa29  mov     rcx, r8; this
0x14000aa2c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x14000aa31  sub     rdx, rdi; DestinationSize
0x14000aa34  mov     rsi, rax
0x14000aa37  cmp     rdx, rax
0x14000aa3a  jb      short loc_14000AA55
0x14000aa3c  mov     r9, rax; SourceSize
0x14000aa3f  mov     rcx, rdi; Destination
0x14000aa42  call    memcpy_s
0x14000aa47  test    rbx, rbx
0x14000aa4a  jz      short loc_14000AA4F
0x14000aa4c  mov     [rbx], rdi
0x14000aa4f  lea     rax, [rsi+rdi]
0x14000aa53  jmp     short loc_14000AA64
0x14000aa55  test    rbx, rbx
0x14000aa58  jz      short loc_14000AA61
0x14000aa5a  mov     qword ptr [r9], 0
0x14000aa61  mov     rax, rdi
0x14000aa64  mov     rbx, [rsp+28h+arg_0]
0x14000aa69  mov     rsi, [rsp+28h+arg_8]
0x14000aa6e  add     rsp, 20h
0x14000aa72  pop     rdi
0x14000aa73  retn
```
