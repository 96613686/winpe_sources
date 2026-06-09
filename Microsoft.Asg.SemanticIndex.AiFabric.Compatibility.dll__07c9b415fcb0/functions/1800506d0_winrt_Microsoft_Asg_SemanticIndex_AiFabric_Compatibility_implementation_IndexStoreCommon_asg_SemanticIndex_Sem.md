# `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::DefaultQueryDistanceThreshold(void)'::`2'::_lambda_1_::operator()(void)

- ea: `0x1800506d0`
- end: `0x18005096a`
- name: `??R_lambda_1_@?1??DefaultQueryDistanceThreshold@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAAMXZ@QEBA@XZ`
- size: `666`
- prototype: `float(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180055b80`

## callees

- `0x18000b0f0`
- `0x18000e890`
- `0x1800178d0`
- `0x18002f8e0`
- `0x180038d00`
- `0x1800506d0`
- `0x180068510`
- `0x1801d2ae0`
- `0x1801d2b20`
- `0x1801d2dc0`
- `0x1801f7110`
- `0x180242120`

## string_xrefs

- `0x180050724`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x18005072f`: `auto __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiF`
- `0x180050826`: `float __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::Ai`

## pseudocode

```c
__m128 __fastcall `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::DefaultQueryDistanceThreshold'::`2'::_lambda_1_::operator()(
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

  v16[0] = ___7___Func_impl_no_alloc_V_lambda_1___1___R1_1__DefaultQueryDistanceThreshold___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UTextEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_U4562789_U4implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__QEAAMXZ_QEBA_XZ_X__V_std__6B_;
  v17 = v16;
  *(_QWORD *)&v18 = 0x3E0000019FLL;
  *((_QWORD *)&v18 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
  v19 = "auto __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<cla"
        "ss asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::"
        "TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::Te"
        "xtEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenera"
        "tor,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerato"
        "r>::DefaultQueryDistanceThreshold::<lambda_1>::operator ()(void) const";
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
    v20[0] = ___7___Func_impl_no_alloc_V_lambda_2___2___R_lambda_1___1__DefaultQueryDistanceThreshold___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UTextEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_U4562789_U4implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__QEAAMXZ_QEBA_XZ_X__V_std__6B_;
    v20[1] = *a1;
    v20[7] = v20;
    *(_QWORD *)&v21 = 0x3D000001C4LL;
    *((_QWORD *)&v21 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
    v22 = "float __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<"
          "class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibil"
          "ity::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementat"
          "ion::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddi"
          "ngsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddi"
          "ngsGenerator>::DefaultQueryDistanceThreshold::<lambda_1>::operator ()(void) const";
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
0x1800506d0  mov     rax, rsp
0x1800506d3  mov     [rax+10h], rbx
0x1800506d7  mov     [rax+18h], rsi
0x1800506db  mov     [rax+20h], rdi
0x1800506df  push    rbp
0x1800506e0  lea     rbp, [rax-28h]
0x1800506e4  sub     rsp, 120h
0x1800506eb  movaps  xmmword ptr [rax-18h], xmm6
0x1800506ef  mov     rax, cs:__security_cookie
0x1800506f6  xor     rax, rsp
0x1800506f9  mov     [rbp+20h+var_20], rax
0x1800506fd  mov     rdi, rcx
0x180050700  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?1???R1?1??DefaultQueryDistanceThreshold@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAAMXZ@QEBA@XZ@X$$V@std@@6B@; const std::_Func_impl_no_alloc<``winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::DefaultQueryDistanceThreshold(void)'::`2'::_lambda_1_::operator()(void)'::`2'::_lambda_1_,void,>::`vftable'
0x180050707  mov     [rsp+120h+var_E0], rax
0x18005070c  lea     rax, [rsp+120h+var_E0]
0x180050711  mov     [rsp+120h+var_A8], rax
0x180050716  mov     dword ptr [rbp+20h+var_A0], 19Fh
0x18005071d  mov     dword ptr [rbp+20h+var_A0+4], 3Eh ; '>'
0x180050724  lea     rsi, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18005072b  mov     qword ptr [rbp+20h+var_A0+8], rsi
0x18005072f  lea     rax, aAutoCdeclWinrt_0; "auto __cdecl winrt::Microsoft::Asg::Sem"...
0x180050736  mov     [rbp+20h+var_90], rax
0x18005073a  mov     r8b, 1
0x18005073d  lea     rdx, [rsp+120h+var_108+8]
0x180050742  mov     rcx, [rcx]
0x180050745  call    ?AcquireLock@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBA?AV?$unique_lock@Vrecursive_mutex@std@@@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(bool)
0x18005074a  nop
0x18005074b  mov     rcx, [rdi]
0x18005074e  movzx   eax, byte ptr [rsp+120h+var_F8]
0x180050753  cmp     byte ptr [rcx+0E0h], 0
0x18005075a  jz      short loc_1800507DB
0x18005075c  nop     dword ptr [rax+00h]
0x180050760  mov     rcx, [rsp+120h+var_108+8]; _Mtx_t
0x180050765  test    rcx, rcx
0x180050768  jz      loc_180050937
0x18005076e  test    al, al
0x180050770  jz      loc_180050937
0x180050776  call    _Mtx_unlock
0x18005077b  mov     byte ptr [rsp+120h+var_F8], 0
0x180050780  mov     [rsp+120h+var_F0], 64h ; 'd'
0x180050789  lea     rcx, [rsp+120h+var_F0]
0x18005078e  call    ??$sleep_for@_JU?$ratio@$00$0DOI@@std@@@this_thread@std@@YAXAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z; std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x180050793  mov     rbx, [rsp+120h+var_108+8]
0x180050798  test    rbx, rbx
0x18005079b  jz      loc_180050937
0x1800507a1  cmp     byte ptr [rsp+120h+var_F8], 0
0x1800507a6  jnz     loc_18005095F
0x1800507ac  mov     rcx, rbx; _Mtx_t
0x1800507af  call    _Mtx_lock
0x1800507b4  test    eax, eax
0x1800507b6  jnz     loc_180050954
0x1800507bc  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x1800507c3  jz      loc_180050942
0x1800507c9  mov     al, 1
0x1800507cb  mov     byte ptr [rsp+120h+var_F8], al
0x1800507cf  mov     rcx, [rdi]
0x1800507d2  cmp     byte ptr [rcx+0E0h], 0
0x1800507d9  jnz     short loc_180050760
0x1800507db  cmp     byte ptr [rcx+0A4h], 0
0x1800507e2  jz      short loc_1800507F3
0x1800507e4  movss   xmm6, dword ptr [rcx+0A0h]
0x1800507ec  test    al, al
0x1800507ee  jmp     loc_1800508F3
0x1800507f3  mov     byte ptr [rcx+0E0h], 1
0x1800507fa  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_2_@?2???R_lambda_1_@?1??DefaultQueryDistanceThreshold@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAAMXZ@QEBA@XZ@X$$V@std@@6B@; const std::_Func_impl_no_alloc<``winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::DefaultQueryDistanceThreshold(void)'::`2'::_lambda_1_::operator()(void)'::`3'::_lambda_2_,void,>::`vftable'
0x180050801  mov     [rbp+20h+var_80], rax
0x180050805  mov     rax, [rdi]
0x180050808  mov     [rbp+20h+var_78], rax
0x18005080c  lea     rax, [rbp+20h+var_80]
0x180050810  mov     [rbp+20h+var_48], rax
0x180050814  mov     dword ptr [rbp+20h+var_40], 1C4h
0x18005081b  mov     dword ptr [rbp+20h+var_40+4], 3Dh ; '='
0x180050822  mov     qword ptr [rbp+20h+var_40+8], rsi
0x180050826  lea     rax, aFloatCdeclWinr; "float __cdecl winrt::Microsoft::Asg::Se"...
0x18005082d  mov     [rbp+20h+var_30], rax
0x180050831  mov     rcx, [rsp+120h+var_A8]
0x180050836  test    rcx, rcx
0x180050839  jz      short loc_18005085C
0x18005083b  lea     rax, [rsp+120h+var_E0]
0x180050840  cmp     rcx, rax
0x180050843  setnz   dl
0x180050846  mov     rax, [rcx]
0x180050849  mov     rax, [rax+20h]
0x18005084d  call    cs:__guard_dispatch_icall_fptr
0x180050853  mov     [rsp+120h+var_A8], 0
0x18005085c  lea     rdx, [rbp+20h+var_80]
0x180050860  lea     rcx, [rsp+120h+var_E0]
0x180050865  call    ?_Reset_move@?$_Func_class@X$$V@std@@IEAAX$$QEAV12@@Z; std::_Func_class<void,>::_Reset_move(std::_Func_class<void,> &&)
0x18005086a  movaps  xmm0, [rbp+20h+var_40]
0x18005086e  movaps  [rbp+20h+var_A0], xmm0
0x180050872  movsd   xmm1, [rbp+20h+var_30]
0x180050877  movsd   [rbp+20h+var_90], xmm1
0x18005087c  lea     rcx, [rbp+20h+var_80]; this
0x180050880  call    ??1OnScopeExit@asg@@QEAA@XZ; asg::OnScopeExit::~OnScopeExit(void)
0x180050885  nop
0x180050886  cmp     byte ptr [rsp+120h+var_F8], 0
0x18005088b  jz      short loc_180050897
0x18005088d  mov     rcx, [rsp+120h+var_108+8]; _Mtx_t
0x180050892  call    _Mtx_unlock
0x180050897  mov     rax, [rdi+8]
0x18005089b  movups  xmm0, xmmword ptr [rax]
0x18005089e  movaps  xmmword ptr [rsp+120h+var_108+8], xmm0
0x1800508a3  lea     rcx, [rsp+120h+var_108+8]
0x1800508a8  call    ?GetDefaultQueryDistanceThresholdForVectorSpace@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YAMUGuid@asg@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::GetDefaultQueryDistanceThresholdForVectorSpace(asg::Guid)
0x1800508ad  movaps  xmm6, xmm0
0x1800508b0  mov     r8b, 1
0x1800508b3  lea     rdx, [rsp+120h+var_108+8]
0x1800508b8  mov     rcx, [rdi]
0x1800508bb  call    ?AcquireLock@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBA?AV?$unique_lock@Vrecursive_mutex@std@@@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(bool)
0x1800508c0  nop
0x1800508c1  mov     rcx, [rdi]
0x1800508c4  cmp     byte ptr [rcx+0A4h], 0
0x1800508cb  jnz     short loc_1800508E6
0x1800508cd  movss   dword ptr [rsp+120h+var_F0], xmm6
0x1800508d3  mov     byte ptr [rsp+120h+var_F0+4], 1
0x1800508d8  mov     rax, [rsp+120h+var_F0]
0x1800508dd  mov     [rcx+0A0h], rax
0x1800508e4  jmp     short loc_1800508EE
0x1800508e6  movss   xmm6, dword ptr [rcx+0A0h]
0x1800508ee  cmp     byte ptr [rsp+120h+var_F8], 0
0x1800508f3  jz      short loc_180050900
0x1800508f5  mov     rcx, [rsp+120h+var_108+8]; _Mtx_t
0x1800508fa  call    _Mtx_unlock
0x1800508ff  nop
0x180050900  lea     rcx, [rsp+120h+var_E0]; this
0x180050905  call    ??1OnScopeExit@asg@@QEAA@XZ; asg::OnScopeExit::~OnScopeExit(void)
0x18005090a  movaps  xmm0, xmm6
0x18005090d  mov     rcx, [rbp+20h+var_20]
0x180050911  xor     rcx, rsp; StackCookie
0x180050914  call    __security_check_cookie
0x180050919  lea     r11, [rsp+120h+var_s0]
0x180050921  mov     rbx, [r11+18h]
0x180050925  mov     rsi, [r11+20h]
0x180050929  mov     rdi, [r11+28h]
0x18005092d  movaps  xmm6, xmmword ptr [r11-10h]
0x180050932  mov     rsp, r11
0x180050935  pop     rbp
0x180050936  retn
0x180050937  mov     ecx, 1
0x18005093c  call    ?_Throw_system_error@std@@YAXW4errc@1@@Z; std::_Throw_system_error(std::errc)
0x180050942  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x180050949  mov     ecx, 6; int
0x18005094e  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180050954  mov     ecx, 5; int
0x180050959  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18005095f  mov     ecx, 24h ; '$'
0x180050964  call    ?_Throw_system_error@std@@YAXW4errc@1@@Z; std::_Throw_system_error(std::errc)
```
