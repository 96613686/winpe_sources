# CSearchPaneViewDefinition::v_ShowView(ShowViewOptions,IInspectable *)

- ea: `0x1800142a0`
- end: `0x1800145a3`
- name: `?v_ShowView@CSearchPaneViewDefinition@@EEAA_NW4ShowViewOptions@@PEAUIInspectable@@@Z`
- size: `771`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180007b3c`
- `0x18000f2a8`
- `0x1800114f4`
- `0x180013fb4`
- `0x1800142a0`
- `0x180015adc`
- `0x180015c04`
- `0x180015d14`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014403`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014442`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001454b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014559`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014403`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014442`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001454b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014559`
- `SHCORE!IUnknown_QueryService` at `0x180014300`
- `SHCORE!IUnknown_QueryService` at `0x180014300`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x180014398`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x180014398`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
char __fastcall CSearchPaneViewDefinition::v_ShowView(__int64 a1, int a2)
{
  IUnknown **v4; // rax
  unsigned int v5; // ebx
  void *v6; // rdi
  int (__fastcall *v7)(void *, _QWORD, GUID *, __int64 *); // rbx
  __int64 v8; // rsi
  void (__fastcall *v9)(__int64, HSTRING, void *, _BYTE *); // rdi
  void *v10; // rbx
  bool v11; // bl
  HSTRING v12; // rdi
  char v14; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v15[7]; // [rsp+31h] [rbp-28h] BYREF
  __int64 v16; // [rsp+38h] [rbp-21h] BYREF
  HSTRING v17; // [rsp+40h] [rbp-19h] BYREF
  HSTRING string; // [rsp+48h] [rbp-11h] BYREF
  void *ppvOut; // [rsp+50h] [rbp-9h] BYREF
  void *ppv; // [rsp+58h] [rbp-1h] BYREF
  HSTRING_HEADER propvar; // [rsp+60h] [rbp+7h] BYREF
  HSTRING v22; // [rsp+78h] [rbp+1Fh]

  ppvOut = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
  v4 = (IUnknown **)CWRLObjectWithGITSite::SiteUnk(a1 + 8, &v17);
  v5 = (unsigned int)IUnknown_QueryService(
                       *v4,
                       &GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd,
                       &GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd,
                       &ppvOut) >> 31;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v17);
  if ( (unsigned __int8)v5 != 1 )
  {
    v16 = 0;
    v6 = ppvOut;
    v7 = *(int (__fastcall **)(void *, _QWORD, GUID *, __int64 *))(*(_QWORD *)ppvOut + 40LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v16);
    if ( v7(v6, 0, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v16) >= 0 )
    {
      if ( *(_BYTE *)(a1 + 196) && a2 == 1 )
      {
        ppv = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
        LOWORD(propvar.Reserved.Reserved1) = 11;
        *(_WORD *)&propvar.Reserved.Reserved2[8] = -1;
        if ( PropVariantToWinRTPropertyValue(
               &propvar.Reserved.Reserved1,
               &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
               &ppv) >= 0 )
        {
          v15[0] = 0;
          v8 = v16;
          v9 = *(void (__fastcall **)(__int64, HSTRING, void *, _BYTE *))(*(_QWORD *)v16 + 80LL);
          v10 = ppv;
          v22 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&propvar, L"ZeroInputDisabled", 0x12u, 0x11u);
          v9(v8, v22, v10, v15);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
      }
      else
      {
        *(_BYTE *)(a1 + 196) = 0;
      }
      v17 = 0;
      WindowsDeleteString(0);
      v17 = 0;
      v22 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&propvar, L"QueryText", 0xAu, 9u);
      GetKeyFromMapAsString(v16, v22, &v17);
      string = 0;
      WindowsDeleteString(0);
      string = 0;
      v22 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&propvar, L"CueText", 8u, 7u);
      GetKeyFromMapAsString(v16, v22, &string);
      v14 = 0;
      v22 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&propvar, L"ShouldSelectText", 0x11u, 0x10u);
      GetKeyFromMapAsBool(v16, v22, &v14);
      v11 = v14 != 0;
      v12 = string;
      v22 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &propvar,
        L"Windows.UI.Search.CurrentApp",
        0x1Du,
        0x1Cu);
      CSearchPaneViewDefinition::_SetQueryAndScope(
        (CSearchPaneViewDefinition *)a1,
        (struct ISearchServices *)ppvOut,
        v17,
        v22,
        v12,
        v11);
      RemoveKey(v16, L"QueryText");
      RemoveKey(v16, L"AppId");
      RemoveKey(v16, L"CueText");
      RemoveKey(v16, L"ShouldSelectText");
      RemoveKey(v16, L"RestoreScope");
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v17);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v16);
  }
  *(_DWORD *)(a1 + 192) = a2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
  return 0;
}

```

## disassembly

