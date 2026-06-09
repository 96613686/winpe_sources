# svchost_singleton_coclass_factory<SessionManagerBroker,SessionManagerBrokerImpl>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180015d10`
- end: `0x180015f88`
- name: `?CreateInstance@?$svchost_singleton_coclass_factory@VSessionManagerBroker@@USessionManagerBrokerImpl@@@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `632`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006608`
- `0x180007f4e`
- `0x18000b064`
- `0x180012ba4`
- `0x180015d10`
- `0x180015f90`
- `0x180018b14`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180015d6d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180015d6d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180015d9f`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180015d9f`

## string_xrefs

- `0x180015d39`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportservice.cpp`
- `0x180015e06`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportservice.cpp`
- `0x180015e63`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportservice.cpp`
- `0x180015ec2`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportservice.cpp`
- `0x180015f29`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportservice.cpp`
- `0x180015f60`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportservice.cpp`

## pseudocode

```c
__int64 __fastcall svchost_singleton_coclass_factory<SessionManagerBroker,SessionManagerBrokerImpl>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // eax
  unsigned int v14; // ebx
  __int64 (__fastcall ***v15)(_QWORD, __int64, _QWORD *); // rbx
  int v16; // eax
  unsigned int v17; // ebx
  IID v18; // [rsp+20h] [rbp-38h] BYREF
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
      v18.Data1);
    return 2147746064LL;
  }
  fPending = 0;
  if ( !__std_init_once_begin_initialize(&g_singletonInit, 0, &fPending, 0) )
    __fastfail(5u);
  if ( fPending )
  {
    *(_QWORD *)&v18.Data1 = &g_singletonInit;
    *(_QWORD *)v18.Data4 = 4;
    std::invoke<_lambda_b88f0c3dac949a4d977743fd3cbabbf1_>();
    if ( !InitOnceComplete(&g_singletonInit, 0, 0) )
      _std_init_once_link_alternate_names_and_abort(v8, v7);
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl'::`2'::impl) )
    goto LABEL_29;
  if ( !memcmp_0(
          &g_indexerSemanticSearchServicesGuid,
          &svchost_singleton_coclass_factory<SessionManagerBroker,SessionManagerBrokerImpl>::c_coclassGuid,
          0x10u) )
  {
    v9 = (**(__int64 (__fastcall ***)(IndexerSemanticSearchServicesImpl *, __int64, _QWORD *))g_singletonIndexerSemanticSearchServices)(
           g_singletonIndexerSemanticSearchServices,
           a3,
           a4);
    v10 = v9;
    if ( v9 >= 0 )
      return 0;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportservice.cpp",
      (const char *)(unsigned int)v9,
      v18.Data1);
    return v10;
  }
  if ( !memcmp_0(
          &g_indexerSemanticStoreManagerGuid,
          &svchost_singleton_coclass_factory<SessionManagerBroker,SessionManagerBrokerImpl>::c_coclassGuid,
          0x10u) )
  {
    v11 = (**(__int64 (__fastcall ***)(__int64, __int64, _QWORD *))g_singletonIndexerSemanticStoreManager)(
            g_singletonIndexerSemanticStoreManager,
            a3,
            a4);
    v12 = v11;
    if ( v11 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x64,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportservice.cpp",
        (const char *)(unsigned int)v11,
        v18.Data1);
      return v12;
    }
  }
  else
  {
LABEL_29:
    if ( !memcmp_0(
            &g_sessionManagerBrokerGuid,
            &svchost_singleton_coclass_factory<SessionManagerBroker,SessionManagerBrokerImpl>::c_coclassGuid,
            0x10u) )
    {
      v13 = (**(__int64 (__fastcall ***)(__int64, __int64, _QWORD *))g_singletonSessionManagerBroker)(
              g_singletonSessionManagerBroker,
              a3,
              a4);
      v14 = v13;
      if ( v13 >= 0 )
      {
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6D,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportservice.cpp",
          (const char *)(unsigned int)v13,
          v18.Data1);
        return v14;
      }
    }
    else
    {
      v15 = (__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *))g_singletonAIFabricResourceManager;
      if ( g_singletonAIFabricResourceManager
        && !memcmp_0(
              &g_AIFabricResourceManagerGuid,
              &svchost_singleton_coclass_factory<SessionManagerBroker,SessionManagerBrokerImpl>::c_coclassGuid,
              0x10u) )
      {
        v16 = (**v15)(v15, a3, a4);
        v17 = v16;
        if ( v16 >= 0 )
        {
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x76,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportservice.cpp",
            (const char *)(unsigned int)v16,
            v18.Data1);
          return v17;
        }
      }
      else
      {
        v18 = svchost_singleton_coclass_factory<SessionManagerBroker,SessionManagerBrokerImpl>::c_coclassGuid;
        SearchIndexerTrace::Error(
          (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportservice.cpp",
          (const wchar_t *)0x7C,
          (unsigned int)L"WSAIFabricSvc class not available: {0}",
          (const wchar_t *)&v18);
        return 2147746065LL;
      }
    }
  }
}

