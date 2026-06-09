# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x140002728`
- end: `0x140002798`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400042b8`

## callees

- `0x140002728`
- `0x140004090`
- `0x140004bb8`

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
0x140002728  mov     [rsp+arg_0], rbx
0x14000272d  mov     [rsp+arg_8], rsi
0x140002732  push    rdi
0x140002733  sub     rsp, 20h
0x140002737  mov     rbx, r9
0x14000273a  mov     rdi, rcx
0x14000273d  cmp     rcx, rdx
0x140002740  jz      short loc_140002779
0x140002742  test    r8, r8
0x140002745  jz      short loc_140002779
0x140002747  cmp     byte ptr [r8], 0
0x14000274b  jz      short loc_140002779
0x14000274d  mov     rcx, r8; this
0x140002750  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140002755  sub     rdx, rdi; DestinationSize
0x140002758  mov     rsi, rax
0x14000275b  cmp     rdx, rax
0x14000275e  jb      short loc_140002779
0x140002760  mov     r9, rax; SourceSize
0x140002763  mov     rcx, rdi; Destination
0x140002766  call    memcpy_s
0x14000276b  test    rbx, rbx
0x14000276e  jz      short loc_140002773
0x140002770  mov     [rbx], rdi
0x140002773  lea     rax, [rsi+rdi]
0x140002777  jmp     short loc_140002788
0x140002779  test    rbx, rbx
0x14000277c  jz      short loc_140002785
0x14000277e  mov     qword ptr [r9], 0
0x140002785  mov     rax, rdi
0x140002788  mov     rbx, [rsp+28h+arg_0]
0x14000278d  mov     rsi, [rsp+28h+arg_8]
0x140002792  add     rsp, 20h
0x140002796  pop     rdi
0x140002797  retn
```
