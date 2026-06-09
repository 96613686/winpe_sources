# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180002dd4`
- end: `0x180002e44`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180004c3c`
- `0x180004d78`

## callees

- `0x180002dd4`
- `0x180004b58`
- `0x180005990`

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
0x180002dd4  mov     [rsp+arg_0], rbx
0x180002dd9  mov     [rsp+arg_8], rsi
0x180002dde  push    rdi
0x180002ddf  sub     rsp, 20h
0x180002de3  mov     rbx, r9
0x180002de6  mov     rdi, rcx
0x180002de9  cmp     rcx, rdx
0x180002dec  jz      short loc_180002E25
0x180002dee  test    r8, r8
0x180002df1  jz      short loc_180002E25
0x180002df3  cmp     byte ptr [r8], 0
0x180002df7  jz      short loc_180002E25
0x180002df9  mov     rcx, r8; this
0x180002dfc  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180002e01  sub     rdx, rdi; DestinationSize
0x180002e04  mov     rsi, rax
0x180002e07  cmp     rdx, rax
0x180002e0a  jb      short loc_180002E25
0x180002e0c  mov     r9, rax; SourceSize
0x180002e0f  mov     rcx, rdi; Destination
0x180002e12  call    memcpy_s
0x180002e17  test    rbx, rbx
0x180002e1a  jz      short loc_180002E1F
0x180002e1c  mov     [rbx], rdi
0x180002e1f  lea     rax, [rsi+rdi]
0x180002e23  jmp     short loc_180002E34
0x180002e25  test    rbx, rbx
0x180002e28  jz      short loc_180002E31
0x180002e2a  mov     qword ptr [r9], 0
0x180002e31  mov     rax, rdi
0x180002e34  mov     rbx, [rsp+28h+arg_0]
0x180002e39  mov     rsi, [rsp+28h+arg_8]
0x180002e3e  add     rsp, 20h
0x180002e42  pop     rdi
0x180002e43  retn
```
