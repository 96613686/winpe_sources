# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x18000366c`
- end: `0x1800036dc`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800094b0`
- `0x1800096e4`

## callees

- `0x18000366c`
- `0x180009328`
- `0x18000b43c`

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
0x18000366c  mov     [rsp+arg_0], rbx
0x180003671  mov     [rsp+arg_8], rsi
0x180003676  push    rdi
0x180003677  sub     rsp, 20h
0x18000367b  mov     rbx, r9
0x18000367e  mov     rdi, rcx
0x180003681  cmp     rcx, rdx
0x180003684  jz      short loc_1800036BD
0x180003686  test    r8, r8
0x180003689  jz      short loc_1800036BD
0x18000368b  cmp     byte ptr [r8], 0
0x18000368f  jz      short loc_1800036BD
0x180003691  mov     rcx, r8; this
0x180003694  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180003699  sub     rdx, rdi; DestinationSize
0x18000369c  mov     rsi, rax
0x18000369f  cmp     rdx, rax
0x1800036a2  jb      short loc_1800036BD
0x1800036a4  mov     r9, rax; SourceSize
0x1800036a7  mov     rcx, rdi; Destination
0x1800036aa  call    memcpy_s
0x1800036af  test    rbx, rbx
0x1800036b2  jz      short loc_1800036B7
0x1800036b4  mov     [rbx], rdi
0x1800036b7  lea     rax, [rsi+rdi]
0x1800036bb  jmp     short loc_1800036CC
0x1800036bd  test    rbx, rbx
0x1800036c0  jz      short loc_1800036C9
0x1800036c2  mov     qword ptr [r9], 0
0x1800036c9  mov     rax, rdi
0x1800036cc  mov     rbx, [rsp+28h+arg_0]
0x1800036d1  mov     rsi, [rsp+28h+arg_8]
0x1800036d6  add     rsp, 20h
0x1800036da  pop     rdi
0x1800036db  retn
```
