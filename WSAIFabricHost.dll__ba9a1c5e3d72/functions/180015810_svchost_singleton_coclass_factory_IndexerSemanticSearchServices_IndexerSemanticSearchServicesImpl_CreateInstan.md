# svchost_singleton_coclass_factory<IndexerSemanticSearchServices,IndexerSemanticSearchServicesImpl>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180015810`
- end: `0x180015a88`
- name: `?CreateInstance@?$svchost_singleton_coclass_factory@VIndexerSemanticSearchServices@@UIndexerSemanticSearchServicesImpl@@@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
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
- `0x180015810`
- `0x180015f90`
- `0x180018b14`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001586d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001586d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001589f`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001589f`

## string_xrefs

- `0x180015839`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportservice.cpp`
- `0x180015906`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportservice.cpp`
- `0x180015963`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportservice.cpp`
- `0x1800159c2`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportservice.cpp`
- `0x180015a29`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportservice.cpp`
- `0x180015a60`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportservice.cpp`

## pseudocode

```c
__int64 __fastcall svchost_singleton_coclass_factory<IndexerSemanticSearchServices,IndexerSemanticSearchServicesImpl>::CreateInstance(
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
          &svchost_singleton_coclass_factory<IndexerSemanticSearchServices,IndexerSemanticSearchServicesImpl>::c_coclassGuid,
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
          &svchost_singleton_coclass_factory<IndexerSemanticSearchServices,IndexerSemanticSearchServicesImpl>::c_coclassGuid,
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
            &svchost_singleton_coclass_factory<IndexerSemanticSearchServices,IndexerSemanticSearchServicesImpl>::c_coclassGuid,
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
              &svchost_singleton_coclass_factory<IndexerSemanticSearchServices,IndexerSemanticSearchServicesImpl>::c_coclassGuid,
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
        v19 = svchost_singleton_coclass_factory<IndexerSemanticSearchServices,IndexerSemanticSearchServicesImpl>::c_coclassGuid;
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
0x180015810  push    rbx
0x180015812  push    rsi
0x180015813  push    rdi
0x180015814  push    r14
0x180015816  sub     rsp, 38h
0x18001581a  mov     rsi, r9
0x18001581d  mov     r14, r8
0x180015820  mov     qword ptr [r9], 0
0x180015827  test    rdx, rdx
0x18001582a  jz      short loc_180015851
0x18001582c  mov     rcx, [rsp+58h]; this
0x180015831  mov     ebx, 80040110h
0x180015836  mov     r9d, ebx; char *
0x180015839  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x180015840  mov     edx, 3Dh ; '='; void *
0x180015845  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001584a  mov     eax, ebx
0x18001584c  jmp     loc_180015A77
0x180015851  mov     [rsp+58h+fPending], 0
0x180015859  xor     r9d, r9d; lpContext
0x18001585c  lea     r8, [rsp+58h+fPending]; fPending
0x180015861  xor     edx, edx; dwFlags
0x180015863  lea     rbx, ?g_singletonInit@@3Uonce_flag@std@@A; std::once_flag g_singletonInit
0x18001586a  mov     rcx, rbx; lpInitOnce
0x18001586d  call    cs:__imp___std_init_once_begin_initialize
0x180015873  test    eax, eax
0x180015875  jnz     short loc_18001587C
0x180015877  lea     ecx, [rax+5]
0x18001587a  int     29h; Win8: RtlFailFast(ecx)
0x18001587c  cmp     [rsp+58h+fPending], 0
0x180015881  jz      short loc_1800158AD
0x180015883  mov     qword ptr [rsp+58h+var_38.Data1], rbx; int
0x180015888  mov     qword ptr [rsp+58h+var_38.Data4], 4
0x180015891  call    ??$invoke@V_lambda_b88f0c3dac949a4d977743fd3cbabbf1_@@@std@@YAX$$QEAV_lambda_b88f0c3dac949a4d977743fd3cbabbf1_@@@Z; std::invoke<_lambda_b88f0c3dac949a4d977743fd3cbabbf1_>(_lambda_b88f0c3dac949a4d977743fd3cbabbf1_ &&)
0x180015896  nop
0x180015897  xor     r8d, r8d; lpContext
0x18001589a  xor     edx, edx; dwFlags
0x18001589c  mov     rcx, rbx; lpInitOnce
0x18001589f  call    cs:__imp_InitOnceComplete
0x1800158a5  test    eax, eax
0x1800158a7  jz      loc_180015A81
0x1800158ad  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_47942714@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714> `wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl(void)'::`2'::impl
0x1800158b4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(void)
0x1800158b9  mov     edi, 10h
0x1800158be  test    al, al
0x1800158c0  jz      loc_180015982
0x1800158c6  mov     r8d, edi; Size
0x1800158c9  lea     rdx, ?c_coclassGuid@?$svchost_singleton_coclass_factory@VIndexerSemanticSearchServices@@UIndexerSemanticSearchServicesImpl@@@@2Uguid@winrt@@B; Buf2
0x1800158d0  lea     rcx, ?g_indexerSemanticSearchServicesGuid@@3Uguid@winrt@@A; Buf1
0x1800158d7  call    memcmp_0
0x1800158dc  test    eax, eax
0x1800158de  jnz     short loc_180015923
0x1800158e0  mov     rcx, cs:?g_singletonIndexerSemanticSearchServices@@3U?$com_ptr@UIndexerSemanticSearchServicesImpl@@@winrt@@A; winrt::com_ptr<IndexerSemanticSearchServicesImpl> g_singletonIndexerSemanticSearchServices
0x1800158e7  mov     rax, [rcx]
0x1800158ea  mov     r8, rsi
0x1800158ed  mov     rdx, r14
0x1800158f0  mov     rax, [rax]
0x1800158f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158f8  mov     ebx, eax
0x1800158fa  test    eax, eax
0x1800158fc  jns     short loc_18001591C
0x1800158fe  mov     rcx, [rsp+58h]; this
0x180015903  mov     r9d, eax; char *
0x180015906  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x18001590d  lea     edx, [rdi+4Eh]; void *
0x180015910  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015915  mov     eax, ebx
0x180015917  jmp     loc_180015A77
0x18001591c  xor     eax, eax
0x18001591e  jmp     loc_180015A77
0x180015923  mov     r8, rdi; Size
0x180015926  lea     rdx, ?c_coclassGuid@?$svchost_singleton_coclass_factory@VIndexerSemanticSearchServices@@UIndexerSemanticSearchServicesImpl@@@@2Uguid@winrt@@B; Buf2
0x18001592d  lea     rcx, ?g_indexerSemanticStoreManagerGuid@@3Uguid@winrt@@A; Buf1
0x180015934  call    memcmp_0
0x180015939  test    eax, eax
0x18001593b  jnz     short loc_180015982
0x18001593d  mov     rcx, cs:?g_singletonIndexerSemanticStoreManager@@3U?$com_ptr@UIndexerSemanticStoreManagerImpl@@@winrt@@A; winrt::com_ptr<IndexerSemanticStoreManagerImpl> g_singletonIndexerSemanticStoreManager
0x180015944  mov     rax, [rcx]
0x180015947  mov     r8, rsi
0x18001594a  mov     rdx, r14
0x18001594d  mov     rax, [rax]
0x180015950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015955  mov     ebx, eax
0x180015957  test    eax, eax
0x180015959  jns     short loc_18001597B
0x18001595b  mov     rcx, [rsp+58h]; this
0x180015960  mov     r9d, eax; char *
0x180015963  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x18001596a  mov     edx, 64h ; 'd'; void *
0x18001596f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015974  mov     eax, ebx
0x180015976  jmp     loc_180015A77
0x18001597b  xor     eax, eax
0x18001597d  jmp     loc_180015A77
0x180015982  mov     r8, rdi; Size
0x180015985  lea     rdx, ?c_coclassGuid@?$svchost_singleton_coclass_factory@VIndexerSemanticSearchServices@@UIndexerSemanticSearchServicesImpl@@@@2Uguid@winrt@@B; Buf2
0x18001598c  lea     rcx, ?g_sessionManagerBrokerGuid@@3Uguid@winrt@@A; Buf1
0x180015993  call    memcmp_0
0x180015998  test    eax, eax
0x18001599a  jnz     short loc_1800159E1
0x18001599c  mov     rcx, cs:?g_singletonSessionManagerBroker@@3U?$com_ptr@USessionManagerBrokerImpl@@@winrt@@A; winrt::com_ptr<SessionManagerBrokerImpl> g_singletonSessionManagerBroker
0x1800159a3  mov     rax, [rcx]
0x1800159a6  mov     r8, rsi
0x1800159a9  mov     rdx, r14
0x1800159ac  mov     rax, [rax]
0x1800159af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159b4  mov     ebx, eax
0x1800159b6  test    eax, eax
0x1800159b8  jns     short loc_1800159DA
0x1800159ba  mov     rcx, [rsp+58h]; this
0x1800159bf  mov     r9d, eax; char *
0x1800159c2  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800159c9  mov     edx, 6Dh ; 'm'; void *
0x1800159ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800159d3  mov     eax, ebx
0x1800159d5  jmp     loc_180015A77
0x1800159da  xor     eax, eax
0x1800159dc  jmp     loc_180015A77
0x1800159e1  mov     rbx, cs:?g_singletonAIFabricResourceManager@@3U?$com_ptr@UAIFabricResourceManagerImpl@@@winrt@@A; winrt::com_ptr<AIFabricResourceManagerImpl> g_singletonAIFabricResourceManager
0x1800159e8  test    rbx, rbx
0x1800159eb  jz      short loc_180015A42
0x1800159ed  mov     r8, rdi; Size
0x1800159f0  lea     rdx, ?c_coclassGuid@?$svchost_singleton_coclass_factory@VIndexerSemanticSearchServices@@UIndexerSemanticSearchServicesImpl@@@@2Uguid@winrt@@B; Buf2
0x1800159f7  lea     rcx, ?g_AIFabricResourceManagerGuid@@3Uguid@winrt@@A; Buf1
0x1800159fe  call    memcmp_0
0x180015a03  test    eax, eax
0x180015a05  jnz     short loc_180015A42
0x180015a07  mov     rax, [rbx]
0x180015a0a  mov     r8, rsi
0x180015a0d  mov     rdx, r14
0x180015a10  mov     rcx, rbx
0x180015a13  mov     rax, [rax]
0x180015a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a1b  mov     ebx, eax
0x180015a1d  test    eax, eax
0x180015a1f  jns     short loc_180015A3E
0x180015a21  mov     rcx, [rsp+58h]; this
0x180015a26  mov     r9d, eax; char *
0x180015a29  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x180015a30  mov     edx, 76h ; 'v'; void *
0x180015a35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015a3a  mov     eax, ebx
0x180015a3c  jmp     short loc_180015A77
0x180015a3e  xor     eax, eax
0x180015a40  jmp     short loc_180015A77
0x180015a42  movups  xmm0, xmmword ptr cs:?c_coclassGuid@?$svchost_singleton_coclass_factory@VIndexerSemanticSearchServices@@UIndexerSemanticSearchServicesImpl@@@@2Uguid@winrt@@B.Data1; winrt::guid const svchost_singleton_coclass_factory<IndexerSemanticSearchServices,IndexerSemanticSearchServicesImpl>::c_coclassGuid ...
0x180015a49  movdqu  xmmword ptr [rsp+58h+var_38.Data1], xmm0
0x180015a4f  lea     r9, [rsp+58h+var_38]; wchar_t *
0x180015a54  lea     r8, aWsaifabricsvcC; "WSAIFabricSvc class not available: {0}"
0x180015a5b  mov     edx, 7Ch ; '|'; wchar_t *
0x180015a60  lea     rcx, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\com"...
0x180015a67  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180015a6c  mov     eax, 80040111h
0x180015a71  jmp     short loc_180015A77
0x180015a73  mov     eax, [rsp+58h+fPending]
0x180015a77  add     rsp, 38h
0x180015a7b  pop     r14
0x180015a7d  pop     rdi
0x180015a7e  pop     rsi
0x180015a7f  pop     rbx
0x180015a80  retn
0x180015a81  call    __std_init_once_link_alternate_names_and_abort
```
