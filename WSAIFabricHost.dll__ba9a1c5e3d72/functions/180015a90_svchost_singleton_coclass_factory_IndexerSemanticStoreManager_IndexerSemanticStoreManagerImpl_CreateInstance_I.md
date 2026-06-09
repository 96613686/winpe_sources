# svchost_singleton_coclass_factory<IndexerSemanticStoreManager,IndexerSemanticStoreManagerImpl>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180015a90`
- end: `0x180015d08`
- name: `?CreateInstance@?$svchost_singleton_coclass_factory@VIndexerSemanticStoreManager@@UIndexerSemanticStoreManagerImpl@@@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `632`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006608`
- `0x180007f4e`
- `0x18000b064`
- `0x180012ba4`
- `0x180015a90`
- `0x180015f90`
- `0x180018b14`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180015aed`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180015aed`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180015b1f`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180015b1f`

## string_xrefs

- `0x180015ab9`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportservice.cpp`
- `0x180015b86`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportservice.cpp`
- `0x180015be3`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportservice.cpp`
- `0x180015c42`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportservice.cpp`
- `0x180015ca9`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportservice.cpp`
- `0x180015ce0`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportservice.cpp`

## pseudocode

```c
__int64 __fastcall svchost_singleton_coclass_factory<IndexerSemanticStoreManager,IndexerSemanticStoreManagerImpl>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  unsigned int v15; // ebx
  __int64 (__fastcall ***v16)(_QWORD, __int64, _QWORD *); // rbx
  int v17; // eax
  unsigned int v18; // ebx
  IID v19; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  WINBOOL fPending; // [rsp+68h] [rbp+10h] BYREF

  *a4 = 0;
  if ( a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportservice.cpp",
      (const char *)0x80040110LL,
      v19.Data1);
    return 2147746064LL;
  }
  fPending = 0;
  if ( !__std_init_once_begin_initialize(&g_singletonInit, 0, &fPending, 0) )
    __fastfail(5u);
  if ( fPending )
  {
    *(_QWORD *)&v19.Data1 = &g_singletonInit;
    *(_QWORD *)v19.Data4 = 4;
    std::invoke<_lambda_b88f0c3dac949a4d977743fd3cbabbf1_>(v7);
    if ( !InitOnceComplete(&g_singletonInit, 0, 0) )
      _std_init_once_link_alternate_names_and_abort(v9, v8);
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl'::`2'::impl) )
    goto LABEL_29;
  if ( !memcmp_0(
          &g_indexerSemanticSearchServicesGuid,
          &svchost_singleton_coclass_factory<IndexerSemanticStoreManager,IndexerSemanticStoreManagerImpl>::c_coclassGuid,
          0x10u) )
  {
    v10 = (**(__int64 (__fastcall ***)(IndexerSemanticSearchServicesImpl *, __int64, _QWORD *))g_singletonIndexerSemanticSearchServices)(
            g_singletonIndexerSemanticSearchServices,
            a3,
            a4);
    v11 = v10;
    if ( v10 >= 0 )
      return 0;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportservice.cpp",
      (const char *)(unsigned int)v10,
      v19.Data1);
    return v11;
  }
  if ( !memcmp_0(
          &g_indexerSemanticStoreManagerGuid,
          &svchost_singleton_coclass_factory<IndexerSemanticStoreManager,IndexerSemanticStoreManagerImpl>::c_coclassGuid,
          0x10u) )
  {
    v12 = (**(__int64 (__fastcall ***)(__int64, __int64, _QWORD *))g_singletonIndexerSemanticStoreManager)(
            g_singletonIndexerSemanticStoreManager,
            a3,
            a4);
    v13 = v12;
    if ( v12 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x64,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportservice.cpp",
        (const char *)(unsigned int)v12,
        v19.Data1);
      return v13;
    }
  }
  else
  {
LABEL_29:
    if ( !memcmp_0(
            &g_sessionManagerBrokerGuid,
            &svchost_singleton_coclass_factory<IndexerSemanticStoreManager,IndexerSemanticStoreManagerImpl>::c_coclassGuid,
            0x10u) )
    {
      v14 = (**(__int64 (__fastcall ***)(__int64, __int64, _QWORD *))g_singletonSessionManagerBroker)(
              g_singletonSessionManagerBroker,
              a3,
              a4);
      v15 = v14;
      if ( v14 >= 0 )
      {
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6D,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportservice.cpp",
          (const char *)(unsigned int)v14,
          v19.Data1);
        return v15;
      }
    }
    else
    {
      v16 = (__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *))g_singletonAIFabricResourceManager;
      if ( g_singletonAIFabricResourceManager
        && !memcmp_0(
              &g_AIFabricResourceManagerGuid,
              &svchost_singleton_coclass_factory<IndexerSemanticStoreManager,IndexerSemanticStoreManagerImpl>::c_coclassGuid,
              0x10u) )
      {
        v17 = (**v16)(v16, a3, a4);
        v18 = v17;
        if ( v17 >= 0 )
        {
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x76,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportservice.cpp",
            (const char *)(unsigned int)v17,
            v19.Data1);
          return v18;
        }
      }
      else
      {
        v19 = svchost_singleton_coclass_factory<IndexerSemanticStoreManager,IndexerSemanticStoreManagerImpl>::c_coclassGuid;
        SearchIndexerTrace::Error(
          (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportservice.cpp",
          (const wchar_t *)0x7C,
          (unsigned int)L"WSAIFabricSvc class not available: {0}",
          (const wchar_t *)&v19);
        return 2147746065LL;
      }
    }
  }
}

