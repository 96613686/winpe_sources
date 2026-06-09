# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x1800101a4`
- end: `0x180010214`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800131a4`

## callees

- `0x18000dbd8`
- `0x1800101a4`
- `0x180013028`

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
0x1800101a4  mov     [rsp+arg_0], rbx
0x1800101a9  mov     [rsp+arg_8], rsi
0x1800101ae  push    rdi
0x1800101af  sub     rsp, 20h
0x1800101b3  mov     rbx, r9
0x1800101b6  mov     rdi, rcx
0x1800101b9  cmp     rcx, rdx
0x1800101bc  jz      short loc_1800101F5
0x1800101be  test    r8, r8
0x1800101c1  jz      short loc_1800101F5
0x1800101c3  cmp     byte ptr [r8], 0
0x1800101c7  jz      short loc_1800101F5
0x1800101c9  mov     rcx, r8; this
0x1800101cc  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800101d1  sub     rdx, rdi; DestinationSize
0x1800101d4  mov     rsi, rax
0x1800101d7  cmp     rdx, rax
0x1800101da  jb      short loc_1800101F5
0x1800101dc  mov     r9, rax; SourceSize
0x1800101df  mov     rcx, rdi; Destination
0x1800101e2  call    memcpy_s
0x1800101e7  test    rbx, rbx
0x1800101ea  jz      short loc_1800101EF
0x1800101ec  mov     [rbx], rdi
0x1800101ef  lea     rax, [rsi+rdi]
0x1800101f3  jmp     short loc_180010204
0x1800101f5  test    rbx, rbx
0x1800101f8  jz      short loc_180010201
0x1800101fa  mov     qword ptr [r9], 0
0x180010201  mov     rax, rdi
0x180010204  mov     rbx, [rsp+28h+arg_0]
0x180010209  mov     rsi, [rsp+28h+arg_8]
0x18001020e  add     rsp, 20h
0x180010212  pop     rdi
0x180010213  retn
```
