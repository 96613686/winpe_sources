# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180004154`
- end: `0x1800041c4`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180007fe0`
- `0x180008214`

## callees

- `0x180004154`
- `0x180007e4c`
- `0x18000a0b8`

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
0x180004154  mov     [rsp+arg_0], rbx
0x180004159  mov     [rsp+arg_8], rsi
0x18000415e  push    rdi
0x18000415f  sub     rsp, 20h
0x180004163  mov     rbx, r9
0x180004166  mov     rdi, rcx
0x180004169  cmp     rcx, rdx
0x18000416c  jz      short loc_1800041A5
0x18000416e  test    r8, r8
0x180004171  jz      short loc_1800041A5
0x180004173  cmp     byte ptr [r8], 0
0x180004177  jz      short loc_1800041A5
0x180004179  mov     rcx, r8; this
0x18000417c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180004181  sub     rdx, rdi; DestinationSize
0x180004184  mov     rsi, rax
0x180004187  cmp     rdx, rax
0x18000418a  jb      short loc_1800041A5
0x18000418c  mov     r9, rax; SourceSize
0x18000418f  mov     rcx, rdi; Destination
0x180004192  call    memcpy_s
0x180004197  test    rbx, rbx
0x18000419a  jz      short loc_18000419F
0x18000419c  mov     [rbx], rdi
0x18000419f  lea     rax, [rsi+rdi]
0x1800041a3  jmp     short loc_1800041B4
0x1800041a5  test    rbx, rbx
0x1800041a8  jz      short loc_1800041B1
0x1800041aa  mov     qword ptr [r9], 0
0x1800041b1  mov     rax, rdi
0x1800041b4  mov     rbx, [rsp+28h+arg_0]
0x1800041b9  mov     rsi, [rsp+28h+arg_8]
0x1800041be  add     rsp, 20h
0x1800041c2  pop     rdi
0x1800041c3  retn
```
