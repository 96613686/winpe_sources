# Uev::Repository::LookupADSettingsStoragePath(boost::filesystem::path &,boost::filesystem::path &)

- ea: `0x14008c0e4`
- end: `0x14008c41c`
- name: `?LookupADSettingsStoragePath@Repository@Uev@@AEBA_NAEAVpath@filesystem@boost@@0@Z`
- size: `824`
- prototype: `bool(Uev::Repository *__hidden this, struct boost::filesystem::path *, struct boost::filesystem::path *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140089ef0`

## callees

- `0x140003e50`
- `0x14000ba60`
- `0x14000c2b8`
- `0x14000d7b4`
- `0x140015190`
- `0x14001a310`
- `0x1400205f4`
- `0x140046e04`
- `0x140046f94`
- `0x1400663e4`
- `0x140089d54`
- `0x14008ab3c`
- `0x14008c0e4`
- `0x14009b010`

## import_xrefs

- `ole32!CoInitializeEx` at `0x14008c142`
- `ole32!CoInitializeEx` at `0x14008c142`
- `ole32!CoUninitialize` at `0x14008c3cf`
- `ole32!CoUninitialize` at `0x14008c3cf`

## string_xrefs

- `0x14008c26b`: `LookupADSettingsStoragePath failed Coinitialize COM. HRESULT: `
- `0x14008c122`: `Repository::LookupADSettingsStoragePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char __fastcall Uev::Repository::LookupADSettingsStoragePath(Uev::Repository *this, __m128i *a2, __m128i *a3)
{
  HRESULT v5; // ebx
  int v6; // r14d
  __int64 v7; // rcx
  _QWORD *v8; // rdi
  void *v9; // rax
  __int64 v10; // rax
  __int128 v11; // xmm6
  __m128i v12; // xmm7
  __int128 *v13; // r9
  _WORD *v14; // rdx
  unsigned __int64 v15; // r8
  Uev::Repository *v16; // rcx
  char v17; // di
  HRESULT v19; // [rsp+28h] [rbp-E0h] BYREF
  __m128i v20; // [rsp+30h] [rbp-D8h] BYREF
  __m128i si128; // [rsp+40h] [rbp-C8h]
  __m128i v22; // [rsp+50h] [rbp-B8h] BYREF
  __m128i v23; // [rsp+60h] [rbp-A8h]
  __m128i v24; // [rsp+70h] [rbp-98h] BYREF
  __m128i v25; // [rsp+80h] [rbp-88h]
  HRESULT v26; // [rsp+90h] [rbp-78h]
  _OWORD v27[2]; // [rsp+98h] [rbp-70h] BYREF
  __int128 v28; // [rsp+B8h] [rbp-50h] BYREF
  __m128i v29; // [rsp+C8h] [rbp-40h]
  _BYTE v30[32]; // [rsp+D8h] [rbp-30h] BYREF
  _QWORD v31[2]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v32[128]; // [rsp+108h] [rbp+0h] BYREF

  Uev::ScopeTracker::ScopeTracker(
    (Uev::ScopeTracker *)v32,
    L"CscChangeManager",
    L"Repository::LookupADSettingsStoragePath");
  v31[0] = 0;
  v5 = CoInitializeEx(0, 0);
  v26 = v5;
  v20 = 0;
  si128 = 0;
  std::wstring::_Construct<1,wchar_t *>(&v20, &Data, 0);
  if ( a2 != &v20 )
  {
    std::wstring::_Tidy_deallocate(a2);
    *a2 = v20;
    a2[1] = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v20.m128i_i16[0] = 0;
  }
  std::wstring::_Tidy_deallocate(&v20);
  v22 = 0;
  v23 = 0;
  std::wstring::_Construct<1,wchar_t *>(&v22, &Data, 0);
  if ( a3 != &v22 )
  {
    std::wstring::_Tidy_deallocate(a3);
    *a3 = v22;
    a3[1] = v23;
    v23 = _mm_load_si128((const __m128i *)&_xmm);
    v22.m128i_i16[0] = 0;
  }
  std::wstring::_Tidy_deallocate(&v22);
  if ( (int)(v5 + 0x80000000) >= 0 && v5 != -2147417850 )
  {
    v6 = v5;
    v19 = v5;
    if ( (*(_BYTE *)(*(_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance(0x80000000LL) + 32LL) & 2) != 0 )
    {
      v8 = (_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance(v7);
      v9 = (void *)boost::lexical_cast<std::wstring,long>(v30, &v19);
      v10 = std::wstring::_Insert<wchar_t>(v9);
      v11 = *(_OWORD *)v10;
      v28 = *(_OWORD *)v10;
      v29 = *(__m128i *)(v10 + 16);
      v12 = v29;
      *(_QWORD *)(v10 + 16) = 0;
      *(_QWORD *)(v10 + 24) = 7;
      *(_WORD *)v10 = 0;
      memset(v27, 0, sizeof(v27));
      std::wstring::_Construct<1,wchar_t *>(v27, L"CscChangeManager", 0x10u);
      v13 = &v28;
      if ( _mm_srli_si128(v12, 8).m128i_u64[0] > 7 )
        v13 = (__int128 *)v11;
      Uev::LogImpl::Write(*v8, 2, v27, v13);
      std::wstring::_Tidy_deallocate(v27);
      std::wstring::_Tidy_deallocate(&v28);
      std::wstring::_Tidy_deallocate(v30);
    }
    goto LABEL_20;
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)Uev::Repository::s_ADSMethods + 8LL))(
         Uev::Repository::s_ADSMethods,
         v31);
  if ( v6 >= 0 )
  {
    if ( v31[0] )
      v14 = *(_WORD **)v31[0];
    else
      v14 = 0;
    v24 = 0;
    v25 = 0;
    v15 = -1;
    do
      ++v15;
    while ( v14[v15] );
    std::wstring::_Construct<1,wchar_t *>(&v24, v14, v15);
    if ( a2 != &v24 )
    {
      std::wstring::_Tidy_deallocate(a2);
      *a2 = v24;
      a2[1] = v25;
      v25 = _mm_load_si128((const __m128i *)&_xmm);
      v24.m128i_i16[0] = 0;
    }
    std::wstring::_Tidy_deallocate(&v24);
    std::wstring::operator=(a3, a2);
    Uev::Repository::ExpandRepositoryPath(v16, (struct boost::filesystem::path *)a2);
LABEL_20:
    v17 = 1;
    if ( v6 >= 0 )
      goto LABEL_22;
  }
  v17 = 0;
LABEL_22:
  if ( v5 >= 0 )
    CoUninitialize();
  _bstr_t::_Free((_bstr_t *)v31);
  Uev::ScopeTracker::~ScopeTracker((Uev::ScopeTracker *)v32);
  return v17;
}

```

