# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x1400039ec`
- end: `0x140003a5c`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140006b50`
- `0x140006c8c`

## callees

- `0x1400039ec`
- `0x1400069d8`
- `0x1400080c0`

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
0x1400039ec  mov     [rsp+arg_0], rbx
0x1400039f1  mov     [rsp+arg_8], rsi
0x1400039f6  push    rdi
0x1400039f7  sub     rsp, 20h
0x1400039fb  mov     rbx, r9
0x1400039fe  mov     rdi, rcx
0x140003a01  cmp     rcx, rdx
0x140003a04  jz      short loc_140003A3D
0x140003a06  test    r8, r8
0x140003a09  jz      short loc_140003A3D
0x140003a0b  cmp     byte ptr [r8], 0
0x140003a0f  jz      short loc_140003A3D
0x140003a11  mov     rcx, r8; this
0x140003a14  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140003a19  sub     rdx, rdi; DestinationSize
0x140003a1c  mov     rsi, rax
0x140003a1f  cmp     rdx, rax
0x140003a22  jb      short loc_140003A3D
0x140003a24  mov     r9, rax; SourceSize
0x140003a27  mov     rcx, rdi; Destination
0x140003a2a  call    memcpy_s
0x140003a2f  test    rbx, rbx
0x140003a32  jz      short loc_140003A37
0x140003a34  mov     [rbx], rdi
0x140003a37  lea     rax, [rsi+rdi]
0x140003a3b  jmp     short loc_140003A4C
0x140003a3d  test    rbx, rbx
0x140003a40  jz      short loc_140003A49
0x140003a42  mov     qword ptr [r9], 0
0x140003a49  mov     rax, rdi
0x140003a4c  mov     rbx, [rsp+28h+arg_0]
0x140003a51  mov     rsi, [rsp+28h+arg_8]
0x140003a56  add     rsp, 20h
0x140003a5a  pop     rdi
0x140003a5b  retn
```
