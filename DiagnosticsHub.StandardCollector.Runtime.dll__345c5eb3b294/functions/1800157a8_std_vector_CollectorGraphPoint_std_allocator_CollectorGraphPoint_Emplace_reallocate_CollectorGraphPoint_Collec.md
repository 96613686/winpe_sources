# std::vector<CollectorGraphPoint,std::allocator<CollectorGraphPoint>>::_Emplace_reallocate<CollectorGraphPoint>(CollectorGraphPoint * const,CollectorGraphPoint &&)

- ea: `0x1800157a8`
- end: `0x18001591e`
- name: `??$_Emplace_reallocate@UCollectorGraphPoint@@@?$vector@UCollectorGraphPoint@@V?$allocator@UCollectorGraphPoint@@@std@@@std@@AEAAPEAUCollectorGraphPoint@@QEAU2@$$QEAU2@@Z`
- size: `374`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013160`
- `0x1800143c4`

## callees

- `0x180009570`
- `0x180009e14`
- `0x180009f84`
- `0x1800157a8`
- `0x18004a078`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x18001586f`
- `VCRUNTIME140!memmove` at `0x180015883`
- `VCRUNTIME140!memmove` at `0x18001586f`
- `VCRUNTIME140!memmove` at `0x180015883`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001590b`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001590b`

## pseudocode

```c
char *__fastcall std::vector<CollectorGraphPoint>::_Emplace_reallocate<CollectorGraphPoint>(
        _QWORD *a1,
        _BYTE *a2,
        _OWORD *a3)
{
  unsigned __int64 v4; // rbp
  __int64 v5; // rdi
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // r14
  __int64 v12; // r14
  char *v13; // rax
  char *v14; // rsi
  char *v15; // rbp
  _BYTE *v16; // r8
  _QWORD *v17; // rdx
  void *v18; // rcx
  size_t v19; // r8
  _QWORD *v20; // rcx

  v4 = (unsigned __int64)&a2[-*a1];
  v5 = (__int64)(a1[1] - *a1) >> 5;
  if ( v5 == 0x7FFFFFFFFFFFFFFLL )
    std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>::_Xlength(a1, a2);
  v8 = v5 + 1;
  v9 = (__int64)(a1[2] - *a1) >> 5;
  v10 = v9 >> 1;
  if ( v9 <= 0x7FFFFFFFFFFFFFFLL - (v9 >> 1) )
  {
    v11 = v8;
    if ( v10 + v9 >= v8 )
      v11 = v10 + v9;
    if ( v11 > 0x7FFFFFFFFFFFFFFLL )
      __scrt_throw_std_bad_array_new_length();
  }
  else
  {
    v11 = 0x7FFFFFFFFFFFFFFLL;
  }
  _mm_lfence();
  v12 = 32 * v11;
  v13 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(v12);
  v14 = v13;
  v15 = &v13[v4 & 0xFFFFFFFFFFFFFFE0uLL];
  *(_OWORD *)v15 = *a3;
  *((_OWORD *)v15 + 1) = a3[1];
  v16 = (_BYTE *)a1[1];
  v17 = (_QWORD *)*a1;
  _mm_lfence();
  v18 = v13;
  if ( a2 == v16 )
  {
    v19 = v16 - (_BYTE *)v17;
  }
  else
  {
    memmove(v13, v17, a2 - (_BYTE *)v17);
    v18 = v15 + 32;
    v19 = a1[1] - (_QWORD)a2;
    v17 = a2;
  }
  memmove(v18, v17, v19);
  v20 = (_QWORD *)*a1;
  if ( *a1 )
  {
    if ( ((a1[2] - (_QWORD)v20) & 0xFFFFFFFFFFFFFFE0uLL) >= 0x1000 )
    {
      _mm_lfence();
      if ( (unsigned __int64)v20 - *(v20 - 1) - 8 > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v20 = (_QWORD *)*(v20 - 1);
    }
    operator delete(v20);
  }
  *a1 = v14;
  a1[1] = &v14[32 * v8];
  a1[2] = &v14[v12];
  _mm_lfence();
  return v15;
}

```

## disassembly

