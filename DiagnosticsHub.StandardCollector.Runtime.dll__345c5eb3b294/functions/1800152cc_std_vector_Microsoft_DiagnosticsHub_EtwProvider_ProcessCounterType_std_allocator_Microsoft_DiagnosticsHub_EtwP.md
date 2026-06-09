# std::vector<Microsoft::DiagnosticsHub::EtwProvider::ProcessCounterType,std::allocator<Microsoft::DiagnosticsHub::EtwProvider::ProcessCounterType>>::push_back(Microsoft::DiagnosticsHub::EtwProvider::ProcessCounterType &&)

- ea: `0x1800152cc`
- end: `0x18001543b`
- name: `?push_back@?$vector@W4ProcessCounterType@EtwProvider@DiagnosticsHub@Microsoft@@V?$allocator@W4ProcessCounterType@EtwProvider@DiagnosticsHub@Microsoft@@@std@@@std@@QEAAX$$QEAW4ProcessCounterType@EtwProvider@DiagnosticsHub@Microsoft@@@Z`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180014084`

## callees

- `0x180009570`
- `0x180009e14`
- `0x180009f84`
- `0x1800152cc`
- `0x18004a078`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x180015391`
- `VCRUNTIME140!memmove` at `0x1800153a9`
- `VCRUNTIME140!memmove` at `0x180015391`
- `VCRUNTIME140!memmove` at `0x1800153a9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180015428`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180015428`

## pseudocode

```c
unsigned __int64 __fastcall std::vector<enum Microsoft::DiagnosticsHub::EtwProvider::ProcessCounterType>::push_back(
        _QWORD *a1,
        _DWORD *a2)
{
  char *v4; // rcx
  char *v5; // rsi
  unsigned __int64 result; // rax
  __int64 v7; // rbp
  unsigned __int64 v8; // r15
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  __int64 v11; // r12
  char *v12; // rdi
  char *v13; // r8
  char *v14; // rdx
  char *v15; // rcx
  size_t v16; // r8
  unsigned __int64 v17; // rax
  char *v18; // rcx

  v4 = (char *)a1[2];
  v5 = (char *)a1[1];
  if ( v5 == v4 )
  {
    v7 = (__int64)&v5[-*a1] >> 2;
    if ( v7 == 0x3FFFFFFFFFFFFFFFLL )
      std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>::_Xlength(v4, a2);
    v8 = v7 + 1;
    v9 = (__int64)&v4[-*a1] >> 2;
    if ( v9 <= 0x3FFFFFFFFFFFFFFFLL - (v9 >> 1) )
    {
      v17 = (v9 >> 1) + v9;
      v10 = v7 + 1;
      if ( v17 >= v8 )
        v10 = v17;
      if ( v10 > 0x3FFFFFFFFFFFFFFFLL )
        __scrt_throw_std_bad_array_new_length();
    }
    else
    {
      v10 = 0x3FFFFFFFFFFFFFFFLL;
    }
    _mm_lfence();
    v11 = 4 * v10;
    v12 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(4 * v10);
    *(_DWORD *)&v12[4 * v7] = *a2;
    v13 = (char *)a1[1];
    v14 = (char *)*a1;
    _mm_lfence();
    v15 = v12;
    if ( v5 == v13 )
    {
      v16 = v13 - v14;
    }
    else
    {
      memmove(v12, v14, v5 - v14);
      v16 = a1[1] - (_QWORD)v5;
      v15 = &v12[4 * v7 + 4];
      v14 = v5;
    }
    memmove(v15, v14, v16);
    v18 = (char *)*a1;
    if ( *a1 )
    {
      if ( ((a1[2] - (_QWORD)v18) & 0xFFFFFFFFFFFFFFFCuLL) >= 0x1000 )
      {
        _mm_lfence();
        if ( (unsigned __int64)&v18[-*((_QWORD *)v18 - 1) - 8] > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
        v18 = (char *)*((_QWORD *)v18 - 1);
      }
      operator delete(v18);
    }
    *a1 = v12;
    a1[1] = &v12[4 * v8];
    result = (unsigned __int64)&v12[v11];
    a1[2] = &v12[v11];
  }
  else
  {
    result = (unsigned int)*a2;
    *(_DWORD *)v5 = result;
    a1[1] += 4LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800152cc  mov     [rsp+arg_8], rbx
0x1800152d1  mov     [rsp+arg_10], rbp
0x1800152d6  push    rsi
0x1800152d7  push    rdi
0x1800152d8  push    r12
0x1800152da  push    r14
0x1800152dc  push    r15
0x1800152de  sub     rsp, 30h
0x1800152e2  mov     rbx, rcx
0x1800152e5  mov     r14, rdx
0x1800152e8  mov     rcx, [rcx+10h]
0x1800152ec  mov     rsi, [rbx+8]
0x1800152f0  cmp     rsi, rcx
0x1800152f3  jz      short loc_180015303
0x1800152f5  mov     eax, [rdx]
0x1800152f7  mov     [rsi], eax
0x1800152f9  add     qword ptr [rbx+8], 4
0x1800152fe  jmp     loc_1800153FE
0x180015303  mov     rbp, rsi
0x180015306  mov     r8, 3FFFFFFFFFFFFFFFh
0x180015310  sub     rbp, [rbx]
0x180015313  sar     rbp, 2
0x180015317  cmp     rbp, r8
0x18001531a  jz      loc_18001542F
0x180015320  sub     rcx, [rbx]
0x180015323  lea     r15, [rbp+1]
0x180015327  sar     rcx, 2
0x18001532b  mov     rax, r8
0x18001532e  mov     rdx, rcx
0x180015331  shr     rdx, 1
0x180015334  sub     rax, rdx
0x180015337  cmp     rcx, rax
0x18001533a  jbe     short loc_180015372
0x18001533c  mov     rcx, r8
0x18001533f  lfence
0x180015342  lea     r12, ds:0[rcx*4]
0x18001534a  mov     rcx, r12
0x18001534d  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180015352  mov     ecx, [r14]
0x180015355  mov     rdi, rax
0x180015358  mov     [rax+rbp*4], ecx
0x18001535b  mov     r8, [rbx+8]
0x18001535f  mov     rdx, [rbx]; Src
0x180015362  lfence
0x180015365  mov     rcx, rax; void *
0x180015368  cmp     rsi, r8
0x18001536b  jnz     short loc_18001538B
0x18001536d  sub     r8, rdx
0x180015370  jmp     short loc_1800153A9
0x180015372  lea     rax, [rdx+rcx]
0x180015376  mov     rcx, r15
0x180015379  cmp     rax, r15
0x18001537c  cmovnb  rcx, rax
0x180015380  cmp     rcx, r8
0x180015383  ja      loc_180015435
0x180015389  jmp     short loc_18001533F
0x18001538b  mov     r8, rsi
0x18001538e  sub     r8, rdx; Size
0x180015391  call    cs:__imp_memmove
0x180015397  mov     r8, [rbx+8]
0x18001539b  lea     rcx, [rbp+1]
0x18001539f  sub     r8, rsi; Size
0x1800153a2  lea     rcx, [rdi+rcx*4]; void *
0x1800153a6  mov     rdx, rsi; Src
0x1800153a9  call    cs:__imp_memmove
0x1800153af  mov     rcx, [rbx]
0x1800153b2  test    rcx, rcx
0x1800153b5  jz      short loc_1800153EB
0x1800153b7  mov     rdx, [rbx+10h]
0x1800153bb  sub     rdx, rcx
0x1800153be  and     rdx, 0FFFFFFFFFFFFFFFCh
0x1800153c2  cmp     rdx, 1000h
0x1800153c9  jb      short loc_1800153E6
0x1800153cb  lfence
0x1800153ce  mov     rax, [rcx-8]
0x1800153d2  add     rdx, 27h ; '''
0x1800153d6  sub     rcx, rax
0x1800153d9  sub     rcx, 8
0x1800153dd  cmp     rcx, 1Fh
0x1800153e1  ja      short loc_180015415
0x1800153e3  mov     rcx, rax; Block
0x1800153e6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800153eb  lea     rax, [rdi+r15*4]
0x1800153ef  mov     [rbx], rdi
0x1800153f2  mov     [rbx+8], rax
0x1800153f6  lea     rax, [r12+rdi]
0x1800153fa  mov     [rbx+10h], rax
0x1800153fe  mov     rbx, [rsp+58h+arg_8]
0x180015403  mov     rbp, [rsp+58h+arg_10]
0x180015408  add     rsp, 30h
0x18001540c  pop     r15
0x18001540e  pop     r14
0x180015410  pop     r12
0x180015412  pop     rdi
0x180015413  pop     rsi
0x180015414  retn
0x180015415  xor     r9d, r9d; LineNo
0x180015418  mov     [rsp+58h+Reserved], 0; Reserved
0x180015421  xor     r8d, r8d; FileName
0x180015424  xor     edx, edx; FunctionName
0x180015426  xor     ecx, ecx; Expression
0x180015428  call    cs:__imp__invoke_watson
0x18001542f  call    ?_Xlength@?$vector@UModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@UModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@CAXXZ; std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>::_Xlength(void)
0x180015435  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
