# CDesktopManager::InitializeComObjects(void)

- ea: `0x1800afb50`
- end: `0x1800afda5`
- name: `?InitializeComObjects@CDesktopManager@@AEAAJXZ`
- size: `597`
- prototype: `__int64 __fastcall(CDesktopManager *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001d710`
- `0x18003e140`

## callees

- `0x180001b40`
- `0x1800029dc`
- `0x18001f43c`
- `0x1800446d0`
- `0x180054734`
- `0x18005d708`
- `0x18005eb18`
- `0x180070548`
- `0x1800794cc`
- `0x180083a34`
- `0x18008414c`
- `0x18008ed20`
- `0x1800ae0c8`
- `0x1800afb50`
- `0x1800b119c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800afc93`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800afcbf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800afc93`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800afcbf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDesktopManager::InitializeComObjects(CAnimationEngine **this, __int64 a2)
{
  int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  int Instance; // ebx
  void *v8; // rax
  CDisplayBroker *v9; // rsi
  int v10; // eax
  CAnimationEngine *v11; // rdx
  LPVOID *ppv; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  LPVOID *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  CAnimationEngine *v20; // rcx
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  CDisplayBroker *v25; // [rsp+68h] [rbp+10h] BYREF

  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopDisplayBroker>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_DesktopDisplayBroker>::GetImpl'::`2'::impl,
    a2);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HandleEnsureDDisplayManagerFail>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_HandleEnsureDDisplayManagerFail>::GetImpl'::`2'::impl) )
  {
    v3 = CDesktopManager::EnsureDDisplayManager((CDesktopManager *)this);
    Instance = v3;
    if ( v3 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v3, 0x681u, 0);
      goto LABEL_29;
    }
  }
  else
  {
    Instance = 0;
    CDesktopManager::EnsureDDisplayManager((CDesktopManager *)this);
  }
  if ( !this[27] )
  {
    v8 = operator new(8u);
    if ( v8 )
      v9 = (CDisplayBroker *)std::unique_ptr<CMilChannel>::unique_ptr<CMilChannel>(v8);
    else
      v9 = 0;
    v25 = v9;
    if ( !v9 )
    {
      Instance = -2147024882;
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147024882, 0x68Eu, 0);
LABEL_11:
      std::unique_ptr<CDisplayBroker>::~unique_ptr<CDisplayBroker>(&v25);
      goto LABEL_29;
    }
    v10 = CDisplayBroker::Initialize(v9, *((struct Windows::Devices::Display::Core::IDisplayManager **)this[159] + 2));
    Instance = v10;
    if ( v10 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v10, 0x68Fu, 0);
      goto LABEL_11;
    }
    v25 = 0;
    v11 = this[27];
    this[27] = v9;
    if ( v11 )
      std::default_delete<CDisplayBroker>::operator()();
    std::unique_ptr<CDisplayBroker>::~unique_ptr<CDisplayBroker>(&v25);
  }
  if ( !this[33] )
  {
    ppv = (LPVOID *)winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
                      this + 34,
                      v4,
                      v5,
                      v6);
    Instance = CoCreateInstance(
                 &CLSID_UIAnimationTransitionLibrary2,
                 0,
                 1u,
                 &GUID_03cfae53_9580_4ee3_b363_2ece51b4af6a,
                 ppv);
    if ( Instance >= 0 )
    {
      v16 = (LPVOID *)winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
                        this + 33,
                        v13,
                        v14,
                        v15);
      Instance = CoCreateInstance(&CLSID_UIAnimationManager2, 0, 1u, &GUID_d8b6f7d4_4109_4d3f_acee_879926968cb1, v16);
      if ( Instance >= 0 )
      {
        v20 = this[22];
        if ( *((_BYTE *)v20 + 120) )
          goto LABEL_29;
        Instance = CAnimationEngine::Initialize(v20, v17, v18, v19);
      }
    }
    if ( Instance == -2147024770 )
    {
      if ( (unsigned int)dword_1801150F8 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801150F8, 1) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          &dword_1801150F8,
          &unk_180100F7D,
          0);
      Instance = 0;
    }
    else if ( Instance < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, Instance, 0x6B5u, 0);
    }
  }
LABEL_29:
  if ( (unsigned int)dword_1801150F8 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801150F8, 1) )
  {
    LODWORD(v25) = Instance;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v21,
      (unsigned int)&unk_180100F44,
      v22,
      v23,
      (__int64)&v25);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800afb50  push    rbx
