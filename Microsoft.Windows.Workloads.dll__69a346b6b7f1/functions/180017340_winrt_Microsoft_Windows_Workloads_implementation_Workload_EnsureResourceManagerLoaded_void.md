# winrt::Microsoft::Windows::Workloads::implementation::Workload::EnsureResourceManagerLoaded(void)

- ea: `0x180017340`
- end: `0x180017680`
- name: `?EnsureResourceManagerLoaded@Workload@implementation@Workloads@Windows@Microsoft@winrt@@AEAAXXZ`
- size: `832`
- prototype: `void __fastcall(winrt::Microsoft::Windows::Workloads::implementation::Workload *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180017910`

## callees

- `0x1800027d0`
- `0x1800029f0`
- `0x1800040a0`
- `0x180004810`
- `0x180013330`
- `0x180017340`
- `0x18001b040`
- `0x18001b430`
- `0x18001b800`
- `0x18001bbb0`
- `0x18001c8c0`
- `0x180034ef0`
- `0x18003bed0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180017570`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180017570`

## string_xrefs

- `0x18001766e`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.2.162\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
void __fastcall winrt::Microsoft::Windows::Workloads::implementation::Workload::EnsureResourceManagerLoaded(
        winrt::Microsoft::Windows::Workloads::implementation::Workload *this)
{
  char v1; // bl
  __m128i si128; // xmm6
  int v3; // eax
  const wchar_t *v4; // r8
  std::filesystem *v5; // rdi
  const wchar_t *v6; // rbx
  const wchar_t *root_name_end; // rax
  const wchar_t *v8; // rcx
  __int16 v9; // dx
  const wchar_t *v10; // rcx
  __int16 v11; // dx
  _QWORD *v12; // rdx
  __int64 v13; // rcx
  int v14; // eax
  __int64 *v15; // rbx
  int v16[4]; // [rsp+28h] [rbp-E0h] BYREF
  __m128i v17; // [rsp+38h] [rbp-D0h]
  __int128 v18; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+58h] [rbp-B0h]
  _BYTE v20[40]; // [rsp+60h] [rbp-A8h] BYREF
  char v21[8]; // [rsp+88h] [rbp-80h] BYREF
  _QWORD v22[14]; // [rsp+90h] [rbp-78h] BYREF
  __int64 *v23; // [rsp+100h] [rbp-8h] BYREF
  int *v24; // [rsp+108h] [rbp+0h] BYREF
  __int64 *v25; // [rsp+110h] [rbp+8h] BYREF
  std::filesystem *v26[2]; // [rsp+118h] [rbp+10h] BYREF
  __m128i v27; // [rsp+128h] [rbp+20h]
  _QWORD Src[4]; // [rsp+138h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+180h] [rbp+78h]

  v23 = 0;
  v1 = winrt::Windows::Foundation::operator==(
         &winrt::Microsoft::Windows::Workloads::implementation::Workload::s_resourceManager,
         &v23);
  if ( v23 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v23);
  if ( v1 )
  {
    *(_OWORD *)v16 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v17 = si128;
    LOWORD(v16[0]) = 0;
    LODWORD(v23) = 1;
    v24 = (int *)0x180000000LL;
    v25 = 0;
    v22[0] = &wistd::__function::__func<_lambda_2d860dc2582dcbaaba41b7ebab4cc740_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::`vftable';
    v22[1] = &v25;
    v22[2] = &v24;
    v22[13] = v22;
    v3 = wil::AdaptFixedSizeToAllocatedResult<std::wstring,128>((__int64)v16, (__int64)v21);
    if ( v3 < 0 )
    {
      _mm_lfence();
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x26C,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.2.162\\inc\\wil\\opensource\\wil\\win32_helpers.h",
        (const char *)(unsigned int)v3,
        v16[0]);
    }
    *(_OWORD *)v26 = *(_OWORD *)v16;
    v27 = v17;
    v17 = si128;
    LOWORD(v16[0]) = 0;
    std::wstring::_Tidy_deallocate((__int64)v16);
    memset(&v20[8], 0, 32);
    std::wstring::_Construct<1,wchar_t const *>(&v20[8], L"Microsoft.Windows.Workloads.pri", 0x1Fu);
    v5 = (std::filesystem *)v26;
    if ( v27.m128i_i64[1] > 7uLL )
      v5 = v26[0];
    v6 = (const wchar_t *)((char *)v5 + 2 * v27.m128i_i64[0]);
    root_name_end = std::filesystem::_Find_root_name_end(v5, v6, v4);
    if ( root_name_end != v6 )
    {
      do
      {
        if ( *root_name_end != 92 && *root_name_end != 47 )
          break;
        ++root_name_end;
      }
      while ( root_name_end != v6 );
      if ( root_name_end != v6 )
      {
        while ( 1 )
        {
          v8 = v6 - 1;
          v9 = *(v6 - 1);
          if ( v9 == 92 || v9 == 47 )
            break;
          --v6;
          if ( root_name_end == v8 )
            goto LABEL_20;
        }
        if ( root_name_end != v6 )
        {
          do
          {
            v10 = v6 - 1;
            v11 = *(v6 - 1);
            if ( v11 != 92 && v11 != 47 )
              break;
            --v6;
          }
          while ( root_name_end != v10 );
        }
      }
    }
