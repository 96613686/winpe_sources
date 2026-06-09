# std::vector<uchar,std::allocator<uchar>>::operator=(std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x180025174`
- end: `0x1800252dd`
- name: `??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@AEBV01@@Z`
- size: `361`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180020ccc`
- `0x18002259c`

## callees

- `0x180009570`
- `0x180009e14`
- `0x180025174`
- `0x18004a078`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x18002524b`
- `VCRUNTIME140!memmove` at `0x180025289`
- `VCRUNTIME140!memmove` at `0x1800252a0`
- `VCRUNTIME140!memmove` at `0x1800252b3`
- `VCRUNTIME140!memmove` at `0x18002524b`
- `VCRUNTIME140!memmove` at `0x180025289`
- `VCRUNTIME140!memmove` at `0x1800252a0`
- `VCRUNTIME140!memmove` at `0x1800252b3`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18002526a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18002526a`

## pseudocode

```c
__int64 __fastcall std::vector<unsigned char>::operator=(__int64 a1, char **a2)
{
  char *v3; // r14
  size_t v4; // rsi
  _QWORD *v5; // rbx
  unsigned __int64 v6; // rdx
  __int64 v7; // rbp
  unsigned __int64 v8; // rcx
  char *v9; // rax
  char *v10; // rbx
  char *v11; // rax
  size_t v12; // rbp
  _QWORD *v13; // rcx
  char *v14; // rbx
  size_t v15; // rsi

  if ( (char **)a1 != a2 )
  {
    v3 = *a2;
    v4 = a2[1] - *a2;
    v5 = *(_QWORD **)a1;
    v6 = *(_QWORD *)(a1 + 16) - *(_QWORD *)a1;
    if ( v4 <= v6 )
    {
      v12 = *(_QWORD *)(a1 + 8) - (_QWORD)v5;
      _mm_lfence();
      v13 = *(_QWORD **)a1;
      if ( v4 <= v12 )
      {
        memmove(v13, v3, v4);
        *(_QWORD *)(a1 + 8) = (char *)v5 + v4;
        return a1;
      }
      memmove(v13, v3, v12);
      v14 = *(char **)(a1 + 8);
      v15 = v4 - v12;
      memmove(v14, &v3[v12], v15);
      v11 = &v14[v15];
    }
    else
    {
      v7 = 0x7FFFFFFFFFFFFFFFLL;
      if ( v4 > 0x7FFFFFFFFFFFFFFFLL )
        std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>::_Xlength(a1, v6);
      v8 = v6 >> 1;
      if ( v6 <= 0x7FFFFFFFFFFFFFFFLL - (v6 >> 1) )
      {
        v7 = v6 + v8;
        if ( v6 + v8 < v4 )
          v7 = v4;
      }
      if ( v5 )
      {
        if ( v6 >= 0x1000 )
        {
          if ( (unsigned __int64)v5 - *(v5 - 1) - 8 > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
          v5 = (_QWORD *)*(v5 - 1);
        }
        _mm_lfence();
        operator delete(v5);
        *(_QWORD *)a1 = 0;
        *(_QWORD *)(a1 + 8) = 0;
        *(_QWORD *)(a1 + 16) = 0;
      }
      _mm_lfence();
      v9 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(v7);
      *(_QWORD *)a1 = v9;
      v10 = v9;
      *(_QWORD *)(a1 + 8) = v9;
      *(_QWORD *)(a1 + 16) = &v9[v7];
      memmove(v9, v3, v4);
      v11 = &v10[v4];
    }
    *(_QWORD *)(a1 + 8) = v11;
  }
  return a1;
}

```

## disassembly

```asm
0x180025174  mov     [rsp+arg_10], rbx
0x180025179  mov     [rsp+arg_18], rbp
0x18002517e  push    rsi
0x18002517f  push    rdi
0x180025180  push    r14
0x180025182  sub     rsp, 30h
0x180025186  mov     rdi, rcx
0x180025189  cmp     rcx, rdx
0x18002518c  jz      loc_1800252C1
0x180025192  mov     r14, [rdx]
0x180025195  mov     rsi, [rdx+8]
0x180025199  mov     rdx, [rcx+10h]
0x18002519d  sub     rsi, r14
0x1800251a0  mov     rbx, [rcx]
0x1800251a3  sub     rdx, rbx
0x1800251a6  cmp     rsi, rdx
0x1800251a9  jbe     loc_180025271
0x1800251af  mov     rbp, 7FFFFFFFFFFFFFFFh
0x1800251b9  cmp     rsi, rbp
0x1800251bc  ja      loc_1800252D7
0x1800251c2  mov     rcx, rdx
0x1800251c5  mov     rax, rbp
0x1800251c8  shr     rcx, 1
0x1800251cb  sub     rax, rcx
0x1800251ce  cmp     rdx, rax
0x1800251d1  ja      short loc_1800251DE
0x1800251d3  lea     rbp, [rdx+rcx]
0x1800251d7  cmp     rbp, rsi
0x1800251da  cmovb   rbp, rsi
0x1800251de  test    rbx, rbx
0x1800251e1  jz      short loc_180025226
0x1800251e3  cmp     rdx, 1000h
0x1800251ea  jb      short loc_180025204
0x1800251ec  mov     rax, [rbx-8]
0x1800251f0  add     rdx, 27h ; '''
0x1800251f4  sub     rbx, rax
0x1800251f7  sub     rbx, 8
0x1800251fb  cmp     rbx, 1Fh
0x1800251ff  ja      short loc_180025257
0x180025201  mov     rbx, rax
0x180025204  lfence
0x180025207  mov     rcx, rbx; Block
0x18002520a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002520f  mov     qword ptr [rdi], 0
0x180025216  mov     qword ptr [rdi+8], 0
0x18002521e  mov     qword ptr [rdi+10h], 0
0x180025226  lfence
0x180025229  mov     rcx, rbp
0x18002522c  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180025231  mov     [rdi], rax
0x180025234  mov     rbx, rax
0x180025237  mov     [rdi+8], rax
0x18002523b  mov     r8, rsi; Size
0x18002523e  add     rax, rbp
0x180025241  mov     rdx, r14; Src
0x180025244  mov     rcx, rbx; void *
0x180025247  mov     [rdi+10h], rax
0x18002524b  call    cs:__imp_memmove
0x180025251  lea     rax, [rbx+rsi]
0x180025255  jmp     short loc_1800252AA
0x180025257  xor     r9d, r9d; LineNo
0x18002525a  mov     [rsp+48h+Reserved], 0; Reserved
0x180025263  xor     r8d, r8d; FileName
0x180025266  xor     edx, edx; FunctionName
0x180025268  xor     ecx, ecx; Expression
0x18002526a  call    cs:__imp__invoke_watson
0x180025271  mov     rbp, [rcx+8]
0x180025275  sub     rbp, rbx
0x180025278  lfence
0x18002527b  mov     rdx, r14; Src
0x18002527e  mov     rcx, rbx; void *
0x180025281  cmp     rsi, rbp
0x180025284  jbe     short loc_1800252B0
0x180025286  mov     r8, rbp; Size
0x180025289  call    cs:__imp_memmove
0x18002528f  mov     rbx, [rdi+8]
0x180025293  lea     rdx, [r14+rbp]; Src
0x180025297  sub     rsi, rbp
0x18002529a  mov     rcx, rbx; void *
0x18002529d  mov     r8, rsi; Size
0x1800252a0  call    cs:__imp_memmove
0x1800252a6  lea     rax, [rsi+rbx]
0x1800252aa  mov     [rdi+8], rax
0x1800252ae  jmp     short loc_1800252C1
0x1800252b0  mov     r8, rsi; Size
0x1800252b3  call    cs:__imp_memmove
0x1800252b9  lea     rcx, [rbx+rsi]
0x1800252bd  mov     [rdi+8], rcx
0x1800252c1  mov     rbx, [rsp+48h+arg_10]
0x1800252c6  mov     rax, rdi
0x1800252c9  mov     rbp, [rsp+48h+arg_18]
0x1800252ce  add     rsp, 30h
0x1800252d2  pop     r14
0x1800252d4  pop     rdi
0x1800252d5  pop     rsi
0x1800252d6  retn
0x1800252d7  call    ?_Xlength@?$vector@UModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@UModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@CAXXZ; std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>::_Xlength(void)
```