```asm
0x1800142a0  mov     [rsp-8+arg_8], rbx
0x1800142a5  mov     [rsp-8+arg_10], rsi
0x1800142aa  push    rbp
0x1800142ab  push    rdi
0x1800142ac  push    r12
0x1800142ae  push    r14
0x1800142b0  push    r15
0x1800142b2  lea     rbp, [rsp-37h]
0x1800142b7  sub     rsp, 90h
0x1800142be  mov     rax, cs:__security_cookie
0x1800142c5  xor     rax, rsp
0x1800142c8  mov     [rbp+57h+var_30], rax
0x1800142cc  mov     r15d, edx
0x1800142cf  mov     r14, rcx
0x1800142d2  xor     r12d, r12d
0x1800142d5  mov     [rbp+57h+ppvOut], r12
0x1800142d9  lea     rcx, [rbp+57h+ppvOut]
0x1800142dd  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800142e2  lea     rcx, [r14+8]
0x1800142e6  lea     rdx, [rbp+57h+var_70]
0x1800142ea  call    ?SiteUnk@CWRLObjectWithGITSite@@IEAA?AV?$ComPtr@UIUnknown@@@WRL@Microsoft@@XZ; CWRLObjectWithGITSite::SiteUnk(void)
0x1800142ef  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x1800142f3  lea     rdx, _GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd; guidService
0x1800142fa  mov     r8, rdx; riid
0x1800142fd  mov     rcx, [rax]; punk
0x180014300  call    cs:__imp_IUnknown_QueryService
0x180014306  mov     ebx, eax
0x180014308  shr     ebx, 1Fh
0x18001430b  lea     rcx, [rbp+57h+var_70]
0x18001430f  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180014314  xor     bl, 1
0x180014317  jz      loc_180014569
0x18001431d  mov     [rbp+57h+var_78], r12
0x180014321  mov     rdi, [rbp+57h+ppvOut]
0x180014325  mov     rax, [rdi]
0x180014328  mov     rbx, [rax+28h]
0x18001432c  lea     rcx, [rbp+57h+var_78]
0x180014330  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180014335  lea     r9, [rbp+57h+var_78]
0x180014339  lea     r8, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180014340  xor     edx, edx
0x180014342  mov     rcx, rdi
0x180014345  mov     rax, rbx
0x180014348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001434d  test    eax, eax
0x18001434f  js      loc_180014560
0x180014355  cmp     [r14+0C4h], r12b
0x18001435c  jz      loc_1800143F6
0x180014362  cmp     r15d, 1
0x180014366  jnz     loc_1800143F6
0x18001436c  mov     [rbp+57h+ppv], r12
0x180014370  lea     rcx, [rbp+57h+ppv]
0x180014374  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180014379  lea     eax, [r12+0Bh]
0x18001437e  mov     word ptr [rbp+57h+propvar], ax
0x180014382  or      eax, 0FFFFFFFFh
0x180014385  mov     [rbp+57h+var_48], ax
0x180014389  lea     r8, [rbp+57h+ppv]; ppv
0x18001438d  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; riid
0x180014394  lea     rcx, [rbp+57h+propvar]; propvar
0x180014398  call    cs:__imp_PropVariantToWinRTPropertyValue
0x18001439e  test    eax, eax
0x1800143a0  js      short loc_1800143EB
0x1800143a2  mov     [rbp+57h+var_7F], r12b
0x1800143a6  mov     rsi, [rbp+57h+var_78]
0x1800143aa  mov     rax, [rsi]
0x1800143ad  mov     rdi, [rax+50h]
0x1800143b1  mov     rbx, [rbp+57h+ppv]
0x1800143b5  mov     [rbp+57h+var_38], r12
0x1800143b9  lea     r9d, [r12+11h]; unsigned int
0x1800143be  lea     r8d, [r12+12h]; unsigned int
0x1800143c3  lea     rdx, aZeroinputdisab; "ZeroInputDisabled"
0x1800143ca  lea     rcx, [rbp+57h+propvar]; hstringHeader
0x1800143ce  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800143d3  nop
0x1800143d4  lea     r9, [rbp+57h+var_7F]
0x1800143d8  mov     r8, rbx
0x1800143db  mov     rdx, [rbp+57h+var_38]
0x1800143df  mov     rcx, rsi
0x1800143e2  mov     rax, rdi
0x1800143e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143ea  nop
0x1800143eb  lea     rcx, [rbp+57h+ppv]
0x1800143ef  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800143f4  jmp     short loc_1800143FD
0x1800143f6  mov     [r14+0C4h], r12b
0x1800143fd  mov     [rbp+57h+var_70], r12
0x180014401  xor     ecx, ecx; string
0x180014403  call    cs:__imp_WindowsDeleteString
0x180014409  mov     [rbp+57h+var_70], r12
0x18001440d  mov     [rbp+57h+var_38], r12
0x180014411  mov     r9d, 9; unsigned int
0x180014417  lea     r8d, [r9+1]; unsigned int
0x18001441b  lea     rdx, aQuerytext; "QueryText"
0x180014422  lea     rcx, [rbp+57h+propvar]; hstringHeader
0x180014426  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001442b  lea     r8, [rbp+57h+var_70]
0x18001442f  mov     rdx, [rbp+57h+var_38]
0x180014433  mov     rcx, [rbp+57h+var_78]
0x180014437  call    GetKeyFromMapAsString
0x18001443c  mov     [rbp+57h+string], r12
0x180014440  xor     ecx, ecx; string
0x180014442  call    cs:__imp_WindowsDeleteString
0x180014448  mov     [rbp+57h+string], r12
0x18001444c  mov     [rbp+57h+var_38], r12
0x180014450  mov     r9d, 7; unsigned int
0x180014456  lea     r8d, [r9+1]; unsigned int
0x18001445a  lea     rdx, aCuetext; "CueText"
0x180014461  lea     rcx, [rbp+57h+propvar]; hstringHeader
0x180014465  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001446a  lea     r8, [rbp+57h+string]
0x18001446e  mov     rdx, [rbp+57h+var_38]
0x180014472  mov     rcx, [rbp+57h+var_78]
0x180014476  call    GetKeyFromMapAsString
0x18001447b  mov     [rbp+57h+var_80], r12b
0x18001447f  mov     [rbp+57h+var_38], r12
0x180014483  mov     r9d, 10h; unsigned int
0x180014489  lea     r8d, [r9+1]; unsigned int
0x18001448d  lea     rdx, aShouldselectte; "ShouldSelectText"
0x180014494  lea     rcx, [rbp+57h+propvar]; hstringHeader
0x180014498  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001449d  lea     r8, [rbp+57h+var_80]
0x1800144a1  mov     rdx, [rbp+57h+var_38]
0x1800144a5  mov     rcx, [rbp+57h+var_78]
0x1800144a9  call    GetKeyFromMapAsBool
0x1800144ae  cmp     [rbp+57h+var_80], r12b
0x1800144b2  setnz   bl
0x1800144b5  mov     rdi, [rbp+57h+string]
0x1800144b9  mov     [rbp+57h+var_38], r12
0x1800144bd  mov     r9d, 1Ch; unsigned int
0x1800144c3  lea     r8d, [r9+1]; unsigned int
0x1800144c7  lea     rdx, c_szSearchPaneCurrentAppAppId; "Windows.UI.Search.CurrentApp"
0x1800144ce  lea     rcx, [rbp+57h+propvar]; hstringHeader
0x1800144d2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800144d7  nop
0x1800144d8  mov     [rsp+0B0h+var_88], bl; bool
0x1800144dc  mov     [rsp+0B0h+var_90], rdi; HSTRING
0x1800144e1  mov     r9, [rbp+57h+var_38]; HSTRING
0x1800144e5  mov     r8, [rbp+57h+var_70]; HSTRING
0x1800144e9  mov     rdx, [rbp+57h+ppvOut]; struct ISearchServices *
0x1800144ed  mov     rcx, r14; this
0x1800144f0  call    ?_SetQueryAndScope@CSearchPaneViewDefinition@@AEAAXPEAUISearchServices@@PEAUHSTRING__@@11_N@Z; CSearchPaneViewDefinition::_SetQueryAndScope(ISearchServices *,HSTRING__ *,HSTRING__ *,HSTRING__ *,bool)
0x1800144f5  nop
0x1800144f6  lea     rdx, aQuerytext; "QueryText"
0x1800144fd  mov     rcx, [rbp+57h+var_78]
0x180014501  call    RemoveKey
0x180014506  lea     rdx, aAppid; "AppId"
0x18001450d  mov     rcx, [rbp+57h+var_78]
0x180014511  call    RemoveKey
0x180014516  lea     rdx, aCuetext; "CueText"
0x18001451d  mov     rcx, [rbp+57h+var_78]
0x180014521  call    RemoveKey
0x180014526  lea     rdx, aShouldselectte; "ShouldSelectText"
0x18001452d  mov     rcx, [rbp+57h+var_78]
0x180014531  call    RemoveKey
0x180014536  lea     rdx, aRestorescope; "RestoreScope"
0x18001453d  mov     rcx, [rbp+57h+var_78]
0x180014541  call    RemoveKey
0x180014546  nop
0x180014547  mov     rcx, [rbp+57h+string]; string
0x18001454b  call    cs:__imp_WindowsDeleteString
0x180014551  mov     [rbp+57h+string], r12
0x180014555  mov     rcx, [rbp+57h+var_70]; string
0x180014559  call    cs:__imp_WindowsDeleteString
0x18001455f  nop
0x180014560  lea     rcx, [rbp+57h+var_78]
0x180014564  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180014569  mov     [r14+0C0h], r15d
0x180014570  lea     rcx, [rbp+57h+ppvOut]
0x180014574  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180014579  xor     al, al
0x18001457b  mov     rcx, [rbp+57h+var_30]
0x18001457f  xor     rcx, rsp; StackCookie
0x180014582  call    __security_check_cookie
0x180014587  lea     r11, [rsp+0B0h+var_20]
0x18001458f  mov     rbx, [r11+38h]
0x180014593  mov     rsi, [r11+40h]
0x180014597  mov     rsp, r11
0x18001459a  pop     r15
0x18001459c  pop     r14
0x18001459e  pop     r12
0x1800145a0  pop     rdi
0x1800145a1  pop     rbp
0x1800145a2  retn
```
