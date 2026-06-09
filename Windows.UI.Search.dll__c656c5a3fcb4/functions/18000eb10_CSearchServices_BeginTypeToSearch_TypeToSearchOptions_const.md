# CSearchServices::BeginTypeToSearch(TypeToSearchOptions const *)

- ea: `0x18000eb10`
- end: `0x18000ef40`
- name: `?BeginTypeToSearch@CSearchServices@@UEAAJPEBUTypeToSearchOptions@@@Z`
- size: `1072`
- prototype: `__int64 __fastcall(CSearchServices *__hidden this, const struct TypeToSearchOptions *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180007b3c`
- `0x18000eb10`
- `0x18000f2a8`
- `0x1800114f4`
- `0x180011d44`
- `0x1800120dc`
- `0x180012400`
- `0x180012544`
- `0x18003da8c`
- `0x18003dd34`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x18000ee0b`
- `SHCORE!IUnknown_QueryService` at `0x18000ee0b`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x18000ebc6`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x18000ec63`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x18000ed4e`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x18000ebc6`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x18000ec63`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x18000ed4e`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CSearchServices::BeginTypeToSearch(CSearchServices *this, HWND *a2)
{
  HRESULT IsForeground; // ebx
  __int64 (__fastcall *v5)(char *, _QWORD, GUID *, void **); // rbx
  void *v6; // rsi
  __int64 (__fastcall *v7)(void *, __int64, void *, _BYTE *); // rdi
  void *v8; // rbx
  enum PROCESS_UICONTEXT *v9; // rdx
  void *v10; // rsi
  __int64 (__fastcall *v11)(void *, __int64, void *, _BYTE *); // rdi
  void *v12; // rbx
  unsigned __int16 **v13; // rdx
  void *v14; // rsi
  __int64 (__fastcall *v15)(void *, __int64, void *, _BYTE *); // rdi
  void *v16; // rbx
  IUnknown **v17; // rax
  void *v18; // rdi
  __int64 (__fastcall *v19)(void *, HWND, GUID *, GUID *, void **); // rbx
  __int64 (__fastcall *v20)(char *, _QWORD, GUID *, GUID *, void **); // rbx
  _BYTE v22[8]; // [rsp+30h] [rbp-39h] BYREF
  void *ppv; // [rsp+38h] [rbp-31h] BYREF
  void *v24; // [rsp+40h] [rbp-29h] BYREF
  void *ppvOut; // [rsp+48h] [rbp-21h] BYREF
  PROPVARIANT propvar; // [rsp+50h] [rbp-19h] BYREF
  __int64 v27; // [rsp+58h] [rbp-11h]
  __int64 v28; // [rsp+60h] [rbp-9h]
  HSTRING_HEADER v29; // [rsp+68h] [rbp-1h] BYREF
  __int64 v30; // [rsp+80h] [rbp+17h]

  IsForeground = CSearchServices::_VerifySourceWindowIsForeground(this, a2[1]);
  if ( IsForeground >= 0 )
  {
    ppvOut = 0;
    v5 = *(__int64 (__fastcall **)(char *, _QWORD, GUID *, void **))(*((_QWORD *)this - 2) + 40LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
    IsForeground = v5((char *)this - 16, *(unsigned int *)a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &ppvOut);
    if ( IsForeground >= 0 )
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
      LOWORD(propvar) = 31;
      v27 = (__int64)&pszDefault;
      IsForeground = PropVariantToWinRTPropertyValue(&propvar, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, &ppv);
      if ( IsForeground >= 0 )
      {
        v22[0] = 0;
        v6 = ppvOut;
        v7 = *(__int64 (__fastcall **)(void *, __int64, void *, _BYTE *))(*(_QWORD *)ppvOut + 80LL);
        v8 = ppv;
        v30 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v29, L"QueryText", 0xAu, 9u);
        IsForeground = v7(v6, v30, v8, v22);
        if ( IsForeground >= 0 )
        {
          if ( a2[2] )
          {
            v24 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v24);
            LOWORD(propvar) = 31;
            v27 = (__int64)a2[2];
            IsForeground = PropVariantToWinRTPropertyValue(&propvar, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, &v24);
            if ( IsForeground >= 0 )
            {
              v22[0] = 0;
              v10 = ppvOut;
              v11 = *(__int64 (__fastcall **)(void *, __int64, void *, _BYTE *))(*(_QWORD *)ppvOut + 80LL);
              v12 = v24;
              v30 = 0;
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v29, L"AppId", 6u, 5u);
              IsForeground = v11(v10, v30, v12, v22);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v24);
          }
          else
          {
            LODWORD(v24) = 0;
            if ( (int)CallerIdentity::GetCallingProcessType((CallerIdentity *)&v24, v9) >= 0
              && (unsigned int)((_DWORD)v24 - 1) <= 1 )
            {
              propvar = 0;
              v27 = 0;
              v28 = 0;
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&propvar);
              v27 = -1;
              v28 = -1;
              if ( (int)CallerIdentity::GetCallingProcessAppId((CallerIdentity *)&propvar, v13) >= 0 )
              {
                v24 = 0;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v24);
                LOWORD(v29.Reserved.Reserved1) = 31;
                *(_QWORD *)&v29.Reserved.Reserved2[8] = propvar;
                IsForeground = PropVariantToWinRTPropertyValue(
                                 &v29.Reserved.Reserved1,
                                 &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                                 &v24);
                if ( IsForeground >= 0 )
                {
                  v22[0] = 0;
                  v14 = ppvOut;
                  v15 = *(__int64 (__fastcall **)(void *, __int64, void *, _BYTE *))(*(_QWORD *)ppvOut + 80LL);
                  v16 = v24;
                  v30 = 0;
                  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v29, L"AppId", 6u, 5u);
                  IsForeground = v15(v14, v30, v16, v22);
                }
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v24);
              }
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&propvar);
            }
          }
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
    if ( IsForeground >= 0 )
    {
      ppvOut = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
      v17 = (IUnknown **)CWRLObjectWithGITSite::SiteUnk((char *)this - 160, &ppv);
      IsForeground = IUnknown_QueryService(
                       *v17,
                       (const GUID *const)&SID_IImmersiveMonitorService,
                       &GUID_4d4c1e64_e410_4faa_bafa_59ca069bfec2,
                       &ppvOut);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
      if ( IsForeground >= 0 )
      {
        ppv = 0;
        v18 = ppvOut;
        v19 = *(__int64 (__fastcall **)(void *, HWND, GUID *, GUID *, void **))(*(_QWORD *)ppvOut + 88LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
        IsForeground = v19(
                         v18,
                         a2[1],
                         &GUID_880b26f8_9197_43d0_8045_8702d0d72000,
                         &GUID_880b26f8_9197_43d0_8045_8702d0d72000,
                         &ppv);
        if ( IsForeground >= 0 )
          IsForeground = CSearchServices::_StartFlowInternal((char *)this - 168, *(unsigned int *)a2, ppv, 1);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
      if ( IsForeground >= 0 )
      {
        ppv = 0;
        v20 = *(__int64 (__fastcall **)(char *, _QWORD, GUID *, GUID *, void **))(*((_QWORD *)this - 2) + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
        IsForeground = v20(
                         (char *)this - 16,
                         *(unsigned int *)a2,
                         &GUID_567f0f7d_a499_4461_973f_072cbdda90d6,
                         &GUID_db8aec44_c731_49ed_b8ef_c8faf39e46c2,
                         &ppv);
        if ( IsForeground >= 0 )
        {
          IsForeground = (*(__int64 (__fastcall **)(void *, HWND *))(*(_QWORD *)ppv + 24LL))(ppv, a2);
          if ( IsForeground >= 0 )
            CSearchServices::_EnsureSearchPaneSqmEntryPointForView(
              (char *)this - 168,
              *(unsigned int *)a2,
              *(_DWORD *)a2 != 0 ? 7 : 4,
              0);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
      }
    }
  }
  return (unsigned int)IsForeground;
}

```

