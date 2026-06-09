# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180013710`
- end: `0x180013780`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180015afc`
- `0x180015c38`

## callees

- `0x180013710`
- `0x180015a18`
- `0x180016a74`

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
0x180013710  mov     [rsp+arg_0], rbx
0x180013715  mov     [rsp+arg_8], rsi
0x18001371a  push    rdi
0x18001371b  sub     rsp, 20h
0x18001371f  mov     rbx, r9
0x180013722  mov     rdi, rcx
0x180013725  cmp     rcx, rdx
0x180013728  jz      short loc_180013761
0x18001372a  test    r8, r8
0x18001372d  jz      short loc_180013761
0x18001372f  cmp     byte ptr [r8], 0
0x180013733  jz      short loc_180013761
0x180013735  mov     rcx, r8; this
0x180013738  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18001373d  sub     rdx, rdi; DestinationSize
0x180013740  mov     rsi, rax
0x180013743  cmp     rdx, rax
0x180013746  jb      short loc_180013761
0x180013748  mov     r9, rax; SourceSize
0x18001374b  mov     rcx, rdi; Destination
0x18001374e  call    memcpy_s
0x180013753  test    rbx, rbx
0x180013756  jz      short loc_18001375B
0x180013758  mov     [rbx], rdi
0x18001375b  lea     rax, [rsi+rdi]
0x18001375f  jmp     short loc_180013770
0x180013761  test    rbx, rbx
0x180013764  jz      short loc_18001376D
0x180013766  mov     qword ptr [r9], 0
0x18001376d  mov     rax, rdi
0x180013770  mov     rbx, [rsp+28h+arg_0]
0x180013775  mov     rsi, [rsp+28h+arg_8]
0x18001377a  add     rsp, 20h
0x18001377e  pop     rdi
0x18001377f  retn
```
