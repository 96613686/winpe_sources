# wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)

- ea: `0x180009240`
- end: `0x1800092a8`
- name: `??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z`
- size: `104`
- prototype: `char *__fastcall(wchar_t *Destination, const wchar_t *, wil::details *, wchar_t **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800047b8`
- `0x18000abd4`

## callees

- `0x180007404`
- `0x180009240`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180009280`
- `msvcrt!memcpy_s` at `0x180009280`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<wchar_t const *>(
        wchar_t *Destination,
        const wchar_t *a2,
        wil::details *a3,
        wchar_t **a4)
{
  rsize_t v6; // rax
  const void *v7; // r8
  __int64 v8; // r10
  rsize_t v9; // r10
  rsize_t v10; // rsi

  if ( Destination != a2
    && a3
    && *(_WORD *)a3
    && (v6 = wil::details::ResultStringSize(a3, a2), v9 = v8 - (_QWORD)Destination, v10 = v6, v9 >= v6) )
  {
    memcpy_s(Destination, v9, v7, v6);
    if ( a4 )
      *a4 = Destination;
    return (char *)Destination + v10;
  }
  else
  {
    if ( a4 )
      *a4 = 0;
    return (char *)Destination;
  }
}

```

## disassembly

```asm
0x180009240  push    rbx
0x180009242  push    rbp
0x180009243  push    rsi
0x180009244  push    rdi
0x180009245  sub     rsp, 28h
0x180009249  xor     ebp, ebp
0x18000924b  mov     rbx, r9
0x18000924e  mov     r10, rdx
0x180009251  mov     rdi, rcx
0x180009254  cmp     rcx, rdx
0x180009257  jz      short loc_180009294
0x180009259  test    r8, r8
0x18000925c  jz      short loc_180009294
0x18000925e  cmp     [r8], bp
0x180009262  jz      short loc_180009294
0x180009264  mov     rcx, r8; this
0x180009267  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x18000926c  sub     r10, rdi
0x18000926f  mov     rsi, rax
0x180009272  cmp     r10, rax
0x180009275  jb      short loc_180009294
0x180009277  mov     r9, rax; SourceSize
0x18000927a  mov     rdx, r10; DestinationSize
0x18000927d  mov     rcx, rdi; Destination
0x180009280  call    cs:__imp_memcpy_s
0x180009286  test    rbx, rbx
0x180009289  jz      short loc_18000928E
0x18000928b  mov     [rbx], rdi
0x18000928e  lea     rax, [rsi+rdi]
0x180009292  jmp     short loc_18000929F
0x180009294  test    rbx, rbx
0x180009297  jz      short loc_18000929C
0x180009299  mov     [r9], rbp
0x18000929c  mov     rax, rdi
0x18000929f  add     rsp, 28h
0x1800092a3  pop     rdi
0x1800092a4  pop     rsi
0x1800092a5  pop     rbp
0x1800092a6  pop     rbx
0x1800092a7  retn
```
