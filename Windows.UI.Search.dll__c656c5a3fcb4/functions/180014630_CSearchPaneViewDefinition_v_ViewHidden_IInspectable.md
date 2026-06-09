# CSearchPaneViewDefinition::v_ViewHidden(IInspectable *)

- ea: `0x180014630`
- end: `0x180014c13`
- name: `?v_ViewHidden@CSearchPaneViewDefinition@@EEAAXPEAUIInspectable@@@Z`
- size: `1507`
- prototype: `void __fastcall(CSearchPaneViewDefinition *__hidden this, struct IInspectable *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180007b3c`
- `0x18000f2a8`
- `0x1800114f4`
- `0x1800120dc`
- `0x180013db4`
- `0x180013e38`
- `0x1800140f4`
- `0x180014630`
- `0x180015d14`
- `0x180026454`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180014756`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800149e2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180014756`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800149e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014880`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001490f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001495a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001496a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014880`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001490f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001495a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001496a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001473d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800149c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001473d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800149c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800148ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014938`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800148ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014938`
- `SHCORE!IUnknown_QueryService` at `0x1800146c4`
- `SHCORE!IUnknown_QueryService` at `0x1800147b1`
- `SHCORE!IUnknown_QueryService` at `0x180014852`
- `SHCORE!IUnknown_QueryService` at `0x180014a37`
- `SHCORE!IUnknown_QueryService` at `0x180014b2c`
- `SHCORE!IUnknown_QueryService` at `0x1800146c4`
- `SHCORE!IUnknown_QueryService` at `0x1800147b1`
- `SHCORE!IUnknown_QueryService` at `0x180014852`
- `SHCORE!IUnknown_QueryService` at `0x180014a37`
- `SHCORE!IUnknown_QueryService` at `0x180014b2c`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x180014a7d`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x180014a7d`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall CSearchPaneViewDefinition::v_ViewHidden(CSearchPaneViewDefinition *this, struct IInspectable *a2)
{
  struct IInspectable *v2; // rdi
  IUnknown **v4; // rax
  unsigned int v5; // ebx
  void *v6; // rdi
  int (__fastcall *v7)(void *, _QWORD, GUID *, __int64 *); // rbx
  __int64 v8; // rbx
  int (__fastcall *v9)(__int64, HSTRING, char *); // rdi
  IUnknown **v10; // rax
  HRESULT v11; // ebx
  void *v12; // rdi
  int (__fastcall *v13)(void *, HSTRING *); // rbx
  IUnknown **v14; // rax
  unsigned int v15; // ebx
  void *v16; // rdi
  int (__fastcall *v17)(void *, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 Reserved1; // r8
  void *v20; // rdi
  int (__fastcall *v21)(void *, HSTRING *); // rbx
  PCWSTR v22; // rax
  __int64 v23; // rbx
  int (__fastcall *v24)(__int64, HSTRING, char *); // rdi
  IUnknown **v25; // rax
  unsigned int v26; // ebx
  __int64 v27; // rsi
  void (__fastcall *v28)(__int64, _QWORD, void *, _BYTE *); // rdi
  void *v29; // rbx
  IUnknown **v30; // rax
  unsigned int v31; // ebx
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rbx
  char v33; // [rsp+30h] [rbp-49h] BYREF
  char v34; // [rsp+31h] [rbp-48h] BYREF
  _BYTE v35[6]; // [rsp+32h] [rbp-47h] BYREF
  HSTRING v36; // [rsp+38h] [rbp-41h] BYREF
  void *v37; // [rsp+40h] [rbp-39h] BYREF
  HSTRING v38; // [rsp+48h] [rbp-31h] BYREF
  void *ppv; // [rsp+50h] [rbp-29h] BYREF
  __int64 v40; // [rsp+58h] [rbp-21h] BYREF
  __int64 v41; // [rsp+60h] [rbp-19h] BYREF
  void *ppvOut; // [rsp+68h] [rbp-11h] BYREF
  struct IInspectable *v43; // [rsp+70h] [rbp-9h]
  HSTRING string; // [rsp+78h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp+7h] BYREF

  v2 = a2;
  v43 = a2;
  CSearchPaneViewDefinition::_NotifyAppOfSeachPaneVisibility(this, 0);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 120);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 144);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 168);
  ppvOut = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
  v4 = (IUnknown **)CWRLObjectWithGITSite::SiteUnk((char *)this + 8, &v36);
  v5 = (unsigned int)IUnknown_QueryService(
                       *v4,
                       &GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd,
                       &GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd,
                       &ppvOut) >> 31;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v36);
  if ( (unsigned __int8)v5 != 1 )
  {
    v40 = 0;
    v6 = ppvOut;
    v7 = *(int (__fastcall **)(void *, _QWORD, GUID *, __int64 *))(*(_QWORD *)ppvOut + 40LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v40);
    if ( v7(v6, 0, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v40) >= 0 )
    {
      v33 = 0;
      v8 = v40;
      v9 = *(int (__fastcall **)(__int64, HSTRING, char *))(*(_QWORD *)v40 + 64LL);
      if ( WindowsCreateStringReference(L"RestoreScope", 0xCu, &hstringHeader, &string) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      if ( v9(v8, string, &v33) >= 0 && v33 )
      {
        ppv = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
        v10 = (IUnknown **)CWRLObjectWithGITSite::SiteUnk((char *)this + 8, &v36);
        v11 = IUnknown_QueryService(
                *v10,
                &GUID_52f077cc_10e3_40ea_ad6d_9313803f91f3,
                &GUID_52f077cc_10e3_40ea_ad6d_9313803f91f3,
                &ppv);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v36);
        if ( v11 >= 0 )
        {
          string = 0;
          *(_OWORD *)&hstringHeader.Reserved.Reserved1 = 0u;
          v12 = ppv;
          v13 = *(int (__fastcall **)(void *, HSTRING *))(*(_QWORD *)ppv + 32LL);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&string);
          hstringHeader.Reserved.Reserved1 = (PVOID)-1LL;
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = -1;
          if ( v13(v12, &string) >= 0 && (unsigned int)IsAppScope((LPCWCH)string) )
          {
            v37 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v37);
            v14 = (IUnknown **)CWRLObjectWithGITSite::SiteUnk((char *)this + 8, &v36);
            v15 = (unsigned int)IUnknown_QueryService(
                                  *v14,
                                  (const GUID *const)&SID_SearchBox,
                                  &GUID_aa90700f_2340_46a7_ab00_867fd691ecee,
                                  &v37) >> 31;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v36);
            if ( (unsigned __int8)v15 != 1 )
            {
              v38 = 0;
              v16 = v37;
              v17 = *(int (__fastcall **)(void *, HSTRING *))(*(_QWORD *)v37 + 48LL);
              WindowsDeleteString(0);
              v38 = 0;
              if ( v17(v16, &v38) >= 0 )
              {
                StringRawBuffer = WindowsGetStringRawBuffer(v38, 0);
                if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                            (char *)this + 144,
                            StringRawBuffer,
                            -1) >= 0 )
                {
                  Reserved1 = (__int64)hstringHeader.Reserved.Reserved1;
                  if ( hstringHeader.Reserved.Reserved1 == (PVOID)-1LL )
                  {
                    if ( string )
                    {
                      Reserved1 = -1;
                      do
                        ++Reserved1;
                      while ( *((_WORD *)string + Reserved1) );
                    }
                    else
                    {
                      Reserved1 = 0;
                    }
                  }
                  if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                              (char *)this + 120,
                              string,
                              Reserved1) >= 0 )
                  {
                    v36 = 0;
                    v20 = v37;
                    v21 = *(int (__fastcall **)(void *, HSTRING *))(*(_QWORD *)v37 + 64LL);
                    WindowsDeleteString(0);
                    v36 = 0;
                    if ( v21(v20, &v36) >= 0 )
                    {
                      v22 = WindowsGetStringRawBuffer(v38, 0);
                      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                        (char *)this + 168,
                        v22,
                        -1);
                    }
                    WindowsDeleteString(v36);
                  }
                }
              }
              WindowsDeleteString(v38);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v37);
          }
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&string);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
      }
      v34 = 0;
      v23 = v40;
      v24 = *(int (__fastcall **)(__int64, HSTRING, char *))(*(_QWORD *)v40 + 64LL);
      if ( WindowsCreateStringReference(L"WaitingForSuggestions", 0x15u, &hstringHeader, &string) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      if ( v24(v23, string, &v34) < 0 || !v34 )
      {
        v37 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v37);
        v25 = (IUnknown **)CWRLObjectWithGITSite::SiteUnk((char *)this + 8, &v36);
        v26 = (unsigned int)IUnknown_QueryService(
                              *v25,
                              (const GUID *const)&SID_SearchBox,
                              &GUID_aa90700f_2340_46a7_ab00_867fd691ecee,
                              &v37) >> 31;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v36);
        if ( (unsigned __int8)v26 != 1 )
        {
          ppv = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
          LOWORD(string) = 11;
          LOWORD(hstringHeader.Reserved.Reserved1) = -1;
          if ( PropVariantToWinRTPropertyValue(
                 (const PROPVARIANT *const)&string,
                 &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                 &ppv) >= 0 )
          {
            v35[0] = 0;
            v27 = v40;
            v28 = *(void (__fastcall **)(__int64, _QWORD, void *, _BYTE *))(*(_QWORD *)v40 + 80LL);
            v29 = ppv;
            *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(
              (HSTRING_HEADER *)&string,
              L"ZeroInputDisabled",
              0x12u,
              0x11u);
            v28(v27, *(_QWORD *)&hstringHeader.Reserved.Reserved2[16], v29, v35);
          }
          (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)v37 + 56LL))(v37, 0);
          (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)v37 + 72LL))(v37, 0);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
        }
        v38 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v38);
        v30 = (IUnknown **)CWRLObjectWithGITSite::SiteUnk((char *)this + 8, &v36);
        v31 = (unsigned int)IUnknown_QueryService(
                              *v30,
                              &GUID_52f077cc_10e3_40ea_ad6d_9313803f91f3,
                              &GUID_52f077cc_10e3_40ea_ad6d_9313803f91f3,
                              (void **)&v38) >> 31;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v36);
        if ( (unsigned __int8)v31 != 1 )
          (*(void (__fastcall **)(HSTRING, const WCHAR *, _QWORD))(*(_QWORD *)v38 + 40LL))(v38, L"Windows.UI.Search", 0);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v38);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v37);
      }
      RemoveKey(v40, L"ViewShown");
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v40);
    v2 = v43;
  }
  v41 = 0;
  QueryInterface = v2->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v41);
  if ( ((int (__fastcall *)(struct IInspectable *, GUID *, __int64 *))QueryInterface)(
         v2,
         &GUID_ed646d0b_332f_4b9b_8b0e_aef71d46f5c7,
         &v41) >= 0 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 64LL))(v41);
  CSearchPaneViewDefinition::_SetSearchPaneIdleTimer(this);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v41);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
}

