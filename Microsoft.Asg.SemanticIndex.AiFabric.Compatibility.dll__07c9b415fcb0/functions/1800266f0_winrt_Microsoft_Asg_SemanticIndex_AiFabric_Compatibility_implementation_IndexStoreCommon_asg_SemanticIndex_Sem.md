# `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::DefaultQueryDistanceThreshold(void)'::`2'::_lambda_1_::operator()(void)

- ea: `0x1800266f0`
- end: `0x18002698a`
- name: `??R_lambda_1_@?1??DefaultQueryDistanceThreshold@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAAMXZ@QEBA@XZ`
- size: `666`
- prototype: `float(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180032230`

## callees

- `0x18000b0f0`
- `0x18000e890`
- `0x1800178d0`
- `0x1800266f0`
- `0x18002f8e0`
- `0x180038d00`
- `0x180068510`
- `0x1801d2ae0`
- `0x1801d2b20`
- `0x1801d2dc0`
- `0x1801f7110`
- `0x180242120`

## string_xrefs

- `0x180026744`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x180026846`: `float __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::`
- `0x18002674f`: `auto __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::A`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__m128 __fastcall `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::DefaultQueryDistanceThreshold'::`2'::_lambda_1_::operator()(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  char i; // al
  _Mtx_t v7; // rbx
  __int128 v8; // xmm6
  bool v9; // zf
  __int128 v10; // xmm0
  __int64 v11; // r8
  __int64 v12; // rcx
  _Mtx_t v14[2]; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v15; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v16[7]; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD *v17; // [rsp+80h] [rbp-88h]
  __int128 v18; // [rsp+88h] [rbp-80h]
  const char *v19; // [rsp+98h] [rbp-70h]
  _QWORD v20[8]; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v21; // [rsp+E8h] [rbp-20h]
  const char *v22; // [rsp+F8h] [rbp-10h]

  v16[0] = ___7___Func_impl_no_alloc_V_lambda_1___1___R1_1__DefaultQueryDistanceThreshold___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UImageEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_UTextEmbeddingsGenerator_562789_UTextEmbeddingsGenerator_implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__QEAAMXZ_QEBA_XZ_X__V_std__6B_;
  v17 = v16;
  *(_QWORD *)&v18 = 0x3E0000019FLL;
  *((_QWORD *)&v18 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
  v19 = "auto __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<cla"
        "ss asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::"
        "ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::I"
        "mageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGene"
        "rator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenera"
        "tor>::DefaultQueryDistanceThreshold::<lambda_1>::operator ()(void) const";
  LOBYTE(a3) = 1;
  winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(
    *a1,
    v14,
    a3);
  v5 = *a1;
  for ( i = (char)v14[1]; *(_BYTE *)(*a1 + 224LL); v5 = *a1 )
  {
    if ( !v14[0]
      || !i
      || (Mtx_unlock(v14[0]),
          LOBYTE(v14[1]) = 0,
          v15 = 100,
          std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(&v15),
          (v7 = v14[0]) == 0) )
    {
      std::_Throw_system_error(1);
    }
    if ( LOBYTE(v14[1]) )
      std::_Throw_system_error(36);
    if ( Mtx_lock(v14[0]) )
      std::_Throw_Cpp_error(5);
    if ( *((_DWORD *)v7 + 19) == 0x7FFFFFFF )
    {
      *((_DWORD *)v7 + 19) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    i = 1;
    LOBYTE(v14[1]) = 1;
  }
  if ( *(_BYTE *)(v5 + 164) )
  {
    v8 = *(unsigned int *)(v5 + 160);
    v9 = i == 0;
  }
  else
  {
    *(_BYTE *)(v5 + 224) = 1;
    v20[0] = ___7___Func_impl_no_alloc_V_lambda_2___2___R_lambda_1___1__DefaultQueryDistanceThreshold___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UImageEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_UTextEmbeddingsGenerator_562789_UTextEmbeddingsGenerator_implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__QEAAMXZ_QEBA_XZ_X__V_std__6B_;
    v20[1] = *a1;
    v20[7] = v20;
    *(_QWORD *)&v21 = 0x3D000001C4LL;
    *((_QWORD *)&v21 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
    v22 = "float __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<"
          "class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibil"
          "ity::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementa"
          "tion::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbed"
          "dingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbed"
          "dingsGenerator>::DefaultQueryDistanceThreshold::<lambda_1>::operator ()(void) const";
    if ( v17 )
    {
      LOBYTE(v4) = v17 != v16;
      (*(void (__fastcall **)(_QWORD *, __int64))(*v17 + 32LL))(v17, v4);
      v17 = 0;
    }
    std::_Func_class<void,>::_Reset_move(v16, v20);
    v18 = v21;
    v19 = v22;
    asg::OnScopeExit::~OnScopeExit((asg::OnScopeExit *)v20);
    if ( LOBYTE(v14[1]) )
      Mtx_unlock(v14[0]);
    *(_OWORD *)v14 = *(_OWORD *)a1[1];
    *((_Mtx_t *)&v10 + 1) = v14[1];
    *(double *)&v10 = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::GetDefaultQueryDistanceThresholdForVectorSpace(v14);
    v8 = v10;
    LOBYTE(v11) = 1;
    winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(
      *a1,
      v14,
      v11);
    v12 = *a1;
    if ( *(_BYTE *)(*a1 + 164LL) )
    {
      v8 = *(unsigned int *)(v12 + 160);
    }
    else
    {
      LODWORD(v15) = v10;
      BYTE4(v15) = 1;
      *(_QWORD *)(v12 + 160) = v15;
    }
    v9 = LOBYTE(v14[1]) == 0;
  }
  if ( !v9 )
    Mtx_unlock(v14[0]);
  asg::OnScopeExit::~OnScopeExit((asg::OnScopeExit *)v16);
  return (__m128)v8;
}

```

## disassembly

```asm
0x1800266f0  mov     rax, rsp
0x1800266f3  mov     [rax+10h], rbx
0x1800266f7  mov     [rax+18h], rsi
0x1800266fb  mov     [rax+20h], rdi
0x1800266ff  push    rbp
0x180026700  lea     rbp, [rax-28h]
0x180026704  sub     rsp, 120h
0x18002670b  movaps  xmmword ptr [rax-18h], xmm6
0x18002670f  mov     rax, cs:__security_cookie
0x180026716  xor     rax, rsp
0x180026719  mov     [rbp+20h+var_20], rax
0x18002671d  mov     rdi, rcx
0x180026720  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?1???R1?1??DefaultQueryDistanceThreshold@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAAMXZ@QEBA@XZ@X$$V@std@@6B@; const std::_Func_impl_no_alloc<``winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::DefaultQueryDistanceThreshold(void)'::`2'::_lambda_1_::operator()(void)'::`2'::_lambda_1_,void,>::`vftable'
0x180026727  mov     [rsp+120h+var_E0], rax
0x18002672c  lea     rax, [rsp+120h+var_E0]
0x180026731  mov     [rsp+120h+var_A8], rax
0x180026736  mov     dword ptr [rbp+20h+var_A0], 19Fh
0x18002673d  mov     dword ptr [rbp+20h+var_A0+4], 3Eh ; '>'
0x180026744  lea     rsi, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18002674b  mov     qword ptr [rbp+20h+var_A0+8], rsi
0x18002674f  lea     rax, aAutoCdeclWinrt; "auto __cdecl winrt::Microsoft::Asg::Sem"...
0x180026756  mov     [rbp+20h+var_90], rax
0x18002675a  mov     r8b, 1
0x18002675d  lea     rdx, [rsp+120h+var_108+8]
0x180026762  mov     rcx, [rcx]
0x180026765  call    ?AcquireLock@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBA?AV?$unique_lock@Vrecursive_mutex@std@@@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(bool)
0x18002676a  nop
0x18002676b  mov     rcx, [rdi]
0x18002676e  movzx   eax, byte ptr [rsp+120h+var_F8]
0x180026773  cmp     byte ptr [rcx+0E0h], 0
0x18002677a  jz      short loc_1800267FB
0x18002677c  nop     dword ptr [rax+00h]
0x180026780  mov     rcx, [rsp+120h+var_108+8]; _Mtx_t
0x180026785  test    rcx, rcx
0x180026788  jz      loc_180026957
0x18002678e  test    al, al
0x180026790  jz      loc_180026957
0x180026796  call    _Mtx_unlock
0x18002679b  mov     byte ptr [rsp+120h+var_F8], 0
0x1800267a0  mov     [rsp+120h+var_F0], 64h ; 'd'
0x1800267a9  lea     rcx, [rsp+120h+var_F0]
0x1800267ae  call    ??$sleep_for@_JU?$ratio@$00$0DOI@@std@@@this_thread@std@@YAXAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z; std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x1800267b3  mov     rbx, [rsp+120h+var_108+8]
0x1800267b8  test    rbx, rbx
0x1800267bb  jz      loc_180026957
0x1800267c1  cmp     byte ptr [rsp+120h+var_F8], 0
0x1800267c6  jnz     loc_18002697F
0x1800267cc  mov     rcx, rbx; _Mtx_t
0x1800267cf  call    _Mtx_lock
0x1800267d4  test    eax, eax
0x1800267d6  jnz     loc_180026974
0x1800267dc  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x1800267e3  jz      loc_180026962
0x1800267e9  mov     al, 1
0x1800267eb  mov     byte ptr [rsp+120h+var_F8], al
0x1800267ef  mov     rcx, [rdi]
0x1800267f2  cmp     byte ptr [rcx+0E0h], 0
0x1800267f9  jnz     short loc_180026780
0x1800267fb  cmp     byte ptr [rcx+0A4h], 0
0x180026802  jz      short loc_180026813
0x180026804  movss   xmm6, dword ptr [rcx+0A0h]
0x18002680c  test    al, al
0x18002680e  jmp     loc_180026913
0x180026813  mov     byte ptr [rcx+0E0h], 1
0x18002681a  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_2_@?2???R_lambda_1_@?1??DefaultQueryDistanceThreshold@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAAMXZ@QEBA@XZ@X$$V@std@@6B@; const std::_Func_impl_no_alloc<``winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::DefaultQueryDistanceThreshold(void)'::`2'::_lambda_1_::operator()(void)'::`3'::_lambda_2_,void,>::`vftable'
0x180026821  mov     [rbp+20h+var_80], rax
0x180026825  mov     rax, [rdi]
0x180026828  mov     [rbp+20h+var_78], rax
0x18002682c  lea     rax, [rbp+20h+var_80]
0x180026830  mov     [rbp+20h+var_48], rax
0x180026834  mov     dword ptr [rbp+20h+var_40], 1C4h
0x18002683b  mov     dword ptr [rbp+20h+var_40+4], 3Dh ; '='
0x180026842  mov     qword ptr [rbp+20h+var_40+8], rsi
0x180026846  lea     rax, aFloatCdeclWinr_0; "float __cdecl winrt::Microsoft::Asg::Se"...
0x18002684d  mov     [rbp+20h+var_30], rax
0x180026851  mov     rcx, [rsp+120h+var_A8]
0x180026856  test    rcx, rcx
0x180026859  jz      short loc_18002687C
0x18002685b  lea     rax, [rsp+120h+var_E0]
0x180026860  cmp     rcx, rax
0x180026863  setnz   dl
0x180026866  mov     rax, [rcx]
0x180026869  mov     rax, [rax+20h]
0x18002686d  call    cs:__guard_dispatch_icall_fptr
0x180026873  mov     [rsp+120h+var_A8], 0
0x18002687c  lea     rdx, [rbp+20h+var_80]
0x180026880  lea     rcx, [rsp+120h+var_E0]
0x180026885  call    ?_Reset_move@?$_Func_class@X$$V@std@@IEAAX$$QEAV12@@Z; std::_Func_class<void,>::_Reset_move(std::_Func_class<void,> &&)
0x18002688a  movaps  xmm0, [rbp+20h+var_40]
0x18002688e  movaps  [rbp+20h+var_A0], xmm0
0x180026892  movsd   xmm1, [rbp+20h+var_30]
0x180026897  movsd   [rbp+20h+var_90], xmm1
0x18002689c  lea     rcx, [rbp+20h+var_80]; this
0x1800268a0  call    ??1OnScopeExit@asg@@QEAA@XZ; asg::OnScopeExit::~OnScopeExit(void)
0x1800268a5  nop
0x1800268a6  cmp     byte ptr [rsp+120h+var_F8], 0
0x1800268ab  jz      short loc_1800268B7
0x1800268ad  mov     rcx, [rsp+120h+var_108+8]; _Mtx_t
0x1800268b2  call    _Mtx_unlock
0x1800268b7  mov     rax, [rdi+8]
0x1800268bb  movups  xmm0, xmmword ptr [rax]
0x1800268be  movaps  xmmword ptr [rsp+120h+var_108+8], xmm0
0x1800268c3  lea     rcx, [rsp+120h+var_108+8]
0x1800268c8  call    ?GetDefaultQueryDistanceThresholdForVectorSpace@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YAMUGuid@asg@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::GetDefaultQueryDistanceThresholdForVectorSpace(asg::Guid)
0x1800268cd  movaps  xmm6, xmm0
0x1800268d0  mov     r8b, 1
0x1800268d3  lea     rdx, [rsp+120h+var_108+8]
0x1800268d8  mov     rcx, [rdi]
0x1800268db  call    ?AcquireLock@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBA?AV?$unique_lock@Vrecursive_mutex@std@@@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(bool)
0x1800268e0  nop
0x1800268e1  mov     rcx, [rdi]
0x1800268e4  cmp     byte ptr [rcx+0A4h], 0
0x1800268eb  jnz     short loc_180026906
0x1800268ed  movss   dword ptr [rsp+120h+var_F0], xmm6
0x1800268f3  mov     byte ptr [rsp+120h+var_F0+4], 1
0x1800268f8  mov     rax, [rsp+120h+var_F0]
0x1800268fd  mov     [rcx+0A0h], rax
0x180026904  jmp     short loc_18002690E
0x180026906  movss   xmm6, dword ptr [rcx+0A0h]
0x18002690e  cmp     byte ptr [rsp+120h+var_F8], 0
0x180026913  jz      short loc_180026920
0x180026915  mov     rcx, [rsp+120h+var_108+8]; _Mtx_t
0x18002691a  call    _Mtx_unlock
0x18002691f  nop
0x180026920  lea     rcx, [rsp+120h+var_E0]; this
0x180026925  call    ??1OnScopeExit@asg@@QEAA@XZ; asg::OnScopeExit::~OnScopeExit(void)
0x18002692a  movaps  xmm0, xmm6
0x18002692d  mov     rcx, [rbp+20h+var_20]
0x180026931  xor     rcx, rsp; StackCookie
0x180026934  call    __security_check_cookie
0x180026939  lea     r11, [rsp+120h+var_s0]
0x180026941  mov     rbx, [r11+18h]
0x180026945  mov     rsi, [r11+20h]
0x180026949  mov     rdi, [r11+28h]
0x18002694d  movaps  xmm6, xmmword ptr [r11-10h]
0x180026952  mov     rsp, r11
0x180026955  pop     rbp
0x180026956  retn
0x180026957  mov     ecx, 1
0x18002695c  call    ?_Throw_system_error@std@@YAXW4errc@1@@Z; std::_Throw_system_error(std::errc)
0x180026962  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x180026969  mov     ecx, 6; int
0x18002696e  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180026974  mov     ecx, 5; int
0x180026979  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18002697f  mov     ecx, 24h ; '$'
0x180026984  call    ?_Throw_system_error@std@@YAXW4errc@1@@Z; std::_Throw_system_error(std::errc)
```