LABEL_20:
    v18 = 0;
    v19 = 0;
    *(_QWORD *)v20 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v18, v5, ((char *)v6 - (char *)v5) >> 1);
    std::filesystem::operator/((std::filesystem *)Src, &v18, &v20[8]);
    std::wstring::_Tidy_deallocate((__int64)&v18);
    std::wstring::_Tidy_deallocate((__int64)&v20[8]);
    v12 = Src;
    if ( Src[3] > 7u )
      v12 = (_QWORD *)Src[0];
    v13 = -1;
    do
      ++v13;
    while ( *((_WORD *)v12 + v13) );
    if ( (_DWORD)v13 )
    {
      if ( *((_WORD *)v12 + (unsigned int)v13) )
        abort();
      v16[2] = 1;
      v16[3] = v13;
      v17.m128i_i64[1] = (__int64)v12;
      *(_QWORD *)v16 = &v16[2];
    }
    else
    {
      *(_QWORD *)v16 = 0;
    }
    v24 = v16;
    v25 = &qword_180059F08;
    _InterlockedIncrement64(&qword_180059F08);
    if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::ApplicationModel::Resources::ResourceManager,winrt::Microsoft::Windows::ApplicationModel::Resources::IResourceManagerFactory> )
    {
      v23 = 0;
      v14 = (*(__int64 (__fastcall **)(__int64, int *, __int64 **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::ApplicationModel::Resources::ResourceManager,winrt::Microsoft::Windows::ApplicationModel::Resources::IResourceManagerFactory>
                                                                  + 48LL))(
              winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::ApplicationModel::Resources::ResourceManager,winrt::Microsoft::Windows::ApplicationModel::Resources::IResourceManagerFactory>,
              *(int **)v16,
              &v23);
      if ( v14 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v14);
      }
      v15 = v23;
      _InterlockedDecrement64(&qword_180059F08);
    }
    else
    {
      _InterlockedDecrement64(&qword_180059F08);
      winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::ApplicationModel::Resources::ResourceManager,winrt::Microsoft::Windows::ApplicationModel::Resources::IResourceManagerFactory>::call<_lambda_ab86e113159967ccfcd807310fe3d049_ &>(
        0,
        &v25,
        (_QWORD **)&v24);
      v15 = v25;
    }
    if ( winrt::Microsoft::Windows::Workloads::implementation::Workload::s_resourceManager )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&winrt::Microsoft::Windows::Workloads::implementation::Workload::s_resourceManager);
    winrt::Microsoft::Windows::Workloads::implementation::Workload::s_resourceManager = v15;
    std::wstring::_Tidy_deallocate((__int64)Src);
    std::wstring::_Tidy_deallocate((__int64)v26);
  }
}

