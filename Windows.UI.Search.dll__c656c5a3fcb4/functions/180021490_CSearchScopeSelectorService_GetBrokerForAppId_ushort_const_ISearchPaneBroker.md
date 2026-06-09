# CSearchScopeSelectorService::GetBrokerForAppId(ushort const *,ISearchPaneBroker * *)

- ea: `0x180021490`
- end: `0x1800216ba`
- name: `?GetBrokerForAppId@CSearchScopeSelectorService@@UEAAJPEBGPEAPEAUISearchPaneBroker@@@Z`
- size: `554`
- prototype: `int(CSearchScopeSelectorService *__hidden this, const unsigned __int16 *, struct ISearchPaneBroker **)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180007b3c`
- `0x180021490`
- `0x180024eac`
- `0x1800254ac`
- `0x1800264bc`
- `0x180032418`
- `0x18007b010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x180021527`
- `SHCORE!IUnknown_QueryService` at `0x180021596`
- `SHCORE!IUnknown_QueryService` at `0x180021527`
- `SHCORE!IUnknown_QueryService` at `0x180021596`
- `SHCORE!IUnknown_SetSite` at `0x18002161f`
- `SHCORE!IUnknown_SetSite` at `0x18002161f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CSearchScopeSelectorService::GetBrokerForAppId(
        IUnknown **this,
        const unsigned __int16 *a2,
        struct ISearchPaneBroker **a3)
{
  CSearchScopeSelectorService *v6; // r12
  int v7; // ebx
  struct ISearchPaneBroker *v8; // rax
  void *v9; // rdi
  __int64 (__fastcall *v10)(void *, const unsigned __int16 *, __int64 *); // rbx
  __int64 v11; // r8
  struct ISearchPaneBroker *v12; // rax
  __int64 v14; // [rsp+20h] [rbp-20h] BYREF
  void *ppvOut; // [rsp+28h] [rbp-18h] BYREF
  __int64 v16; // [rsp+30h] [rbp-10h] BYREF
  void *v17; // [rsp+38h] [rbp-8h] BYREF
  IUnknown *punk; // [rsp+80h] [rbp+40h] BYREF
  __int64 (__fastcall ***v19)(_QWORD, GUID *, IUnknown **); // [rsp+90h] [rbp+50h] BYREF
  void *v20; // [rsp+98h] [rbp+58h] BYREF

  *a3 = 0;
  punk = 0;
  v6 = (CSearchScopeSelectorService *)(this - 10);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&punk);
  v7 = CSearchScopeSelectorService::_LookupBroker(v6, a2, &GUID_edac73e0_7bd0_4a38_b4dd_f2d0d4eb9da6, (void **)&punk);
  if ( v7 >= 0 )
  {
    v8 = (struct ISearchPaneBroker *)punk;
    if ( punk )
    {
      punk = 0;
      *a3 = v8;
    }
    else
    {
      ppvOut = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
      v7 = IUnknown_QueryService(
             *(this - 8),
             (const GUID *const)&SID_ImmersiveApplicationArrayService,
             &GUID_a3c23ab7_6be2_4778_8eb0_1adb7977f76a,
             &ppvOut);
      if ( v7 >= 0 )
      {
        v14 = 0;
        v9 = ppvOut;
        v10 = *(__int64 (__fastcall **)(void *, const unsigned __int16 *, __int64 *))(*(_QWORD *)ppvOut + 32LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v14);
        v7 = v10(v9, a2, &v14);
        if ( v7 >= 0 )
        {
          v20 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v20);
          v7 = IUnknown_QueryService(
                 this[8],
                 &IID_ISearchControlClient,
                 &GUID_510e2e14_c900_4b1b_a81c_a5ddb0dfa079,
                 &v20);
          if ( v7 >= 0 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&punk);
            v16 = v14;
            v17 = v20;
            punk = 0;
            v19 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v19);
            v7 = Microsoft::WRL::Details::MakeAndInitialize<CSearchPaneBroker,IUnknown,ISearchControlClient * &,IImmersiveApplication * &>(
                   &v19,
                   &v17,
                   &v16);
            if ( v7 >= 0 )
              v7 = (**v19)(v19, &GUID_edac73e0_7bd0_4a38_b4dd_f2d0d4eb9da6, &punk);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v19);
            if ( v7 >= 0 )
            {
              IUnknown_SetSite(punk, (IUnknown *)v6);
              v7 = CSearchScopeSelectorService::_CacheBroker(v6, a2, (struct ISearchPaneBroker *)punk);
              if ( v7 >= 0 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 4u )
                {
                  WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 22), 13, v11, a2);
                }
                v12 = (struct ISearchPaneBroker *)punk;
                punk = 0;
                *a3 = v12;
              }
            }
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v20);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v14);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&punk);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180021490  push    rbp
0x180021492  push    rbx
0x180021493  push    rsi
0x180021494  push    rdi
0x180021495  push    r12
0x180021497  push    r14
0x180021499  push    r15
0x18002149b  mov     rbp, rsp
0x18002149e  sub     rsp, 40h
0x1800214a2  mov     rsi, r8
0x1800214a5  mov     r14, rdx
0x1800214a8  mov     r15, rcx
0x1800214ab  mov     qword ptr [r8], 0
0x1800214b2  mov     [rbp+punk], 0
0x1800214ba  lea     r12, [rcx-50h]
0x1800214be  lea     rcx, [rbp+punk]
0x1800214c2  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800214c7  lea     r9, [rbp+punk]; void **
0x1800214cb  lea     r8, _GUID_edac73e0_7bd0_4a38_b4dd_f2d0d4eb9da6; struct _GUID *
0x1800214d2  mov     rdx, r14; unsigned __int16 *
0x1800214d5  mov     rcx, r12; this
0x1800214d8  call    ?_LookupBroker@CSearchScopeSelectorService@@AEAAJPEBGAEBU_GUID@@PEAPEAX@Z; CSearchScopeSelectorService::_LookupBroker(ushort const *,_GUID const &,void * *)
0x1800214dd  mov     ebx, eax
0x1800214df  test    eax, eax
0x1800214e1  js      loc_1800216A0
0x1800214e7  mov     rax, [rbp+punk]
0x1800214eb  test    rax, rax
0x1800214ee  jz      short loc_180021500
0x1800214f0  mov     [rbp+punk], 0
0x1800214f8  mov     [rsi], rax
0x1800214fb  jmp     loc_1800216A0
0x180021500  mov     [rbp+ppvOut], 0
0x180021508  lea     rcx, [rbp+ppvOut]
0x18002150c  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180021511  lea     r9, [rbp+ppvOut]; ppvOut
0x180021515  lea     r8, _GUID_a3c23ab7_6be2_4778_8eb0_1adb7977f76a; riid
0x18002151c  lea     rdx, SID_ImmersiveApplicationArrayService; guidService
0x180021523  mov     rcx, [r15-40h]; punk
0x180021527  call    cs:__imp_IUnknown_QueryService
0x18002152d  mov     ebx, eax
0x18002152f  test    eax, eax
0x180021531  js      loc_180021696
0x180021537  mov     [rbp+var_20], 0
0x18002153f  mov     rdi, [rbp+ppvOut]
0x180021543  mov     rax, [rdi]
0x180021546  mov     rbx, [rax+20h]
0x18002154a  lea     rcx, [rbp+var_20]
0x18002154e  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180021553  lea     r8, [rbp+var_20]
0x180021557  mov     rdx, r14
0x18002155a  mov     rcx, rdi
0x18002155d  mov     rax, rbx
0x180021560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021565  mov     ebx, eax
0x180021567  test    eax, eax
0x180021569  js      loc_18002168C
0x18002156f  mov     [rbp+arg_18], 0
0x180021577  lea     rcx, [rbp+arg_18]
0x18002157b  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180021580  lea     r9, [rbp+arg_18]; ppvOut
0x180021584  lea     r8, _GUID_510e2e14_c900_4b1b_a81c_a5ddb0dfa079; riid
0x18002158b  lea     rdx, IID_ISearchControlClient; guidService
0x180021592  mov     rcx, [r15+40h]; punk
0x180021596  call    cs:__imp_IUnknown_QueryService
0x18002159c  mov     ebx, eax
0x18002159e  test    eax, eax
0x1800215a0  js      loc_180021682
0x1800215a6  lea     rcx, [rbp+punk]
0x1800215aa  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800215af  mov     rax, [rbp+var_20]
0x1800215b3  mov     [rbp+var_10], rax
0x1800215b7  mov     rax, [rbp+arg_18]
0x1800215bb  mov     [rbp+var_8], rax
0x1800215bf  mov     [rbp+punk], 0
0x1800215c7  mov     [rbp+arg_10], 0
0x1800215cf  lea     rcx, [rbp+arg_10]
0x1800215d3  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800215d8  lea     r8, [rbp+var_10]
0x1800215dc  lea     rdx, [rbp+var_8]
0x1800215e0  lea     rcx, [rbp+arg_10]
0x1800215e4  call    ??$MakeAndInitialize@VCSearchPaneBroker@@UIUnknown@@AEAPEAUISearchControlClient@@AEAPEAUIImmersiveApplication@@@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@AEAPEAUISearchControlClient@@AEAPEAUIImmersiveApplication@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CSearchPaneBroker,IUnknown,ISearchControlClient * &,IImmersiveApplication * &>(IUnknown * *,ISearchControlClient * &,IImmersiveApplication * &)
0x1800215e9  mov     ebx, eax
0x1800215eb  test    eax, eax
0x1800215ed  js      short loc_18002160B
0x1800215ef  mov     rcx, [rbp+arg_10]
0x1800215f3  mov     rax, [rcx]
0x1800215f6  lea     r8, [rbp+punk]
0x1800215fa  lea     rdx, _GUID_edac73e0_7bd0_4a38_b4dd_f2d0d4eb9da6
0x180021601  mov     rax, [rax]
0x180021604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021609  mov     ebx, eax
0x18002160b  lea     rcx, [rbp+arg_10]
0x18002160f  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180021614  test    ebx, ebx
0x180021616  js      short loc_180021682
0x180021618  mov     rdx, r12; punkSite
0x18002161b  mov     rcx, [rbp+punk]; punk
0x18002161f  call    cs:__imp_IUnknown_SetSite
0x180021625  mov     r8, [rbp+punk]; struct ISearchPaneBroker *
0x180021629  mov     rdx, r14; unsigned __int16 *
0x18002162c  mov     rcx, r12; this
0x18002162f  call    ?_CacheBroker@CSearchScopeSelectorService@@AEAAJPEBGPEAUISearchPaneBroker@@@Z; CSearchScopeSelectorService::_CacheBroker(ushort const *,ISearchPaneBroker *)
0x180021634  mov     ebx, eax
0x180021636  test    eax, eax
0x180021638  js      short loc_180021682
0x18002163a  lea     rax, WPP_GLOBAL_Control
0x180021641  mov     rcx, cs:WPP_GLOBAL_Control
0x180021648  cmp     rcx, rax
0x18002164b  jz      short loc_180021673
0x18002164d  test    byte ptr [rcx+0BCh], 1
0x180021654  jz      short loc_180021673
0x180021656  cmp     byte ptr [rcx+0B9h], 4
0x18002165d  jb      short loc_180021673
0x18002165f  mov     edx, 0Dh
0x180021664  mov     r9, r14
0x180021667  mov     rcx, [rcx+0B0h]
0x18002166e  call    WPP_SF_S
0x180021673  mov     rax, [rbp+punk]
0x180021677  mov     [rbp+punk], 0
0x18002167f  mov     [rsi], rax
0x180021682  lea     rcx, [rbp+arg_18]
0x180021686  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002168b  nop
0x18002168c  lea     rcx, [rbp+var_20]
0x180021690  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180021695  nop
0x180021696  lea     rcx, [rbp+ppvOut]
0x18002169a  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002169f  nop
0x1800216a0  lea     rcx, [rbp+punk]
0x1800216a4  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800216a9  mov     eax, ebx
0x1800216ab  add     rsp, 40h
0x1800216af  pop     r15
0x1800216b1  pop     r14
0x1800216b3  pop     r12
0x1800216b5  pop     rdi
0x1800216b6  pop     rsi
0x1800216b7  pop     rbx
0x1800216b8  pop     rbp
0x1800216b9  retn
```
