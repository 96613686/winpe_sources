# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180002fac`
- end: `0x18000301c`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180007570`
- `0x180007798`

## callees

- `0x180002fac`
- `0x1800073e0`
- `0x18000934c`

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
0x180002fac  mov     [rsp+arg_0], rbx
0x180002fb1  mov     [rsp+arg_8], rsi
0x180002fb6  push    rdi
0x180002fb7  sub     rsp, 20h
0x180002fbb  mov     rbx, r9
0x180002fbe  mov     rdi, rcx
0x180002fc1  cmp     rcx, rdx
0x180002fc4  jz      short loc_180002FFD
0x180002fc6  test    r8, r8
0x180002fc9  jz      short loc_180002FFD
0x180002fcb  cmp     byte ptr [r8], 0
0x180002fcf  jz      short loc_180002FFD
0x180002fd1  mov     rcx, r8; this
0x180002fd4  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180002fd9  sub     rdx, rdi; DestinationSize
0x180002fdc  mov     rsi, rax
0x180002fdf  cmp     rdx, rax
0x180002fe2  jb      short loc_180002FFD
0x180002fe4  mov     r9, rax; SourceSize
0x180002fe7  mov     rcx, rdi; Destination
0x180002fea  call    memcpy_s
0x180002fef  test    rbx, rbx
0x180002ff2  jz      short loc_180002FF7
0x180002ff4  mov     [rbx], rdi
0x180002ff7  lea     rax, [rsi+rdi]
0x180002ffb  jmp     short loc_18000300C
0x180002ffd  test    rbx, rbx
0x180003000  jz      short loc_180003009
0x180003002  mov     qword ptr [r9], 0
0x180003009  mov     rax, rdi
0x18000300c  mov     rbx, [rsp+28h+arg_0]
0x180003011  mov     rsi, [rsp+28h+arg_8]
0x180003016  add     rsp, 20h
0x18000301a  pop     rdi
0x18000301b  retn
```
