# LocalFileLoader::SerializeReferenceKeyTo(wchar_t const *,DateTime const *,wchar_t const *,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x18000e9d8`
- end: `0x18000eb9d`
- name: `?SerializeReferenceKeyTo@LocalFileLoader@@SAXPEB_WPEBVDateTime@@0AEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `453`
- prototype: `__int64 __fastcall(LPCWCH lpString2)`
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000df40`
- `0x18000f8a4`
- `0x1800a596c`

## callees

- `0x18000e9d8`
- `0x18000eba4`
- `0x18000ed8c`
- `0x18000ee1c`
- `0x18000ee4c`
- `0x18000ee88`
- `0x18000ef34`
- `0x180028c50`
- `0x18009e420`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000ea9d`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000ea9d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000ead8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000ead8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LocalFileLoader::SerializeReferenceKeyTo(
        LPCWCH lpString2,
        const struct DateTime *a2,
        unsigned __int64 a3,
        _QWORD *a4)
{
  const WCHAR *v5; // r15
  unsigned __int64 v6; // rsi
  unsigned __int8 v7; // r12
  unsigned __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  struct DWrite::RefString::Data *v11; // rbx
  unsigned __int64 v12; // r14
  const WCHAR *v13; // rcx
  bool v14; // zf
  WCHAR *v15; // r14
  WCHAR *v16; // rax
  struct DWrite::RefString::Data *v17; // [rsp+30h] [rbp-28h] BYREF
  unsigned __int64 v18; // [rsp+38h] [rbp-20h] BYREF
  __int64 v19; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int64 v20; // [rsp+48h] [rbp-10h] BYREF
  unsigned __int64 v21; // [rsp+B0h] [rbp+58h] BYREF

  v21 = a3;
  v5 = lpString2;
  v20 = GetFileLastWriteTimeTicks(lpString2, a2);
  v6 = -1;
  do
    ++v6;
  while ( v5[v6] );
  v7 = 0;
  GetFontsDirectory(&v17);
  v11 = v17;
  v12 = *((unsigned int *)v17 + 1);
  if ( v6 >= v12 )
  {
    v13 = (const WCHAR *)((char *)v17 + 8);
    if ( v17 == (struct DWrite::RefString::Data *)-8LL )
    {
      v14 = v5 == 0;
    }
    else
    {
      if ( !v5 )
        goto LABEL_4;
      if ( (unsigned int)v12 > 0x7FFFFFFF )
        goto LABEL_26;
      v14 = CompareStringOrdinal(v13, v12, v5, v12, 1) == 2;
    }
    if ( v14 )
    {
      v5 += v12;
      v6 -= v12;
      v7 = 1;
    }
  }
LABEL_4:
  if ( *a4 != a4[1] )
    a4[1] = *a4;
  v19 = 2;
  v18 = v6 + 1;
  v21 = 0;
  LargeIntRegMultiply<unsigned __int64,unsigned __int64>::RegMultiplyThrow<SafeIntExceptionHandler<Exception>>(
    &v19,
    &v18,
    &v21);
  v8 = v21 + 2 * (v7 + 4LL);
  if ( v8 < v21 )
LABEL_26:
    SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v13, v8, v9, v10);
  v21 += 2 * (v7 + 4LL);
  if ( v8 > a4[2] - *a4 )
  {
    if ( v8 > 0x7FFFFFFFFFFFFFFFLL )
      std::_Xlength_error("vector too long");
    std::vector<unsigned char>::_Reallocate<0>(a4, &v21);
  }
  std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(a4, a4[1], &v20, 8);
  if ( v7 )
    std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(a4, a4[1], L"*", 2);
  v15 = (WCHAR *)a4[1];
  std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(a4, v15, v5, 2 * v6 + 2);
  ToUpperInvariant(v15, v6);
  v16 = &v15[v6];
  while ( v15 != v16 )
  {
    if ( *v15 == 47 )
      *v15 = 92;
    ++v15;
  }
  DWrite::RefString::DecrementRef(v11);
}

```

## disassembly

