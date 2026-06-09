# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x140002950`
- end: `0x1400029c0`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140006070`
- `0x14000629c`

## callees

- `0x140002950`
- `0x140005edc`
- `0x140007a00`

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
0x140002950  mov     [rsp+arg_0], rbx
0x140002955  mov     [rsp+arg_8], rsi
0x14000295a  push    rdi
0x14000295b  sub     rsp, 20h
0x14000295f  mov     rbx, r9
0x140002962  mov     rdi, rcx
0x140002965  cmp     rcx, rdx
0x140002968  jz      short loc_1400029A1
0x14000296a  test    r8, r8
0x14000296d  jz      short loc_1400029A1
0x14000296f  cmp     byte ptr [r8], 0
0x140002973  jz      short loc_1400029A1
0x140002975  mov     rcx, r8; this
0x140002978  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x14000297d  sub     rdx, rdi; DestinationSize
0x140002980  mov     rsi, rax
0x140002983  cmp     rdx, rax
0x140002986  jb      short loc_1400029A1
0x140002988  mov     r9, rax; SourceSize
0x14000298b  mov     rcx, rdi; Destination
0x14000298e  call    memcpy_s
0x140002993  test    rbx, rbx
0x140002996  jz      short loc_14000299B
0x140002998  mov     [rbx], rdi
0x14000299b  lea     rax, [rsi+rdi]
0x14000299f  jmp     short loc_1400029B0
0x1400029a1  test    rbx, rbx
0x1400029a4  jz      short loc_1400029AD
0x1400029a6  mov     qword ptr [r9], 0
0x1400029ad  mov     rax, rdi
0x1400029b0  mov     rbx, [rsp+28h+arg_0]
0x1400029b5  mov     rsi, [rsp+28h+arg_8]
0x1400029ba  add     rsp, 20h
0x1400029be  pop     rdi
0x1400029bf  retn
```
