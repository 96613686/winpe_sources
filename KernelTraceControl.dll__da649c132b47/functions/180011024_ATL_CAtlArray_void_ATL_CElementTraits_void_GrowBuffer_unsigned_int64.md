# ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::GrowBuffer(unsigned __int64)

- ea: `0x180011024`
- end: `0x180011120`
- name: `?GrowBuffer@?$CAtlArray@PEAXV?$CElementTraits@PEAX@ATL@@@ATL@@AEAA_N_K@Z`
- size: `252`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800098d0`
- `0x180010df4`
- `0x1800140dc`

## callees

- `0x18000139c`
- `0x180011024`

## import_xrefs

- `msvcrt!calloc` at `0x18001105f`
- `msvcrt!calloc` at `0x1800110a0`
- `msvcrt!calloc` at `0x18001105f`
- `msvcrt!calloc` at `0x1800110a0`
- `msvcrt!free` at `0x1800110e0`
- `msvcrt!free` at `0x1800110e0`
- `msvcrt!memmove_s` at `0x1800110bf`
- `msvcrt!memmove_s` at `0x1800110bf`

## pseudocode

```c
char __fastcall ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::GrowBuffer(__int64 a1, size_t a2)
{
  unsigned __int64 v4; // rdx
  void *v5; // rax
  size_t v7; // rcx
  void *v8; // rax
  void *v9; // rsi
  errno_t v10; // eax

  v4 = *(_QWORD *)(a1 + 16);
  if ( a2 > v4 )
  {
    if ( *(_QWORD *)a1 )
    {
      v7 = *(int *)(a1 + 24);
      if ( !v7 )
      {
        v7 = v4 >> 1;
        if ( a2 - v4 > v4 >> 1 )
          v7 = a2 - v4;
      }
      if ( a2 < v4 + v7 )
        a2 = v4 + v7;
      v8 = calloc(a2, 8u);
      v9 = v8;
      if ( !v8 )
        return 0;
      v10 = memmove_s(v8, 8LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 8LL * *(_QWORD *)(a1 + 8));
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
      *(_QWORD *)a1 = v9;
    }
    else
    {
      if ( *(int *)(a1 + 24) > a2 )
        a2 = *(int *)(a1 + 24);
      v5 = calloc(a2, 8u);
      *(_QWORD *)a1 = v5;
      if ( !v5 )
        return 0;
    }
    *(_QWORD *)(a1 + 16) = a2;
  }
  return 1;
}

```

## disassembly

```asm
0x180011024  mov     [rsp+arg_0], rbx
0x180011029  mov     [rsp+arg_8], rsi
0x18001102e  push    rdi
0x18001102f  sub     rsp, 20h
0x180011033  mov     rdi, rdx
0x180011036  mov     rbx, rcx
0x180011039  mov     rdx, [rcx+10h]
0x18001103d  cmp     rdi, rdx
0x180011040  jbe     loc_1800110ED
0x180011046  cmp     qword ptr [rcx], 0
0x18001104a  jnz     short loc_180011071
0x18001104c  movsxd  rax, dword ptr [rcx+18h]
0x180011050  mov     edx, 8; Size
0x180011055  cmp     rax, rdi
0x180011058  cmova   rdi, rax
0x18001105c  mov     rcx, rdi; Count
0x18001105f  call    cs:__imp_calloc
0x180011065  mov     [rbx], rax
0x180011068  test    rax, rax
0x18001106b  jnz     short loc_1800110E9
0x18001106d  xor     al, al
0x18001106f  jmp     short loc_1800110EF
0x180011071  movsxd  rcx, dword ptr [rcx+18h]
0x180011075  test    rcx, rcx
0x180011078  jnz     short loc_18001108D
0x18001107a  mov     rcx, rdx
0x18001107d  mov     rax, rdi
0x180011080  shr     rcx, 1
0x180011083  sub     rax, rdx
0x180011086  cmp     rax, rcx
0x180011089  cmova   rcx, rax
0x18001108d  lea     rax, [rdx+rcx]
0x180011091  mov     edx, 8; Size
0x180011096  cmp     rdi, rax
0x180011099  cmovb   rdi, rax
0x18001109d  mov     rcx, rdi; Count
0x1800110a0  call    cs:__imp_calloc
0x1800110a6  mov     rsi, rax
0x1800110a9  test    rax, rax
0x1800110ac  jz      short loc_18001106D
0x1800110ae  mov     rdx, [rbx+8]
0x1800110b2  mov     rcx, rax; Destination
0x1800110b5  mov     r8, [rbx]; Source
0x1800110b8  shl     rdx, 3; DestinationSize
0x1800110bc  mov     r9, rdx; SourceSize
0x1800110bf  call    cs:__imp_memmove_s
0x1800110c5  test    eax, eax
0x1800110c7  jz      short loc_1800110DD
0x1800110c9  cmp     eax, 0Ch
0x1800110cc  jz      short loc_180011115
0x1800110ce  cmp     eax, 16h
0x1800110d1  jz      short loc_18001110A
0x1800110d3  cmp     eax, 22h ; '"'
0x1800110d6  jz      short loc_18001110A
0x1800110d8  cmp     eax, 50h ; 'P'
0x1800110db  jnz     short loc_1800110FF
0x1800110dd  mov     rcx, [rbx]; Block
0x1800110e0  call    cs:__imp_free
0x1800110e6  mov     [rbx], rsi
0x1800110e9  mov     [rbx+10h], rdi
0x1800110ed  mov     al, 1
0x1800110ef  mov     rbx, [rsp+28h+arg_0]
0x1800110f4  mov     rsi, [rsp+28h+arg_8]
0x1800110f9  add     rsp, 20h
0x1800110fd  pop     rdi
0x1800110fe  retn
0x1800110ff  mov     ecx, 80004005h; int
0x180011104  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001110a  mov     ecx, 80070057h; int
0x18001110f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180011115  mov     ecx, 8007000Eh; int
0x18001111a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
