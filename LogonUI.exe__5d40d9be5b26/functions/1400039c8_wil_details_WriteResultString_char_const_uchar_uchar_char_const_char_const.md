# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x1400039c8`
- end: `0x140003a38`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140006254`

## callees

- `0x140001cdc`
- `0x1400039c8`
- `0x1400060dc`

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
0x1400039c8  mov     [rsp+arg_0], rbx
0x1400039cd  mov     [rsp+arg_8], rsi
0x1400039d2  push    rdi
0x1400039d3  sub     rsp, 20h
0x1400039d7  mov     rbx, r9
0x1400039da  mov     rdi, rcx
0x1400039dd  cmp     rcx, rdx
0x1400039e0  jz      short loc_140003A19
0x1400039e2  test    r8, r8
0x1400039e5  jz      short loc_140003A19
0x1400039e7  cmp     byte ptr [r8], 0
0x1400039eb  jz      short loc_140003A19
0x1400039ed  mov     rcx, r8; this
0x1400039f0  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1400039f5  sub     rdx, rdi; DestinationSize
0x1400039f8  mov     rsi, rax
0x1400039fb  cmp     rdx, rax
0x1400039fe  jb      short loc_140003A19
0x140003a00  mov     r9, rax; SourceSize
0x140003a03  mov     rcx, rdi; Destination
0x140003a06  call    memcpy_s
0x140003a0b  test    rbx, rbx
0x140003a0e  jz      short loc_140003A13
0x140003a10  mov     [rbx], rdi
0x140003a13  lea     rax, [rsi+rdi]
0x140003a17  jmp     short loc_140003A28
0x140003a19  test    rbx, rbx
0x140003a1c  jz      short loc_140003A25
0x140003a1e  mov     qword ptr [r9], 0
0x140003a25  mov     rax, rdi
0x140003a28  mov     rbx, [rsp+28h+arg_0]
0x140003a2d  mov     rsi, [rsp+28h+arg_8]
0x140003a32  add     rsp, 20h
0x140003a36  pop     rdi
0x140003a37  retn
```