```

## disassembly

```asm
0x180014630  mov     [rsp-8+arg_10], rbx
0x180014635  push    rbp
0x180014636  push    rsi
0x180014637  push    rdi
0x180014638  push    r12
0x18001463a  push    r13
0x18001463c  push    r14
0x18001463e  push    r15
0x180014640  lea     rbp, [rsp-27h]
0x180014645  sub     rsp, 0A0h
0x18001464c  mov     rax, cs:__security_cookie
0x180014653  xor     rax, rsp
0x180014656  mov     [rbp+57h+var_38], rax
0x18001465a  mov     rdi, rdx
0x18001465d  mov     [rbp+57h+var_60], rdx
0x180014661  mov     r13, rcx
0x180014664  xor     edx, edx; bool
0x180014666  call    ?_NotifyAppOfSeachPaneVisibility@CSearchPaneViewDefinition@@AEAAX_N@Z; CSearchPaneViewDefinition::_NotifyAppOfSeachPaneVisibility(bool)
0x18001466b  lea     rcx, [r13+78h]
0x18001466f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180014674  lea     rsi, [r13+90h]
0x18001467b  mov     rcx, rsi
0x18001467e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180014683  lea     r12, [r13+0A8h]
0x18001468a  mov     rcx, r12
0x18001468d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180014692  mov     [rbp+57h+ppvOut], 0
0x18001469a  lea     rcx, [rbp+57h+ppvOut]
0x18001469e  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800146a3  lea     r14, [r13+8]
0x1800146a7  lea     rdx, [rbp+57h+var_98]
0x1800146ab  mov     rcx, r14
0x1800146ae  call    ?SiteUnk@CWRLObjectWithGITSite@@IEAA?AV?$ComPtr@UIUnknown@@@WRL@Microsoft@@XZ; CWRLObjectWithGITSite::SiteUnk(void)
0x1800146b3  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x1800146b7  lea     rdx, _GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd; guidService
0x1800146be  mov     r8, rdx; riid
0x1800146c1  mov     rcx, [rax]; punk
0x1800146c4  call    cs:__imp_IUnknown_QueryService
0x1800146ca  mov     ebx, eax
0x1800146cc  shr     ebx, 1Fh
0x1800146cf  lea     rcx, [rbp+57h+var_98]
0x1800146d3  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800146d8  xor     eax, eax
0x1800146da  xor     bl, 1
0x1800146dd  jz      loc_180014B93
0x1800146e3  mov     [rbp+57h+var_78], rax
0x1800146e7  mov     rdi, [rbp+57h+ppvOut]
0x1800146eb  mov     rax, [rdi]
0x1800146ee  mov     rbx, [rax+28h]
0x1800146f2  lea     rcx, [rbp+57h+var_78]
0x1800146f6  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800146fb  lea     r9, [rbp+57h+var_78]
0x1800146ff  lea     r8, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180014706  xor     edx, edx
0x180014708  mov     rcx, rdi
0x18001470b  mov     rax, rbx
0x18001470e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014713  xor     ecx, ecx
0x180014715  test    eax, eax
0x180014717  js      loc_180014B84
0x18001471d  mov     [rbp+57h+var_A0], cl
0x180014720  mov     rbx, [rbp+57h+var_78]
0x180014724  mov     rax, [rbx]
0x180014727  mov     rdi, [rax+40h]
0x18001472b  lea     r9, [rbp+57h+string]; string
0x18001472f  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180014733  lea     edx, [rcx+0Ch]; length
0x180014736  lea     rcx, aRestorescope; "RestoreScope"
0x18001473d  call    cs:__imp_WindowsCreateStringReference
0x180014743  test    eax, eax
0x180014745  jns     short loc_18001475C
0x180014747  xor     r9d, r9d; lpArguments
0x18001474a  xor     r8d, r8d; nNumberOfArguments
0x18001474d  lea     edx, [r9+1]; dwExceptionFlags
0x180014751  mov     ecx, 0C000000Dh; dwExceptionCode
0x180014756  call    cs:__imp_RaiseException
0x18001475c  lea     r8, [rbp+57h+var_A0]
0x180014760  mov     rdx, [rbp+57h+string]
0x180014764  mov     rcx, rbx
0x180014767  mov     rax, rdi
0x18001476a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001476f  xor     edi, edi
0x180014771  test    eax, eax
0x180014773  js      loc_18001499F
0x180014779  cmp     [rbp+57h+var_A0], dil
0x18001477d  jz      loc_18001499F
0x180014783  mov     [rbp+57h+ppv], rdi
0x180014787  lea     rcx, [rbp+57h+ppv]
0x18001478b  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180014790  lea     rdx, [rbp+57h+var_98]
0x180014794  mov     rcx, r14
0x180014797  call    ?SiteUnk@CWRLObjectWithGITSite@@IEAA?AV?$ComPtr@UIUnknown@@@WRL@Microsoft@@XZ; CWRLObjectWithGITSite::SiteUnk(void)
0x18001479c  lea     r9, [rbp+57h+ppv]; ppvOut
0x1800147a0  lea     r8, _GUID_52f077cc_10e3_40ea_ad6d_9313803f91f3; riid
0x1800147a7  lea     rdx, _GUID_52f077cc_10e3_40ea_ad6d_9313803f91f3; guidService
0x1800147ae  mov     rcx, [rax]; punk
0x1800147b1  call    cs:__imp_IUnknown_QueryService
0x1800147b7  mov     ebx, eax
0x1800147b9  lea     rcx, [rbp+57h+var_98]
0x1800147bd  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800147c2  shr     ebx, 1Fh
0x1800147c5  xor     bl, 1
0x1800147c8  jz      loc_180014990
0x1800147ce  mov     [rbp+57h+string], rdi
0x1800147d2  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rdi
0x1800147d6  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], rdi
0x1800147da  mov     rdi, [rbp+57h+ppv]
0x1800147de  mov     rax, [rdi]
0x1800147e1  mov     rbx, [rax+20h]
0x1800147e5  lea     rcx, [rbp+57h+string]
0x1800147e9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800147ee  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800147f2  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x1800147f6  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], rax
0x1800147fa  lea     rdx, [rbp+57h+string]
0x1800147fe  mov     rcx, rdi
0x180014801  mov     rax, rbx
0x180014804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014809  xor     edi, edi
0x18001480b  test    eax, eax
0x18001480d  js      loc_180014981
0x180014813  mov     rcx, [rbp+57h+string]; lpString1
0x180014817  call    IsAppScope
0x18001481c  test    eax, eax
0x18001481e  jz      loc_180014981
0x180014824  mov     [rbp+57h+var_90], rdi
0x180014828  lea     rcx, [rbp+57h+var_90]
0x18001482c  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180014831  lea     rdx, [rbp+57h+var_98]
0x180014835  mov     rcx, r14
0x180014838  call    ?SiteUnk@CWRLObjectWithGITSite@@IEAA?AV?$ComPtr@UIUnknown@@@WRL@Microsoft@@XZ; CWRLObjectWithGITSite::SiteUnk(void)
0x18001483d  lea     r9, [rbp+57h+var_90]; ppvOut
0x180014841  lea     r8, _GUID_aa90700f_2340_46a7_ab00_867fd691ecee; riid
0x180014848  lea     rdx, SID_SearchBox; guidService
0x18001484f  mov     rcx, [rax]; punk
0x180014852  call    cs:__imp_IUnknown_QueryService
0x180014858  mov     ebx, eax
0x18001485a  shr     ebx, 1Fh
0x18001485d  lea     rcx, [rbp+57h+var_98]
0x180014861  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180014866  xor     bl, 1
0x180014869  jz      loc_180014972
0x18001486f  mov     [rbp+57h+var_88], rdi
0x180014873  mov     rdi, [rbp+57h+var_90]
0x180014877  mov     rax, [rdi]
0x18001487a  mov     rbx, [rax+30h]
0x18001487e  xor     ecx, ecx; string
0x180014880  call    cs:__imp_WindowsDeleteString
0x180014886  mov     [rbp+57h+var_88], 0
0x18001488e  lea     rdx, [rbp+57h+var_88]
0x180014892  mov     rcx, rdi
0x180014895  mov     rax, rbx
0x180014898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001489d  xor     edi, edi
0x18001489f  test    eax, eax
0x1800148a1  js      loc_180014962
0x1800148a7  xor     edx, edx; length
0x1800148a9  mov     rcx, [rbp+57h+var_88]; string
0x1800148ad  call    cs:__imp_WindowsGetStringRawBuffer
0x1800148b3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800148b7  mov     r8, rbx
0x1800148ba  mov     rdx, rax
0x1800148bd  mov     rcx, rsi
0x1800148c0  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800148c5  test    eax, eax
0x1800148c7  js      loc_180014962
0x1800148cd  mov     r8, qword ptr [rbp+57h+hstringHeader.Reserved]
0x1800148d1  mov     rdx, [rbp+57h+string]
0x1800148d5  cmp     r8, rbx
0x1800148d8  jnz     short loc_1800148F1
0x1800148da  test    rdx, rdx
0x1800148dd  jz      short loc_1800148EE
0x1800148df  mov     r8, rbx
0x1800148e2  inc     r8
0x1800148e5  cmp     [rdx+r8*2], di
0x1800148ea  jnz     short loc_1800148E2
0x1800148ec  jmp     short loc_1800148F1
0x1800148ee  mov     r8, rdi
0x1800148f1  lea     rcx, [r13+78h]
0x1800148f5  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800148fa  test    eax, eax
0x1800148fc  js      short loc_180014962
0x1800148fe  mov     [rbp+57h+var_98], rdi
0x180014902  mov     rdi, [rbp+57h+var_90]
0x180014906  mov     rax, [rdi]
0x180014909  mov     rbx, [rax+40h]
0x18001490d  xor     ecx, ecx; string
0x18001490f  call    cs:__imp_WindowsDeleteString
0x180014915  mov     [rbp+57h+var_98], 0
0x18001491d  lea     rdx, [rbp+57h+var_98]
0x180014921  mov     rcx, rdi
0x180014924  mov     rax, rbx
0x180014927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001492c  xor     edi, edi
0x18001492e  test    eax, eax
0x180014930  js      short loc_180014952
0x180014932  xor     edx, edx; length
0x180014934  mov     rcx, [rbp+57h+var_88]; string
0x180014938  call    cs:__imp_WindowsGetStringRawBuffer
0x18001493e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180014942  mov     r8, rsi
0x180014945  mov     rdx, rax
0x180014948  mov     rcx, r12
0x18001494b  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180014950  jmp     short loc_180014956
0x180014952  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180014956  mov     rcx, [rbp+57h+var_98]; string
0x18001495a  call    cs:__imp_WindowsDeleteString
0x180014960  jmp     short loc_180014966
0x180014962  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180014966  mov     rcx, [rbp+57h+var_88]; string
0x18001496a  call    cs:__imp_WindowsDeleteString
0x180014970  jmp     short loc_180014976
0x180014972  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180014976  lea     rcx, [rbp+57h+var_90]
0x18001497a  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18001497f  jmp     short loc_180014985
0x180014981  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180014985  lea     rcx, [rbp+57h+string]
0x180014989  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001498e  jmp     short loc_180014994
0x180014990  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180014994  lea     rcx, [rbp+57h+ppv]
0x180014998  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18001499d  jmp     short loc_1800149A3
0x18001499f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800149a3  mov     [rbp+57h+var_9F], dil
0x1800149a7  mov     rbx, [rbp+57h+var_78]
0x1800149ab  mov     rax, [rbx]
0x1800149ae  mov     rdi, [rax+40h]
0x1800149b2  lea     r9, [rbp+57h+string]; string
0x1800149b6  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800149ba  mov     edx, 15h; length
0x1800149bf  lea     rcx, aWaitingforsugg; "WaitingForSuggestions"
0x1800149c6  call    cs:__imp_WindowsCreateStringReference
0x1800149cc  xor     r15d, r15d
0x1800149cf  test    eax, eax
0x1800149d1  jns     short loc_1800149E8
0x1800149d3  xor     r9d, r9d; lpArguments
0x1800149d6  xor     r8d, r8d; nNumberOfArguments
0x1800149d9  lea     edx, [r15+1]; dwExceptionFlags
0x1800149dd  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800149e2  call    cs:__imp_RaiseException
0x1800149e8  lea     r8, [rbp+57h+var_9F]
0x1800149ec  mov     rdx, [rbp+57h+string]
0x1800149f0  mov     rcx, rbx
0x1800149f3  mov     rax, rdi
0x1800149f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149fb  test    eax, eax
0x1800149fd  js      short loc_180014A09
0x1800149ff  cmp     [rbp+57h+var_9F], r15b
0x180014a03  jnz     loc_180014B73
0x180014a09  mov     [rbp+57h+var_90], r15
0x180014a0d  lea     rcx, [rbp+57h+var_90]
0x180014a11  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180014a16  lea     rdx, [rbp+57h+var_98]
0x180014a1a  mov     rcx, r14
0x180014a1d  call    ?SiteUnk@CWRLObjectWithGITSite@@IEAA?AV?$ComPtr@UIUnknown@@@WRL@Microsoft@@XZ; CWRLObjectWithGITSite::SiteUnk(void)
0x180014a22  lea     r9, [rbp+57h+var_90]; ppvOut
0x180014a26  lea     r8, _GUID_aa90700f_2340_46a7_ab00_867fd691ecee; riid
0x180014a2d  lea     rdx, SID_SearchBox; guidService
0x180014a34  mov     rcx, [rax]; punk
0x180014a37  call    cs:__imp_IUnknown_QueryService
0x180014a3d  mov     ebx, eax
0x180014a3f  shr     ebx, 1Fh
0x180014a42  lea     rcx, [rbp+57h+var_98]
0x180014a46  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180014a4b  xor     bl, 1
0x180014a4e  jz      loc_180014AFE
0x180014a54  mov     [rbp+57h+ppv], r15
0x180014a58  lea     rcx, [rbp+57h+ppv]
0x180014a5c  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180014a61  mov     eax, 0Bh
0x180014a66  mov     word ptr [rbp+57h+string], ax
0x180014a6a  mov     word ptr [rbp+57h+hstringHeader.Reserved], si
0x180014a6e  lea     r8, [rbp+57h+ppv]; ppv
0x180014a72  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; riid
0x180014a79  lea     rcx, [rbp+57h+string]; propvar
0x180014a7d  call    cs:__imp_PropVariantToWinRTPropertyValue
0x180014a83  test    eax, eax
0x180014a85  js      short loc_180014AD0
0x180014a87  mov     [rbp+57h+var_9E], r15b
0x180014a8b  mov     rsi, [rbp+57h+var_78]
0x180014a8f  mov     rax, [rsi]
0x180014a92  mov     rdi, [rax+50h]
0x180014a96  mov     rbx, [rbp+57h+ppv]
0x180014a9a  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], r15
0x180014a9e  mov     r9d, 11h; unsigned int
0x180014aa4  lea     r8d, [r9+1]; unsigned int
0x180014aa8  lea     rdx, aZeroinputdisab; "ZeroInputDisabled"
0x180014aaf  lea     rcx, [rbp+57h+string]; hstringHeader
0x180014ab3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180014ab8  nop
0x180014ab9  lea     r9, [rbp+57h+var_9E]
0x180014abd  mov     r8, rbx
0x180014ac0  mov     rdx, qword ptr [rbp+57h+hstringHeader.Reserved+10h]
0x180014ac4  mov     rcx, rsi
0x180014ac7  mov     rax, rdi
0x180014aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014acf  nop
  ... truncated ...
```