```

## disassembly

```asm
0x180015a90  push    rbx
0x180015a92  push    rsi
0x180015a93  push    rdi
0x180015a94  push    r14
0x180015a96  sub     rsp, 38h
0x180015a9a  mov     rsi, r9
0x180015a9d  mov     r14, r8
0x180015aa0  mov     qword ptr [r9], 0
0x180015aa7  test    rdx, rdx
0x180015aaa  jz      short loc_180015AD1
0x180015aac  mov     rcx, [rsp+58h]; this
0x180015ab1  mov     ebx, 80040110h
0x180015ab6  mov     r9d, ebx; char *
0x180015ab9  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x180015ac0  mov     edx, 3Dh ; '='; void *
0x180015ac5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015aca  mov     eax, ebx
0x180015acc  jmp     loc_180015CF7
0x180015ad1  mov     [rsp+58h+fPending], 0
0x180015ad9  xor     r9d, r9d; lpContext
0x180015adc  lea     r8, [rsp+58h+fPending]; fPending
0x180015ae1  xor     edx, edx; dwFlags
0x180015ae3  lea     rbx, ?g_singletonInit@@3Uonce_flag@std@@A; std::once_flag g_singletonInit
0x180015aea  mov     rcx, rbx; lpInitOnce
0x180015aed  call    cs:__imp___std_init_once_begin_initialize
0x180015af3  test    eax, eax
0x180015af5  jnz     short loc_180015AFC
0x180015af7  lea     ecx, [rax+5]
0x180015afa  int     29h; Win8: RtlFailFast(ecx)
0x180015afc  cmp     [rsp+58h+fPending], 0
0x180015b01  jz      short loc_180015B2D
0x180015b03  mov     qword ptr [rsp+58h+var_38.Data1], rbx; int
0x180015b08  mov     qword ptr [rsp+58h+var_38.Data4], 4
0x180015b11  call    ??$invoke@V_lambda_b88f0c3dac949a4d977743fd3cbabbf1_@@@std@@YAX$$QEAV_lambda_b88f0c3dac949a4d977743fd3cbabbf1_@@@Z; std::invoke<_lambda_b88f0c3dac949a4d977743fd3cbabbf1_>(_lambda_b88f0c3dac949a4d977743fd3cbabbf1_ &&)
0x180015b16  nop
0x180015b17  xor     r8d, r8d; lpContext
0x180015b1a  xor     edx, edx; dwFlags
0x180015b1c  mov     rcx, rbx; lpInitOnce
0x180015b1f  call    cs:__imp_InitOnceComplete
0x180015b25  test    eax, eax
0x180015b27  jz      loc_180015D01
0x180015b2d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_47942714@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714> `wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl(void)'::`2'::impl
0x180015b34  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(void)
0x180015b39  mov     edi, 10h
0x180015b3e  test    al, al
0x180015b40  jz      loc_180015C02
0x180015b46  mov     r8d, edi; Size
0x180015b49  lea     rdx, ?c_coclassGuid@?$svchost_singleton_coclass_factory@VIndexerSemanticStoreManager@@UIndexerSemanticStoreManagerImpl@@@@2Uguid@winrt@@B; Buf2
0x180015b50  lea     rcx, ?g_indexerSemanticSearchServicesGuid@@3Uguid@winrt@@A; Buf1
0x180015b57  call    memcmp_0
0x180015b5c  test    eax, eax
0x180015b5e  jnz     short loc_180015BA3
0x180015b60  mov     rcx, cs:?g_singletonIndexerSemanticSearchServices@@3U?$com_ptr@UIndexerSemanticSearchServicesImpl@@@winrt@@A; winrt::com_ptr<IndexerSemanticSearchServicesImpl> g_singletonIndexerSemanticSearchServices
0x180015b67  mov     rax, [rcx]
0x180015b6a  mov     r8, rsi
0x180015b6d  mov     rdx, r14
0x180015b70  mov     rax, [rax]
0x180015b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b78  mov     ebx, eax
0x180015b7a  test    eax, eax
0x180015b7c  jns     short loc_180015B9C
0x180015b7e  mov     rcx, [rsp+58h]; this
0x180015b83  mov     r9d, eax; char *
0x180015b86  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x180015b8d  lea     edx, [rdi+4Eh]; void *
0x180015b90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015b95  mov     eax, ebx
0x180015b97  jmp     loc_180015CF7
0x180015b9c  xor     eax, eax
0x180015b9e  jmp     loc_180015CF7
0x180015ba3  mov     r8, rdi; Size
0x180015ba6  lea     rdx, ?c_coclassGuid@?$svchost_singleton_coclass_factory@VIndexerSemanticStoreManager@@UIndexerSemanticStoreManagerImpl@@@@2Uguid@winrt@@B; Buf2
0x180015bad  lea     rcx, ?g_indexerSemanticStoreManagerGuid@@3Uguid@winrt@@A; Buf1
0x180015bb4  call    memcmp_0
0x180015bb9  test    eax, eax
0x180015bbb  jnz     short loc_180015C02
0x180015bbd  mov     rcx, cs:?g_singletonIndexerSemanticStoreManager@@3U?$com_ptr@UIndexerSemanticStoreManagerImpl@@@winrt@@A; winrt::com_ptr<IndexerSemanticStoreManagerImpl> g_singletonIndexerSemanticStoreManager
0x180015bc4  mov     rax, [rcx]
0x180015bc7  mov     r8, rsi
0x180015bca  mov     rdx, r14
0x180015bcd  mov     rax, [rax]
0x180015bd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bd5  mov     ebx, eax
0x180015bd7  test    eax, eax
0x180015bd9  jns     short loc_180015BFB
0x180015bdb  mov     rcx, [rsp+58h]; this
0x180015be0  mov     r9d, eax; char *
0x180015be3  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x180015bea  mov     edx, 64h ; 'd'; void *
0x180015bef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015bf4  mov     eax, ebx
0x180015bf6  jmp     loc_180015CF7
0x180015bfb  xor     eax, eax
0x180015bfd  jmp     loc_180015CF7
0x180015c02  mov     r8, rdi; Size
0x180015c05  lea     rdx, ?c_coclassGuid@?$svchost_singleton_coclass_factory@VIndexerSemanticStoreManager@@UIndexerSemanticStoreManagerImpl@@@@2Uguid@winrt@@B; Buf2
0x180015c0c  lea     rcx, ?g_sessionManagerBrokerGuid@@3Uguid@winrt@@A; Buf1
0x180015c13  call    memcmp_0
0x180015c18  test    eax, eax
0x180015c1a  jnz     short loc_180015C61
0x180015c1c  mov     rcx, cs:?g_singletonSessionManagerBroker@@3U?$com_ptr@USessionManagerBrokerImpl@@@winrt@@A; winrt::com_ptr<SessionManagerBrokerImpl> g_singletonSessionManagerBroker
0x180015c23  mov     rax, [rcx]
0x180015c26  mov     r8, rsi
0x180015c29  mov     rdx, r14
0x180015c2c  mov     rax, [rax]
0x180015c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c34  mov     ebx, eax
0x180015c36  test    eax, eax
0x180015c38  jns     short loc_180015C5A
0x180015c3a  mov     rcx, [rsp+58h]; this
0x180015c3f  mov     r9d, eax; char *
0x180015c42  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x180015c49  mov     edx, 6Dh ; 'm'; void *
0x180015c4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015c53  mov     eax, ebx
0x180015c55  jmp     loc_180015CF7
0x180015c5a  xor     eax, eax
0x180015c5c  jmp     loc_180015CF7
0x180015c61  mov     rbx, cs:?g_singletonAIFabricResourceManager@@3U?$com_ptr@UAIFabricResourceManagerImpl@@@winrt@@A; winrt::com_ptr<AIFabricResourceManagerImpl> g_singletonAIFabricResourceManager
0x180015c68  test    rbx, rbx
0x180015c6b  jz      short loc_180015CC2
0x180015c6d  mov     r8, rdi; Size
0x180015c70  lea     rdx, ?c_coclassGuid@?$svchost_singleton_coclass_factory@VIndexerSemanticStoreManager@@UIndexerSemanticStoreManagerImpl@@@@2Uguid@winrt@@B; Buf2
0x180015c77  lea     rcx, ?g_AIFabricResourceManagerGuid@@3Uguid@winrt@@A; Buf1
0x180015c7e  call    memcmp_0
0x180015c83  test    eax, eax
0x180015c85  jnz     short loc_180015CC2
0x180015c87  mov     rax, [rbx]
0x180015c8a  mov     r8, rsi
0x180015c8d  mov     rdx, r14
0x180015c90  mov     rcx, rbx
0x180015c93  mov     rax, [rax]
0x180015c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c9b  mov     ebx, eax
0x180015c9d  test    eax, eax
0x180015c9f  jns     short loc_180015CBE
0x180015ca1  mov     rcx, [rsp+58h]; this
0x180015ca6  mov     r9d, eax; char *
0x180015ca9  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x180015cb0  mov     edx, 76h ; 'v'; void *
0x180015cb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015cba  mov     eax, ebx
0x180015cbc  jmp     short loc_180015CF7
0x180015cbe  xor     eax, eax
0x180015cc0  jmp     short loc_180015CF7
0x180015cc2  movups  xmm0, xmmword ptr cs:?c_coclassGuid@?$svchost_singleton_coclass_factory@VIndexerSemanticStoreManager@@UIndexerSemanticStoreManagerImpl@@@@2Uguid@winrt@@B.Data1; winrt::guid const svchost_singleton_coclass_factory<IndexerSemanticStoreManager,IndexerSemanticStoreManagerImpl>::c_coclassGuid ...
0x180015cc9  movdqu  xmmword ptr [rsp+58h+var_38.Data1], xmm0
0x180015ccf  lea     r9, [rsp+58h+var_38]; wchar_t *
0x180015cd4  lea     r8, aWsaifabricsvcC; "WSAIFabricSvc class not available: {0}"
0x180015cdb  mov     edx, 7Ch ; '|'; wchar_t *
0x180015ce0  lea     rcx, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\com"...
0x180015ce7  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180015cec  mov     eax, 80040111h
0x180015cf1  jmp     short loc_180015CF7
0x180015cf3  mov     eax, [rsp+58h+fPending]
0x180015cf7  add     rsp, 38h
0x180015cfb  pop     r14
0x180015cfd  pop     rdi
0x180015cfe  pop     rsi
0x180015cff  pop     rbx
0x180015d00  retn
0x180015d01  call    __std_init_once_link_alternate_names_and_abort
```
