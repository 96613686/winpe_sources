# ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::GrowBuffer(unsigned __int64)

- ea: `0x180011134`
- end: `0x180011230`
- name: `?GrowBuffer@?$CAtlArray@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@V?$CElementTraits@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@@3@@ATL@@AEAA_N_K@Z`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010f24`

## callees

- `0x18000139c`
- `0x180011134`

## import_xrefs

- `msvcrt!calloc` at `0x18001116f`
- `msvcrt!calloc` at `0x1800111b0`
- `msvcrt!calloc` at `0x18001116f`
- `msvcrt!calloc` at `0x1800111b0`
- `msvcrt!free` at `0x1800111f0`
- `msvcrt!free` at `0x1800111f0`
- `msvcrt!memmove_s` at `0x1800111cf`
- `msvcrt!memmove_s` at `0x1800111cf`

## pseudocode

```c
char __fastcall ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::GrowBuffer(
        __int64 a1,
        size_t a2)
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
      v8 = calloc(a2, 0x10u);
      v9 = v8;
      if ( !v8 )
        return 0;
      v10 = memmove_s(v8, 16LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 16LL * *(_QWORD *)(a1 + 8));
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
      v5 = calloc(a2, 0x10u);
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
0x180011134  mov     [rsp+arg_0], rbx
0x180011139  mov     [rsp+arg_8], rsi
0x18001113e  push    rdi
0x18001113f  sub     rsp, 20h
0x180011143  mov     rdi, rdx
0x180011146  mov     rbx, rcx
0x180011149  mov     rdx, [rcx+10h]
0x18001114d  cmp     rdi, rdx
0x180011150  jbe     loc_1800111FD
0x180011156  cmp     qword ptr [rcx], 0
0x18001115a  jnz     short loc_180011181
0x18001115c  movsxd  rax, dword ptr [rcx+18h]
0x180011160  mov     edx, 10h; Size
0x180011165  cmp     rax, rdi
0x180011168  cmova   rdi, rax
0x18001116c  mov     rcx, rdi; Count
0x18001116f  call    cs:__imp_calloc
0x180011175  mov     [rbx], rax
0x180011178  test    rax, rax
0x18001117b  jnz     short loc_1800111F9
0x18001117d  xor     al, al
0x18001117f  jmp     short loc_1800111FF
0x180011181  movsxd  rcx, dword ptr [rcx+18h]
0x180011185  test    rcx, rcx
0x180011188  jnz     short loc_18001119D
0x18001118a  mov     rcx, rdx
0x18001118d  mov     rax, rdi
0x180011190  shr     rcx, 1
0x180011193  sub     rax, rdx
0x180011196  cmp     rax, rcx
0x180011199  cmova   rcx, rax
0x18001119d  lea     rax, [rdx+rcx]
0x1800111a1  mov     edx, 10h; Size
0x1800111a6  cmp     rdi, rax
0x1800111a9  cmovb   rdi, rax
0x1800111ad  mov     rcx, rdi; Count
0x1800111b0  call    cs:__imp_calloc
0x1800111b6  mov     rsi, rax
0x1800111b9  test    rax, rax
0x1800111bc  jz      short loc_18001117D
0x1800111be  mov     rdx, [rbx+8]
0x1800111c2  mov     rcx, rax; Destination
0x1800111c5  mov     r8, [rbx]; Source
0x1800111c8  shl     rdx, 4; DestinationSize
0x1800111cc  mov     r9, rdx; SourceSize
0x1800111cf  call    cs:__imp_memmove_s
0x1800111d5  test    eax, eax
0x1800111d7  jz      short loc_1800111ED
0x1800111d9  cmp     eax, 0Ch
0x1800111dc  jz      short loc_180011225
0x1800111de  cmp     eax, 16h
0x1800111e1  jz      short loc_18001121A
0x1800111e3  cmp     eax, 22h ; '"'
0x1800111e6  jz      short loc_18001121A
0x1800111e8  cmp     eax, 50h ; 'P'
0x1800111eb  jnz     short loc_18001120F
0x1800111ed  mov     rcx, [rbx]; Block
0x1800111f0  call    cs:__imp_free
0x1800111f6  mov     [rbx], rsi
0x1800111f9  mov     [rbx+10h], rdi
0x1800111fd  mov     al, 1
0x1800111ff  mov     rbx, [rsp+28h+arg_0]
0x180011204  mov     rsi, [rsp+28h+arg_8]
0x180011209  add     rsp, 20h
0x18001120d  pop     rdi
0x18001120e  retn
0x18001120f  mov     ecx, 80004005h; int
0x180011214  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001121a  mov     ecx, 80070057h; int
0x18001121f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180011225  mov     ecx, 8007000Eh; int
0x18001122a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
