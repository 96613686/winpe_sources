# CSearchPaneViewDefinition::v_ViewShown(IInspectable *)

- ea: `0x180014c20`
- end: `0x180014e33`
- name: `?v_ViewShown@CSearchPaneViewDefinition@@EEAAXPEAUIInspectable@@@Z`
- size: `531`
- prototype: `void __fastcall(CSearchPaneViewDefinition *__hidden this, struct IInspectable *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180007b3c`
- `0x18000f2a8`
- `0x1800114f4`
- `0x1800120dc`
- `0x180013928`
- `0x180013e38`
- `0x180014c20`
- `0x180015d14`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x180014c79`
- `SHCORE!IUnknown_QueryService` at `0x180014c79`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x180014d2a`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x180014d2a`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CSearchPaneViewDefinition::v_ViewShown(CSearchPaneViewDefinition *this, struct IInspectable *a2)
{
  IUnknown **v4; // rax
  unsigned int v5; // ebx
  void *v6; // rdi
  int (__fastcall *v7)(void *, _QWORD, GUID *, __int64 *); // rbx
  __int64 v8; // rsi
  void (__fastcall *v9)(__int64, __int64, void *, _BYTE *); // rdi
  void *v10; // rbx
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rbx
  _BYTE v12[8]; // [rsp+30h] [rbp-50h] BYREF
  void *ppv; // [rsp+38h] [rbp-48h] BYREF
  __int64 v14; // [rsp+40h] [rbp-40h] BYREF
  __int64 v15; // [rsp+48h] [rbp-38h] BYREF
  void *ppvOut; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER propvar; // [rsp+58h] [rbp-28h] BYREF
  __int64 v18; // [rsp+70h] [rbp-10h]

  ppvOut = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
  v4 = (IUnknown **)CWRLObjectWithGITSite::SiteUnk((char *)this + 8, &ppv);
  v5 = (unsigned int)IUnknown_QueryService(
                       *v4,
                       &GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd,
                       &GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd,
                       &ppvOut) >> 31;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
  if ( (unsigned __int8)v5 != 1 )
  {
    v14 = 0;
    v6 = ppvOut;
    v7 = *(int (__fastcall **)(void *, _QWORD, GUID *, __int64 *))(*(_QWORD *)ppvOut + 40LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v14);
    if ( v7(v6, 0, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v14) >= 0 )
    {
      if ( !*((_BYTE *)this + 196) )
        RemoveKey(v14, L"ZeroInputDisabled");
      if ( !*((_DWORD *)this + 48) )
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
          v12[0] = 0;
          v8 = v14;
          v9 = *(void (__fastcall **)(__int64, __int64, void *, _BYTE *))(*(_QWORD *)v14 + 80LL);
          v10 = ppv;
          v18 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&propvar, L"ViewShown", 0xAu, 9u);
          v9(v8, v18, v10, v12);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v14);
  }
  v15 = 0;
  QueryInterface = a2->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v15);
  if ( ((int (__fastcall *)(struct IInspectable *, GUID *, __int64 *))QueryInterface)(
         a2,
         &GUID_ed646d0b_332f_4b9b_8b0e_aef71d46f5c7,
         &v15) >= 0 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 48LL))(v15);
  CSearchPaneViewDefinition::_NotifyAppOfSeachPaneVisibility(this, 1);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)this + 120);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)this + 144);
  CSearchPaneViewDefinition::_CancelSearchPaneIdleTimer(this);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v15);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
}

```

## disassembly

