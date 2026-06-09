# CSearchPaneBroker::_EnsureSearchPaneScopeAndVisibility(ushort const *,ushort const *,ushort const *,SEARCHPANE_CLIENT_STATE_FLAGS)

- ea: `0x180038c1c`
- end: `0x180039026`
- name: `?_EnsureSearchPaneScopeAndVisibility@CSearchPaneBroker@@AEAAJPEBG00W4SEARCHPANE_CLIENT_STATE_FLAGS@@@Z`
- size: `1034`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800381f0`

## callees

- `0x180007b3c`
- `0x18000f2a8`
- `0x180015464`
- `0x180015878`
- `0x180038c1c`
- `0x1800393ac`
- `0x1800393fc`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x180038c75`
- `SHCORE!IUnknown_QueryService` at `0x180038d26`
- `SHCORE!IUnknown_QueryService` at `0x180038c75`
- `SHCORE!IUnknown_QueryService` at `0x180038d26`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x180038e00`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x180038e98`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x180038f39`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x180038e00`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x180038e98`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x180038f39`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CSearchPaneBroker::_EnsureSearchPaneScopeAndVisibility(
        IUnknown **a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        char a5)
{
  HRESULT v9; // esi
  void *v10; // rdi
  __int64 (__fastcall *v11)(void *, _QWORD, GUID *, GUID *, void **); // rbx
  void *v12; // rdi
  void (__fastcall *v13)(void *, _QWORD); // rbx
  __int64 v14; // rax
  void *v15; // rdi
  __int64 (__fastcall *v16)(void *, _QWORD, GUID *, void **); // rbx
  void *v17; // rsi
  __int64 (__fastcall *v18)(void *, __int64, void *, _BYTE *); // rdi
  void *v19; // rbx
  void *v20; // rsi
  __int64 (__fastcall *v21)(void *, __int64, void *, _BYTE *); // rdi
  void *v22; // rbx
  void *v23; // rsi
  __int64 (__fastcall *v24)(void *, __int64, void *, _BYTE *); // rdi
  void *v25; // rbx
  _BYTE v27[8]; // [rsp+30h] [rbp-50h] BYREF
  void *ppv; // [rsp+38h] [rbp-48h] BYREF
  void *v29; // [rsp+40h] [rbp-40h] BYREF
  void *ppvOut; // [rsp+48h] [rbp-38h] BYREF
  __int64 v31; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER propvar; // [rsp+58h] [rbp-28h] BYREF
  __int64 v33; // [rsp+70h] [rbp-10h]

  v31 = a4;
  ppvOut = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
  v9 = IUnknown_QueryService(
         a1[8],
         &GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd,
         &GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd,
         &ppvOut);
  if ( v9 >= 0 )
  {
    if ( CSearchPaneBroker::_IsSearchPaneVisible((CSearchPaneBroker *)a1) )
    {
      ppv = 0;
      v10 = ppvOut;
      v11 = *(__int64 (__fastcall **)(void *, _QWORD, GUID *, GUID *, void **))(*(_QWORD *)ppvOut + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
      v9 = v11(v10, 0, &GUID_52f077cc_10e3_40ea_ad6d_9313803f91f3, &GUID_52f077cc_10e3_40ea_ad6d_9313803f91f3, &ppv);
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppv + 40LL))(ppv, a2, 1);
        if ( v9 >= 0 )
        {
          v29 = 0;
          if ( a4 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v29);
            if ( IUnknown_QueryService(
                   a1[8],
                   (const GUID *const)&SID_SearchBox,
                   &GUID_aa90700f_2340_46a7_ab00_867fd691ecee,
                   &v29) >= 0 )
            {
              v12 = v29;
              v13 = *(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)v29 + 72LL);
              v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&propvar, &v31);
              v13(v12, *(_QWORD *)(v14 + 24));
            }
          }
          LogSqmPointForSearchScopeSelection(0, 0, a2, 1, a3 != 0);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v29);
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
    }
    else
    {
      v29 = 0;
      v15 = ppvOut;
      v16 = *(__int64 (__fastcall **)(void *, _QWORD, GUID *, void **))(*(_QWORD *)ppvOut + 40LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v29);
      v9 = v16(v15, 0, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v29);
      if ( v9 >= 0 )
      {
        if ( !a3 )
          goto LABEL_15;
        ppv = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
        LOWORD(propvar.Reserved.Reserved1) = 31;
        *(_QWORD *)&propvar.Reserved.Reserved2[8] = a3;
        v9 = PropVariantToWinRTPropertyValue(
               &propvar.Reserved.Reserved1,
               &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
               &ppv);
        if ( v9 >= 0 )
        {
          v27[0] = 0;
          v17 = v29;
          v18 = *(__int64 (__fastcall **)(void *, __int64, void *, _BYTE *))(*(_QWORD *)v29 + 80LL);
          v19 = ppv;
          v33 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&propvar, L"QueryText", 0xAu, 9u);
          v9 = v18(v17, v33, v19, v27);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
        if ( v9 >= 0 )
        {
LABEL_15:
          ppv = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
          LOWORD(propvar.Reserved.Reserved1) = 31;
          *(_QWORD *)&propvar.Reserved.Reserved2[8] = a2;
          v9 = PropVariantToWinRTPropertyValue(
                 &propvar.Reserved.Reserved1,
                 &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                 &ppv);
          if ( v9 >= 0 )
          {
            v27[0] = 0;
            v20 = v29;
            v21 = *(__int64 (__fastcall **)(void *, __int64, void *, _BYTE *))(*(_QWORD *)v29 + 80LL);
            v22 = ppv;
            v33 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&propvar, L"AppId", 6u, 5u);
            v9 = v21(v20, v33, v22, v27);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
          if ( v9 >= 0 )
          {
            if ( !a4 )
              goto LABEL_22;
            ppv = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
            LOWORD(propvar.Reserved.Reserved1) = 31;
            *(_QWORD *)&propvar.Reserved.Reserved2[8] = a4;
            v9 = PropVariantToWinRTPropertyValue(
                   &propvar.Reserved.Reserved1,
                   &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                   &ppv);
            if ( v9 >= 0 )
            {
              v27[0] = 0;
              v23 = v29;
              v24 = *(__int64 (__fastcall **)(void *, __int64, void *, _BYTE *))(*(_QWORD *)v29 + 80LL);
              v25 = ppv;
              v33 = 0;
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(&propvar, L"CueText", 8u, 7u);
              v9 = v24(v23, v33, v25, v27);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
            if ( v9 >= 0 )
            {
LABEL_22:
              v9 = CSearchPaneBroker::_SetViewMonitorForApplication((CSearchPaneBroker *)a1);
              if ( v9 >= 0 )
              {
                if ( (a5 & 8) != 0 )
                  (*(void (__fastcall **)(void *, __int64, bool))(*(_QWORD *)ppvOut + 56LL))(ppvOut, 1, a3 != 0);
                v9 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD))(*(_QWORD *)ppvOut + 24LL))(ppvOut, 0, 0);
              }
            }
          }
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v29);
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180038c1c  mov     [rsp-38h+arg_10], rbx
0x180038c21  push    rbp
0x180038c22  push    rsi
0x180038c23  push    rdi
0x180038c24  push    r12
0x180038c26  push    r13
0x180038c28  push    r14
0x180038c2a  push    r15
0x180038c2c  mov     rbp, rsp
0x180038c2f  sub     rsp, 80h
0x180038c36  mov     rax, cs:__security_cookie
0x180038c3d  xor     rax, rsp
0x180038c40  mov     [rbp+var_8], rax
0x180038c44  mov     r14, r9
0x180038c47  mov     r15, r8
0x180038c4a  mov     r12, rdx
0x180038c4d  mov     r13, rcx
0x180038c50  mov     [rbp+var_30], r9
0x180038c54  xor     ebx, ebx
0x180038c56  mov     [rbp+ppvOut], rbx
0x180038c5a  lea     rcx, [rbp+ppvOut]
0x180038c5e  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180038c63  lea     r9, [rbp+ppvOut]; ppvOut
0x180038c67  lea     rdx, _GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd; guidService
0x180038c6e  mov     r8, rdx; riid
0x180038c71  mov     rcx, [r13+40h]; punk
0x180038c75  call    cs:__imp_IUnknown_QueryService
0x180038c7b  mov     esi, eax
0x180038c7d  test    eax, eax
0x180038c7f  js      loc_180038FF4
0x180038c85  mov     rcx, r13; this
0x180038c88  call    ?_IsSearchPaneVisible@CSearchPaneBroker@@AEAA_NXZ; CSearchPaneBroker::_IsSearchPaneVisible(void)
0x180038c8d  test    al, al
0x180038c8f  jz      loc_180038D90
0x180038c95  mov     [rbp+ppv], rbx
0x180038c99  mov     rdi, [rbp+ppvOut]
0x180038c9d  mov     rax, [rdi]
0x180038ca0  mov     rbx, [rax+30h]
0x180038ca4  lea     rcx, [rbp+ppv]
0x180038ca8  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180038cad  lea     rax, [rbp+ppv]
0x180038cb1  mov     [rsp+80h+var_60], rax
0x180038cb6  lea     r8, _GUID_52f077cc_10e3_40ea_ad6d_9313803f91f3
0x180038cbd  mov     r9, r8
0x180038cc0  xor     edx, edx
0x180038cc2  mov     rcx, rdi
0x180038cc5  mov     rax, rbx
0x180038cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038ccd  mov     esi, eax
0x180038ccf  test    eax, eax
0x180038cd1  js      loc_180038D82
0x180038cd7  mov     rcx, [rbp+ppv]
0x180038cdb  mov     rax, [rcx]
0x180038cde  mov     r8d, 1
0x180038ce4  mov     rdx, r12
0x180038ce7  mov     rax, [rax+28h]
0x180038ceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038cf0  mov     esi, eax
0x180038cf2  test    eax, eax
0x180038cf4  js      loc_180038D82
0x180038cfa  mov     [rbp+var_40], 0
0x180038d02  test    r14, r14
0x180038d05  jz      short loc_180038D59
0x180038d07  lea     rcx, [rbp+var_40]
0x180038d0b  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180038d10  lea     r9, [rbp+var_40]; ppvOut
0x180038d14  lea     r8, _GUID_aa90700f_2340_46a7_ab00_867fd691ecee; riid
0x180038d1b  lea     rdx, SID_SearchBox; guidService
0x180038d22  mov     rcx, [r13+40h]; punk
0x180038d26  call    cs:__imp_IUnknown_QueryService
0x180038d2c  test    eax, eax
0x180038d2e  js      short loc_180038D59
0x180038d30  mov     rdi, [rbp+var_40]
0x180038d34  mov     rax, [rdi]
0x180038d37  mov     rbx, [rax+48h]
0x180038d3b  lea     rdx, [rbp+var_30]
0x180038d3f  lea     rcx, [rbp+propvar]
0x180038d43  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180038d48  nop
0x180038d49  mov     rdx, [rax+18h]
0x180038d4d  mov     rcx, rdi
0x180038d50  mov     rax, rbx
0x180038d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d58  nop
0x180038d59  xor     eax, eax
0x180038d5b  test    r15, r15
0x180038d5e  setnz   al
0x180038d61  mov     dword ptr [rsp+80h+var_60], eax
0x180038d65  mov     r9d, 1
0x180038d6b  mov     r8, r12
0x180038d6e  xor     edx, edx
0x180038d70  xor     ecx, ecx
0x180038d72  call    LogSqmPointForSearchScopeSelection
0x180038d77  nop
0x180038d78  lea     rcx, [rbp+var_40]
0x180038d7c  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180038d81  nop
0x180038d82  lea     rcx, [rbp+ppv]
0x180038d86  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180038d8b  jmp     loc_180038FF4
0x180038d90  mov     [rbp+var_40], rbx
0x180038d94  mov     rdi, [rbp+ppvOut]
0x180038d98  mov     rax, [rdi]
0x180038d9b  mov     rbx, [rax+28h]
0x180038d9f  lea     rcx, [rbp+var_40]
0x180038da3  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180038da8  lea     r9, [rbp+var_40]
0x180038dac  lea     r8, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180038db3  xor     edx, edx
0x180038db5  mov     rcx, rdi
0x180038db8  mov     rax, rbx
0x180038dbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038dc0  mov     esi, eax
0x180038dc2  test    eax, eax
0x180038dc4  js      loc_180038FEA
0x180038dca  mov     ebx, 1Fh
0x180038dcf  test    r15, r15
0x180038dd2  jz      loc_180038E70
0x180038dd8  mov     [rbp+ppv], 0
0x180038de0  lea     rcx, [rbp+ppv]
0x180038de4  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180038de9  mov     word ptr [rbp+propvar], bx
0x180038ded  mov     [rbp+var_20], r15
0x180038df1  lea     r8, [rbp+ppv]; ppv
0x180038df5  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; riid
0x180038dfc  lea     rcx, [rbp+propvar]; propvar
0x180038e00  call    cs:__imp_PropVariantToWinRTPropertyValue
0x180038e06  mov     esi, eax
0x180038e08  test    eax, eax
0x180038e0a  js      short loc_180038E5F
0x180038e0c  mov     [rbp+var_50], 0
0x180038e10  mov     rsi, [rbp+var_40]
0x180038e14  mov     rax, [rsi]
0x180038e17  mov     rdi, [rax+50h]
0x180038e1b  mov     rbx, [rbp+ppv]
0x180038e1f  mov     [rbp+var_10], 0
0x180038e27  mov     r9d, 9; unsigned int
0x180038e2d  lea     r8d, [r9+1]; unsigned int
0x180038e31  lea     rdx, aQuerytext; "QueryText"
0x180038e38  lea     rcx, [rbp+propvar]; hstringHeader
0x180038e3c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180038e41  nop
0x180038e42  lea     r9, [rbp+var_50]
0x180038e46  mov     r8, rbx
0x180038e49  mov     rdx, [rbp+var_10]
0x180038e4d  mov     rcx, rsi
0x180038e50  mov     rax, rdi
0x180038e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e58  mov     esi, eax
0x180038e5a  mov     ebx, 1Fh
0x180038e5f  lea     rcx, [rbp+ppv]
0x180038e63  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180038e68  test    esi, esi
0x180038e6a  js      loc_180038FEA
0x180038e70  mov     [rbp+ppv], 0
0x180038e78  lea     rcx, [rbp+ppv]
0x180038e7c  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180038e81  mov     word ptr [rbp+propvar], bx
0x180038e85  mov     [rbp+var_20], r12
0x180038e89  lea     r8, [rbp+ppv]; ppv
0x180038e8d  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; riid
0x180038e94  lea     rcx, [rbp+propvar]; propvar
0x180038e98  call    cs:__imp_PropVariantToWinRTPropertyValue
0x180038e9e  mov     esi, eax
0x180038ea0  test    eax, eax
0x180038ea2  js      short loc_180038EF7
0x180038ea4  mov     [rbp+var_50], 0
0x180038ea8  mov     rsi, [rbp+var_40]
0x180038eac  mov     rax, [rsi]
0x180038eaf  mov     rdi, [rax+50h]
0x180038eb3  mov     rbx, [rbp+ppv]
0x180038eb7  mov     [rbp+var_10], 0
0x180038ebf  mov     r9d, 5; unsigned int
0x180038ec5  lea     r8d, [r9+1]; unsigned int
0x180038ec9  lea     rdx, aAppid; "AppId"
0x180038ed0  lea     rcx, [rbp+propvar]; hstringHeader
0x180038ed4  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180038ed9  nop
0x180038eda  lea     r9, [rbp+var_50]
0x180038ede  mov     r8, rbx
0x180038ee1  mov     rdx, [rbp+var_10]
0x180038ee5  mov     rcx, rsi
0x180038ee8  mov     rax, rdi
0x180038eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038ef0  mov     esi, eax
0x180038ef2  mov     ebx, 1Fh
0x180038ef7  lea     rcx, [rbp+ppv]
0x180038efb  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180038f00  test    esi, esi
0x180038f02  js      loc_180038FEA
0x180038f08  test    r14, r14
0x180038f0b  jz      loc_180038FA0
0x180038f11  mov     [rbp+ppv], 0
0x180038f19  lea     rcx, [rbp+ppv]
0x180038f1d  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180038f22  mov     word ptr [rbp+propvar], bx
0x180038f26  mov     [rbp+var_20], r14
0x180038f2a  lea     r8, [rbp+ppv]; ppv
0x180038f2e  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; riid
0x180038f35  lea     rcx, [rbp+propvar]; propvar
0x180038f39  call    cs:__imp_PropVariantToWinRTPropertyValue
0x180038f3f  mov     esi, eax
0x180038f41  test    eax, eax
0x180038f43  js      short loc_180038F93
0x180038f45  mov     [rbp+var_50], 0
0x180038f49  mov     rsi, [rbp+var_40]
0x180038f4d  mov     rax, [rsi]
0x180038f50  mov     rdi, [rax+50h]
0x180038f54  mov     rbx, [rbp+ppv]
0x180038f58  mov     [rbp+var_10], 0
0x180038f60  mov     r9d, 7; unsigned int
0x180038f66  lea     r8d, [r9+1]; unsigned int
0x180038f6a  lea     rdx, aCuetext; "CueText"
0x180038f71  lea     rcx, [rbp+propvar]; hstringHeader
0x180038f75  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180038f7a  nop
0x180038f7b  lea     r9, [rbp+var_50]
0x180038f7f  mov     r8, rbx
0x180038f82  mov     rdx, [rbp+var_10]
0x180038f86  mov     rcx, rsi
0x180038f89  mov     rax, rdi
0x180038f8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f91  mov     esi, eax
0x180038f93  lea     rcx, [rbp+ppv]
0x180038f97  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180038f9c  test    esi, esi
0x180038f9e  js      short loc_180038FEA
0x180038fa0  mov     rcx, r13; this
0x180038fa3  call    ?_SetViewMonitorForApplication@CSearchPaneBroker@@AEAAJXZ; CSearchPaneBroker::_SetViewMonitorForApplication(void)
0x180038fa8  mov     esi, eax
0x180038faa  test    eax, eax
0x180038fac  js      short loc_180038FEA
0x180038fae  test    [rbp+arg_20], 8
0x180038fb2  jz      short loc_180038FD3
0x180038fb4  mov     rcx, [rbp+ppvOut]
0x180038fb8  mov     rax, [rcx]
0x180038fbb  xor     r8d, r8d
0x180038fbe  test    r15, r15
0x180038fc1  setnz   r8b
0x180038fc5  mov     edx, 1
0x180038fca  mov     rax, [rax+38h]
0x180038fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038fd3  mov     rcx, [rbp+ppvOut]
0x180038fd7  mov     rax, [rcx]
0x180038fda  xor     r8d, r8d
0x180038fdd  xor     edx, edx
0x180038fdf  mov     rax, [rax+18h]
0x180038fe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038fe8  mov     esi, eax
0x180038fea  lea     rcx, [rbp+var_40]
0x180038fee  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180038ff3  nop
0x180038ff4  lea     rcx, [rbp+ppvOut]
0x180038ff8  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180038ffd  mov     eax, esi
0x180038fff  mov     rcx, [rbp+var_8]
0x180039003  xor     rcx, rsp; StackCookie
0x180039006  call    __security_check_cookie
0x18003900b  mov     rbx, [rsp+80h+arg_10]
0x180039013  add     rsp, 80h
0x18003901a  pop     r15
0x18003901c  pop     r14
0x18003901e  pop     r13
0x180039020  pop     r12
0x180039022  pop     rdi
0x180039023  pop     rsi
0x180039024  pop     rbp
0x180039025  retn
```