```

## disassembly

```asm
0x180015d10  push    rbx
0x180015d12  push    rsi
0x180015d13  push    rdi
0x180015d14  push    r14
0x180015d16  sub     rsp, 38h
0x180015d1a  mov     rsi, r9
0x180015d1d  mov     r14, r8
0x180015d20  mov     qword ptr [r9], 0
0x180015d27  test    rdx, rdx
0x180015d2a  jz      short loc_180015D51
0x180015d2c  mov     rcx, [rsp+58h]; this
0x180015d31  mov     ebx, 80040110h
0x180015d36  mov     r9d, ebx; char *
0x180015d39  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x180015d40  mov     edx, 3Dh ; '='; void *
0x180015d45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015d4a  mov     eax, ebx
0x180015d4c  jmp     loc_180015F77
0x180015d51  mov     [rsp+58h+fPending], 0
0x180015d59  xor     r9d, r9d; lpContext
0x180015d5c  lea     r8, [rsp+58h+fPending]; fPending
0x180015d61  xor     edx, edx; dwFlags
0x180015d63  lea     rbx, ?g_singletonInit@@3Uonce_flag@std@@A; std::once_flag g_singletonInit
0x180015d6a  mov     rcx, rbx; lpInitOnce
0x180015d6d  call    cs:__imp___std_init_once_begin_initialize
0x180015d73  test    eax, eax
0x180015d75  jnz     short loc_180015D7C
0x180015d77  lea     ecx, [rax+5]
0x180015d7a  int     29h; Win8: RtlFailFast(ecx)
0x180015d7c  cmp     [rsp+58h+fPending], 0
0x180015d81  jz      short loc_180015DAD
0x180015d83  mov     qword ptr [rsp+58h+var_38.Data1], rbx; int
0x180015d88  mov     qword ptr [rsp+58h+var_38.Data4], 4
0x180015d91  call    ??$invoke@V_lambda_b88f0c3dac949a4d977743fd3cbabbf1_@@@std@@YAX$$QEAV_lambda_b88f0c3dac949a4d977743fd3cbabbf1_@@@Z; std::invoke<_lambda_b88f0c3dac949a4d977743fd3cbabbf1_>(_lambda_b88f0c3dac949a4d977743fd3cbabbf1_ &&)
0x180015d96  nop
0x180015d97  xor     r8d, r8d; lpContext
0x180015d9a  xor     edx, edx; dwFlags
0x180015d9c  mov     rcx, rbx; lpInitOnce
0x180015d9f  call    cs:__imp_InitOnceComplete
0x180015da5  test    eax, eax
0x180015da7  jz      loc_180015F81
0x180015dad  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_47942714@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714> `wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl(void)'::`2'::impl
0x180015db4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(void)
0x180015db9  mov     edi, 10h
0x180015dbe  test    al, al
0x180015dc0  jz      loc_180015E82
0x180015dc6  mov     r8d, edi; Size
0x180015dc9  lea     rdx, ?c_coclassGuid@?$svchost_singleton_coclass_factory@VSessionManagerBroker@@USessionManagerBrokerImpl@@@@2Uguid@winrt@@B; Buf2
0x180015dd0  lea     rcx, ?g_indexerSemanticSearchServicesGuid@@3Uguid@winrt@@A; Buf1
0x180015dd7  call    memcmp_0
0x180015ddc  test    eax, eax
0x180015dde  jnz     short loc_180015E23
0x180015de0  mov     rcx, cs:?g_singletonIndexerSemanticSearchServices@@3U?$com_ptr@UIndexerSemanticSearchServicesImpl@@@winrt@@A; winrt::com_ptr<IndexerSemanticSearchServicesImpl> g_singletonIndexerSemanticSearchServices
0x180015de7  mov     rax, [rcx]
0x180015dea  mov     r8, rsi
0x180015ded  mov     rdx, r14
0x180015df0  mov     rax, [rax]
0x180015df3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015df8  mov     ebx, eax
0x180015dfa  test    eax, eax
0x180015dfc  jns     short loc_180015E1C
0x180015dfe  mov     rcx, [rsp+58h]; this
0x180015e03  mov     r9d, eax; char *
0x180015e06  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x180015e0d  lea     edx, [rdi+4Eh]; void *
0x180015e10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015e15  mov     eax, ebx
0x180015e17  jmp     loc_180015F77
0x180015e1c  xor     eax, eax
0x180015e1e  jmp     loc_180015F77
0x180015e23  mov     r8, rdi; Size
0x180015e26  lea     rdx, ?c_coclassGuid@?$svchost_singleton_coclass_factory@VSessionManagerBroker@@USessionManagerBrokerImpl@@@@2Uguid@winrt@@B; Buf2
0x180015e2d  lea     rcx, ?g_indexerSemanticStoreManagerGuid@@3Uguid@winrt@@A; Buf1
0x180015e34  call    memcmp_0
0x180015e39  test    eax, eax
0x180015e3b  jnz     short loc_180015E82
0x180015e3d  mov     rcx, cs:?g_singletonIndexerSemanticStoreManager@@3U?$com_ptr@UIndexerSemanticStoreManagerImpl@@@winrt@@A; winrt::com_ptr<IndexerSemanticStoreManagerImpl> g_singletonIndexerSemanticStoreManager
0x180015e44  mov     rax, [rcx]
0x180015e47  mov     r8, rsi
0x180015e4a  mov     rdx, r14
0x180015e4d  mov     rax, [rax]
0x180015e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e55  mov     ebx, eax
0x180015e57  test    eax, eax
0x180015e59  jns     short loc_180015E7B
0x180015e5b  mov     rcx, [rsp+58h]; this
0x180015e60  mov     r9d, eax; char *
0x180015e63  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x180015e6a  mov     edx, 64h ; 'd'; void *
0x180015e6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015e74  mov     eax, ebx
0x180015e76  jmp     loc_180015F77
0x180015e7b  xor     eax, eax
0x180015e7d  jmp     loc_180015F77
0x180015e82  mov     r8, rdi; Size
0x180015e85  lea     rdx, ?c_coclassGuid@?$svchost_singleton_coclass_factory@VSessionManagerBroker@@USessionManagerBrokerImpl@@@@2Uguid@winrt@@B; Buf2
0x180015e8c  lea     rcx, ?g_sessionManagerBrokerGuid@@3Uguid@winrt@@A; Buf1
0x180015e93  call    memcmp_0
0x180015e98  test    eax, eax
0x180015e9a  jnz     short loc_180015EE1
0x180015e9c  mov     rcx, cs:?g_singletonSessionManagerBroker@@3U?$com_ptr@USessionManagerBrokerImpl@@@winrt@@A; winrt::com_ptr<SessionManagerBrokerImpl> g_singletonSessionManagerBroker
0x180015ea3  mov     rax, [rcx]
0x180015ea6  mov     r8, rsi
0x180015ea9  mov     rdx, r14
0x180015eac  mov     rax, [rax]
0x180015eaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015eb4  mov     ebx, eax
0x180015eb6  test    eax, eax
0x180015eb8  jns     short loc_180015EDA
0x180015eba  mov     rcx, [rsp+58h]; this
0x180015ebf  mov     r9d, eax; char *
0x180015ec2  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x180015ec9  mov     edx, 6Dh ; 'm'; void *
0x180015ece  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015ed3  mov     eax, ebx
0x180015ed5  jmp     loc_180015F77
0x180015eda  xor     eax, eax
0x180015edc  jmp     loc_180015F77
0x180015ee1  mov     rbx, cs:?g_singletonAIFabricResourceManager@@3U?$com_ptr@UAIFabricResourceManagerImpl@@@winrt@@A; winrt::com_ptr<AIFabricResourceManagerImpl> g_singletonAIFabricResourceManager
0x180015ee8  test    rbx, rbx
0x180015eeb  jz      short loc_180015F42
0x180015eed  mov     r8, rdi; Size
0x180015ef0  lea     rdx, ?c_coclassGuid@?$svchost_singleton_coclass_factory@VSessionManagerBroker@@USessionManagerBrokerImpl@@@@2Uguid@winrt@@B; Buf2
0x180015ef7  lea     rcx, ?g_AIFabricResourceManagerGuid@@3Uguid@winrt@@A; Buf1
0x180015efe  call    memcmp_0
0x180015f03  test    eax, eax
0x180015f05  jnz     short loc_180015F42
0x180015f07  mov     rax, [rbx]
0x180015f0a  mov     r8, rsi
0x180015f0d  mov     rdx, r14
0x180015f10  mov     rcx, rbx
0x180015f13  mov     rax, [rax]
0x180015f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f1b  mov     ebx, eax
0x180015f1d  test    eax, eax
0x180015f1f  jns     short loc_180015F3E
0x180015f21  mov     rcx, [rsp+58h]; this
0x180015f26  mov     r9d, eax; char *
0x180015f29  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x180015f30  mov     edx, 76h ; 'v'; void *
0x180015f35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015f3a  mov     eax, ebx
0x180015f3c  jmp     short loc_180015F77
0x180015f3e  xor     eax, eax
0x180015f40  jmp     short loc_180015F77
0x180015f42  movups  xmm0, xmmword ptr cs:?c_coclassGuid@?$svchost_singleton_coclass_factory@VSessionManagerBroker@@USessionManagerBrokerImpl@@@@2Uguid@winrt@@B.Data1; winrt::guid const svchost_singleton_coclass_factory<SessionManagerBroker,SessionManagerBrokerImpl>::c_coclassGuid ...
0x180015f49  movdqu  xmmword ptr [rsp+58h+var_38.Data1], xmm0
0x180015f4f  lea     r9, [rsp+58h+var_38]; wchar_t *
0x180015f54  lea     r8, aWsaifabricsvcC; "WSAIFabricSvc class not available: {0}"
0x180015f5b  mov     edx, 7Ch ; '|'; wchar_t *
0x180015f60  lea     rcx, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\com"...
0x180015f67  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180015f6c  mov     eax, 80040111h
0x180015f71  jmp     short loc_180015F77
0x180015f73  mov     eax, [rsp+58h+fPending]
0x180015f77  add     rsp, 38h
0x180015f7b  pop     r14
0x180015f7d  pop     rdi
0x180015f7e  pop     rsi
0x180015f7f  pop     rbx
0x180015f80  retn
0x180015f81  call    __std_init_once_link_alternate_names_and_abort
```
