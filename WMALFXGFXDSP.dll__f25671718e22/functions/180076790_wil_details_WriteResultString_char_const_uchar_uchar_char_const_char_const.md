# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180076790`
- end: `0x180076800`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180078fcc`

## callees

- `0x180015e48`
- `0x180076790`
- `0x180078f20`

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
0x180076790  mov     [rsp+arg_0], rbx
0x180076795  mov     [rsp+arg_8], rsi
0x18007679a  push    rdi
0x18007679b  sub     rsp, 20h
0x18007679f  mov     rbx, r9
0x1800767a2  mov     rdi, rcx
0x1800767a5  cmp     rcx, rdx
0x1800767a8  jz      short loc_1800767E1
0x1800767aa  test    r8, r8
0x1800767ad  jz      short loc_1800767E1
0x1800767af  cmp     byte ptr [r8], 0
0x1800767b3  jz      short loc_1800767E1
0x1800767b5  mov     rcx, r8; this
0x1800767b8  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800767bd  sub     rdx, rdi; DestinationSize
0x1800767c0  mov     rsi, rax
0x1800767c3  cmp     rdx, rax
0x1800767c6  jb      short loc_1800767E1
0x1800767c8  mov     r9, rax; SourceSize
0x1800767cb  mov     rcx, rdi; Destination
0x1800767ce  call    memcpy_s
0x1800767d3  test    rbx, rbx
0x1800767d6  jz      short loc_1800767DB
0x1800767d8  mov     [rbx], rdi
0x1800767db  lea     rax, [rsi+rdi]
0x1800767df  jmp     short loc_1800767F0
0x1800767e1  test    rbx, rbx
0x1800767e4  jz      short loc_1800767ED
0x1800767e6  mov     qword ptr [r9], 0
0x1800767ed  mov     rax, rdi
0x1800767f0  mov     rbx, [rsp+28h+arg_0]
0x1800767f5  mov     rsi, [rsp+28h+arg_8]
0x1800767fa  add     rsp, 20h
0x1800767fe  pop     rdi
0x1800767ff  retn
```
