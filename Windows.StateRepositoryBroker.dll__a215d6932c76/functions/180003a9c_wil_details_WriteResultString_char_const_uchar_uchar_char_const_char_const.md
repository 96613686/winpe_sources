# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180003a9c`
- end: `0x180003b0c`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000629c`

## callees

- `0x180003a9c`
- `0x1800061c0`
- `0x180006c80`

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
    memcpy_s_0(Destination, v9, v7, v6);
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
0x180003a9c  mov     [rsp+arg_0], rbx
0x180003aa1  mov     [rsp+arg_8], rsi
0x180003aa6  push    rdi
0x180003aa7  sub     rsp, 20h
0x180003aab  mov     rbx, r9
0x180003aae  mov     rdi, rcx
0x180003ab1  cmp     rcx, rdx
0x180003ab4  jz      short loc_180003AED
0x180003ab6  test    r8, r8
0x180003ab9  jz      short loc_180003AED
0x180003abb  cmp     byte ptr [r8], 0
0x180003abf  jz      short loc_180003AED
0x180003ac1  mov     rcx, r8; this
0x180003ac4  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180003ac9  sub     rdx, rdi; DestinationSize
0x180003acc  mov     rsi, rax
0x180003acf  cmp     rdx, rax
0x180003ad2  jb      short loc_180003AED
0x180003ad4  mov     r9, rax; SourceSize
0x180003ad7  mov     rcx, rdi; Destination
0x180003ada  call    memcpy_s_0
0x180003adf  test    rbx, rbx
0x180003ae2  jz      short loc_180003AE7
0x180003ae4  mov     [rbx], rdi
0x180003ae7  lea     rax, [rsi+rdi]
0x180003aeb  jmp     short loc_180003AFC
0x180003aed  test    rbx, rbx
0x180003af0  jz      short loc_180003AF9
0x180003af2  mov     qword ptr [r9], 0
0x180003af9  mov     rax, rdi
0x180003afc  mov     rbx, [rsp+28h+arg_0]
0x180003b01  mov     rsi, [rsp+28h+arg_8]
0x180003b06  add     rsp, 20h
0x180003b0a  pop     rdi
0x180003b0b  retn
```
