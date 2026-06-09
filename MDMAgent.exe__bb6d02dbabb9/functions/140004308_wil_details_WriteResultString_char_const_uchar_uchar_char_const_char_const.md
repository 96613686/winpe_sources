# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x140004308`
- end: `0x140004379`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140006cd4`
- `0x140006e20`

## callees

- `0x140004308`
- `0x140006b48`
- `0x140008200`

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
0x140004308  mov     [rsp+arg_0], rbx
0x14000430d  mov     [rsp+arg_8], rsi
0x140004312  push    rdi
0x140004313  sub     rsp, 20h
0x140004317  mov     rbx, r9
0x14000431a  mov     rdi, rcx
0x14000431d  cmp     rcx, rdx
0x140004320  jz      short loc_140004359
0x140004322  test    r8, r8
0x140004325  jz      short loc_140004359
0x140004327  cmp     byte ptr [r8], 0
0x14000432b  jz      short loc_140004359
0x14000432d  mov     rcx, r8; this
0x140004330  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140004335  sub     rdx, rdi; DestinationSize
0x140004338  mov     rsi, rax
0x14000433b  cmp     rdx, rax
0x14000433e  jb      short loc_140004359
0x140004340  mov     r9, rax; SourceSize
0x140004343  mov     rcx, rdi; Destination
0x140004346  call    memcpy_s
0x14000434b  test    rbx, rbx
0x14000434e  jz      short loc_140004353
0x140004350  mov     [rbx], rdi
0x140004353  lea     rax, [rsi+rdi]
0x140004357  jmp     short loc_140004368
0x140004359  test    rbx, rbx
0x14000435c  jz      short loc_140004365
0x14000435e  mov     qword ptr [r9], 0
0x140004365  mov     rax, rdi
0x140004368  mov     rbx, [rsp+28h+arg_0]
0x14000436d  mov     rsi, [rsp+28h+arg_8]
0x140004372  add     rsp, 20h
0x140004376  pop     rdi
0x140004377  retn
```
