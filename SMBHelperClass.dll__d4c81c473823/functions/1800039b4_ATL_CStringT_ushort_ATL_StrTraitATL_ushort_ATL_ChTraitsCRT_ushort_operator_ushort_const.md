# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ushort const *)

- ea: `0x1800039b4`
- end: `0x180003ae3`
- name: `??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBG@Z`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004ee0`

## callees

- `0x1800039b4`
- `0x180004684`
- `0x180007250`
- `0x180012010`

## import_xrefs

- `msvcrt!memmove_s` at `0x180003a2e`
- `msvcrt!memmove_s` at `0x180003a2e`
- `msvcrt!memcpy_s` at `0x180003a39`
- `msvcrt!memcpy_s` at `0x180003a39`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int **__fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        int **a1,
        char *a2)
{
  __int64 v4; // rbx
  unsigned __int64 v5; // r15
  unsigned __int64 v6; // rbp
  char *v7; // rcx
  rsize_t v8; // r9
  int *v9; // rax
  volatile signed __int32 *v10; // rdx
  __int64 v11; // rbx

  if ( !a2 )
    goto LABEL_13;
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)&a2[2 * v4] );
  if ( (_DWORD)v4 )
  {
    v5 = (unsigned int)*(*a1 - 4);
    v6 = (a2 - (char *)*a1) >> 1;
    if ( (int)((*(*a1 - 3) - v4) | (1 - *(*a1 - 2))) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, (unsigned int)v4);
    v7 = (char *)*a1;
    v8 = 2LL * (int)v4;
    if ( v6 > v5 )
      memcpy_s(v7, v8, a2, v8);
    else
      memmove_s(v7, v8, &v7[2 * v6], v8);
    if ( (int)v4 < 0 || (int)v4 > *(*a1 - 3) )
      ATL::AtlThrowImpl(-2147024809);
    *(*a1 - 4) = v4;
    *((_WORD *)*a1 + (int)v4) = 0;
  }
  else
  {
LABEL_13:
    v9 = *a1;
    v10 = *a1 - 6;
    if ( *((_DWORD *)v10 + 2) )
    {
      if ( *((int *)v10 + 4) >= 0 )
      {
        v11 = *(_QWORD *)v10;
        if ( _InterlockedDecrement(v10 + 4) <= 0 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v10 + 8LL))(*(_QWORD *)v10);
        *a1 = (int *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 24LL))(v11) + 24);
      }
      else
      {
        if ( *(v9 - 3) < 0 )
          ATL::AtlThrowImpl(-2147024809);
        *(v9 - 4) = 0;
        *(_WORD *)*a1 = 0;
      }
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800039b4  push    rbx
0x1800039b6  push    rbp
0x1800039b7  push    rsi
0x1800039b8  push    rdi
0x1800039b9  push    r12
0x1800039bb  push    r14
0x1800039bd  push    r15
0x1800039bf  sub     rsp, 20h
0x1800039c3  mov     r14, rdx
0x1800039c6  mov     rdi, rcx
0x1800039c9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800039cd  xor     r12d, r12d
0x1800039d0  test    rdx, rdx
0x1800039d3  jz      loc_180003A60
0x1800039d9  mov     rbx, rcx
0x1800039dc  inc     rbx
0x1800039df  cmp     [rdx+rbx*2], r12w
0x1800039e4  jnz     short loc_1800039DC
0x1800039e6  test    ebx, ebx
0x1800039e8  jz      short loc_180003A60
0x1800039ea  mov     rax, [rdi]
0x1800039ed  mov     r15d, [rax-10h]
0x1800039f1  mov     rbp, r14
0x1800039f4  sub     rbp, rax
0x1800039f7  sar     rbp, 1
0x1800039fa  mov     ecx, 1
0x1800039ff  sub     ecx, [rax-8]
0x180003a02  mov     eax, [rax-0Ch]
0x180003a05  sub     eax, ebx
0x180003a07  or      ecx, eax
0x180003a09  jge     short loc_180003A15
0x180003a0b  mov     edx, ebx
0x180003a0d  mov     rcx, rdi
0x180003a10  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180003a15  mov     rcx, [rdi]; Destination
0x180003a18  movsxd  rax, ebx
0x180003a1b  lea     rsi, [rax+rax]
0x180003a1f  mov     r9, rsi; SourceSize
0x180003a22  mov     rdx, rsi; DestinationSize
0x180003a25  cmp     rbp, r15
0x180003a28  ja      short loc_180003A36
0x180003a2a  lea     r8, [rcx+rbp*2]; Source
0x180003a2e  call    cs:__imp_memmove_s
0x180003a34  jmp     short loc_180003A3F
0x180003a36  mov     r8, r14; Source
0x180003a39  call    cs:__imp_memcpy_s
0x180003a3f  test    ebx, ebx
0x180003a41  js      loc_180003AD8
0x180003a47  mov     rax, [rdi]
0x180003a4a  cmp     ebx, [rax-0Ch]
0x180003a4d  jg      loc_180003AD8
0x180003a53  mov     [rax-10h], ebx
0x180003a56  mov     rcx, [rdi]
0x180003a59  mov     [rsi+rcx], r12w
0x180003a5e  jmp     short loc_180003ABB
0x180003a60  mov     rax, [rdi]
0x180003a63  lea     rdx, [rax-18h]
0x180003a67  cmp     [rdx+8], r12d
0x180003a6b  jz      short loc_180003ABB
0x180003a6d  cmp     [rdx+10h], r12d
0x180003a71  jge     short loc_180003A86
0x180003a73  cmp     [rax-0Ch], r12d
0x180003a77  jl      short loc_180003ACD
0x180003a79  mov     [rax-10h], r12d
0x180003a7d  mov     rcx, [rdi]
0x180003a80  mov     [rcx], r12w
0x180003a84  jmp     short loc_180003ABB
0x180003a86  mov     rbx, [rdx]
0x180003a89  mov     eax, ecx
0x180003a8b  lock xadd [rdx+10h], eax
0x180003a90  add     eax, ecx
0x180003a92  test    eax, eax
0x180003a94  jg      short loc_180003AA5
0x180003a96  mov     rcx, [rdx]
0x180003a99  mov     rax, [rcx]
0x180003a9c  mov     rax, [rax+8]
0x180003aa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003aa5  mov     rax, [rbx]
0x180003aa8  mov     rcx, rbx
0x180003aab  mov     rax, [rax+18h]
0x180003aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ab4  add     rax, 18h
0x180003ab8  mov     [rdi], rax
0x180003abb  mov     rax, rdi
0x180003abe  add     rsp, 20h
0x180003ac2  pop     r15
0x180003ac4  pop     r14
0x180003ac6  pop     r12
0x180003ac8  pop     rdi
0x180003ac9  pop     rsi
0x180003aca  pop     rbp
0x180003acb  pop     rbx
0x180003acc  retn
0x180003acd  mov     ecx, 80070057h; int
0x180003ad2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003ad8  mov     ecx, 80070057h; int
0x180003add  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
