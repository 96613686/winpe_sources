# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x140004244`
- end: `0x1400042b4`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140006a50`
- `0x140006b8c`

## callees

- `0x140004244`
- `0x1400068e8`
- `0x140007ea4`

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
0x140004244  mov     [rsp+arg_0], rbx
0x140004249  mov     [rsp+arg_8], rsi
0x14000424e  push    rdi
0x14000424f  sub     rsp, 20h
0x140004253  mov     rbx, r9
0x140004256  mov     rdi, rcx
0x140004259  cmp     rcx, rdx
0x14000425c  jz      short loc_140004295
0x14000425e  test    r8, r8
0x140004261  jz      short loc_140004295
0x140004263  cmp     byte ptr [r8], 0
0x140004267  jz      short loc_140004295
0x140004269  mov     rcx, r8; this
0x14000426c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140004271  sub     rdx, rdi; DestinationSize
0x140004274  mov     rsi, rax
0x140004277  cmp     rdx, rax
0x14000427a  jb      short loc_140004295
0x14000427c  mov     r9, rax; SourceSize
0x14000427f  mov     rcx, rdi; Destination
0x140004282  call    memcpy_s
0x140004287  test    rbx, rbx
0x14000428a  jz      short loc_14000428F
0x14000428c  mov     [rbx], rdi
0x14000428f  lea     rax, [rsi+rdi]
0x140004293  jmp     short loc_1400042A4
0x140004295  test    rbx, rbx
0x140004298  jz      short loc_1400042A1
0x14000429a  mov     qword ptr [r9], 0
0x1400042a1  mov     rax, rdi
0x1400042a4  mov     rbx, [rsp+28h+arg_0]
0x1400042a9  mov     rsi, [rsp+28h+arg_8]
0x1400042ae  add     rsp, 20h
0x1400042b2  pop     rdi
0x1400042b3  retn
```