```asm
0x1800157a8  mov     [rsp+arg_10], rbx
0x1800157ad  mov     [rsp+arg_18], rbp
0x1800157b2  push    rsi
0x1800157b3  push    rdi
0x1800157b4  push    r12
0x1800157b6  push    r14
0x1800157b8  push    r15
0x1800157ba  sub     rsp, 30h
0x1800157be  mov     rdi, [rcx+8]
0x1800157c2  mov     rbp, rdx
0x1800157c5  sub     rdi, [rcx]
0x1800157c8  mov     r12, r8
0x1800157cb  sub     rbp, [rcx]
0x1800157ce  mov     r8, 7FFFFFFFFFFFFFFh
0x1800157d8  sar     rdi, 5
0x1800157dc  mov     r15, rdx
0x1800157df  mov     rbx, rcx
0x1800157e2  cmp     rdi, r8
0x1800157e5  jz      loc_180015912
0x1800157eb  mov     rcx, [rcx+10h]
0x1800157ef  mov     rax, r8
0x1800157f2  sub     rcx, [rbx]
0x1800157f5  inc     rdi
0x1800157f8  sar     rcx, 5
0x1800157fc  mov     rdx, rcx
0x1800157ff  shr     rdx, 1
0x180015802  sub     rax, rdx
0x180015805  cmp     rcx, rax
0x180015808  jbe     short loc_180015850
0x18001580a  mov     r14, r8
0x18001580d  lfence
0x180015810  shl     r14, 5
0x180015814  mov     rcx, r14
0x180015817  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001581c  movups  xmm0, xmmword ptr [r12]
0x180015821  and     rbp, 0FFFFFFFFFFFFFFE0h
0x180015825  mov     rsi, rax
0x180015828  add     rbp, rax
0x18001582b  movups  xmmword ptr [rbp+0], xmm0
0x18001582f  movups  xmm1, xmmword ptr [r12+10h]
0x180015835  movups  xmmword ptr [rbp+10h], xmm1
0x180015839  mov     r8, [rbx+8]
0x18001583d  mov     rdx, [rbx]; Src
0x180015840  lfence
0x180015843  mov     rcx, rax; void *
0x180015846  cmp     r15, r8
0x180015849  jnz     short loc_180015869
0x18001584b  sub     r8, rdx
0x18001584e  jmp     short loc_180015883
0x180015850  lea     rax, [rdx+rcx]
0x180015854  mov     r14, rdi
0x180015857  cmp     rax, rdi
0x18001585a  cmovnb  r14, rax
0x18001585e  cmp     r14, r8
0x180015861  ja      loc_180015918
0x180015867  jmp     short loc_18001580D
0x180015869  mov     r8, r15
0x18001586c  sub     r8, rdx; Size
0x18001586f  call    cs:__imp_memmove
0x180015875  mov     r8, [rbx+8]
0x180015879  lea     rcx, [rbp+20h]; void *
0x18001587d  sub     r8, r15; Size
0x180015880  mov     rdx, r15; Src
0x180015883  call    cs:__imp_memmove
0x180015889  mov     rcx, [rbx]
0x18001588c  test    rcx, rcx
0x18001588f  jz      short loc_1800158C5
0x180015891  mov     rdx, [rbx+10h]
0x180015895  sub     rdx, rcx
0x180015898  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18001589c  cmp     rdx, 1000h
0x1800158a3  jb      short loc_1800158C0
0x1800158a5  lfence
0x1800158a8  mov     rax, [rcx-8]
0x1800158ac  add     rdx, 27h ; '''
0x1800158b0  sub     rcx, rax
0x1800158b3  sub     rcx, 8
0x1800158b7  cmp     rcx, 1Fh
0x1800158bb  ja      short loc_1800158F8
0x1800158bd  mov     rcx, rax; Block
0x1800158c0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800158c5  mov     [rbx], rsi
0x1800158c8  lea     rcx, [r14+rsi]
0x1800158cc  shl     rdi, 5
0x1800158d0  add     rdi, rsi
0x1800158d3  mov     [rbx+8], rdi
0x1800158d7  mov     [rbx+10h], rcx
0x1800158db  lfence
0x1800158de  mov     rbx, [rsp+58h+arg_10]
0x1800158e3  mov     rax, rbp
0x1800158e6  mov     rbp, [rsp+58h+arg_18]
0x1800158eb  add     rsp, 30h
0x1800158ef  pop     r15
0x1800158f1  pop     r14
0x1800158f3  pop     r12
0x1800158f5  pop     rdi
0x1800158f6  pop     rsi
0x1800158f7  retn
0x1800158f8  xor     r9d, r9d; LineNo
0x1800158fb  mov     [rsp+58h+Reserved], 0; Reserved
0x180015904  xor     r8d, r8d; FileName
0x180015907  xor     edx, edx; FunctionName
0x180015909  xor     ecx, ecx; Expression
0x18001590b  call    cs:__imp__invoke_watson
0x180015912  call    ?_Xlength@?$vector@UModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@UModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@CAXXZ; std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>::_Xlength(void)
0x180015918  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
