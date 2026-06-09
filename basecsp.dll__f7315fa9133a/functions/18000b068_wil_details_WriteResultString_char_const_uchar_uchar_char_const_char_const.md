# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x18000b068`
- end: `0x18000b0d9`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180016770`
- `0x1800169a4`

## callees

- `0x18000b068`
- `0x1800165e8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000b0a6`
- `msvcrt!memcpy_s` at `0x18000b0a6`

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
0x18000b068  mov     [rsp+arg_0], rbx
0x18000b06d  mov     [rsp+arg_8], rsi
0x18000b072  push    rdi
0x18000b073  sub     rsp, 20h
0x18000b077  mov     rbx, r9
0x18000b07a  mov     rdi, rcx
0x18000b07d  cmp     rcx, rdx
0x18000b080  jz      short loc_18000B0BA
0x18000b082  test    r8, r8
0x18000b085  jz      short loc_18000B0BA
0x18000b087  cmp     byte ptr [r8], 0
0x18000b08b  jz      short loc_18000B0BA
0x18000b08d  mov     rcx, r8; this
0x18000b090  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000b095  sub     rdx, rdi; DestinationSize
0x18000b098  mov     rsi, rax
0x18000b09b  cmp     rdx, rax
0x18000b09e  jb      short loc_18000B0BA
0x18000b0a0  mov     r9, rax; SourceSize
0x18000b0a3  mov     rcx, rdi; Destination
0x18000b0a6  call    cs:__imp_memcpy_s
0x18000b0ac  test    rbx, rbx
0x18000b0af  jz      short loc_18000B0B4
0x18000b0b1  mov     [rbx], rdi
0x18000b0b4  lea     rax, [rsi+rdi]
0x18000b0b8  jmp     short loc_18000B0C9
0x18000b0ba  test    rbx, rbx
0x18000b0bd  jz      short loc_18000B0C6
0x18000b0bf  mov     qword ptr [r9], 0
0x18000b0c6  mov     rax, rdi
0x18000b0c9  mov     rbx, [rsp+28h+arg_0]
0x18000b0ce  mov     rsi, [rsp+28h+arg_8]
0x18000b0d3  add     rsp, 20h
0x18000b0d7  pop     rdi
0x18000b0d8  retn
```