## disassembly

```asm
0x18000eb10  mov     [rsp-8+arg_10], rbx
0x18000eb15  push    rbp
0x18000eb16  push    rsi
0x18000eb17  push    rdi
0x18000eb18  push    r12
0x18000eb1a  push    r13
0x18000eb1c  push    r14
0x18000eb1e  push    r15
0x18000eb20  lea     rbp, [rsp-27h]
0x18000eb25  sub     rsp, 90h
0x18000eb2c  mov     rax, cs:__security_cookie
0x18000eb33  xor     rax, rsp
0x18000eb36  mov     [rbp+57h+var_38], rax
0x18000eb3a  mov     r14, rdx
0x18000eb3d  mov     r13, rcx
0x18000eb40  mov     rdx, [rdx+8]; HWND
0x18000eb44  call    ?_VerifySourceWindowIsForeground@CSearchServices@@AEAAJPEAUHWND__@@@Z; CSearchServices::_VerifySourceWindowIsForeground(HWND__ *)
0x18000eb49  mov     ebx, eax
0x18000eb4b  xor     esi, esi
0x18000eb4d  test    eax, eax
0x18000eb4f  js      loc_18000EF17
0x18000eb55  lea     r15, [r13-0A8h]
0x18000eb5c  mov     [rbp+57h+ppvOut], rsi
0x18000eb60  mov     rax, [r15+98h]
0x18000eb67  mov     rbx, [rax+28h]
0x18000eb6b  lea     rcx, [rbp+57h+ppvOut]
0x18000eb6f  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18000eb74  lea     r9, [rbp+57h+ppvOut]
0x18000eb78  lea     r8, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18000eb7f  mov     edx, [r14]
0x18000eb82  lea     rcx, [r13-10h]
0x18000eb86  mov     rax, rbx
0x18000eb89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb8e  mov     ebx, eax
0x18000eb90  test    eax, eax
0x18000eb92  js      loc_18000EDC8
0x18000eb98  mov     [rbp+57h+ppv], rsi
0x18000eb9c  lea     rcx, [rbp+57h+ppv]
0x18000eba0  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18000eba5  lea     eax, [rsi+1Fh]
0x18000eba8  mov     word ptr [rbp+57h+propvar], ax
0x18000ebac  lea     rax, pszDefault
0x18000ebb3  mov     [rbp+57h+var_68], rax
0x18000ebb7  lea     r8, [rbp+57h+ppv]; ppv
0x18000ebbb  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; riid
0x18000ebc2  lea     rcx, [rbp+57h+propvar]; propvar
0x18000ebc6  call    cs:__imp_PropVariantToWinRTPropertyValue
0x18000ebcc  mov     ebx, eax
0x18000ebce  test    eax, eax
0x18000ebd0  js      loc_18000EDBE
0x18000ebd6  mov     [rbp+57h+var_90], sil
0x18000ebda  mov     rsi, [rbp+57h+ppvOut]
0x18000ebde  mov     rax, [rsi]
0x18000ebe1  mov     rdi, [rax+50h]
0x18000ebe5  mov     rbx, [rbp+57h+ppv]
0x18000ebe9  mov     [rbp+57h+var_40], 0
0x18000ebf1  mov     r9d, 9; unsigned int
0x18000ebf7  lea     r8d, [r9+1]; unsigned int
0x18000ebfb  lea     rdx, aQuerytext; "QueryText"
0x18000ec02  lea     rcx, [rbp+57h+var_58]; hstringHeader
0x18000ec06  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000ec0b  nop
0x18000ec0c  lea     r9, [rbp+57h+var_90]
0x18000ec10  mov     r8, rbx
0x18000ec13  mov     rdx, [rbp+57h+var_40]
0x18000ec17  mov     rcx, rsi
0x18000ec1a  mov     rax, rdi
0x18000ec1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec22  mov     ebx, eax
0x18000ec24  xor     esi, esi
0x18000ec26  test    eax, eax
0x18000ec28  js      loc_18000EDBE
0x18000ec2e  cmp     [r14+10h], rsi
0x18000ec32  jz      loc_18000ECCD
0x18000ec38  mov     [rbp+57h+var_80], rsi
0x18000ec3c  lea     rcx, [rbp+57h+var_80]
0x18000ec40  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18000ec45  lea     eax, [rsi+1Fh]
0x18000ec48  mov     word ptr [rbp+57h+propvar], ax
0x18000ec4c  mov     rax, [r14+10h]
0x18000ec50  mov     [rbp+57h+var_68], rax
0x18000ec54  lea     r8, [rbp+57h+var_80]; ppv
0x18000ec58  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; riid
0x18000ec5f  lea     rcx, [rbp+57h+propvar]; propvar
0x18000ec63  call    cs:__imp_PropVariantToWinRTPropertyValue
0x18000ec69  mov     ebx, eax
0x18000ec6b  test    eax, eax
0x18000ec6d  js      short loc_18000ECBF
0x18000ec6f  mov     [rbp+57h+var_90], sil
0x18000ec73  mov     rsi, [rbp+57h+ppvOut]
0x18000ec77  mov     rax, [rsi]
0x18000ec7a  mov     rdi, [rax+50h]
0x18000ec7e  mov     rbx, [rbp+57h+var_80]
0x18000ec82  mov     [rbp+57h+var_40], 0
0x18000ec8a  mov     r9d, 5; unsigned int
0x18000ec90  lea     r8d, [r9+1]; unsigned int
0x18000ec94  lea     rdx, aAppid; "AppId"
0x18000ec9b  lea     rcx, [rbp+57h+var_58]; hstringHeader
0x18000ec9f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000eca4  nop
0x18000eca5  lea     r9, [rbp+57h+var_90]
0x18000eca9  mov     r8, rbx
0x18000ecac  mov     rdx, [rbp+57h+var_40]
0x18000ecb0  mov     rcx, rsi
0x18000ecb3  mov     rax, rdi
0x18000ecb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecbb  mov     ebx, eax
0x18000ecbd  xor     esi, esi
0x18000ecbf  lea     rcx, [rbp+57h+var_80]
0x18000ecc3  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18000ecc8  jmp     loc_18000EDBE
0x18000eccd  mov     dword ptr [rbp+57h+var_80], esi
0x18000ecd0  lea     rcx, [rbp+57h+var_80]; this
0x18000ecd4  call    ?GetCallingProcessType@CallerIdentity@@YAJPEAW4PROCESS_UICONTEXT@@@Z; CallerIdentity::GetCallingProcessType(PROCESS_UICONTEXT *)
0x18000ecd9  test    eax, eax
0x18000ecdb  js      loc_18000EDBE
0x18000ece1  mov     eax, dword ptr [rbp+57h+var_80]
0x18000ece4  dec     eax
0x18000ece6  cmp     eax, 1
0x18000ece9  ja      loc_18000EDBE
0x18000ecef  mov     [rbp+57h+propvar], rsi
0x18000ecf3  mov     [rbp+57h+var_68], rsi
0x18000ecf7  mov     [rbp+57h+var_60], rsi
0x18000ecfb  lea     rcx, [rbp+57h+propvar]
0x18000ecff  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000ed04  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ed08  mov     [rbp+57h+var_68], rax
0x18000ed0c  mov     [rbp+57h+var_60], rax
0x18000ed10  lea     rcx, [rbp+57h+propvar]; this
0x18000ed14  call    ?GetCallingProcessAppId@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessAppId(ushort * *)
0x18000ed19  test    eax, eax
0x18000ed1b  js      loc_18000EDB4
0x18000ed21  mov     [rbp+57h+var_80], rsi
0x18000ed25  lea     rcx, [rbp+57h+var_80]
0x18000ed29  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18000ed2e  mov     eax, 1Fh
0x18000ed33  mov     word ptr [rbp+57h+var_58], ax
0x18000ed37  mov     rax, [rbp+57h+propvar]
0x18000ed3b  mov     [rbp+57h+var_50], rax
0x18000ed3f  lea     r8, [rbp+57h+var_80]; ppv
0x18000ed43  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; riid
0x18000ed4a  lea     rcx, [rbp+57h+var_58]; propvar
0x18000ed4e  call    cs:__imp_PropVariantToWinRTPropertyValue
0x18000ed54  mov     ebx, eax
0x18000ed56  test    eax, eax
0x18000ed58  js      short loc_18000EDAA
0x18000ed5a  mov     [rbp+57h+var_90], sil
0x18000ed5e  mov     rsi, [rbp+57h+ppvOut]
0x18000ed62  mov     rax, [rsi]
0x18000ed65  mov     rdi, [rax+50h]
0x18000ed69  mov     rbx, [rbp+57h+var_80]
0x18000ed6d  mov     [rbp+57h+var_40], 0
0x18000ed75  mov     r9d, 5; unsigned int
0x18000ed7b  lea     r8d, [r9+1]; unsigned int
0x18000ed7f  lea     rdx, aAppid; "AppId"
0x18000ed86  lea     rcx, [rbp+57h+var_58]; hstringHeader
0x18000ed8a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000ed8f  nop
0x18000ed90  lea     r9, [rbp+57h+var_90]
0x18000ed94  mov     r8, rbx
0x18000ed97  mov     rdx, [rbp+57h+var_40]
0x18000ed9b  mov     rcx, rsi
0x18000ed9e  mov     rax, rdi
0x18000eda1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eda6  mov     ebx, eax
0x18000eda8  xor     esi, esi
0x18000edaa  lea     rcx, [rbp+57h+var_80]
0x18000edae  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18000edb3  nop
0x18000edb4  lea     rcx, [rbp+57h+propvar]
0x18000edb8  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000edbd  nop
0x18000edbe  lea     rcx, [rbp+57h+ppv]
0x18000edc2  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18000edc7  nop
0x18000edc8  lea     rcx, [rbp+57h+ppvOut]
0x18000edcc  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18000edd1  test    ebx, ebx
0x18000edd3  js      loc_18000EF17
0x18000edd9  mov     [rbp+57h+ppvOut], rsi
0x18000eddd  lea     rcx, [rbp+57h+ppvOut]
0x18000ede1  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18000ede6  lea     rcx, [r13-0A0h]
0x18000eded  lea     rdx, [rbp+57h+ppv]
0x18000edf1  call    ?SiteUnk@CWRLObjectWithGITSite@@IEAA?AV?$ComPtr@UIUnknown@@@WRL@Microsoft@@XZ; CWRLObjectWithGITSite::SiteUnk(void)
0x18000edf6  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x18000edfa  lea     r8, _GUID_4d4c1e64_e410_4faa_bafa_59ca069bfec2; riid
0x18000ee01  lea     rdx, SID_IImmersiveMonitorService; guidService
0x18000ee08  mov     rcx, [rax]; punk
0x18000ee0b  call    cs:__imp_IUnknown_QueryService
0x18000ee11  mov     ebx, eax
0x18000ee13  lea     rcx, [rbp+57h+ppv]
0x18000ee17  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18000ee1c  test    ebx, ebx
0x18000ee1e  js      short loc_18000EE81
0x18000ee20  mov     [rbp+57h+ppv], rsi
0x18000ee24  mov     rdi, [rbp+57h+ppvOut]
0x18000ee28  mov     rax, [rdi]
0x18000ee2b  mov     rbx, [rax+58h]
0x18000ee2f  lea     rcx, [rbp+57h+ppv]
0x18000ee33  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18000ee38  lea     rax, [rbp+57h+ppv]
0x18000ee3c  mov     [rsp+0C0h+var_A0], rax
0x18000ee41  lea     r8, _GUID_880b26f8_9197_43d0_8045_8702d0d72000
0x18000ee48  mov     r9, r8
0x18000ee4b  mov     rdx, [r14+8]
0x18000ee4f  mov     rcx, rdi
0x18000ee52  mov     rax, rbx
0x18000ee55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee5a  mov     ebx, eax
0x18000ee5c  test    eax, eax
0x18000ee5e  js      short loc_18000EE77
0x18000ee60  mov     r9d, 1
0x18000ee66  mov     r8, [rbp+57h+ppv]
0x18000ee6a  mov     edx, [r14]
0x18000ee6d  mov     rcx, r15
0x18000ee70  call    ?_StartFlowInternal@CSearchServices@@AEAAJW4SearchView@@PEAUIImmersiveMonitor@@W4ShowViewOptions@@@Z; CSearchServices::_StartFlowInternal(SearchView,IImmersiveMonitor *,ShowViewOptions)
0x18000ee75  mov     ebx, eax
0x18000ee77  lea     rcx, [rbp+57h+ppv]
0x18000ee7b  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18000ee80  nop
0x18000ee81  lea     rcx, [rbp+57h+ppvOut]
0x18000ee85  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18000ee8a  test    ebx, ebx
0x18000ee8c  js      loc_18000EF17
0x18000ee92  mov     [rbp+57h+ppv], rsi
0x18000ee96  mov     rax, [r15+98h]
0x18000ee9d  mov     rbx, [rax+30h]
0x18000eea1  lea     rcx, [rbp+57h+ppv]
0x18000eea5  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18000eeaa  lea     rax, [rbp+57h+ppv]
0x18000eeae  mov     [rsp+0C0h+var_A0], rax
0x18000eeb3  lea     r9, _GUID_db8aec44_c731_49ed_b8ef_c8faf39e46c2
0x18000eeba  lea     r8, _GUID_567f0f7d_a499_4461_973f_072cbdda90d6
0x18000eec1  mov     edx, [r14]
0x18000eec4  lea     rcx, [r13-10h]
0x18000eec8  mov     rax, rbx
0x18000eecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eed0  mov     ebx, eax
0x18000eed2  test    eax, eax
0x18000eed4  js      short loc_18000EF0E
0x18000eed6  mov     rcx, [rbp+57h+ppv]
0x18000eeda  mov     rax, [rcx]
0x18000eedd  mov     rdx, r14
0x18000eee0  mov     rax, [rax+18h]
0x18000eee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eee9  mov     ebx, eax
0x18000eeeb  test    eax, eax
0x18000eeed  js      short loc_18000EF0E
0x18000eeef  mov     eax, [r14]
0x18000eef2  neg     eax
0x18000eef4  sbb     r8d, r8d
0x18000eef7  and     r8d, 3
0x18000eefb  add     r8d, 4
0x18000eeff  xor     r9d, r9d
0x18000ef02  mov     edx, [r14]
0x18000ef05  mov     rcx, r15
0x18000ef08  call    ?_EnsureSearchPaneSqmEntryPointForView@CSearchServices@@AEAAJW4SearchView@@W4SearchPaneEntryPoint@@W4SearchPaneSqmQuery@@@Z; CSearchServices::_EnsureSearchPaneSqmEntryPointForView(SearchView,SearchPaneEntryPoint,SearchPaneSqmQuery)
0x18000ef0d  nop
0x18000ef0e  lea     rcx, [rbp+57h+ppv]
0x18000ef12  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18000ef17  mov     eax, ebx
0x18000ef19  mov     rcx, [rbp+57h+var_38]
0x18000ef1d  xor     rcx, rsp; StackCookie
0x18000ef20  call    __security_check_cookie
0x18000ef25  mov     rbx, [rsp+0C0h+arg_10]
0x18000ef2d  add     rsp, 90h
0x18000ef34  pop     r15
0x18000ef36  pop     r14
0x18000ef38  pop     r13
0x18000ef3a  pop     r12
0x18000ef3c  pop     rdi
0x18000ef3d  pop     rsi
0x18000ef3e  pop     rbp
0x18000ef3f  retn
```
