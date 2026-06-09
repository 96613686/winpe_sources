# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x18000b518`
- end: `0x18000b588`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000cebc`
- `0x18000cff8`

## callees

- `0x180008854`
- `0x18000b518`
- `0x18000cdd8`

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
0x18000b518  mov     [rsp+arg_0], rbx
0x18000b51d  mov     [rsp+arg_8], rsi
0x18000b522  push    rdi
0x18000b523  sub     rsp, 20h
0x18000b527  mov     rbx, r9
0x18000b52a  mov     rdi, rcx
0x18000b52d  cmp     rcx, rdx
0x18000b530  jz      short loc_18000B569
0x18000b532  test    r8, r8
0x18000b535  jz      short loc_18000B569
0x18000b537  cmp     byte ptr [r8], 0
0x18000b53b  jz      short loc_18000B569
0x18000b53d  mov     rcx, r8; this
0x18000b540  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000b545  sub     rdx, rdi; DestinationSize
0x18000b548  mov     rsi, rax
0x18000b54b  cmp     rdx, rax
0x18000b54e  jb      short loc_18000B569
0x18000b550  mov     r9, rax; SourceSize
0x18000b553  mov     rcx, rdi; Destination
0x18000b556  call    memcpy_s
0x18000b55b  test    rbx, rbx
0x18000b55e  jz      short loc_18000B563
0x18000b560  mov     [rbx], rdi
0x18000b563  lea     rax, [rsi+rdi]
0x18000b567  jmp     short loc_18000B578
0x18000b569  test    rbx, rbx
0x18000b56c  jz      short loc_18000B575
0x18000b56e  mov     qword ptr [r9], 0
0x18000b575  mov     rax, rdi
0x18000b578  mov     rbx, [rsp+28h+arg_0]
0x18000b57d  mov     rsi, [rsp+28h+arg_8]
0x18000b582  add     rsp, 20h
0x18000b586  pop     rdi
0x18000b587  retn
```