```asm
0x180014c20  mov     [rsp-28h+arg_10], rbx
0x180014c25  push    rbp
0x180014c26  push    rsi
0x180014c27  push    rdi
0x180014c28  push    r14
0x180014c2a  push    r15
0x180014c2c  mov     rbp, rsp
0x180014c2f  sub     rsp, 80h
0x180014c36  mov     rax, cs:__security_cookie
0x180014c3d  xor     rax, rsp
0x180014c40  mov     [rbp+var_8], rax
0x180014c44  mov     r15, rdx
0x180014c47  mov     r14, rcx
0x180014c4a  mov     [rbp+ppvOut], 0
0x180014c52  lea     rcx, [rbp+ppvOut]
0x180014c56  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180014c5b  lea     rcx, [r14+8]
0x180014c5f  lea     rdx, [rbp+ppv]
0x180014c63  call    ?SiteUnk@CWRLObjectWithGITSite@@IEAA?AV?$ComPtr@UIUnknown@@@WRL@Microsoft@@XZ; CWRLObjectWithGITSite::SiteUnk(void)
0x180014c68  lea     r9, [rbp+ppvOut]; ppvOut
0x180014c6c  lea     rdx, _GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd; guidService
0x180014c73  mov     r8, rdx; riid
0x180014c76  mov     rcx, [rax]; punk
0x180014c79  call    cs:__imp_IUnknown_QueryService
0x180014c7f  mov     ebx, eax
0x180014c81  shr     ebx, 1Fh
0x180014c84  lea     rcx, [rbp+ppv]
0x180014c88  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180014c8d  xor     bl, 1
0x180014c90  jz      loc_180014D94
0x180014c96  mov     [rbp+var_40], 0
0x180014c9e  mov     rdi, [rbp+ppvOut]
0x180014ca2  mov     rax, [rdi]
0x180014ca5  mov     rbx, [rax+28h]
0x180014ca9  lea     rcx, [rbp+var_40]
0x180014cad  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180014cb2  lea     r9, [rbp+var_40]
0x180014cb6  lea     r8, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180014cbd  xor     edx, edx
0x180014cbf  mov     rcx, rdi
0x180014cc2  mov     rax, rbx
0x180014cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cca  test    eax, eax
0x180014ccc  js      loc_180014D8B
0x180014cd2  cmp     byte ptr [r14+0C4h], 0
0x180014cda  jnz     short loc_180014CEC
0x180014cdc  lea     rdx, aZeroinputdisab; "ZeroInputDisabled"
0x180014ce3  mov     rcx, [rbp+var_40]
0x180014ce7  call    RemoveKey
0x180014cec  cmp     dword ptr [r14+0C0h], 0
0x180014cf4  jnz     loc_180014D8B
0x180014cfa  mov     [rbp+ppv], 0
0x180014d02  lea     rcx, [rbp+ppv]
0x180014d06  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180014d0b  mov     eax, 0Bh
0x180014d10  mov     word ptr [rbp+propvar], ax
0x180014d14  or      eax, 0FFFFFFFFh
0x180014d17  mov     [rbp+var_20], ax
0x180014d1b  lea     r8, [rbp+ppv]; ppv
0x180014d1f  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; riid
0x180014d26  lea     rcx, [rbp+propvar]; propvar
0x180014d2a  call    cs:__imp_PropVariantToWinRTPropertyValue
0x180014d30  test    eax, eax
0x180014d32  js      short loc_180014D81
0x180014d34  mov     [rbp+var_50], 0
0x180014d38  mov     rsi, [rbp+var_40]
0x180014d3c  mov     rax, [rsi]
0x180014d3f  mov     rdi, [rax+50h]
0x180014d43  mov     rbx, [rbp+ppv]
0x180014d47  mov     [rbp+var_10], 0
0x180014d4f  mov     r9d, 9; unsigned int
0x180014d55  lea     r8d, [r9+1]; unsigned int
0x180014d59  lea     rdx, aViewshown; "ViewShown"
0x180014d60  lea     rcx, [rbp+propvar]; hstringHeader
0x180014d64  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180014d69  nop
0x180014d6a  lea     r9, [rbp+var_50]
0x180014d6e  mov     r8, rbx
0x180014d71  mov     rdx, [rbp+var_10]
0x180014d75  mov     rcx, rsi
0x180014d78  mov     rax, rdi
0x180014d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d80  nop
0x180014d81  lea     rcx, [rbp+ppv]
0x180014d85  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180014d8a  nop
0x180014d8b  lea     rcx, [rbp+var_40]
0x180014d8f  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180014d94  mov     [rbp+var_38], 0
0x180014d9c  mov     rax, [r15]
0x180014d9f  mov     rbx, [rax]
0x180014da2  lea     rcx, [rbp+var_38]
0x180014da6  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180014dab  lea     r8, [rbp+var_38]
0x180014daf  lea     rdx, _GUID_ed646d0b_332f_4b9b_8b0e_aef71d46f5c7
0x180014db6  mov     rcx, r15
0x180014db9  mov     rax, rbx
0x180014dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dc1  test    eax, eax
0x180014dc3  js      short loc_180014DD5
0x180014dc5  mov     rcx, [rbp+var_38]
0x180014dc9  mov     rax, [rcx]
0x180014dcc  mov     rax, [rax+30h]
0x180014dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dd5  mov     dl, 1; bool
0x180014dd7  mov     rcx, r14; this
0x180014dda  call    ?_NotifyAppOfSeachPaneVisibility@CSearchPaneViewDefinition@@AEAAX_N@Z; CSearchPaneViewDefinition::_NotifyAppOfSeachPaneVisibility(bool)
0x180014ddf  lea     rcx, [r14+78h]
0x180014de3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180014de8  lea     rcx, [r14+90h]
0x180014def  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180014df4  mov     rcx, r14; this
0x180014df7  call    ?_CancelSearchPaneIdleTimer@CSearchPaneViewDefinition@@AEAAXXZ; CSearchPaneViewDefinition::_CancelSearchPaneIdleTimer(void)
0x180014dfc  nop
0x180014dfd  lea     rcx, [rbp+var_38]
0x180014e01  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180014e06  nop
0x180014e07  lea     rcx, [rbp+ppvOut]
0x180014e0b  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180014e10  mov     rcx, [rbp+var_8]
0x180014e14  xor     rcx, rsp; StackCookie
0x180014e17  call    __security_check_cookie
0x180014e1c  mov     rbx, [rsp+80h+arg_10]
0x180014e24  add     rsp, 80h
0x180014e2b  pop     r15
0x180014e2d  pop     r14
0x180014e2f  pop     rdi
0x180014e30  pop     rsi
0x180014e31  pop     rbp
0x180014e32  retn
```