## disassembly

```asm
0x14008c0e4  mov     rax, rsp
0x14008c0e7  mov     [rax+8], rbx
0x14008c0eb  push    rbp
0x14008c0ec  push    rsi
0x14008c0ed  push    rdi
0x14008c0ee  push    r14
0x14008c0f0  push    r15
0x14008c0f2  lea     rbp, [rax-0D8h]
0x14008c0f9  sub     rsp, 1B0h
0x14008c100  movaps  xmmword ptr [rax-38h], xmm6
0x14008c104  movaps  xmmword ptr [rax-48h], xmm7
0x14008c108  mov     rax, cs:__security_cookie
0x14008c10f  xor     rax, rsp
0x14008c112  mov     [rbp+0D0h+var_50], rax
0x14008c119  mov     rsi, r8
0x14008c11c  mov     rdi, rdx
0x14008c11f  xor     r15d, r15d
0x14008c122  lea     r8, aRepositoryLook; "Repository::LookupADSettingsStoragePath"
0x14008c129  lea     rdx, aCscchangemanag; "CscChangeManager"
0x14008c130  lea     rcx, [rbp+0D0h+var_D0]; this
0x14008c134  call    ??0ScopeTracker@Uev@@QEAA@PEB_W0@Z; Uev::ScopeTracker::ScopeTracker(wchar_t const *,wchar_t const *)
0x14008c139  nop
0x14008c13a  mov     [rbp+0D0h+var_E0], r15
0x14008c13e  xor     edx, edx; dwCoInit
0x14008c140  xor     ecx, ecx; pvReserved
0x14008c142  call    cs:__imp_CoInitializeEx
0x14008c148  mov     ebx, eax
0x14008c14a  mov     [rbp+0D0h+var_148], eax
0x14008c14d  xorps   xmm0, xmm0
0x14008c150  movups  [rsp+1D0h+var_1B0+8], xmm0
0x14008c155  xorps   xmm1, xmm1
0x14008c158  movdqu  [rsp+1D0h+var_1A0+8], xmm1
0x14008c15e  xor     r8d, r8d
0x14008c161  lea     rdx, Data
0x14008c168  lea     rcx, [rsp+1D0h+var_1B0+8]
0x14008c16d  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14008c172  lea     rax, [rsp+1D0h+var_1B0+8]
0x14008c177  cmp     rdi, rax
0x14008c17a  jz      short loc_14008C1A9
0x14008c17c  mov     rcx, rdi
0x14008c17f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008c184  movups  xmm0, [rsp+1D0h+var_1B0+8]
0x14008c189  movups  xmmword ptr [rdi], xmm0
0x14008c18c  movups  xmm1, [rsp+1D0h+var_1A0+8]
0x14008c191  movups  xmmword ptr [rdi+10h], xmm1
0x14008c195  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14008c19d  movdqu  [rsp+1D0h+var_1A0+8], xmm0
0x14008c1a3  mov     word ptr [rsp+1D0h+var_1B0+8], r15w
0x14008c1a9  lea     rcx, [rsp+1D0h+var_1B0+8]
0x14008c1ae  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008c1b3  xorps   xmm0, xmm0
0x14008c1b6  movups  [rsp+1D0h+var_190+8], xmm0
0x14008c1bb  xorps   xmm1, xmm1
0x14008c1be  movdqu  [rsp+1D0h+var_180+8], xmm1
0x14008c1c4  xor     r8d, r8d
0x14008c1c7  lea     rdx, Data
0x14008c1ce  lea     rcx, [rsp+1D0h+var_190+8]
0x14008c1d3  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14008c1d8  lea     rax, [rsp+1D0h+var_190+8]
0x14008c1dd  cmp     rsi, rax
0x14008c1e0  jz      short loc_14008C20F
0x14008c1e2  mov     rcx, rsi
0x14008c1e5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008c1ea  movups  xmm0, [rsp+1D0h+var_190+8]
0x14008c1ef  movups  xmmword ptr [rsi], xmm0
0x14008c1f2  movups  xmm1, [rsp+1D0h+var_180+8]
0x14008c1f7  movups  xmmword ptr [rsi+10h], xmm1
0x14008c1fb  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14008c203  movdqu  [rsp+1D0h+var_180+8], xmm0
0x14008c209  mov     word ptr [rsp+1D0h+var_190+8], r15w
0x14008c20f  lea     rcx, [rsp+1D0h+var_190+8]
0x14008c214  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008c219  mov     ecx, 80000000h
0x14008c21e  lea     eax, [rbx+rcx]
0x14008c221  test    ecx, eax
0x14008c223  jnz     loc_14008C310
0x14008c229  cmp     ebx, 80010106h
0x14008c22f  jz      loc_14008C310
0x14008c235  mov     r14d, ebx
0x14008c238  mov     dword ptr [rsp+1D0h+var_1B0], ebx
0x14008c23c  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x14008c241  mov     rax, [rax]
0x14008c244  test    byte ptr [rax+20h], 2
0x14008c248  jbe     loc_14008C3C0
0x14008c24e  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x14008c253  mov     rdi, rax
0x14008c256  lea     rdx, [rsp+1D0h+var_1B0]
0x14008c25b  lea     rcx, [rbp+0D0h+var_100]
0x14008c25f  call    ??$lexical_cast@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@J@boost@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBJ@Z; boost::lexical_cast<std::wstring,long>(long const &)
0x14008c264  nop
0x14008c265  mov     r9d, 3Eh ; '>'
0x14008c26b  lea     r8, aLookupadsettin; "LookupADSettingsStoragePath failed Coin"...
0x14008c272  xor     edx, edx
0x14008c274  mov     rcx, rax; Src
0x14008c277  call    ??$_Insert@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KQEB_W0@Z; std::wstring::_Insert<wchar_t>(unsigned __int64,wchar_t const * const,unsigned __int64)
0x14008c27c  movups  xmm6, xmmword ptr [rax]
0x14008c27f  movups  [rbp+0D0h+var_120], xmm6
0x14008c283  movups  xmm7, xmmword ptr [rax+10h]
0x14008c287  movups  [rbp+0D0h+var_110], xmm7
0x14008c28b  mov     [rax+10h], r15
0x14008c28f  mov     qword ptr [rax+18h], 7
0x14008c297  mov     [rax], r15w
0x14008c29b  xorps   xmm0, xmm0
0x14008c29e  movups  [rbp+0D0h+var_140], xmm0
0x14008c2a2  xorps   xmm1, xmm1
0x14008c2a5  movdqu  [rbp+0D0h+var_130], xmm1
0x14008c2aa  mov     r8d, 10h
0x14008c2b0  lea     rdx, aCscchangemanag; "CscChangeManager"
0x14008c2b7  lea     rcx, [rbp+0D0h+var_140]
0x14008c2bb  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14008c2c0  nop
0x14008c2c1  lea     r9, [rbp+0D0h+var_120]
0x14008c2c5  movq    rcx, xmm6
0x14008c2ca  psrldq  xmm7, 8
0x14008c2cf  movq    rax, xmm7
0x14008c2d4  cmp     rax, 7
0x14008c2d8  cmova   r9, rcx
0x14008c2dc  lea     r8, [rbp+0D0h+var_140]
0x14008c2e0  mov     edx, 2
0x14008c2e5  mov     rcx, [rdi]
0x14008c2e8  call    ?Write@LogImpl@Uev@@QEBAXW4UEV_LOG_LEVEL@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; Uev::LogImpl::Write(Uev::UEV_LOG_LEVEL,std::wstring const &,wchar_t const *)
0x14008c2ed  nop
0x14008c2ee  lea     rcx, [rbp+0D0h+var_140]
0x14008c2f2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008c2f7  nop
0x14008c2f8  lea     rcx, [rbp+0D0h+var_120]
0x14008c2fc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008c301  nop
0x14008c302  lea     rcx, [rbp+0D0h+var_100]
0x14008c306  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008c30b  jmp     loc_14008C3C0
0x14008c310  mov     rcx, qword ptr cs:?s_ADSMethods@Repository@Uev@@0V?$shared_ptr@VIADSMethods@Uev@@@std@@A; std::shared_ptr<Uev::IADSMethods> Uev::Repository::s_ADSMethods
0x14008c317  mov     rax, [rcx]
0x14008c31a  lea     rdx, [rbp+0D0h+var_E0]
0x14008c31e  mov     rax, [rax+8]
0x14008c322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008c327  mov     r14d, eax
0x14008c32a  test    eax, eax
0x14008c32c  js      loc_14008C3C8
0x14008c332  mov     rcx, [rbp+0D0h+var_E0]
0x14008c336  test    rcx, rcx
0x14008c339  jz      short loc_14008C340
0x14008c33b  mov     rdx, [rcx]
0x14008c33e  jmp     short loc_14008C343
0x14008c340  mov     rdx, r15
0x14008c343  xorps   xmm0, xmm0
0x14008c346  movups  [rsp+1D0h+var_170+8], xmm0
0x14008c34b  xorps   xmm1, xmm1
0x14008c34e  movdqu  xmmword ptr [rsp+1D0h+var_160+8], xmm1
0x14008c354  or      r8, 0FFFFFFFFFFFFFFFFh
0x14008c358  inc     r8
0x14008c35b  cmp     [rdx+r8*2], r15w
0x14008c360  jnz     short loc_14008C358
0x14008c362  lea     rcx, [rsp+1D0h+var_170+8]
0x14008c367  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14008c36c  lea     rax, [rsp+1D0h+var_170+8]
0x14008c371  cmp     rdi, rax
0x14008c374  jz      short loc_14008C3A3
0x14008c376  mov     rcx, rdi
0x14008c379  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008c37e  movups  xmm0, [rsp+1D0h+var_170+8]
0x14008c383  movups  xmmword ptr [rdi], xmm0
0x14008c386  movups  xmm1, xmmword ptr [rsp+1D0h+var_160+8]
0x14008c38b  movups  xmmword ptr [rdi+10h], xmm1
0x14008c38f  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14008c397  movdqu  xmmword ptr [rsp+1D0h+var_160+8], xmm0
0x14008c39d  mov     word ptr [rsp+1D0h+var_170+8], r15w
0x14008c3a3  lea     rcx, [rsp+1D0h+var_170+8]
0x14008c3a8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008c3ad  mov     rdx, rdi
0x14008c3b0  mov     rcx, rsi
0x14008c3b3  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14008c3b8  mov     rdx, rdi; struct boost::filesystem::path *
0x14008c3bb  call    ?ExpandRepositoryPath@Repository@Uev@@AEBA_NAEAVpath@filesystem@boost@@@Z; Uev::Repository::ExpandRepositoryPath(boost::filesystem::path &)
0x14008c3c0  test    r14d, r14d
0x14008c3c3  mov     dil, 1
0x14008c3c6  jns     short loc_14008C3CB
0x14008c3c8  mov     dil, r15b
0x14008c3cb  test    ebx, ebx
0x14008c3cd  js      short loc_14008C3D6
0x14008c3cf  call    cs:__imp_CoUninitialize
0x14008c3d5  nop
0x14008c3d6  lea     rcx, [rbp+0D0h+var_E0]; this
0x14008c3da  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14008c3df  nop
0x14008c3e0  lea     rcx, [rbp+0D0h+var_D0]; this
0x14008c3e4  call    ??1ScopeTracker@Uev@@UEAA@XZ; Uev::ScopeTracker::~ScopeTracker(void)
0x14008c3e9  mov     al, dil
0x14008c3ec  mov     rcx, [rbp+0D0h+var_50]
0x14008c3f3  xor     rcx, rsp; StackCookie
0x14008c3f6  call    __security_check_cookie
0x14008c3fb  lea     r11, [rsp+1D0h+var_20]
0x14008c403  mov     rbx, [r11+30h]
0x14008c407  movaps  xmm6, xmmword ptr [r11-10h]
0x14008c40c  movaps  xmm7, xmmword ptr [r11-20h]
0x14008c411  mov     rsp, r11
0x14008c414  pop     r15
0x14008c416  pop     r14
0x14008c418  pop     rdi
0x14008c419  pop     rsi
0x14008c41a  pop     rbp
0x14008c41b  retn
```
