# std::vector<EtwProviderConfigWithFilter,std::allocator<EtwProviderConfigWithFilter>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)

- ea: `0x180026c04`
- end: `0x180026d82`
- name: `??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UEtwProviderConfigWithFilter@@V?$allocator@UEtwProviderConfigWithFilter@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001d790`

## callees

- `0x180009570`
- `0x180009e14`
- `0x180009f84`
- `0x180026c04`
- `0x18004a078`
- `0x18004ad26`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x180026cc1`
- `VCRUNTIME140!memmove` at `0x180026cc1`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180026d6f`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180026d6f`

## pseudocode

```c
char *__fastcall std::vector<EtwProviderConfigWithFilter>::_Resize_reallocate<std::_Value_init_tag>(
        __int64 a1,
        unsigned __int64 a2)
{
  __int64 v4; // rbp
  unsigned __int64 v5; // rdx
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // rax
  __int64 v8; // r14
  char *v9; // rsi
  _QWORD *v10; // r8
  char *result; // rax

  if ( a2 > 0x492492492492492LL )
    std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>::_Xlength(a1, a2);
  v4 = (*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) / 56LL;
  v5 = (*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) / 56LL;
  v6 = v5 >> 1;
  if ( v5 <= 0x492492492492492LL - (v5 >> 1) )
  {
    v7 = v6 + v5;
    if ( v6 + v5 >= a2 )
    {
      if ( v7 > 0x492492492492492LL )
        __scrt_throw_std_bad_array_new_length();
    }
    else
    {
      v7 = a2;
    }
  }
  else
  {
    v7 = 0x492492492492492LL;
  }
  _mm_lfence();
  v8 = 56 * v7;
  v9 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(56 * v7);
  if ( a2 != v4 )
    memset_0(&v9[56 * v4], 0, 56 * (a2 - v4));
  memmove(v9, *(const void **)a1, *(_QWORD *)(a1 + 8) - *(_QWORD *)a1);
  v10 = *(_QWORD **)a1;
  if ( *(_QWORD *)a1 )
  {
    if ( (unsigned __int64)(56 * ((*(_QWORD *)(a1 + 16) - (_QWORD)v10) / 56LL)) >= 0x1000 )
    {
      _mm_lfence();
      if ( (unsigned __int64)v10 - *(v10 - 1) - 8 > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v10 = (_QWORD *)*(v10 - 1);
    }
    operator delete(v10);
  }
  *(_QWORD *)a1 = v9;
  *(_QWORD *)(a1 + 8) = &v9[56 * a2];
  result = &v9[v8];
  *(_QWORD *)(a1 + 16) = &v9[v8];
  return result;
}

```

## disassembly

```asm
0x180026c04  mov     [rsp+arg_10], rbx
0x180026c09  push    rbp
0x180026c0a  push    rsi
0x180026c0b  push    rdi
0x180026c0c  push    r14
0x180026c0e  push    r15
0x180026c10  sub     rsp, 30h
0x180026c14  mov     r8, 492492492492492h
0x180026c1e  mov     rdi, rdx
0x180026c21  mov     rbx, rcx
0x180026c24  cmp     rdx, r8
0x180026c27  ja      loc_180026D76
0x180026c2d  mov     rcx, [rcx+8]
0x180026c31  mov     r15, 4924924924924925h
0x180026c3b  sub     rcx, [rbx]
0x180026c3e  mov     rax, r15
0x180026c41  imul    rcx
0x180026c44  mov     rcx, [rbx+10h]
0x180026c48  sub     rcx, [rbx]
0x180026c4b  mov     rbp, rdx
0x180026c4e  sar     rbp, 4
0x180026c52  mov     rax, rbp
0x180026c55  shr     rax, 3Fh
0x180026c59  add     rbp, rax
0x180026c5c  mov     rax, r15
0x180026c5f  imul    rcx
0x180026c62  sar     rdx, 4
0x180026c66  mov     rax, rdx
0x180026c69  shr     rax, 3Fh
0x180026c6d  add     rdx, rax
0x180026c70  mov     rax, r8
0x180026c73  mov     rcx, rdx
0x180026c76  shr     rcx, 1
0x180026c79  sub     rax, rcx
0x180026c7c  cmp     rdx, rax
0x180026c7f  jbe     loc_180026D41
0x180026c85  mov     rax, r8
0x180026c88  lfence
0x180026c8b  imul    r14, rax, 38h ; '8'
0x180026c8f  mov     rcx, r14
0x180026c92  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180026c97  mov     rsi, rax
0x180026c9a  mov     rax, rdi
0x180026c9d  imul    rcx, rbp, 38h ; '8'
0x180026ca1  add     rcx, rsi; void *
0x180026ca4  sub     rax, rbp
0x180026ca7  jz      short loc_180026CB4
0x180026ca9  imul    r8, rax, 38h ; '8'; Size
0x180026cad  xor     edx, edx; Val
0x180026caf  call    memset_0
0x180026cb4  mov     r8, [rbx+8]
0x180026cb8  mov     rcx, rsi; void *
0x180026cbb  sub     r8, [rbx]; Size
0x180026cbe  mov     rdx, [rbx]; Src
0x180026cc1  call    cs:__imp_memmove
0x180026cc7  mov     r8, [rbx]
0x180026cca  test    r8, r8
0x180026ccd  jz      short loc_180026D1A
0x180026ccf  mov     rcx, [rbx+10h]
0x180026cd3  mov     rax, r15
0x180026cd6  sub     rcx, r8
0x180026cd9  imul    rcx
0x180026cdc  sar     rdx, 4
0x180026ce0  mov     rax, rdx
0x180026ce3  shr     rax, 3Fh
0x180026ce7  add     rdx, rax
0x180026cea  imul    rdx, 38h ; '8'
0x180026cee  cmp     rdx, 1000h
0x180026cf5  jb      short loc_180026D12
0x180026cf7  lfence
0x180026cfa  mov     rax, [r8-8]
0x180026cfe  add     rdx, 27h ; '''
0x180026d02  sub     r8, rax
0x180026d05  sub     r8, 8
0x180026d09  cmp     r8, 1Fh
0x180026d0d  ja      short loc_180026D5C
0x180026d0f  mov     r8, rax
0x180026d12  mov     rcx, r8; Block
0x180026d15  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180026d1a  mov     [rbx], rsi
0x180026d1d  imul    rax, rdi, 38h ; '8'
0x180026d21  add     rax, rsi
0x180026d24  mov     [rbx+8], rax
0x180026d28  lea     rax, [r14+rsi]
0x180026d2c  mov     [rbx+10h], rax
0x180026d30  mov     rbx, [rsp+58h+arg_10]
0x180026d35  add     rsp, 30h
0x180026d39  pop     r15
0x180026d3b  pop     r14
0x180026d3d  pop     rdi
0x180026d3e  pop     rsi
0x180026d3f  pop     rbp
0x180026d40  retn
0x180026d41  lea     rax, [rcx+rdx]
0x180026d45  cmp     rax, rdi
0x180026d48  jnb     short loc_180026D52
0x180026d4a  mov     rax, rdi
0x180026d4d  jmp     loc_180026C88
0x180026d52  cmp     rax, r8
0x180026d55  ja      short loc_180026D7C
0x180026d57  jmp     loc_180026C88
0x180026d5c  xor     r9d, r9d; LineNo
0x180026d5f  mov     [rsp+58h+Reserved], 0; Reserved
0x180026d68  xor     r8d, r8d; FileName
0x180026d6b  xor     edx, edx; FunctionName
0x180026d6d  xor     ecx, ecx; Expression
0x180026d6f  call    cs:__imp__invoke_watson
0x180026d76  call    ?_Xlength@?$vector@UModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@UModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@CAXXZ; std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>::_Xlength(void)
0x180026d7c  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
