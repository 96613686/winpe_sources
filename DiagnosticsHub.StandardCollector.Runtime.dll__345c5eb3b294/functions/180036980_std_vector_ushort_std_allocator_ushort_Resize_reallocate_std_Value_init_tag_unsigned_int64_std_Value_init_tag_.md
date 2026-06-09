# std::vector<ushort,std::allocator<ushort>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)

- ea: `0x180036980`
- end: `0x180036ab6`
- name: `??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180035c60`

## callees

- `0x180009570`
- `0x180009e14`
- `0x180009f84`
- `0x180036980`
- `0x18004a078`

## import_xrefs

- `VCRUNTIME140!memset` at `0x1800369f8`
- `VCRUNTIME140!memset` at `0x1800369f8`
- `VCRUNTIME140!memmove` at `0x180036a0b`
- `VCRUNTIME140!memmove` at `0x180036a0b`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180036aa3`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180036aa3`

## pseudocode

```c
char *__fastcall std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(__int64 a1, unsigned __int64 a2)
{
  __int64 v4; // rbp
  unsigned __int64 v5; // rcx
  __int64 v6; // rbp
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rax
  __int64 v9; // r14
  char *v10; // rsi
  _QWORD *v11; // rcx
  char *result; // rax

  if ( a2 > 0x7FFFFFFFFFFFFFFFLL )
    std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>::_Xlength(a1, a2);
  v4 = *(_QWORD *)(a1 + 8) - *(_QWORD *)a1;
  v5 = (__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 1;
  v6 = v4 >> 1;
  v7 = v5 >> 1;
  if ( v5 <= 0x7FFFFFFFFFFFFFFFLL - (v5 >> 1) )
  {
    v8 = v7 + v5;
    if ( v7 + v5 >= a2 )
    {
      if ( v8 > 0x7FFFFFFFFFFFFFFFLL )
        __scrt_throw_std_bad_array_new_length();
    }
    else
    {
      v8 = a2;
    }
  }
  else
  {
    v8 = 0x7FFFFFFFFFFFFFFFLL;
  }
  _mm_lfence();
  v9 = 2 * v8;
  v10 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(2 * v8);
  memset(&v10[2 * v6], 0, 2 * (a2 - v6));
  memmove(v10, *(const void **)a1, *(_QWORD *)(a1 + 8) - *(_QWORD *)a1);
  v11 = *(_QWORD **)a1;
  if ( *(_QWORD *)a1 )
  {
    if ( (unsigned __int64)(2 * ((__int64)(*(_QWORD *)(a1 + 16) - (_QWORD)v11) >> 1)) >= 0x1000 )
    {
      _mm_lfence();
      if ( (unsigned __int64)v11 - *(v11 - 1) - 8 > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v11 = (_QWORD *)*(v11 - 1);
    }
    operator delete(v11);
  }
  *(_QWORD *)a1 = v10;
  *(_QWORD *)(a1 + 8) = &v10[2 * a2];
  result = &v10[v9];
  *(_QWORD *)(a1 + 16) = &v10[v9];
  return result;
}

```

## disassembly

```asm
0x180036980  mov     [rsp+arg_10], rbx
0x180036985  mov     [rsp+arg_18], rbp
0x18003698a  push    rsi
0x18003698b  push    rdi
0x18003698c  push    r14
0x18003698e  sub     rsp, 30h
0x180036992  mov     r8, 7FFFFFFFFFFFFFFFh
0x18003699c  mov     rdi, rdx
0x18003699f  mov     rbx, rcx
0x1800369a2  cmp     rdx, r8
0x1800369a5  ja      loc_180036AAA
0x1800369ab  mov     rbp, [rcx+8]
0x1800369af  mov     rax, r8
0x1800369b2  sub     rbp, [rcx]
0x1800369b5  mov     rcx, [rcx+10h]
0x1800369b9  sub     rcx, [rbx]
0x1800369bc  sar     rcx, 1
0x1800369bf  mov     rdx, rcx
0x1800369c2  sar     rbp, 1
0x1800369c5  shr     rdx, 1
0x1800369c8  sub     rax, rdx
0x1800369cb  cmp     rcx, rax
0x1800369ce  jbe     loc_180036A75
0x1800369d4  mov     rax, r8
0x1800369d7  lfence
0x1800369da  lea     r14, [rax+rax]
0x1800369de  mov     rcx, r14
0x1800369e1  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800369e6  mov     r8, rdi
0x1800369e9  xor     edx, edx; Val
0x1800369eb  sub     r8, rbp
0x1800369ee  mov     rsi, rax
0x1800369f1  add     r8, r8; Size
0x1800369f4  lea     rcx, [rax+rbp*2]; void *
0x1800369f8  call    cs:__imp_memset
0x1800369fe  mov     r8, [rbx+8]
0x180036a02  mov     rcx, rsi; void *
0x180036a05  sub     r8, [rbx]; Size
0x180036a08  mov     rdx, [rbx]; Src
0x180036a0b  call    cs:__imp_memmove
0x180036a11  mov     rcx, [rbx]
0x180036a14  test    rcx, rcx
0x180036a17  jz      short loc_180036A4F
0x180036a19  mov     rdx, [rbx+10h]
0x180036a1d  sub     rdx, rcx
0x180036a20  sar     rdx, 1
0x180036a23  add     rdx, rdx
0x180036a26  cmp     rdx, 1000h
0x180036a2d  jb      short loc_180036A4A
0x180036a2f  lfence
0x180036a32  mov     rax, [rcx-8]
0x180036a36  add     rdx, 27h ; '''
0x180036a3a  sub     rcx, rax
0x180036a3d  sub     rcx, 8
0x180036a41  cmp     rcx, 1Fh
0x180036a45  ja      short loc_180036A90
0x180036a47  mov     rcx, rax; Block
0x180036a4a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180036a4f  mov     rbp, [rsp+48h+arg_18]
0x180036a54  lea     rax, [rsi+rdi*2]
0x180036a58  mov     [rbx], rsi
0x180036a5b  mov     [rbx+8], rax
0x180036a5f  lea     rax, [r14+rsi]
0x180036a63  mov     [rbx+10h], rax
0x180036a67  mov     rbx, [rsp+48h+arg_10]
0x180036a6c  add     rsp, 30h
0x180036a70  pop     r14
0x180036a72  pop     rdi
0x180036a73  pop     rsi
0x180036a74  retn
0x180036a75  lea     rax, [rdx+rcx]
0x180036a79  cmp     rax, rdi
0x180036a7c  jnb     short loc_180036A86
0x180036a7e  mov     rax, rdi
0x180036a81  jmp     loc_1800369D7
0x180036a86  cmp     rax, r8
0x180036a89  ja      short loc_180036AB0
0x180036a8b  jmp     loc_1800369D7
0x180036a90  xor     r9d, r9d; LineNo
0x180036a93  mov     [rsp+48h+Reserved], 0; Reserved
0x180036a9c  xor     r8d, r8d; FileName
0x180036a9f  xor     edx, edx; FunctionName
0x180036aa1  xor     ecx, ecx; Expression
0x180036aa3  call    cs:__imp__invoke_watson
0x180036aaa  call    ?_Xlength@?$vector@UModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@UModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@CAXXZ; std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>::_Xlength(void)
0x180036ab0  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