0x1800afb52  push    rsi
0x1800afb53  push    rdi
0x1800afb54  push    r14
0x1800afb56  sub     rsp, 38h
0x1800afb5a  mov     rdi, rcx
0x1800afb5d  mov     r14d, 1
0x1800afb63  mov     dl, r14b
0x1800afb66  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopDisplayBroker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopDisplayBroker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopDisplayBroker> `wil::Feature<__WilFeatureTraits_Feature_DesktopDisplayBroker>::GetImpl(void)'::`2'::impl
0x1800afb6d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopDisplayBroker@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopDisplayBroker>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800afb72  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HandleEnsureDDisplayManagerFail@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HandleEnsureDDisplayManagerFail@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HandleEnsureDDisplayManagerFail> `wil::Feature<__WilFeatureTraits_Feature_HandleEnsureDDisplayManagerFail>::GetImpl(void)'::`2'::impl
0x1800afb79  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_HandleEnsureDDisplayManagerFail@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HandleEnsureDDisplayManagerFail>::__private_IsEnabled(void)
0x1800afb7e  mov     rcx, rdi; this
0x1800afb81  test    al, al
0x1800afb83  jz      short loc_1800AFBA9
0x1800afb85  call    ?EnsureDDisplayManager@CDesktopManager@@AEAAJXZ; CDesktopManager::EnsureDDisplayManager(void)
0x1800afb8a  mov     ebx, eax
0x1800afb8c  test    eax, eax
0x1800afb8e  jns     short loc_1800AFBB0
0x1800afb90  mov     [rsp+58h+var_30], 0
0x1800afb99  mov     dword ptr [rsp+58h+ppv], 681h
0x1800afba1  mov     r9d, eax
0x1800afba4  jmp     loc_1800AFD54
0x1800afba9  xor     ebx, ebx
0x1800afbab  call    ?EnsureDDisplayManager@CDesktopManager@@AEAAJXZ; CDesktopManager::EnsureDDisplayManager(void)
0x1800afbb0  cmp     qword ptr [rdi+0D8h], 0
0x1800afbb8  jnz     loc_1800AFC61
0x1800afbbe  mov     ecx, 8; unsigned __int64
0x1800afbc3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800afbc8  test    rax, rax
0x1800afbcb  jz      short loc_1800AFBDA
0x1800afbcd  mov     rcx, rax
0x1800afbd0  call    ??$?0U?$default_delete@VCMilChannel@@@std@@$0A@@?$unique_ptr@VCMilChannel@@U?$default_delete@VCMilChannel@@@std@@@std@@QEAA@XZ; std::unique_ptr<CMilChannel>::unique_ptr<CMilChannel>(void)
0x1800afbd5  mov     rsi, rax
0x1800afbd8  jmp     short loc_1800AFBDC
0x1800afbda  xor     esi, esi
0x1800afbdc  mov     [rsp+58h+arg_8], rsi
0x1800afbe1  test    rsi, rsi
0x1800afbe4  jnz     short loc_1800AFC18
0x1800afbe6  mov     ebx, 8007000Eh
0x1800afbeb  mov     [rsp+58h+var_30], rsi; void *
0x1800afbf0  mov     dword ptr [rsp+58h+ppv], 68Eh; unsigned int
0x1800afbf8  mov     r9d, ebx; int
0x1800afbfb  xor     r8d, r8d; unsigned int
0x1800afbfe  xor     edx, edx; int *
0x1800afc00  lea     ecx, [rdx+14h]; unsigned int
0x1800afc03  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800afc08  nop
0x1800afc09  lea     rcx, [rsp+58h+arg_8]
0x1800afc0e  call    ??1?$unique_ptr@VCDisplayBroker@@U?$default_delete@VCDisplayBroker@@@std@@@std@@QEAA@XZ; std::unique_ptr<CDisplayBroker>::~unique_ptr<CDisplayBroker>(void)
0x1800afc13  jmp     loc_1800AFD61
0x1800afc18  mov     rdx, [rdi+4F8h]
0x1800afc1f  mov     rdx, [rdx+10h]; struct Windows::Devices::Display::Core::IDisplayManager *
0x1800afc23  mov     rcx, rsi; this
0x1800afc26  call    ?Initialize@CDisplayBroker@@QEAAJPEAUIDisplayManager@Core@Display@Devices@Windows@@@Z; CDisplayBroker::Initialize(Windows::Devices::Display::Core::IDisplayManager *)
0x1800afc2b  mov     ebx, eax
0x1800afc2d  test    eax, eax
0x1800afc2f  js      loc_1800AFD23
0x1800afc35  mov     [rsp+58h+arg_8], 0
0x1800afc3e  mov     rdx, [rdi+0D8h]
0x1800afc45  mov     [rdi+0D8h], rsi
0x1800afc4c  test    rdx, rdx
0x1800afc4f  jz      short loc_1800AFC57
0x1800afc51  call    ??R?$default_delete@VCDisplayBroker@@@std@@QEBAXPEAVCDisplayBroker@@@Z; std::default_delete<CDisplayBroker>::operator()(CDisplayBroker *)
0x1800afc56  nop
0x1800afc57  lea     rcx, [rsp+58h+arg_8]
0x1800afc5c  call    ??1?$unique_ptr@VCDisplayBroker@@U?$default_delete@VCDisplayBroker@@@std@@@std@@QEAA@XZ; std::unique_ptr<CDisplayBroker>::~unique_ptr<CDisplayBroker>(void)
0x1800afc61  lea     rsi, [rdi+108h]
0x1800afc68  cmp     qword ptr [rsi], 0
0x1800afc6c  jnz     loc_1800AFD61
0x1800afc72  lea     rcx, [rsi+8]
0x1800afc76  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x1800afc7b  mov     [rsp+58h+ppv], rax; ppv
0x1800afc80  lea     r9, _GUID_03cfae53_9580_4ee3_b363_2ece51b4af6a; riid
0x1800afc87  mov     r8d, r14d; dwClsContext
0x1800afc8a  xor     edx, edx; pUnkOuter
0x1800afc8c  lea     rcx, CLSID_UIAnimationTransitionLibrary2; rclsid
0x1800afc93  call    cs:__imp_CoCreateInstance
0x1800afc99  mov     ebx, eax
0x1800afc9b  test    eax, eax
0x1800afc9d  js      short loc_1800AFCE3
0x1800afc9f  mov     rcx, rsi
0x1800afca2  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x1800afca7  mov     [rsp+58h+ppv], rax; ppv
0x1800afcac  lea     r9, _GUID_d8b6f7d4_4109_4d3f_acee_879926968cb1; riid
0x1800afcb3  mov     r8d, r14d; dwClsContext
0x1800afcb6  xor     edx, edx; pUnkOuter
0x1800afcb8  lea     rcx, CLSID_UIAnimationManager2; rclsid
0x1800afcbf  call    cs:__imp_CoCreateInstance
0x1800afcc5  mov     ebx, eax
0x1800afcc7  test    eax, eax
0x1800afcc9  js      short loc_1800AFCE3
0x1800afccb  mov     rcx, [rdi+0B0h]; this
0x1800afcd2  cmp     byte ptr [rcx+78h], 0
0x1800afcd6  jnz     loc_1800AFD61
0x1800afcdc  call    ?Initialize@CAnimationEngine@@QEAAJXZ; CAnimationEngine::Initialize(void)
0x1800afce1  mov     ebx, eax
0x1800afce3  cmp     ebx, 8007007Eh
0x1800afce9  jnz     short loc_1800AFD3C
0x1800afceb  mov     eax, cs:dword_1801150F8
0x1800afcf1  cmp     eax, 4
0x1800afcf4  jbe     short loc_1800AFD1F
0x1800afcf6  mov     rdx, r14
0x1800afcf9  lea     rcx, dword_1801150F8
0x1800afd00  call    _tlgKeywordOn
0x1800afd05  test    al, al
0x1800afd07  jz      short loc_1800AFD1F
0x1800afd09  xor     r8d, r8d
0x1800afd0c  lea     rdx, unk_180100F7D
0x1800afd13  lea     rcx, dword_1801150F8
0x1800afd1a  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800afd1f  xor     ebx, ebx
0x1800afd21  jmp     short loc_1800AFD61
0x1800afd23  mov     [rsp+58h+var_30], 0
0x1800afd2c  mov     dword ptr [rsp+58h+ppv], 68Fh
0x1800afd34  mov     r9d, eax
0x1800afd37  jmp     loc_1800AFBFB
0x1800afd3c  test    ebx, ebx
0x1800afd3e  jns     short loc_1800AFD61
0x1800afd40  mov     [rsp+58h+var_30], 0; void *
0x1800afd49  mov     dword ptr [rsp+58h+ppv], 6B5h; unsigned int
0x1800afd51  mov     r9d, ebx; int
0x1800afd54  xor     r8d, r8d; unsigned int
0x1800afd57  xor     edx, edx; int *
0x1800afd59  lea     ecx, [rdx+14h]; unsigned int
0x1800afd5c  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800afd61  mov     eax, cs:dword_1801150F8
0x1800afd67  cmp     eax, 4
0x1800afd6a  jbe     short loc_1800AFD99
0x1800afd6c  mov     rdx, r14
0x1800afd6f  lea     rcx, dword_1801150F8
0x1800afd76  call    _tlgKeywordOn
0x1800afd7b  test    al, al
0x1800afd7d  jz      short loc_1800AFD99
0x1800afd7f  mov     dword ptr [rsp+58h+arg_8], ebx
0x1800afd83  lea     rax, [rsp+58h+arg_8]
0x1800afd88  mov     [rsp+58h+ppv], rax
0x1800afd8d  lea     rdx, unk_180100F44
0x1800afd94  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800afd99  mov     eax, ebx
0x1800afd9b  add     rsp, 38h
0x1800afd9f  pop     r14
0x1800afda1  pop     rdi
0x1800afda2  pop     rsi
0x1800afda3  pop     rbx
0x1800afda4  retn
```
