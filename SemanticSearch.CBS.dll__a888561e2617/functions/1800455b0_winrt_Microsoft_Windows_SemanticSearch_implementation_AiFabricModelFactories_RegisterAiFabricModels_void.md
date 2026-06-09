# winrt::Microsoft::Windows::SemanticSearch::implementation::AiFabricModelFactories::RegisterAiFabricModels(void)

- ea: `0x1800455b0`
- end: `0x1800458d2`
- name: `?RegisterAiFabricModels@AiFabricModelFactories@implementation@SemanticSearch@Windows@Microsoft@winrt@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `802`
- prototype: `void **()`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800454f0`

## callees

- `0x180002bb0`
- `0x180008600`
- `0x180008820`
- `0x180008840`
- `0x180008920`
- `0x180009580`
- `0x1800455b0`
- `0x180045b00`
- `0x18004a450`
- `0x18004a500`
- `0x18004c070`
- `0x18004c8cc`
- `0x1800513bb`
- `0x18005e260`
- `0x18005e770`

## string_xrefs

- `0x180045677`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`

## pseudocode

```c
void **winrt::Microsoft::Windows::SemanticSearch::implementation::AiFabricModelFactories::RegisterAiFabricModels()
{
  _QWORD *v0; // rax
  int v1; // eax
  __int64 v2; // rcx
  _QWORD *v3; // rdi
  __int64 v4; // rax
  unsigned __int64 v5; // rbx
  _QWORD *v6; // rsi
  __int64 v7; // r15
  void **v8; // r13
  __int64 v9; // r12
  __int128 *v10; // r14
  __int64 v11; // rcx
  _QWORD *i; // rbx
  _QWORD *v14; // [rsp+38h] [rbp-31h] BYREF
  const char *v15; // [rsp+40h] [rbp-29h]
  __int128 v16; // [rsp+48h] [rbp-21h] BYREF
  __int64 v17; // [rsp+58h] [rbp-11h]
  __int64 v18; // [rsp+60h] [rbp-9h]
  void **v19; // [rsp+68h] [rbp-1h]
  __int64 *v20; // [rsp+70h] [rbp+7h]
  unsigned int v21; // [rsp+78h] [rbp+Fh] BYREF
  LPVOID pv; // [rsp+80h] [rbp+17h] BYREF
  _QWORD *v23; // [rsp+88h] [rbp+1Fh] BYREF

  v19 = &Src;
  v0 = operator new(0x18u);
  *v0 = 0;
  v0[1] = 0;
  v0[2] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::AiFabricModelFactoryRegistrar,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IModelFactoryRegistrar>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v0[1] = 1;
  *v0 = &winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::AiFabricModelFactoryRegistrar>::`vftable';
  v23 = v0 + 2;
  pv = &v23;
  v20 = &qword_180086B88;
  _InterlockedIncrement64(&qword_180086B88);
  if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticVectorSpaceModelRegistry,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticVectorSpaceModelRegistryStatics> )
  {
    v21 = 0;
    pv = 0;
    LODWORD(v14) = 1237;
    v15 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
          "Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    v1 = (*(__int64 (__fastcall **)(__int64, _QWORD *, unsigned int *, LPVOID *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticVectorSpaceModelRegistry,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticVectorSpaceModelRegistryStatics>
                                                                                + 48LL))(
           winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticVectorSpaceModelRegistry,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticVectorSpaceModelRegistryStatics>,
           v23,
           &v21,
           &pv);
    if ( v1 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v1, &v14);
    }
    v3 = pv;
    v14 = pv;
    v4 = v21;
    LODWORD(v15) = v21;
    _InterlockedDecrement64(&qword_180086B88);
  }
  else
  {
    _InterlockedDecrement64(&qword_180086B88);
    ___call_AEAV_lambda_1___1__RegisterModelFactories_SemanticVectorSpaceModelRegistry_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUIModelFactoryRegistrar_456789__Z____factory_cache_entry_USemanticVectorSpaceModelRegistry_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticVectorSpaceModelRegistryStatics_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__RegisterModelFactories_SemanticVectorSpaceModelRegistry_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUIModelFactoryRegistrar_6789Microsoft_2__Z__Z(
      0,
      (__int64)&v14,
      (_QWORD **)&pv);
    v4 = (unsigned int)v15;
    v3 = v14;
  }
  v16 = 0;
  v17 = 0;
  v5 = 7;
  v18 = 7;
  LOWORD(v16) = 0;
  v6 = &v3[v4];
  std::transform_reduce_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::RegisterEmbeddingModelFactoryResult___std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____std::plus_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t_______winrt::Microsoft::Windows::SemanticSearch::implementation::AiFabricModelFactories::RegisterAiFabricModels_::_2_::_lambda_1___(
    v2,
    v3,
    v6,
    &v16);
  v7 = xmmword_180086BF8;
  if ( (_QWORD)xmmword_180086BF8 )
  {
    if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - xmmword_180086BF8) < 0x30 )
      std::_Xlen_string();
    v8 = &Src;
    if ( *((_QWORD *)&xmmword_180086BF8 + 1) > 7u )
      v8 = (void **)Src;
    v16 = 0;
    v9 = xmmword_180086BF8 + 48;
    v10 = &v16;
    if ( (unsigned __int64)(xmmword_180086BF8 + 48) > 7 )
    {
      v5 = v9 | 7;
      if ( (v9 | 7uLL) <= 0x7FFFFFFFFFFFFFFELL )
      {
        if ( v5 < 0xA )
          v5 = 10;
        v11 = v5 + 1;
        if ( v5 + 1 > 0x7FFFFFFFFFFFFFFFLL )
          __scrt_throw_std_bad_array_new_length();
      }
      else
      {
        v5 = 0x7FFFFFFFFFFFFFFELL;
        v11 = 0x7FFFFFFFFFFFFFFFLL;
      }
      _mm_lfence();
      v10 = (__int128 *)std::_Allocate<16,std::_Default_allocate_traits>(2 * v11);
      *(_QWORD *)&v16 = v10;
    }
    v17 = v7 + 48;
    v18 = v5;
    *v10 = *(_OWORD *)L"Failed to register the following vector spaces:\n";
    v10[1] = *(_OWORD *)L"o register the following vector spaces:\n";
    v10[2] = *(_OWORD *)L"er the following vector spaces:\n";
    v10[3] = *(_OWORD *)L"ollowing vector spaces:\n";
    v10[4] = *(_OWORD *)L" vector spaces:\n";
    v10[5] = *(_OWORD *)L"spaces:\n";
    memmove(v10 + 6, v8, 2 * v7);
    *((_WORD *)v10 + v9) = 0;
    std::wstring::operator=(&Src, &v16);
    std::wstring::_Tidy_deallocate(&v16);
  }
  if ( v3 )
  {
    for ( i = v3; i != v6; ++i )
    {
      if ( *i )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(i);
    }
    CoTaskMemFree_0(v3);
  }
  if ( v23 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v23);
  return &Src;
}

```

## disassembly

```asm
0x1800455b0  mov     [rsp-8+arg_0], rbx
0x1800455b5  mov     [rsp-8+arg_8], rsi
0x1800455ba  mov     [rsp-8+arg_10], rdi
0x1800455bf  push    rbp
0x1800455c0  push    r12
0x1800455c2  push    r13
0x1800455c4  push    r14
0x1800455c6  push    r15
0x1800455c8  lea     rbp, [rsp-37h]
0x1800455cd  sub     rsp, 0A0h
0x1800455d4  mov     rax, cs:__security_cookie
0x1800455db  xor     rax, rsp
0x1800455de  mov     [rbp+57h+var_30], rax
0x1800455e2  mov     rax, [rbp+57h+var_58]
0x1800455e6  mov     [rbp+57h+var_58], rax
0x1800455ea  xor     esi, esi
0x1800455ec  mov     [rbp+57h+var_8C], esi
0x1800455ef  lea     r12, Src
0x1800455f6  mov     [rbp+57h+var_58], r12
0x1800455fa  mov     ecx, 18h; Size
0x1800455ff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045604  mov     [rax], rsi
0x180045607  mov     [rax+8], rsi
0x18004560b  lea     rcx, [rax+10h]
0x18004560f  lea     rdx, ??_7?$produce@UAiFabricModelFactoryRegistrar@implementation@SemanticSearch@Windows@Microsoft@winrt@@UIModelFactoryRegistrar@Compatibility@AiFabric@SemanticIndex@Asg@56@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::AiFabricModelFactoryRegistrar,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IModelFactoryRegistrar>::`vftable'
0x180045616  mov     [rcx], rdx
0x180045619  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180045620  mov     qword ptr [rax+8], 1
0x180045628  lea     rdx, ??_7?$heap_implements@UAiFabricModelFactoryRegistrar@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::AiFabricModelFactoryRegistrar>::`vftable'
0x18004562f  mov     [rax], rdx
0x180045632  mov     [rbp+57h+var_38], rcx
0x180045636  mov     [rbp+57h+var_8C], 2
0x18004563d  lea     rax, [rbp+57h+var_38]
0x180045641  mov     [rbp+57h+pv], rax
0x180045645  lea     rax, qword_180086B88
0x18004564c  mov     [rbp+57h+var_50], rax
0x180045650  lock inc cs:qword_180086B88
0x180045658  mov     ebx, 0Ah
0x18004565d  mov     rcx, cs:??$factory_cache_entry_v@USemanticVectorSpaceModelRegistry@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticVectorSpaceModelRegistryStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticVectorSpaceModelRegistry@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticVectorSpaceModelRegistryStatics@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticVectorSpaceModelRegistry,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticVectorSpaceModelRegistryStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticVectorSpaceModelRegistry,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticVectorSpaceModelRegistryStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticVectorSpaceModelRegistry,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticVectorSpaceModelRegistryStatics>
0x180045664  test    rcx, rcx
0x180045667  jz      short loc_1800456C1
0x180045669  mov     [rbp+57h+var_48], esi
0x18004566c  mov     [rbp+57h+pv], rsi
0x180045670  mov     dword ptr [rbp+57h+var_88], 4D5h
0x180045677  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18004567e  mov     [rbp+57h+var_80], rax
0x180045682  mov     rax, [rcx]
0x180045685  lea     r9, [rbp+57h+pv]
0x180045689  lea     r8, [rbp+57h+var_48]
0x18004568d  mov     rdx, [rbp+57h+var_38]
0x180045691  mov     rax, [rax+30h]
0x180045695  call    cs:__guard_dispatch_icall_fptr
0x18004569b  test    eax, eax
0x18004569d  js      loc_1800458C3
0x1800456a3  mov     rdi, [rbp+57h+pv]
0x1800456a7  mov     [rbp+57h+var_88], rdi
0x1800456ab  mov     eax, [rbp+57h+var_48]
0x1800456ae  mov     dword ptr [rbp+57h+var_80], eax
0x1800456b1  mov     r14d, 3Ah ; ':'
0x1800456b7  lock dec cs:qword_180086B88
0x1800456bf  jmp     short loc_1800456E0
0x1800456c1  lock dec cs:qword_180086B88
0x1800456c9  lea     r8, [rbp+57h+pv]
0x1800456cd  lea     rdx, [rbp+57h+var_88]
0x1800456d1  call    ??$call@AEAV_lambda_1_@?1??RegisterModelFactories@SemanticVectorSpaceModelRegistry@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUIModelFactoryRegistrar@456789@@Z@@?$factory_cache_entry@USemanticVectorSpaceModelRegistry@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticVectorSpaceModelRegistryStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??RegisterModelFactories@SemanticVectorSpaceModelRegistry@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUIModelFactoryRegistrar@6789Microsoft@2@@Z@@Z
0x1800456d6  mov     r14d, ebx
0x1800456d9  mov     eax, dword ptr [rbp+57h+var_80]
0x1800456dc  mov     rdi, [rbp+57h+var_88]
0x1800456e0  or      r14d, 4
0x1800456e4  mov     [rbp+57h+var_8C], r14d
0x1800456e8  xorps   xmm0, xmm0
0x1800456eb  movups  [rbp+57h+var_78], xmm0
0x1800456ef  mov     [rbp+57h+var_68], rsi
0x1800456f3  mov     ebx, 7
0x1800456f8  mov     [rbp+57h+var_60], rbx
0x1800456fc  mov     word ptr [rbp+57h+var_78], si
0x180045700  lea     rsi, [rdi+rax*8]
0x180045704  movzx   eax, [rbp+57h+var_90]
0x180045708  mov     [rsp+0C0h+var_98], al
0x18004570c  lea     r9, [rbp+57h+var_78]
0x180045710  mov     r8, rsi
0x180045713  mov     rdx, rdi
0x180045716  call    std__transform_reduce_winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__RegisterEmbeddingModelFactoryResult___std__basic_string_wchar_t_std__char_traits_wchar_t__std__allocator_wchar_t____std__plus_std__basic_string_wchar_t_std__char_traits_wchar_t__std__allocator_wchar_t_______winrt__Microsoft__Windows__SemanticSearch__implementation__AiFabricModelFactories__RegisterAiFabricModels____2____lambda_1___
0x18004571b  or      r14d, 1
0x18004571f  mov     [rbp+57h+var_8C], r14d
0x180045723  mov     r15, qword ptr cs:xmmword_180086BF8
0x18004572a  test    r15, r15
0x18004572d  jz      loc_180045825
0x180045733  mov     rcx, 7FFFFFFFFFFFFFFEh
0x18004573d  mov     rax, rcx
0x180045740  sub     rax, r15
0x180045743  cmp     rax, 30h ; '0'
0x180045747  jb      loc_1800458B7
0x18004574d  mov     r13, r12
0x180045750  cmp     qword ptr cs:xmmword_180086BF8+8, rbx
0x180045757  cmova   r13, qword ptr cs:Src
0x18004575f  xorps   xmm0, xmm0
0x180045762  movups  [rbp+57h+var_78], xmm0
0x180045766  lea     r12, [r15+30h]
0x18004576a  lea     r14, [rbp+57h+var_78]
0x18004576e  cmp     r12, rbx
0x180045771  jbe     short loc_1800457A2
0x180045773  mov     rbx, r12
0x180045776  or      rbx, 7
0x18004577a  cmp     rbx, rcx
0x18004577d  jbe     loc_180045892
0x180045783  mov     rbx, rcx
0x180045786  mov     rcx, 7FFFFFFFFFFFFFFFh
0x180045790  lfence
0x180045793  add     rcx, rcx
0x180045796  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18004579b  mov     r14, rax
0x18004579e  mov     qword ptr [rbp+57h+var_78], rax
0x1800457a2  mov     [rbp+57h+var_68], r12
0x1800457a6  mov     [rbp+57h+var_60], rbx
0x1800457aa  movaps  xmm0, xmmword ptr cs:aFailedToRegist; "Failed to register the following vector"...
0x1800457b1  movups  xmmword ptr [r14], xmm0
0x1800457b5  movaps  xmm1, xmmword ptr cs:aFailedToRegist+10h; "o register the following vector spaces:"...
0x1800457bc  movups  xmmword ptr [r14+10h], xmm1
0x1800457c1  movaps  xmm0, xmmword ptr cs:aFailedToRegist+20h; "er the following vector spaces:\n"
0x1800457c8  movups  xmmword ptr [r14+20h], xmm0
0x1800457cd  movaps  xmm1, xmmword ptr cs:aFailedToRegist+30h; "ollowing vector spaces:\n"
0x1800457d4  movups  xmmword ptr [r14+30h], xmm1
0x1800457d9  movaps  xmm0, xmmword ptr cs:aFailedToRegist+40h; " vector spaces:\n"
0x1800457e0  movups  xmmword ptr [r14+40h], xmm0
0x1800457e5  movaps  xmm1, xmmword ptr cs:aFailedToRegist+50h; "spaces:\n"
0x1800457ec  movups  xmmword ptr [r14+50h], xmm1
0x1800457f1  lea     r8, [r15+r15]; Size
0x1800457f5  lea     rcx, [r14+60h]; void *
0x1800457f9  mov     rdx, r13; Src
0x1800457fc  call    memmove
0x180045801  xor     eax, eax
0x180045803  mov     [r14+r12*2], ax
0x180045808  lea     rdx, [rbp+57h+var_78]
0x18004580c  lea     r12, Src
0x180045813  mov     rcx, r12
0x180045816  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004581b  lea     rcx, [rbp+57h+var_78]
0x18004581f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180045824  nop
0x180045825  test    rdi, rdi
0x180045828  jz      short loc_180045852
0x18004582a  mov     rbx, rdi
0x18004582d  cmp     rdi, rsi
0x180045830  jz      short loc_180045849
0x180045832  cmp     qword ptr [rbx], 0
0x180045836  jz      short loc_180045840
0x180045838  mov     rcx, rbx
0x18004583b  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180045840  add     rbx, 8
0x180045844  cmp     rbx, rsi
0x180045847  jnz     short loc_180045832
0x180045849  mov     rcx, rdi; pv
0x18004584c  call    CoTaskMemFree_0
0x180045851  nop
0x180045852  cmp     [rbp+57h+var_38], 0
0x180045857  jz      short loc_180045862
0x180045859  lea     rcx, [rbp+57h+var_38]
0x18004585d  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180045862  mov     rax, r12
0x180045865  mov     rcx, [rbp+57h+var_30]
0x180045869  xor     rcx, rsp; StackCookie
0x18004586c  call    __security_check_cookie
0x180045871  lea     r11, [rsp+0C0h+var_20]
0x180045879  mov     rbx, [r11+30h]
0x18004587d  mov     rsi, [r11+38h]
0x180045881  mov     rdi, [r11+40h]
0x180045885  mov     rsp, r11
0x180045888  pop     r15
0x18004588a  pop     r14
0x18004588c  pop     r13
0x18004588e  pop     r12
0x180045890  pop     rbp
0x180045891  retn
0x180045892  cmp     rbx, 0Ah
0x180045896  mov     eax, 0Ah
0x18004589b  cmovb   rbx, rax
0x18004589f  lea     rcx, [rbx+1]
0x1800458a3  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800458ad  cmp     rcx, rax
0x1800458b0  ja      short loc_1800458BD
0x1800458b2  jmp     loc_180045790
0x1800458b7  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x1800458bd  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x1800458c3  lfence
0x1800458c6  lea     rdx, [rbp+57h+var_88]
0x1800458ca  mov     ecx, eax
0x1800458cc  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
