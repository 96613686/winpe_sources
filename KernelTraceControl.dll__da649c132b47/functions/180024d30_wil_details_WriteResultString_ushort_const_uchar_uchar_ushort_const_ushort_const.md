# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180024d30`
- end: `0x180024de9`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `185`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001f568`
- `0x1800206b0`

## callees

- `0x180024d30`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180024da1`
- `msvcrt!memcpy_s` at `0x180024da1`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<unsigned short const *>(
        char *Destination,
        __int64 a2,
        __int16 *a3,
        _QWORD *a4)
{
  __int16 *v5; // rcx
  unsigned __int64 v7; // rsi
  __int64 v8; // rax
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rbx
  __int64 v12; // r14
  char *v13; // rax
  __int16 v15; // [rsp+40h] [rbp+8h] BYREF

  v15 = 0;
  v5 = &v15;
  if ( a3 )
    v5 = a3;
  if ( v5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( v5[v8] );
    v7 = 2 * v8 + 2;
  }
  else
  {
    v7 = 2;
  }
  v9 = v7 >> 1;
  v10 = (unsigned __int64)(a2 - (_QWORD)Destination) >> 1;
  v11 = v10;
  if ( v9 < v10 )
    v11 = v9;
  v12 = 2 * v11;
  memcpy_s(Destination, 2 * v10, v5, 2 * v11);
  if ( a4 )
  {
    v13 = 0;
    if ( v11 > 1 )
      v13 = Destination;
    *a4 = v13;
  }
  if ( v11 < v9 && v11 )
    *(_WORD *)&Destination[v12 - 2] = 0;
  return &Destination[v12];
}

```

## disassembly

```asm
0x180024d30  mov     rax, rsp
0x180024d33  mov     [rax+10h], rbx
0x180024d37  mov     [rax+18h], rbp
0x180024d3b  mov     [rax+20h], rsi
0x180024d3f  push    rdi
0x180024d40  push    r14
0x180024d42  push    r15
0x180024d44  sub     rsp, 20h
0x180024d48  xor     ebp, ebp
0x180024d4a  mov     rdi, rcx
0x180024d4d  test    r8, r8
0x180024d50  mov     [rax+8], bp
0x180024d54  lea     rcx, [rax+8]
0x180024d58  mov     r15, r9
0x180024d5b  cmovnz  rcx, r8
0x180024d5f  test    rcx, rcx
0x180024d62  jnz     short loc_180024D69
0x180024d64  lea     esi, [rbp+2]
0x180024d67  jmp     short loc_180024D7E
0x180024d69  or      rax, 0FFFFFFFFFFFFFFFFh
0x180024d6d  inc     rax
0x180024d70  cmp     [rcx+rax*2], bp
0x180024d74  jnz     short loc_180024D6D
0x180024d76  lea     rsi, ds:2[rax*2]
0x180024d7e  sub     rdx, rdi
0x180024d81  shr     rsi, 1
0x180024d84  shr     rdx, 1
0x180024d87  mov     r8, rcx; Source
0x180024d8a  cmp     rsi, rdx
0x180024d8d  mov     rbx, rdx
0x180024d90  mov     rcx, rdi; Destination
0x180024d93  cmovb   rbx, rsi
0x180024d97  add     rdx, rdx; DestinationSize
0x180024d9a  lea     r14, [rbx+rbx]
0x180024d9e  mov     r9, r14; SourceSize
0x180024da1  call    cs:__imp_memcpy_s
0x180024da7  test    r15, r15
0x180024daa  jz      short loc_180024DBA
0x180024dac  cmp     rbx, 1
0x180024db0  mov     rax, rbp
0x180024db3  cmova   rax, rdi
0x180024db7  mov     [r15], rax
0x180024dba  cmp     rbx, rsi
0x180024dbd  jnb     short loc_180024DCC
0x180024dbf  test    rbx, rbx
0x180024dc2  jz      short loc_180024DCC
0x180024dc4  xor     eax, eax
0x180024dc6  mov     [r14+rdi-2], ax
0x180024dcc  mov     rbx, [rsp+38h+arg_8]
0x180024dd1  lea     rax, [r14+rdi]
0x180024dd5  mov     rbp, [rsp+38h+arg_10]
0x180024dda  mov     rsi, [rsp+38h+arg_18]
0x180024ddf  add     rsp, 20h
0x180024de3  pop     r15
0x180024de5  pop     r14
0x180024de7  pop     rdi
0x180024de8  retn
```
