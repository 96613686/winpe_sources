# svchost_singleton_coclass_factory<AIFabricResourceManager,AIFabricResourceManagerImpl>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180015590`
- end: `0x180015808`
- name: `?CreateInstance@?$svchost_singleton_coclass_factory@VAIFabricResourceManager@@UAIFabricResourceManagerImpl@@@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
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
- `0x180015590`
- `0x180015f90`
- `0x180018b14`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800155ed`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800155ed`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001561f`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001561f`

## string_xrefs

- `0x1800155b9`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportservice.cpp`
- `0x180015686`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportservice.cpp`
- `0x1800156e3`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportservice.cpp`
- `0x180015742`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportservice.cpp`
- `0x1800157a9`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportservice.cpp`
- `0x1800157e0`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall svchost_singleton_coclass_factory<AIFabricResourceManager,AIFabricResourceManagerImpl>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 result; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // eax
  const char *v12; // r9
  unsigned int v13; // ebx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // eax
  unsigned int v17; // ebx
  __int64 (__fastcall ***v18)(_QWORD, __int64, _QWORD *); // rbx
  int v19; // eax
  unsigned int v20; // ebx
  IID v21; // [rsp+20h] [rbp-38h] BYREF
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
      v21.Data1);
    return 2147746064LL;
  }
  fPending = 0;
  if ( !__std_init_once_begin_initialize(&g_singletonInit, 0, &fPending, 0) )
    __fastfail(5u);
  try
  {
    if ( fPending )
    {
      *(_QWORD *)&v21.Data1 = &g_singletonInit;
      *(_QWORD *)v21.Data4 = 4;
      std::invoke<_lambda_b88f0c3dac949a4d977743fd3cbabbf1_>(v8);
      if ( !InitOnceComplete(&g_singletonInit, 0, 0) )
        _std_init_once_link_alternate_names_and_abort(v10, v9);
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl'::`2'::impl) )
      goto LABEL_35;
    if ( !memcmp_0(
            &g_indexerSemanticSearchServicesGuid,
            &svchost_singleton_coclass_factory<AIFabricResourceManager,AIFabricResourceManagerImpl>::c_coclassGuid,
            0x10u) )
    {
      v11 = (**(__int64 (__fastcall ***)(IndexerSemanticSearchServicesImpl *, __int64, _QWORD *))g_singletonIndexerSemanticSearchServices)(
              g_singletonIndexerSemanticSearchServices,
              a3,
              a4);
      v13 = v11;
      if ( v11 >= 0 )
        return 0;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportservice.cpp",
        (const char *)(unsigned int)v11,
        v21.Data1);
      return v13;
    }
    if ( memcmp_0(
           &g_indexerSemanticStoreManagerGuid,
           &svchost_singleton_coclass_factory<AIFabricResourceManager,AIFabricResourceManagerImpl>::c_coclassGuid,
           0x10u) )
    {
LABEL_35:
      if ( !memcmp_0(
              &g_sessionManagerBrokerGuid,
              &svchost_singleton_coclass_factory<AIFabricResourceManager,AIFabricResourceManagerImpl>::c_coclassGuid,
              0x10u) )
      {
        v16 = (**(__int64 (__fastcall ***)(__int64, __int64, _QWORD *))g_singletonSessionManagerBroker)(
                g_singletonSessionManagerBroker,
                a3,
                a4);
        v17 = v16;
        if ( v16 >= 0 )
        {
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6D,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportservice.cpp",
            (const char *)(unsigned int)v16,
            v21.Data1);
          return v17;
        }
      }
      else
      {
        v18 = (__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *))g_singletonAIFabricResourceManager;
        if ( g_singletonAIFabricResourceManager
          && !memcmp_0(
                &g_AIFabricResourceManagerGuid,
                &svchost_singleton_coclass_factory<AIFabricResourceManager,AIFabricResourceManagerImpl>::c_coclassGuid,
                0x10u) )
        {
          v19 = (**v18)(v18, a3, a4);
          v20 = v19;
          if ( v19 >= 0 )
          {
            return 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x76,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportservice.cpp",
              (const char *)(unsigned int)v19,
              v21.Data1);
            return v20;
          }
        }
        else
        {
          v21 = svchost_singleton_coclass_factory<AIFabricResourceManager,AIFabricResourceManagerImpl>::c_coclassGuid;
          SearchIndexerTrace::Error(
            (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportservice.cpp",
            (const wchar_t *)0x7C,
            (unsigned int)L"WSAIFabricSvc class not available: {0}",
            (const wchar_t *)&v21);
          return 2147746065LL;
        }
      }
    }
    v14 = (**(__int64 (__fastcall ***)(__int64, __int64, _QWORD *))g_singletonIndexerSemanticStoreManager)(
            g_singletonIndexerSemanticStoreManager,
            a3,
            a4);
    v15 = v14;
    if ( v14 >= 0 )
    {
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x64,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportservice.cpp",
        (const char *)(unsigned int)v14,
        v21.Data1);
      result = v15;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x7F,
                           (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsu"
                                         "pportservice.cpp",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x180015590  push    rbx
0x180015592  push    rsi
0x180015593  push    rdi
0x180015594  push    r14
0x180015596  sub     rsp, 38h
0x18001559a  mov     rsi, r9
0x18001559d  mov     r14, r8
0x1800155a0  mov     qword ptr [r9], 0
0x1800155a7  test    rdx, rdx
0x1800155aa  jz      short loc_1800155D1
0x1800155ac  mov     rcx, [rsp+58h]; this
0x1800155b1  mov     ebx, 80040110h
0x1800155b6  mov     r9d, ebx; char *
0x1800155b9  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800155c0  mov     edx, 3Dh ; '='; void *
0x1800155c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800155ca  mov     eax, ebx
0x1800155cc  jmp     loc_1800157F7
0x1800155d1  mov     [rsp+58h+fPending], 0
0x1800155d9  xor     r9d, r9d; lpContext
0x1800155dc  lea     r8, [rsp+58h+fPending]; fPending
0x1800155e1  xor     edx, edx; dwFlags
0x1800155e3  lea     rbx, ?g_singletonInit@@3Uonce_flag@std@@A; std::once_flag g_singletonInit
0x1800155ea  mov     rcx, rbx; lpInitOnce
0x1800155ed  call    cs:__imp___std_init_once_begin_initialize
0x1800155f3  test    eax, eax
0x1800155f5  jnz     short loc_1800155FC
0x1800155f7  lea     ecx, [rax+5]
0x1800155fa  int     29h; Win8: RtlFailFast(ecx)
0x1800155fc  cmp     [rsp+58h+fPending], 0
0x180015601  jz      short loc_18001562D
0x180015603  mov     qword ptr [rsp+58h+var_38.Data1], rbx; int
0x180015608  mov     qword ptr [rsp+58h+var_38.Data4], 4
0x180015611  call    ??$invoke@V_lambda_b88f0c3dac949a4d977743fd3cbabbf1_@@@std@@YAX$$QEAV_lambda_b88f0c3dac949a4d977743fd3cbabbf1_@@@Z; std::invoke<_lambda_b88f0c3dac949a4d977743fd3cbabbf1_>(_lambda_b88f0c3dac949a4d977743fd3cbabbf1_ &&)
0x180015616  nop
0x180015617  xor     r8d, r8d; lpContext
0x18001561a  xor     edx, edx; dwFlags
0x18001561c  mov     rcx, rbx; lpInitOnce
0x18001561f  call    cs:__imp_InitOnceComplete
0x180015625  test    eax, eax
0x180015627  jz      loc_180015801
0x18001562d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_47942714@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714> `wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl(void)'::`2'::impl
0x180015634  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(void)
0x180015639  mov     edi, 10h
0x18001563e  test    al, al
0x180015640  jz      loc_180015702
0x180015646  mov     r8d, edi; Size
0x180015649  lea     rdx, ?c_coclassGuid@?$svchost_singleton_coclass_factory@VAIFabricResourceManager@@UAIFabricResourceManagerImpl@@@@2Uguid@winrt@@B; Buf2
0x180015650  lea     rcx, ?g_indexerSemanticSearchServicesGuid@@3Uguid@winrt@@A; Buf1
0x180015657  call    memcmp_0
0x18001565c  test    eax, eax
0x18001565e  jnz     short loc_1800156A3
0x180015660  mov     rcx, cs:?g_singletonIndexerSemanticSearchServices@@3U?$com_ptr@UIndexerSemanticSearchServicesImpl@@@winrt@@A; winrt::com_ptr<IndexerSemanticSearchServicesImpl> g_singletonIndexerSemanticSearchServices
0x180015667  mov     rax, [rcx]
0x18001566a  mov     r8, rsi
0x18001566d  mov     rdx, r14
0x180015670  mov     rax, [rax]
0x180015673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015678  mov     ebx, eax
0x18001567a  test    eax, eax
0x18001567c  jns     short loc_18001569C
0x18001567e  mov     rcx, [rsp+58h]; this
0x180015683  mov     r9d, eax; char *
0x180015686  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x18001568d  lea     edx, [rdi+4Eh]; void *
0x180015690  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015695  mov     eax, ebx
0x180015697  jmp     loc_1800157F7
0x18001569c  xor     eax, eax
0x18001569e  jmp     loc_1800157F7
0x1800156a3  mov     r8, rdi; Size
0x1800156a6  lea     rdx, ?c_coclassGuid@?$svchost_singleton_coclass_factory@VAIFabricResourceManager@@UAIFabricResourceManagerImpl@@@@2Uguid@winrt@@B; Buf2
0x1800156ad  lea     rcx, ?g_indexerSemanticStoreManagerGuid@@3Uguid@winrt@@A; Buf1
0x1800156b4  call    memcmp_0
0x1800156b9  test    eax, eax
0x1800156bb  jnz     short loc_180015702
0x1800156bd  mov     rcx, cs:?g_singletonIndexerSemanticStoreManager@@3U?$com_ptr@UIndexerSemanticStoreManagerImpl@@@winrt@@A; winrt::com_ptr<IndexerSemanticStoreManagerImpl> g_singletonIndexerSemanticStoreManager
0x1800156c4  mov     rax, [rcx]
0x1800156c7  mov     r8, rsi
0x1800156ca  mov     rdx, r14
0x1800156cd  mov     rax, [rax]
0x1800156d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156d5  mov     ebx, eax
0x1800156d7  test    eax, eax
0x1800156d9  jns     short loc_1800156FB
0x1800156db  mov     rcx, [rsp+58h]; this
0x1800156e0  mov     r9d, eax; char *
0x1800156e3  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800156ea  mov     edx, 64h ; 'd'; void *
0x1800156ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800156f4  mov     eax, ebx
0x1800156f6  jmp     loc_1800157F7
0x1800156fb  xor     eax, eax
0x1800156fd  jmp     loc_1800157F7
0x180015702  mov     r8, rdi; Size
0x180015705  lea     rdx, ?c_coclassGuid@?$svchost_singleton_coclass_factory@VAIFabricResourceManager@@UAIFabricResourceManagerImpl@@@@2Uguid@winrt@@B; Buf2
0x18001570c  lea     rcx, ?g_sessionManagerBrokerGuid@@3Uguid@winrt@@A; Buf1
0x180015713  call    memcmp_0
0x180015718  test    eax, eax
0x18001571a  jnz     short loc_180015761
0x18001571c  mov     rcx, cs:?g_singletonSessionManagerBroker@@3U?$com_ptr@USessionManagerBrokerImpl@@@winrt@@A; winrt::com_ptr<SessionManagerBrokerImpl> g_singletonSessionManagerBroker
0x180015723  mov     rax, [rcx]
0x180015726  mov     r8, rsi
0x180015729  mov     rdx, r14
0x18001572c  mov     rax, [rax]
0x18001572f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015734  mov     ebx, eax
0x180015736  test    eax, eax
0x180015738  jns     short loc_18001575A
0x18001573a  mov     rcx, [rsp+58h]; this
0x18001573f  mov     r9d, eax; char *
0x180015742  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x180015749  mov     edx, 6Dh ; 'm'; void *
0x18001574e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015753  mov     eax, ebx
0x180015755  jmp     loc_1800157F7
0x18001575a  xor     eax, eax
0x18001575c  jmp     loc_1800157F7
0x180015761  mov     rbx, cs:?g_singletonAIFabricResourceManager@@3U?$com_ptr@UAIFabricResourceManagerImpl@@@winrt@@A; winrt::com_ptr<AIFabricResourceManagerImpl> g_singletonAIFabricResourceManager
0x180015768  test    rbx, rbx
0x18001576b  jz      short loc_1800157C2
0x18001576d  mov     r8, rdi; Size
0x180015770  lea     rdx, ?c_coclassGuid@?$svchost_singleton_coclass_factory@VAIFabricResourceManager@@UAIFabricResourceManagerImpl@@@@2Uguid@winrt@@B; Buf2
0x180015777  lea     rcx, ?g_AIFabricResourceManagerGuid@@3Uguid@winrt@@A; Buf1
0x18001577e  call    memcmp_0
0x180015783  test    eax, eax
0x180015785  jnz     short loc_1800157C2
0x180015787  mov     rax, [rbx]
0x18001578a  mov     r8, rsi
0x18001578d  mov     rdx, r14
0x180015790  mov     rcx, rbx
0x180015793  mov     rax, [rax]
0x180015796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001579b  mov     ebx, eax
0x18001579d  test    eax, eax
0x18001579f  jns     short loc_1800157BE
0x1800157a1  mov     rcx, [rsp+58h]; this
0x1800157a6  mov     r9d, eax; char *
0x1800157a9  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800157b0  mov     edx, 76h ; 'v'; void *
0x1800157b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800157ba  mov     eax, ebx
0x1800157bc  jmp     short loc_1800157F7
0x1800157be  xor     eax, eax
0x1800157c0  jmp     short loc_1800157F7
0x1800157c2  movups  xmm0, xmmword ptr cs:?c_coclassGuid@?$svchost_singleton_coclass_factory@VAIFabricResourceManager@@UAIFabricResourceManagerImpl@@@@2Uguid@winrt@@B.Data1; winrt::guid const svchost_singleton_coclass_factory<AIFabricResourceManager,AIFabricResourceManagerImpl>::c_coclassGuid ...
0x1800157c9  movdqu  xmmword ptr [rsp+58h+var_38.Data1], xmm0
0x1800157cf  lea     r9, [rsp+58h+var_38]; wchar_t *
0x1800157d4  lea     r8, aWsaifabricsvcC; "WSAIFabricSvc class not available: {0}"
0x1800157db  mov     edx, 7Ch ; '|'; wchar_t *
0x1800157e0  lea     rcx, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800157e7  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800157ec  mov     eax, 80040111h
0x1800157f1  jmp     short loc_1800157F7
0x1800157f3  mov     eax, [rsp+58h+fPending]
0x1800157f7  add     rsp, 38h
0x1800157fb  pop     r14
0x1800157fd  pop     rdi
0x1800157fe  pop     rsi
0x1800157ff  pop     rbx
0x180015800  retn
0x180015801  call    __std_init_once_link_alternate_names_and_abort
```