```asm
0x18000e9d8  mov     [rsp-40h+arg_10], r8
0x18000e9dd  push    rbp
0x18000e9de  push    rbx
0x18000e9df  push    rsi
0x18000e9e0  push    rdi
0x18000e9e1  push    r12
0x18000e9e3  push    r13
0x18000e9e5  push    r14
0x18000e9e7  push    r15
0x18000e9e9  mov     rbp, rsp
0x18000e9ec  sub     rsp, 58h
0x18000e9f0  mov     rdi, r9
0x18000e9f3  mov     r15, rcx
0x18000e9f6  call    ?GetFileLastWriteTimeTicks@@YA_KPEB_WPEBVDateTime@@@Z; GetFileLastWriteTimeTicks(wchar_t const *,DateTime const *)
0x18000e9fb  mov     [rbp+var_10], rax
0x18000e9ff  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000ea03  xor     r13d, r13d
0x18000ea06  inc     rsi
0x18000ea09  cmp     [r15+rsi*2], r13w
0x18000ea0e  jnz     short loc_18000EA06
0x18000ea10  mov     r12b, r13b
0x18000ea13  lea     rcx, [rbp+var_28]
0x18000ea17  call    ?GetFontsDirectory@@YA?AVRefString@DWrite@@XZ; GetFontsDirectory(void)
0x18000ea1c  nop
0x18000ea1d  mov     rbx, [rbp+var_28]
0x18000ea21  mov     r14d, [rbx+4]
0x18000ea25  cmp     rsi, r14
0x18000ea28  jnb     short loc_18000EAA4
0x18000ea2a  mov     rax, [rdi]
0x18000ea2d  cmp     rax, [rdi+8]
0x18000ea31  jz      short loc_18000EA37
0x18000ea33  mov     [rdi+8], rax
0x18000ea37  mov     r14d, 2
0x18000ea3d  mov     [rbp+var_18], r14
0x18000ea41  lea     rax, [rsi+1]
0x18000ea45  mov     [rbp+var_20], rax
0x18000ea49  mov     [rbp+arg_10], r13
0x18000ea4d  lea     r8, [rbp+arg_10]
0x18000ea51  lea     rdx, [rbp+var_20]
0x18000ea55  lea     rcx, [rbp+var_18]
0x18000ea59  call    ??$RegMultiplyThrow@V?$SafeIntExceptionHandler@VException@@@@@?$LargeIntRegMultiply@_K_K@@SAXAEB_K0AEA_K@Z; LargeIntRegMultiply<unsigned __int64,unsigned __int64>::RegMultiplyThrow<SafeIntExceptionHandler<Exception>>(unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 &)
0x18000ea5e  mov     rax, [rbp+arg_10]
0x18000ea62  movzx   edx, r12b
0x18000ea66  add     rdx, 4
0x18000ea6a  lea     rdx, [rax+rdx*2]
0x18000ea6e  cmp     rdx, rax
0x18000ea71  jb      loc_18000EB97
0x18000ea77  mov     [rbp+arg_10], rdx
0x18000ea7b  mov     rax, [rdi+10h]
0x18000ea7f  sub     rax, [rdi]
0x18000ea82  cmp     rdx, rax
0x18000ea85  jbe     short loc_18000EB02
0x18000ea87  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000ea91  cmp     rdx, rax
0x18000ea94  jbe     short loc_18000EAF6
0x18000ea96  lea     rcx, aVectorTooLong; "vector too long"
0x18000ea9d  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000eaa4  lea     rcx, [rbx+8]; lpString1
0x18000eaa8  test    rcx, rcx
0x18000eaab  jz      loc_18000EB8F
0x18000eab1  test    r15, r15
0x18000eab4  jz      loc_18000EA2A
0x18000eaba  cmp     r14d, 7FFFFFFFh
0x18000eac1  ja      loc_18000EB97
0x18000eac7  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x18000eacf  mov     r9d, r14d; cchCount2
0x18000ead2  mov     r8, r15; lpString2
0x18000ead5  mov     edx, r14d; cchCount1
0x18000ead8  call    cs:__imp_CompareStringOrdinal
0x18000eade  add     eax, 0FFFFFFFEh
0x18000eae1  jnz     loc_18000EA2A
0x18000eae7  lea     r15, [r15+r14*2]
0x18000eaeb  sub     rsi, r14
0x18000eaee  mov     r12b, 1
0x18000eaf1  jmp     loc_18000EA2A
0x18000eaf6  lea     rdx, [rbp+arg_10]
0x18000eafa  mov     rcx, rdi
0x18000eafd  call    ??$_Reallocate@$0A@@?$vector@EV?$allocator@E@std@@@std@@AEAAXAEA_K@Z; std::vector<uchar>::_Reallocate<0>(unsigned __int64 &)
0x18000eb02  mov     r9d, 8
0x18000eb08  lea     r8, [rbp+var_10]
0x18000eb0c  mov     rdx, [rdi+8]
0x18000eb10  mov     rcx, rdi
0x18000eb13  call    ??$_Insert_counted_range@PEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEBE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar const *,unsigned __int64)
0x18000eb18  test    r12b, r12b
0x18000eb1b  jz      short loc_18000EB33
0x18000eb1d  mov     r9, r14
0x18000eb20  lea     r8, asc_1800EAEF0; "*"
0x18000eb27  mov     rdx, [rdi+8]
0x18000eb2b  mov     rcx, rdi
0x18000eb2e  call    ??$_Insert_counted_range@PEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEBE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar const *,unsigned __int64)
0x18000eb33  mov     r14, [rdi+8]
0x18000eb37  lea     r9, ds:2[rsi*2]
0x18000eb3f  mov     r8, r15
0x18000eb42  mov     rdx, r14
0x18000eb45  mov     rcx, rdi
0x18000eb48  call    ??$_Insert_counted_range@PEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEBE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar const *,unsigned __int64)
0x18000eb4d  mov     rdx, rsi; cchDest
0x18000eb50  mov     rcx, r14; lpDestStr
0x18000eb53  call    ?ToUpperInvariant@@YAXPEA_W_K@Z; ToUpperInvariant(wchar_t *,unsigned __int64)
0x18000eb58  lea     rax, [r14+rsi*2]
0x18000eb5c  cmp     r14, rax
0x18000eb5f  jz      short loc_18000EB76
0x18000eb61  cmp     word ptr [r14], 2Fh ; '/'
0x18000eb66  jz      short loc_18000EB6E
0x18000eb68  add     r14, 2
0x18000eb6c  jmp     short loc_18000EB5C
0x18000eb6e  mov     word ptr [r14], 5Ch ; '\'
0x18000eb74  jmp     short loc_18000EB68
0x18000eb76  mov     rcx, rbx; struct DWrite::RefString::Data *
0x18000eb79  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18000eb7e  add     rsp, 58h
0x18000eb82  pop     r15
0x18000eb84  pop     r14
0x18000eb86  pop     r13
0x18000eb88  pop     r12
0x18000eb8a  pop     rdi
0x18000eb8b  pop     rsi
0x18000eb8c  pop     rbx
0x18000eb8d  pop     rbp
0x18000eb8e  retn
0x18000eb8f  test    r15, r15
0x18000eb92  jmp     loc_18000EAE1
0x18000eb97  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@@@@SAXXZ; SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(void)
```
