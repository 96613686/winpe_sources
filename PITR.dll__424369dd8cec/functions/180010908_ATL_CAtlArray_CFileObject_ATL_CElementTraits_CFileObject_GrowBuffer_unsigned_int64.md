# ATL::CAtlArray<CFileObject *,ATL::CElementTraits<CFileObject *>>::GrowBuffer(unsigned __int64)

- ea: `0x180010908`
- end: `0x180010a02`
- name: `?GrowBuffer@?$CAtlArray@PEAVCFileObject@@V?$CElementTraits@PEAVCFileObject@@@ATL@@@ATL@@AEAA_N_K@Z`
- size: `250`
- prototype: `char __fastcall(__int64, size_t)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007ea4`
- `0x18001b508`

## callees

- `0x1800082e4`
- `0x180010908`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800109a1`
- `msvcrt!memmove_s` at `0x1800109a1`
- `msvcrt!free` at `0x1800109c2`
- `msvcrt!free` at `0x1800109c2`
- `msvcrt!calloc` at `0x180010943`
- `msvcrt!calloc` at `0x18001097e`
- `msvcrt!calloc` at `0x180010943`
- `msvcrt!calloc` at `0x18001097e`

## pseudocode

```c
char __fastcall ATL::CAtlArray<CFileObject *,ATL::CElementTraits<CFileObject *>>::GrowBuffer(__int64 a1, size_t a2)
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
    v7 = calloc(a2, 8u);
    v8 = v7;
    if ( v7 )
    {
      v10 = memmove_s(v7, 8LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 8LL * *(_QWORD *)(a1 + 8));
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
  v6 = calloc(a2, 8u);
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
0x180010908  mov     [rsp+arg_0], rbx
0x18001090d  mov     [rsp+arg_8], rsi
0x180010912  push    rdi
0x180010913  sub     rsp, 20h
0x180010917  mov     rdi, rdx
0x18001091a  mov     rbx, rcx
0x18001091d  mov     rdx, [rcx+10h]
0x180010921  cmp     rdi, rdx
0x180010924  jbe     loc_1800109CF
0x18001092a  cmp     qword ptr [rbx], 0
0x18001092e  movsxd  rcx, dword ptr [rcx+18h]
0x180010932  jnz     short loc_180010953
0x180010934  cmp     rcx, rdi
0x180010937  mov     edx, 8; Size
0x18001093c  cmova   rdi, rcx
0x180010940  mov     rcx, rdi; Count
0x180010943  call    cs:__imp_calloc
0x180010949  mov     [rbx], rax
0x18001094c  test    rax, rax
0x18001094f  jz      short loc_18001098C
0x180010951  jmp     short loc_1800109CB
0x180010953  test    rcx, rcx
0x180010956  jnz     short loc_18001096B
0x180010958  mov     rcx, rdx
0x18001095b  mov     rax, rdi
0x18001095e  shr     rcx, 1
0x180010961  sub     rax, rdx
0x180010964  cmp     rax, rcx
0x180010967  cmova   rcx, rax
0x18001096b  lea     rax, [rdx+rcx]
0x18001096f  mov     edx, 8; Size
0x180010974  cmp     rdi, rax
0x180010977  cmovb   rdi, rax
0x18001097b  mov     rcx, rdi; Count
0x18001097e  call    cs:__imp_calloc
0x180010984  mov     rsi, rax
0x180010987  test    rax, rax
0x18001098a  jnz     short loc_180010990
0x18001098c  xor     al, al
0x18001098e  jmp     short loc_1800109D1
0x180010990  mov     rdx, [rbx+8]
0x180010994  mov     rcx, rsi; Destination
0x180010997  mov     r8, [rbx]; Source
0x18001099a  shl     rdx, 3; DestinationSize
0x18001099e  mov     r9, rdx; SourceSize
0x1800109a1  call    cs:__imp_memmove_s
0x1800109a7  test    eax, eax
0x1800109a9  jz      short loc_1800109BF
0x1800109ab  cmp     eax, 0Ch
0x1800109ae  jz      short loc_1800109F7
0x1800109b0  cmp     eax, 16h
0x1800109b3  jz      short loc_1800109EC
0x1800109b5  cmp     eax, 22h ; '"'
0x1800109b8  jz      short loc_1800109EC
0x1800109ba  cmp     eax, 50h ; 'P'
0x1800109bd  jnz     short loc_1800109E1
0x1800109bf  mov     rcx, [rbx]; Block
0x1800109c2  call    cs:__imp_free
0x1800109c8  mov     [rbx], rsi
0x1800109cb  mov     [rbx+10h], rdi
0x1800109cf  mov     al, 1
0x1800109d1  mov     rbx, [rsp+28h+arg_0]
0x1800109d6  mov     rsi, [rsp+28h+arg_8]
0x1800109db  add     rsp, 20h
0x1800109df  pop     rdi
0x1800109e0  retn
0x1800109e1  mov     ecx, 80004005h; int
0x1800109e6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800109ec  mov     ecx, 80070057h; int
0x1800109f1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800109f7  mov     ecx, 8007000Eh; int
0x1800109fc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