```

## disassembly

```asm
0x180017340  mov     rax, rsp
0x180017343  mov     [rax+8], rbx
0x180017347  mov     [rax+10h], rsi
0x18001734b  mov     [rax+18h], rdi
0x18001734f  push    rbp
0x180017350  lea     rbp, [rax-78h]
0x180017354  sub     rsp, 170h
0x18001735b  movaps  xmmword ptr [rax-18h], xmm6
0x18001735f  mov     rax, cs:__security_cookie
0x180017366  xor     rax, rsp
0x180017369  mov     [rbp+70h+var_20], rax
0x18001736d  xor     esi, esi
0x18001736f  mov     dword ptr [rbp+70h+var_78], esi
0x180017372  mov     [rbp+70h+var_78], rsi
0x180017376  lea     rdx, [rbp+70h+var_78]
0x18001737a  lea     rcx, ?s_resourceManager@Workload@implementation@Workloads@Windows@Microsoft@winrt@@0UResourceManager@Resources@ApplicationModel@456@A; winrt::Microsoft::Windows::ApplicationModel::Resources::ResourceManager winrt::Microsoft::Windows::Workloads::implementation::Workload::s_resourceManager
0x180017381  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180017386  movzx   ebx, al
0x180017389  cmp     [rbp+70h+var_78], rsi
0x18001738d  jz      short loc_180017398
0x18001738f  lea     rcx, [rbp+70h+var_78]
0x180017393  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180017398  test    bl, bl
0x18001739a  jz      loc_180017633
0x1800173a0  xorps   xmm0, xmm0
0x1800173a3  movups  xmmword ptr [rsp+170h+var_158+8], xmm0
0x1800173a8  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800173b0  movdqu  [rsp+170h+var_148+8], xmm6
0x1800173b6  mov     word ptr [rsp+170h+var_158+8], si; int
0x1800173bb  mov     dword ptr [rbp+70h+var_78], 1
0x1800173c2  lea     rax, cs:180000000h
0x1800173c9  mov     [rbp+70h+var_70], rax
0x1800173cd  mov     [rbp+70h+var_68], rsi
0x1800173d1  lea     rax, ??_7?$__func@V_lambda_2d860dc2582dcbaaba41b7ebab4cc740_@@$$A6AJPEA_W_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_2d860dc2582dcbaaba41b7ebab4cc740_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x1800173d8  mov     [rbp+70h+var_E8], rax
0x1800173dc  lea     rax, [rbp+70h+var_68]
0x1800173e0  mov     [rbp+70h+var_E0], rax
0x1800173e4  lea     rax, [rbp+70h+var_70]
0x1800173e8  mov     [rbp+70h+var_D8], rax
0x1800173ec  lea     rax, [rbp+70h+var_E8]
0x1800173f0  mov     [rbp+70h+var_80], rax
0x1800173f4  lea     rdx, [rbp+70h+var_F0]
0x1800173f8  lea     rcx, [rsp+170h+var_158+8]
0x1800173fd  call    ??$AdaptFixedSizeToAllocatedResult@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0IA@@wil@@YAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<std::wstring,128>(std::wstring &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)
0x180017402  mov     rcx, [rbp+78h]; this
0x180017406  test    eax, eax
0x180017408  js      loc_180017668
0x18001740e  movups  xmm0, xmmword ptr [rsp+170h+var_158+8]
0x180017413  movups  xmmword ptr [rbp+70h+var_60], xmm0
0x180017417  movups  xmm1, [rsp+170h+var_148+8]
0x18001741c  movups  [rbp+70h+var_50], xmm1
0x180017420  movdqu  [rsp+170h+var_148+8], xmm6
0x180017426  mov     word ptr [rsp+170h+var_158+8], si
0x18001742b  lea     rcx, [rsp+170h+var_158+8]
0x180017430  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017435  xorps   xmm0, xmm0
0x180017438  movups  xmmword ptr [rsp+170h+var_118+8], xmm0
0x18001743d  mov     [rsp+170h+var_100], rsi
0x180017442  mov     [rsp+170h+var_F8], rsi
0x180017447  mov     r8d, 1Fh
0x18001744d  lea     rdx, aMicrosoftWindo_14; "Microsoft.Windows.Workloads.pri"
0x180017454  lea     rcx, [rsp+170h+var_118+8]
0x180017459  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001745e  nop
0x18001745f  lea     rdi, [rbp+70h+var_60]
0x180017463  cmp     qword ptr [rbp+70h+var_50+8], 7
0x180017468  cmova   rdi, [rbp+70h+var_60]
0x18001746d  mov     rax, qword ptr [rbp+70h+var_50]
0x180017471  lea     rbx, [rdi+rax*2]
0x180017475  mov     rdx, rbx; wchar_t *
0x180017478  mov     rcx, rdi; this
0x18001747b  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x180017480  cmp     rax, rbx
0x180017483  jz      short loc_1800174EB
0x180017485  movzx   ecx, word ptr [rax]
0x180017488  cmp     cx, 5Ch ; '\'
0x18001748c  jz      short loc_180017494
0x18001748e  cmp     cx, 2Fh ; '/'
0x180017492  jnz     short loc_18001749D
0x180017494  add     rax, 2
0x180017498  cmp     rax, rbx
0x18001749b  jnz     short loc_180017485
0x18001749d  cmp     rax, rbx
0x1800174a0  jz      short loc_1800174EB
0x1800174a2  lea     rcx, [rbx-2]
0x1800174a6  movzx   edx, word ptr [rcx]
0x1800174a9  cmp     dx, 5Ch ; '\'
0x1800174ad  jz      short loc_1800174BF
0x1800174af  cmp     dx, 2Fh ; '/'
0x1800174b3  jz      short loc_1800174BF
0x1800174b5  mov     rbx, rcx
0x1800174b8  cmp     rax, rcx
0x1800174bb  jnz     short loc_1800174A2
0x1800174bd  jmp     short loc_1800174EB
0x1800174bf  cmp     rax, rbx
0x1800174c2  jz      short loc_1800174EB
0x1800174c4  nop     dword ptr [rax+00h]
0x1800174c8  nop     dword ptr [rax+rax+00000000h]
0x1800174d0  lea     rcx, [rbx-2]
0x1800174d4  movzx   edx, word ptr [rcx]
0x1800174d7  cmp     dx, 5Ch ; '\'
0x1800174db  jz      short loc_1800174E3
0x1800174dd  cmp     dx, 2Fh ; '/'
0x1800174e1  jnz     short loc_1800174EB
0x1800174e3  mov     rbx, rcx
0x1800174e6  cmp     rax, rcx
0x1800174e9  jnz     short loc_1800174D0
0x1800174eb  sub     rbx, rdi
0x1800174ee  sar     rbx, 1
0x1800174f1  xorps   xmm0, xmm0
0x1800174f4  movups  xmmword ptr [rsp+170h+var_138+8], xmm0
0x1800174f9  mov     [rsp+170h+var_120], rsi
0x1800174fe  mov     qword ptr [rsp+170h+var_118], rsi
0x180017503  mov     r8, rbx
0x180017506  mov     rdx, rdi
0x180017509  lea     rcx, [rsp+170h+var_138+8]
0x18001750e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180017513  nop
0x180017514  lea     r8, [rsp+170h+var_118+8]; void *
0x180017519  lea     rdx, [rsp+170h+var_138+8]; void *
0x18001751e  lea     rcx, [rbp+70h+Src]; Src
0x180017522  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180017527  nop
0x180017528  lea     rcx, [rsp+170h+var_138+8]
0x18001752d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017532  nop
0x180017533  lea     rcx, [rsp+170h+var_118+8]
0x180017538  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001753d  lea     rdx, [rbp+70h+Src]
0x180017541  cmp     [rbp+70h+var_28], 7
0x180017546  cmova   rdx, [rbp+70h+Src]
0x18001754b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180017552  inc     rcx
0x180017555  cmp     word ptr [rdx+rcx*2], 0
0x18001755a  jnz     short loc_180017552
0x18001755c  test    ecx, ecx
0x18001755e  jnz     short loc_180017567
0x180017560  mov     qword ptr [rsp+170h+var_158+8], rsi
0x180017565  jmp     short loc_180017592
0x180017567  mov     eax, ecx
0x180017569  cmp     word ptr [rdx+rax*2], 0
0x18001756e  jz      short loc_180017577
0x180017570  call    cs:__imp_abort
0x180017577  mov     dword ptr [rsp+170h+var_148], 1
0x18001757f  mov     dword ptr [rsp+170h+var_148+4], ecx
0x180017583  mov     qword ptr [rsp+170h+var_138], rdx
0x180017588  lea     rax, [rsp+170h+var_148]
0x18001758d  mov     qword ptr [rsp+170h+var_158+8], rax
0x180017592  lea     rax, [rsp+170h+var_158+8]
0x180017597  mov     [rbp+70h+var_70], rax
0x18001759b  lea     rax, qword_180059F08
0x1800175a2  mov     [rbp+70h+var_68], rax
0x1800175a6  lock inc cs:qword_180059F08
0x1800175ae  mov     rcx, cs:??$factory_cache_entry_v@UResourceManager@Resources@ApplicationModel@Windows@Microsoft@winrt@@UIResourceManagerFactory@23456@@impl@winrt@@3U?$factory_cache_entry@UResourceManager@Resources@ApplicationModel@Windows@Microsoft@winrt@@UIResourceManagerFactory@23456@@12@A; factory_cache_entry<winrt::Microsoft::Windows::ApplicationModel::Resources::ResourceManager,winrt::Microsoft::Windows::ApplicationModel::Resources::IResourceManagerFactory>::winrt::factory_cache_entry<winrt::Microsoft::Windows::ApplicationModel::Resources::ResourceManager,winrt::Microsoft::Windows::ApplicationModel::Resources::IResourceManagerFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::ApplicationModel::Resources::ResourceManager,winrt::Microsoft::Windows::ApplicationModel::Resources::IResourceManagerFactory>
0x1800175b5  test    rcx, rcx
0x1800175b8  jz      short loc_1800175EA
0x1800175ba  mov     [rbp+70h+var_78], rsi
0x1800175be  mov     rax, [rcx]
0x1800175c1  lea     r8, [rbp+70h+var_78]
0x1800175c5  mov     rdx, qword ptr [rsp+170h+var_158+8]
0x1800175ca  mov     rax, [rax+30h]
0x1800175ce  call    cs:__guard_dispatch_icall_fptr
0x1800175d4  test    eax, eax
0x1800175d6  js      loc_18001765D
0x1800175dc  mov     rbx, [rbp+70h+var_78]
0x1800175e0  lock dec cs:qword_180059F08
0x1800175e8  jmp     short loc_180017603
0x1800175ea  lock dec cs:qword_180059F08
0x1800175f2  lea     r8, [rbp+70h+var_70]
0x1800175f6  lea     rdx, [rbp+70h+var_68]
0x1800175fa  call    ??$call@AEAV_lambda_ab86e113159967ccfcd807310fe3d049_@@@?$factory_cache_entry@UResourceManager@Resources@ApplicationModel@Windows@Microsoft@winrt@@UIResourceManagerFactory@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_ab86e113159967ccfcd807310fe3d049_@@@Z
0x1800175ff  mov     rbx, [rbp+70h+var_68]
0x180017603  cmp     cs:?s_resourceManager@Workload@implementation@Workloads@Windows@Microsoft@winrt@@0UResourceManager@Resources@ApplicationModel@456@A, 0; winrt::Microsoft::Windows::ApplicationModel::Resources::ResourceManager winrt::Microsoft::Windows::Workloads::implementation::Workload::s_resourceManager
0x18001760b  jz      short loc_180017619
0x18001760d  lea     rcx, ?s_resourceManager@Workload@implementation@Workloads@Windows@Microsoft@winrt@@0UResourceManager@Resources@ApplicationModel@456@A; winrt::Microsoft::Windows::ApplicationModel::Resources::ResourceManager winrt::Microsoft::Windows::Workloads::implementation::Workload::s_resourceManager
0x180017614  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180017619  mov     cs:?s_resourceManager@Workload@implementation@Workloads@Windows@Microsoft@winrt@@0UResourceManager@Resources@ApplicationModel@456@A, rbx; winrt::Microsoft::Windows::ApplicationModel::Resources::ResourceManager winrt::Microsoft::Windows::Workloads::implementation::Workload::s_resourceManager
0x180017620  lea     rcx, [rbp+70h+Src]
0x180017624  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017629  nop
0x18001762a  lea     rcx, [rbp+70h+var_60]
0x18001762e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017633  mov     rcx, [rbp+70h+var_20]
0x180017637  xor     rcx, rsp; StackCookie
0x18001763a  call    __security_check_cookie
0x18001763f  lea     r11, [rsp+170h+var_s0]
0x180017647  mov     rbx, [r11+10h]
0x18001764b  mov     rsi, [r11+18h]
0x18001764f  mov     rdi, [r11+20h]
0x180017653  movaps  xmm6, xmmword ptr [r11-10h]
0x180017658  mov     rsp, r11
0x18001765b  pop     rbp
0x18001765c  retn
0x18001765d  lfence
0x180017660  mov     ecx, eax
0x180017662  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x180017668  lfence
0x18001766b  mov     r9d, eax; char *
0x18001766e  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180017675  mov     edx, 26Ch; void *
0x18001767a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
