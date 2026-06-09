# ATL::CAtlArray<ulong,ATL::CElementTraits<ulong>>::GrowBuffer(unsigned __int64)

- ea: `0x1800294e4`
- end: `0x1800295de`
- name: `?GrowBuffer@?$CAtlArray@KV?$CElementTraits@K@ATL@@@ATL@@AEAA_N_K@Z`
- size: `250`
- prototype: `char __fastcall(__int64, size_t)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800264f4`
- `0x18002d720`

## callees

- `0x1800082e4`
- `0x1800294e4`

## import_xrefs

- `msvcrt!memmove_s` at `0x18002957d`
- `msvcrt!memmove_s` at `0x18002957d`
- `msvcrt!free` at `0x18002959e`
- `msvcrt!free` at `0x18002959e`
- `msvcrt!calloc` at `0x18002951f`
- `msvcrt!calloc` at `0x18002955a`
- `msvcrt!calloc` at `0x18002951f`
- `msvcrt!calloc` at `0x18002955a`

## pseudocode

```c
char __fastcall ATL::CAtlArray<unsigned long,ATL::CElementTraits<unsigned long>>::GrowBuffer(__int64 a1, size_t a2)
{
  size_t v4; // rdx
  size_t v5; // rcx
  void *v6; // rax
  void *v7; // rax
  void *v8; // rsi
  errno_t v10; // eax

  v4 = *(_QWORD *)(a1 + 16);
  if ( a2 <= v4 )
    return 1;
  v5 = *(int *)(a1 + 24);
  if ( *(_QWORD *)a1 )
  {
    if ( !v5 )
    {
      v5 = v4 >> 1;
      if ( a2 - v4 > v4 >> 1 )
        v5 = a2 - v4;
    }
    if ( a2 < v4 + v5 )
      a2 = v4 + v5;
    v7 = calloc(a2, 4u);
    v8 = v7;
    if ( v7 )
    {
      v10 = memmove_s(v7, 4LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 4LL * *(_QWORD *)(a1 + 8));
      if ( v10 )
      {
        if ( v10 == 12 )
          ATL::AtlThrowImpl(-2147024882);
        if ( v10 == 22 || v10 == 34 )
          ATL::AtlThrowImpl(-2147024809);
        if ( v10 != 80 )
          ATL::AtlThrowImpl(-2147467259);
      }
      free(*(void **)a1);
      *(_QWORD *)a1 = v8;
      goto LABEL_20;
    }
    return 0;
  }
  if ( v5 > a2 )
    a2 = v5;
  v6 = calloc(a2, 4u);
  *(_QWORD *)a1 = v6;
  if ( !v6 )
    return 0;
LABEL_20:
  *(_QWORD *)(a1 + 16) = a2;
  return 1;
}

```

## disassembly

```asm
0x1800294e4  mov     [rsp+arg_0], rbx
0x1800294e9  mov     [rsp+arg_8], rsi
0x1800294ee  push    rdi
0x1800294ef  sub     rsp, 20h
0x1800294f3  mov     rdi, rdx
0x1800294f6  mov     rbx, rcx
0x1800294f9  mov     rdx, [rcx+10h]
0x1800294fd  cmp     rdi, rdx
0x180029500  jbe     loc_1800295AB
0x180029506  cmp     qword ptr [rbx], 0
0x18002950a  movsxd  rcx, dword ptr [rcx+18h]
0x18002950e  jnz     short loc_18002952F
0x180029510  cmp     rcx, rdi
0x180029513  mov     edx, 4; Size
0x180029518  cmova   rdi, rcx
0x18002951c  mov     rcx, rdi; Count
0x18002951f  call    cs:__imp_calloc
0x180029525  mov     [rbx], rax
0x180029528  test    rax, rax
0x18002952b  jz      short loc_180029568
0x18002952d  jmp     short loc_1800295A7
0x18002952f  test    rcx, rcx
0x180029532  jnz     short loc_180029547
0x180029534  mov     rcx, rdx
0x180029537  mov     rax, rdi
0x18002953a  shr     rcx, 1
0x18002953d  sub     rax, rdx
0x180029540  cmp     rax, rcx
0x180029543  cmova   rcx, rax
0x180029547  lea     rax, [rdx+rcx]
0x18002954b  mov     edx, 4; Size
0x180029550  cmp     rdi, rax
0x180029553  cmovb   rdi, rax
0x180029557  mov     rcx, rdi; Count
0x18002955a  call    cs:__imp_calloc
0x180029560  mov     rsi, rax
0x180029563  test    rax, rax
0x180029566  jnz     short loc_18002956C
0x180029568  xor     al, al
0x18002956a  jmp     short loc_1800295AD
0x18002956c  mov     rdx, [rbx+8]
0x180029570  mov     rcx, rsi; Destination
0x180029573  mov     r8, [rbx]; Source
0x180029576  shl     rdx, 2; DestinationSize
0x18002957a  mov     r9, rdx; SourceSize
0x18002957d  call    cs:__imp_memmove_s
0x180029583  test    eax, eax
0x180029585  jz      short loc_18002959B
0x180029587  cmp     eax, 0Ch
0x18002958a  jz      short loc_1800295D3
0x18002958c  cmp     eax, 16h
0x18002958f  jz      short loc_1800295C8
0x180029591  cmp     eax, 22h ; '"'
0x180029594  jz      short loc_1800295C8
0x180029596  cmp     eax, 50h ; 'P'
0x180029599  jnz     short loc_1800295BD
0x18002959b  mov     rcx, [rbx]; Block
0x18002959e  call    cs:__imp_free
0x1800295a4  mov     [rbx], rsi
0x1800295a7  mov     [rbx+10h], rdi
0x1800295ab  mov     al, 1
0x1800295ad  mov     rbx, [rsp+28h+arg_0]
0x1800295b2  mov     rsi, [rsp+28h+arg_8]
0x1800295b7  add     rsp, 20h
0x1800295bb  pop     rdi
0x1800295bc  retn
0x1800295bd  mov     ecx, 80004005h; int
0x1800295c2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800295c8  mov     ecx, 80070057h; int
0x1800295cd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800295d3  mov     ecx, 8007000Eh; int
0x1800295d8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
