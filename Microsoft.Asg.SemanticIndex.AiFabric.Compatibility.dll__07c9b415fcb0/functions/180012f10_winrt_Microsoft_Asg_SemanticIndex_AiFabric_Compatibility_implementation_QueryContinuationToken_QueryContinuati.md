# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::QueryContinuationToken::QueryContinuationToken(std::shared_ptr<asg::SemanticIndex::DiskAnn::QueryContinuationData const>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::InternalContinuation)

- ea: `0x180012f10`
- end: `0x18001325a`
- name: `??0QueryContinuationToken@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA@V?$shared_ptr@$$CBUQueryContinuationData@DiskAnn@SemanticIndex@asg@@@std@@UInternalContinuation@1234567@@Z`
- size: `842`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001eb50`

## callees

- `0x180003bd0`
- `0x180003df0`
- `0x18000d230`
- `0x1800128e0`
- `0x180012e40`
- `0x180012f10`
- `0x1801f97e0`
- `0x180242120`

## string_xrefs

- `0x180013141`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\QueryContinuationToken.cpp`
- `0x180013189`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\QueryContinuationToken.cpp`
- `0x1800131d1`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\QueryContinuationToken.cpp`
- `0x180013219`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\QueryContinuationToken.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::QueryContinuationToken::QueryContinuationToken(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  __int64 v6; // r9
  __int64 v7; // rax
  _QWORD *v8; // rcx
  volatile signed __int32 *v9; // rbx
  volatile signed __int32 *v10; // rbx
  int v12; // [rsp+20h] [rbp-50h] BYREF
  const char *v13; // [rsp+28h] [rbp-48h]
  __int64 v14; // [rsp+30h] [rbp-40h]
  _BYTE pExceptionObject[24]; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v16[32]; // [rsp+50h] [rbp-20h] BYREF

  *(_QWORD *)(a1 + 16) = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::QueryContinuationToken,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IQueryContinuationToken>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::QueryContinuationToken::`vftable';
  *(_WORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 48) = *a2;
  *(_QWORD *)(a1 + 56) = a2[1];
  *a2 = 0;
  a2[1] = 0;
  asg::SemanticIndex::MatchOptions::MatchOptions(
    (asg::SemanticIndex::MatchOptions *)(a1 + 64),
    (const struct asg::SemanticIndex::MatchOptions *)(a3 + 1));
  v7 = a3[18];
  a3[18] = v6;
  *(_QWORD *)(a1 + 200) = v7;
  *(_QWORD *)(a1 + 208) = v6;
  *(_QWORD *)(a1 + 216) = v6;
  *(_QWORD *)(a1 + 208) = a3[19];
  *(_QWORD *)(a1 + 216) = a3[20];
  a3[19] = v6;
  a3[20] = v6;
  *(_OWORD *)(a1 + 248) = 0;
  *(_OWORD *)(a1 + 264) = 0;
  *(_OWORD *)(a1 + 280) = 0;
  *(_QWORD *)(a1 + 232) = v6;
  *(_QWORD *)(a1 + 240) = v6;
  *(_DWORD *)(a1 + 296) = -1;
  *(_DWORD *)(a1 + 224) = 2;
  *(_DWORD *)(a1 + 300) = v6;
  if ( *(_QWORD *)(a1 + 48) == v6 )
  {
    v12 = 60;
    v13 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\QueryContinuationToken.cpp";
    v14 = v6;
    winrt::param::hstring::hstring((winrt::param::hstring *)v16, L"continuationData cannot be null");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)pExceptionObject,
      (const struct winrt::param::hstring *)v16,
      (const struct winrt::impl::slim_source_location *)&v12);
    throw (winrt::hresult_invalid_argument *)pExceptionObject;
  }
  if ( *(_QWORD *)(a1 + 200) == v6 )
  {
    v12 = 65;
    v13 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\QueryContinuationToken.cpp";
    v14 = v6;
    winrt::param::hstring::hstring((winrt::param::hstring *)v16, L"queryEmbeddings cannot be null");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)pExceptionObject,
      (const struct winrt::param::hstring *)v16,
      (const struct winrt::impl::slim_source_location *)&v12);
    throw (winrt::hresult_invalid_argument *)pExceptionObject;
  }
  *(_WORD *)(a1 + 24) = 1;
  if ( *(_BYTE *)(a1 + 120) != (_BYTE)v6 )
  {
    v8 = *(_QWORD **)(a1 + 208);
    if ( !v8 )
    {
      v12 = 75;
      v13 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\QueryContinuationToken.cpp";
      v14 = v6;
      winrt::param::hstring::hstring(
        (winrt::param::hstring *)v16,
        L"expected a valid item id filter from the previous internal continuation");
      winrt::hresult_invalid_argument::hresult_invalid_argument(
        (winrt::hresult_invalid_argument *)pExceptionObject,
        (const struct winrt::param::hstring *)v16,
        (const struct winrt::impl::slim_source_location *)&v12);
      throw (winrt::hresult_invalid_argument *)pExceptionObject;
    }
    if ( *(_QWORD *)(a1 + 104) != *v8
      || _mm_srli_si128(*(__m128i *)(a1 + 104), 8).m128i_u64[0] != (__int64)(v8[1] - *v8) >> 4 )
    {
      v12 = 82;
      v13 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\QueryContinuationToken.cpp";
      v14 = v6;
      winrt::param::hstring::hstring(
        (winrt::param::hstring *)v16,
        L"expected the match options item id filter to be the same as the one from the previous internal continuation");
      winrt::hresult_invalid_argument::hresult_invalid_argument(
        (winrt::hresult_invalid_argument *)pExceptionObject,
        (const struct winrt::param::hstring *)v16,
        (const struct winrt::impl::slim_source_location *)&v12);
      throw (winrt::hresult_invalid_argument *)pExceptionObject;
    }
  }
  v9 = (volatile signed __int32 *)a2[1];
  if ( v9 )
  {
    if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  v10 = (volatile signed __int32 *)a3[20];
  if ( v10 )
  {
    if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  if ( a3[18] )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a3 + 18);
  asg::SemanticIndex::MatchOptions::~MatchOptions((asg::SemanticIndex::MatchOptions *)(a3 + 1));
  return a1;
}

```

## disassembly

```asm
0x180012f10  mov     [rsp-38h+arg_10], r8
0x180012f15  mov     [rsp-38h+arg_8], rdx
0x180012f1a  mov     [rsp-38h+arg_0], rcx
0x180012f1f  push    rbp
0x180012f20  push    rbx
0x180012f21  push    rsi
0x180012f22  push    rdi
0x180012f23  push    r12
0x180012f25  push    r14
0x180012f27  push    r15
0x180012f29  mov     rbp, rsp
0x180012f2c  sub     rsp, 70h
0x180012f30  mov     r15, r8
0x180012f33  mov     rbx, rdx
0x180012f36  mov     rdi, rcx
0x180012f39  lea     rax, ??_7?$produce@UQueryContinuationToken@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIQueryContinuationToken@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::QueryContinuationToken,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IQueryContinuationToken>::`vftable'
0x180012f40  mov     [rcx+10h], rax
0x180012f44  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180012f4b  mov     qword ptr [rcx+8], 1
0x180012f53  lea     rax, ??_7QueryContinuationToken@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@6B@; const winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::QueryContinuationToken::`vftable'
0x180012f5a  mov     [rcx], rax
0x180012f5d  mov     word ptr [rcx+18h], 0
0x180012f63  xor     r9d, r9d
0x180012f66  mov     [rcx+30h], r9
0x180012f6a  mov     [rcx+38h], r9
0x180012f6e  mov     rax, [rdx]
0x180012f71  mov     [rcx+30h], rax
0x180012f75  mov     rax, [rdx+8]
0x180012f79  mov     [rcx+38h], rax
0x180012f7d  mov     [rdx], r9
0x180012f80  mov     [rdx+8], r9
0x180012f84  add     rcx, 40h ; '@'; this
0x180012f88  lea     rdx, [r8+8]; struct asg::SemanticIndex::MatchOptions *
0x180012f8c  call    ??0MatchOptions@SemanticIndex@asg@@QEAA@AEBU012@@Z; asg::SemanticIndex::MatchOptions::MatchOptions(asg::SemanticIndex::MatchOptions const &)
0x180012f91  nop
0x180012f92  mov     rax, [r15+90h]
0x180012f99  mov     [r15+90h], r9
0x180012fa0  mov     [rdi+0C8h], rax
0x180012fa7  mov     [rdi+0D0h], r9
0x180012fae  mov     [rdi+0D8h], r9
0x180012fb5  mov     rax, [r15+98h]
0x180012fbc  mov     [rdi+0D0h], rax
0x180012fc3  mov     rax, [r15+0A0h]
0x180012fca  mov     [rdi+0D8h], rax
0x180012fd1  mov     [r15+98h], r9
0x180012fd8  mov     [r15+0A0h], r9
0x180012fdf  xorps   xmm0, xmm0
0x180012fe2  movups  xmmword ptr [rdi+0F8h], xmm0
0x180012fe9  movups  xmmword ptr [rdi+108h], xmm0
0x180012ff0  movups  xmmword ptr [rdi+118h], xmm0
0x180012ff7  mov     [rdi+0E8h], r9
0x180012ffe  mov     [rdi+0F0h], r9
0x180013005  mov     esi, 0FFFFFFFFh
0x18001300a  mov     [rdi+128h], esi
0x180013010  mov     dword ptr [rdi+0E0h], 2
0x18001301a  mov     [rdi+12Ch], r9d
0x180013021  cmp     [rdi+30h], r9
0x180013025  jz      loc_180013182
0x18001302b  cmp     [rdi+0C8h], r9
0x180013032  jz      loc_1800131CA
0x180013038  mov     word ptr [rdi+18h], 1
0x18001303e  cmp     [rdi+78h], r9b
0x180013042  jz      short loc_180013087
0x180013044  mov     rcx, [rdi+0D0h]
0x18001304b  test    rcx, rcx
0x18001304e  jz      loc_180013212
0x180013054  movups  xmm0, xmmword ptr [rdi+68h]
0x180013058  mov     rdx, [rcx]
0x18001305b  movq    rax, xmm0
0x180013060  cmp     rax, rdx
0x180013063  jnz     loc_18001313A
0x180013069  mov     rcx, [rcx+8]
0x18001306d  sub     rcx, rdx
0x180013070  sar     rcx, 4
0x180013074  psrldq  xmm0, 8
0x180013079  movq    rax, xmm0
0x18001307e  cmp     rax, rcx
0x180013081  jnz     loc_18001313A
0x180013087  mov     rbx, [rbx+8]
0x18001308b  test    rbx, rbx
0x18001308e  jz      short loc_1800130C8
0x180013090  mov     eax, esi
0x180013092  lock xadd [rbx+8], eax
0x180013097  cmp     eax, 1
0x18001309a  jnz     short loc_1800130C8
0x18001309c  mov     rax, [rbx]
0x18001309f  mov     rcx, rbx
0x1800130a2  mov     rax, [rax]
0x1800130a5  call    cs:__guard_dispatch_icall_fptr
0x1800130ab  mov     eax, esi
0x1800130ad  lock xadd [rbx+0Ch], eax
0x1800130b2  cmp     eax, 1
0x1800130b5  jnz     short loc_1800130C8
0x1800130b7  mov     rax, [rbx]
0x1800130ba  mov     rcx, rbx
0x1800130bd  mov     rax, [rax+8]
0x1800130c1  call    cs:__guard_dispatch_icall_fptr
0x1800130c7  nop
0x1800130c8  mov     rbx, [r15+0A0h]
0x1800130cf  test    rbx, rbx
0x1800130d2  jz      short loc_180013109
0x1800130d4  mov     eax, esi
0x1800130d6  lock xadd [rbx+8], eax
0x1800130db  cmp     eax, 1
0x1800130de  jnz     short loc_180013109
0x1800130e0  mov     rax, [rbx]
0x1800130e3  mov     rcx, rbx
0x1800130e6  mov     rax, [rax]
0x1800130e9  call    cs:__guard_dispatch_icall_fptr
0x1800130ef  lock xadd [rbx+0Ch], esi
0x1800130f4  cmp     esi, 1
0x1800130f7  jnz     short loc_180013109
0x1800130f9  mov     rax, [rbx]
0x1800130fc  mov     rcx, rbx
0x1800130ff  mov     rax, [rax+8]
0x180013103  call    cs:__guard_dispatch_icall_fptr
0x180013109  cmp     qword ptr [r15+90h], 0
0x180013111  jz      short loc_18001311F
0x180013113  lea     rcx, [r15+90h]
0x18001311a  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18001311f  lea     rcx, [r15+8]; this
0x180013123  call    ??1MatchOptions@SemanticIndex@asg@@QEAA@XZ; asg::SemanticIndex::MatchOptions::~MatchOptions(void)
0x180013128  mov     rax, rdi
0x18001312b  add     rsp, 70h
0x18001312f  pop     r15
0x180013131  pop     r14
0x180013133  pop     r12
0x180013135  pop     rdi
0x180013136  pop     rsi
0x180013137  pop     rbx
0x180013138  pop     rbp
0x180013139  retn
0x18001313a  mov     [rbp+var_50], 52h ; 'R'
0x180013141  lea     rax, aCW1SSrcSemanti_3; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180013148  mov     [rbp+var_48], rax
0x18001314c  mov     [rbp+var_40], r9
0x180013150  lea     rdx, aExpectedTheMat; "expected the match options item id filt"...
0x180013157  lea     rcx, [rbp+var_20]; this
0x18001315b  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180013160  lea     r8, [rbp+var_50]; struct winrt::impl::slim_source_location *
0x180013164  lea     rdx, [rbp+var_20]; struct winrt::param::hstring *
0x180013168  lea     rcx, [rbp+pExceptionObject]; this
0x18001316c  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180013171  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180013178  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001317c  call    _CxxThrowException
0x180013182  mov     [rbp+var_50], 3Ch ; '<'
0x180013189  lea     rax, aCW1SSrcSemanti_3; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180013190  mov     [rbp+var_48], rax
0x180013194  mov     [rbp+var_40], r9
0x180013198  lea     rdx, aContinuationda; "continuationData cannot be null"
0x18001319f  lea     rcx, [rbp+var_20]; this
0x1800131a3  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x1800131a8  lea     r8, [rbp+var_50]; struct winrt::impl::slim_source_location *
0x1800131ac  lea     rdx, [rbp+var_20]; struct winrt::param::hstring *
0x1800131b0  lea     rcx, [rbp+pExceptionObject]; this
0x1800131b4  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x1800131b9  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x1800131c0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800131c4  call    _CxxThrowException
0x1800131ca  mov     [rbp+var_50], 41h ; 'A'
0x1800131d1  lea     rax, aCW1SSrcSemanti_3; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x1800131d8  mov     [rbp+var_48], rax
0x1800131dc  mov     [rbp+var_40], r9
0x1800131e0  lea     rdx, aQueryembedding; "queryEmbeddings cannot be null"
0x1800131e7  lea     rcx, [rbp+var_20]; this
0x1800131eb  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x1800131f0  lea     r8, [rbp+var_50]; struct winrt::impl::slim_source_location *
0x1800131f4  lea     rdx, [rbp+var_20]; struct winrt::param::hstring *
0x1800131f8  lea     rcx, [rbp+pExceptionObject]; this
0x1800131fc  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180013201  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180013208  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001320c  call    _CxxThrowException
0x180013212  mov     [rbp+var_50], 4Bh ; 'K'
0x180013219  lea     rax, aCW1SSrcSemanti_3; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180013220  mov     [rbp+var_48], rax
0x180013224  mov     [rbp+var_40], r9
0x180013228  lea     rdx, aExpectedAValid; "expected a valid item id filter from th"...
0x18001322f  lea     rcx, [rbp+var_20]; this
0x180013233  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180013238  lea     r8, [rbp+var_50]; struct winrt::impl::slim_source_location *
0x18001323c  lea     rdx, [rbp+var_20]; struct winrt::param::hstring *
0x180013240  lea     rcx, [rbp+pExceptionObject]; this
0x180013244  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180013249  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180013250  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180013254  call    _CxxThrowException
```
