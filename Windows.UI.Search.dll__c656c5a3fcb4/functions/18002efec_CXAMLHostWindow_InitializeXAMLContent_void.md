# CXAMLHostWindow::_InitializeXAMLContent(void)

- ea: `0x18002efec`
- end: `0x18002f367`
- name: `?_InitializeXAMLContent@CXAMLHostWindow@@AEAAJXZ`
- size: `891`
- prototype: `__int64 __fastcall(CXAMLHostWindow *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002fa58`

## callees

- `0x180007b3c`
- `0x180010fd0`
- `0x18001fa9c`
- `0x18002a1bc`
- `0x18002a3f4`
- `0x18002a7f4`
- `0x18002ea20`
- `0x18002efec`
- `0x18002f370`
- `0x180030cd4`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f05f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f05f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f046`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f046`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002f080`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002f080`
- `SHCORE!IUnknown_SetSite` at `0x18002f217`
- `SHCORE!IUnknown_SetSite` at `0x18002f217`
- `SHCORE!__imp_SHSetWindowSubclass` at `0x18002f18f`
- `SHCORE!__imp_SHSetWindowSubclass` at `0x18002f18f`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CXAMLHostWindow::_InitializeXAMLContent(CXAMLHostWindow *this)
{
  int ActivationFactory; // ebx
  HSTRING v3; // rbx
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD, char *); // rbx
  _QWORD *v6; // r14
  __int64 (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v8)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v9; // rdx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, GUID *, char *); // rbx
  _QWORD *v12; // r15
  IUnknown **v13; // rdi
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, GUID *, char *); // rbx
  __int64 v16; // rax
  GUID *v17; // rbx
  __int64 (__fastcall ***v19)(_QWORD, GUID *, char *); // [rsp+30h] [rbp-29h] BYREF
  __int64 v20; // [rsp+38h] [rbp-21h] BYREF
  __int64 v21; // [rsp+40h] [rbp-19h] BYREF
  GUID *v22; // [rsp+48h] [rbp-11h] BYREF
  __int128 v23; // [rsp+50h] [rbp-9h] BYREF
  HSTRING string; // [rsp+60h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+Fh] BYREF

  ActivationFactory = CXAMLHostWindow::_InitializeXAMLRuntimeSite(this);
  if ( ActivationFactory >= 0 )
  {
    v21 = 0;
    if ( WindowsCreateStringReference(L"Windows.UI.Xaml.Hosting.XamlPresenter", 0x25u, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v3 = string;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v21);
    ActivationFactory = RoGetActivationFactory(v3, &GUID_5c6ef05e_f60d_4433_8bc6_40586456afeb, &v21);
    if ( ActivationFactory >= 0 )
    {
      v4 = v21;
      v5 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v21 + 48LL);
      v6 = (_QWORD *)((char *)this + 232);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 232);
      ActivationFactory = v5(v4, *((unsigned int *)this + 48), (char *)this + 232);
      if ( ActivationFactory >= 0 )
      {
        v20 = 0;
        v7 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v6;
        v8 = **(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v6;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v20);
        ActivationFactory = v8(v7, &GUID_04d09167_1945_43ac_a0a9_b1aed01be2d8, &v20);
        if ( ActivationFactory >= 0 )
        {
          ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v20 + 24LL))(
                                v20,
                                *((_QWORD *)this + 33));
          if ( ActivationFactory >= 0 )
          {
            v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 24LL))(*((_QWORD *)this + 26));
            if ( (*(_BYTE *)(v9 + 40) & 4) == 0
              || (ActivationFactory = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v6 + 64LL))(
                                        *v6,
                                        *(unsigned int *)(v9 + 48),
                                        *(unsigned int *)(v9 + 52)),
                  ActivationFactory >= 0) )
            {
              ActivationFactory = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v6 + 72LL))(*v6, v9);
              if ( ActivationFactory >= 0 )
              {
                if ( (unsigned int)SHSetWindowSubclass(
                                     *((_QWORD *)this + 24),
                                     CXAMLHostWindow::s_SubclassWndProc,
                                     0,
                                     this)
                  || (ActivationFactory = ResultFromKnownLastError(), ActivationFactory >= 0) )
                {
                  v10 = *((_QWORD *)this + 26);
                  v11 = *(__int64 (__fastcall **)(__int64, GUID *, char *))(*(_QWORD *)v10 + 64LL);
                  v12 = (_QWORD *)((char *)this + 240);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 240);
                  ActivationFactory = v11(v10, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, (char *)this + 240);
                  if ( ActivationFactory >= 0 )
                  {
                    v19 = (__int64 (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 14);
                    v13 = (IUnknown **)((char *)this + 256);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 256);
                    ActivationFactory = Microsoft::WRL::Details::MakeAndInitialize<CSiteWithAgileServices,IServiceProvider,IUnknown *>(
                                          (_QWORD *)this + 32,
                                          &v19);
                    if ( ActivationFactory >= 0 )
                    {
                      ActivationFactory = IUnknown_SetSite(*v13, (IUnknown *)this);
                      if ( ActivationFactory >= 0 )
                      {
                        ActivationFactory = IInspectable_SetSite(*v12, *v13);
                        if ( ActivationFactory >= 0 )
                        {
                          v14 = *((_QWORD *)this + 26);
                          v15 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, char *))(*(_QWORD *)v14 + 72LL);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 248);
                          ActivationFactory = v15(
                                                v14,
                                                *v12,
                                                &GUID_676d0be9_b65c_41c6_ba40_58cf87f201c1,
                                                (char *)this + 248);
                          if ( ActivationFactory >= 0 )
                          {
                            v19 = 0;
                            if ( (int)Microsoft::WRL::ComPtr<Windows::UI::Xaml::IUIElement>::As<Windows::UI::Xaml::IFrameworkElement>(
                                        (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))this + 31,
                                        (__int64)&v19) >= 0 )
                            {
                              *(_QWORD *)&v23 = CXAMLHostWindow::_OnLayoutUpdated;
                              DWORD2(v23) = 0;
                              v22 = (GUID *)this;
                              v16 = _lambda_04913792f92a59aefb070e822afdeddb_::_lambda_04913792f92a59aefb070e822afdeddb_(
                                      (__int64)&string,
                                      &v22,
                                      &v23);
                              Microsoft::WRL::Callback<Windows::Foundation::IEventHandler<IInspectable *>,_lambda_8e298b9c695ec0a57076ec54e1d6b1ce_>(
                                (__int64 *)&v22,
                                v16);
                              v17 = v22;
                              (*v19)[49](v19, v22, (char *)this + 440);
                              if ( v17 )
                                (*(void (__fastcall **)(GUID *))(*(_QWORD *)&v17->Data1 + 16LL))(v17);
                            }
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v19);
                            CXAMLHostWindow::_InitializeRootLanguageInfo(this);
                            ActivationFactory = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v6 + 56LL))(
                                                  *v6,
                                                  *((_QWORD *)this + 31));
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v20);
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v21);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18002efec  mov     [rsp-8+arg_8], rbx
0x18002eff1  mov     [rsp-8+arg_10], rsi
0x18002eff6  push    rbp
0x18002eff7  push    rdi
0x18002eff8  push    r12
0x18002effa  push    r14
0x18002effc  push    r15
0x18002effe  lea     rbp, [rsp-37h]
0x18002f003  sub     rsp, 90h
0x18002f00a  mov     rax, cs:__security_cookie
0x18002f011  xor     rax, rsp
0x18002f014  mov     [rbp+57h+var_30], rax
0x18002f018  mov     rsi, rcx
0x18002f01b  call    ?_InitializeXAMLRuntimeSite@CXAMLHostWindow@@AEAAJXZ; CXAMLHostWindow::_InitializeXAMLRuntimeSite(void)
0x18002f020  mov     ebx, eax
0x18002f022  test    eax, eax
0x18002f024  js      loc_18002F33D
0x18002f02a  mov     [rbp+57h+var_70], 0
0x18002f032  lea     r9, [rbp+57h+string]; string
0x18002f036  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18002f03a  mov     edx, 25h ; '%'; length
0x18002f03f  lea     rcx, ?RuntimeClass_Windows_UI_Xaml_Hosting_XamlPresenter@@3QBGB; "Windows.UI.Xaml.Hosting.XamlPresenter"
0x18002f046  call    cs:__imp_WindowsCreateStringReference
0x18002f04c  test    eax, eax
0x18002f04e  jns     short loc_18002F065
0x18002f050  xor     r9d, r9d; lpArguments
0x18002f053  xor     r8d, r8d; nNumberOfArguments
0x18002f056  lea     edx, [r9+1]; dwExceptionFlags
0x18002f05a  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002f05f  call    cs:__imp_RaiseException
0x18002f065  mov     rbx, [rbp+57h+string]
0x18002f069  lea     rcx, [rbp+57h+var_70]
0x18002f06d  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002f072  lea     r8, [rbp+57h+var_70]
0x18002f076  lea     rdx, _GUID_5c6ef05e_f60d_4433_8bc6_40586456afeb
0x18002f07d  mov     rcx, rbx
0x18002f080  call    cs:__imp_RoGetActivationFactory
0x18002f086  mov     ebx, eax
0x18002f088  test    eax, eax
0x18002f08a  js      loc_18002F334
0x18002f090  mov     rdi, [rbp+57h+var_70]
0x18002f094  mov     rax, [rdi]
0x18002f097  mov     rbx, [rax+30h]
0x18002f09b  lea     r14, [rsi+0E8h]
0x18002f0a2  mov     rcx, r14
0x18002f0a5  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002f0aa  mov     r8, r14
0x18002f0ad  mov     edx, [rsi+0C0h]
0x18002f0b3  mov     rcx, rdi
0x18002f0b6  mov     rax, rbx
0x18002f0b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0be  mov     ebx, eax
0x18002f0c0  test    eax, eax
0x18002f0c2  js      loc_18002F334
0x18002f0c8  mov     [rbp+57h+var_78], 0
0x18002f0d0  mov     rdi, [r14]
0x18002f0d3  mov     rax, [rdi]
0x18002f0d6  mov     rbx, [rax]
0x18002f0d9  lea     rcx, [rbp+57h+var_78]
0x18002f0dd  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002f0e2  lea     r8, [rbp+57h+var_78]
0x18002f0e6  lea     rdx, _GUID_04d09167_1945_43ac_a0a9_b1aed01be2d8
0x18002f0ed  mov     rcx, rdi
0x18002f0f0  mov     rax, rbx
0x18002f0f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0f8  mov     ebx, eax
0x18002f0fa  test    eax, eax
0x18002f0fc  js      loc_18002F32A
0x18002f102  mov     rcx, [rbp+57h+var_78]
0x18002f106  mov     rax, [rcx]
0x18002f109  mov     rdx, [rsi+108h]
0x18002f110  mov     rax, [rax+18h]
0x18002f114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f119  mov     ebx, eax
0x18002f11b  test    eax, eax
0x18002f11d  js      loc_18002F32A
0x18002f123  mov     rcx, [rsi+0D0h]
0x18002f12a  mov     rax, [rcx]
0x18002f12d  mov     rax, [rax+18h]
0x18002f131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f136  mov     rdx, rax
0x18002f139  test    byte ptr [rax+28h], 4
0x18002f13d  jz      short loc_18002F162
0x18002f13f  mov     r9, [r14]
0x18002f142  mov     rcx, [r9]
0x18002f145  mov     rax, [rcx+40h]
0x18002f149  mov     r8d, [rdx+34h]
0x18002f14d  mov     edx, [rdx+30h]
0x18002f150  mov     rcx, r9
0x18002f153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f158  mov     ebx, eax
0x18002f15a  test    eax, eax
0x18002f15c  js      loc_18002F32A
0x18002f162  mov     rcx, [r14]
0x18002f165  mov     rax, [rcx]
0x18002f168  mov     rax, [rax+48h]
0x18002f16c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f171  mov     ebx, eax
0x18002f173  test    eax, eax
0x18002f175  js      loc_18002F32A
0x18002f17b  mov     r9, rsi
0x18002f17e  xor     r8d, r8d
0x18002f181  lea     rdx, ?s_SubclassWndProc@CXAMLHostWindow@@CA_JPEAUHWND__@@I_K_J11@Z; CXAMLHostWindow::s_SubclassWndProc(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64)
0x18002f188  mov     rcx, [rsi+0C0h]
0x18002f18f  call    cs:__imp_SHSetWindowSubclass
0x18002f195  test    eax, eax
0x18002f197  jnz     short loc_18002F1A8
0x18002f199  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002f19e  mov     ebx, eax
0x18002f1a0  test    eax, eax
0x18002f1a2  js      loc_18002F32A
0x18002f1a8  mov     rdi, [rsi+0D0h]
0x18002f1af  mov     rax, [rdi]
0x18002f1b2  mov     rbx, [rax+40h]
0x18002f1b6  lea     r15, [rsi+0F0h]
0x18002f1bd  mov     rcx, r15
0x18002f1c0  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002f1c5  mov     r8, r15
0x18002f1c8  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18002f1cf  mov     rcx, rdi
0x18002f1d2  mov     rax, rbx
0x18002f1d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1da  mov     ebx, eax
0x18002f1dc  test    eax, eax
0x18002f1de  js      loc_18002F32A
0x18002f1e4  mov     rax, [rsi+70h]
0x18002f1e8  mov     [rbp+57h+var_80], rax
0x18002f1ec  lea     rdi, [rsi+100h]
0x18002f1f3  mov     rcx, rdi
0x18002f1f6  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002f1fb  lea     rdx, [rbp+57h+var_80]
0x18002f1ff  mov     rcx, rdi
0x18002f202  call    ??$MakeAndInitialize@VCSiteWithAgileServices@@UIServiceProvider@@PEAUIUnknown@@@Details@WRL@Microsoft@@YAJPEAPEAUIServiceProvider@@$$QEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CSiteWithAgileServices,IServiceProvider,IUnknown *>(IServiceProvider * *,IUnknown * &&)
0x18002f207  mov     ebx, eax
0x18002f209  test    eax, eax
0x18002f20b  js      loc_18002F32A
0x18002f211  mov     rdx, rsi; punkSite
0x18002f214  mov     rcx, [rdi]; punk
0x18002f217  call    cs:__imp_IUnknown_SetSite
0x18002f21d  mov     ebx, eax
0x18002f21f  test    eax, eax
0x18002f221  js      loc_18002F32A
0x18002f227  mov     rdx, [rdi]
0x18002f22a  mov     rcx, [r15]
0x18002f22d  call    IInspectable_SetSite
0x18002f232  mov     ebx, eax
0x18002f234  test    eax, eax
0x18002f236  js      loc_18002F32A
0x18002f23c  mov     rdi, [rsi+0D0h]
0x18002f243  mov     rax, [rdi]
0x18002f246  mov     rbx, [rax+48h]
0x18002f24a  lea     r12, [rsi+0F8h]
0x18002f251  mov     rcx, r12
0x18002f254  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002f259  mov     r9, r12
0x18002f25c  lea     r8, _GUID_676d0be9_b65c_41c6_ba40_58cf87f201c1
0x18002f263  mov     rdx, [r15]
0x18002f266  mov     rcx, rdi
0x18002f269  mov     rax, rbx
0x18002f26c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f271  mov     ebx, eax
0x18002f273  test    eax, eax
0x18002f275  js      loc_18002F32A
0x18002f27b  mov     [rbp+57h+var_80], 0
0x18002f283  lea     rdx, [rbp+57h+var_80]
0x18002f287  mov     rcx, r12
0x18002f28a  call    ??$As@UIFrameworkElement@Xaml@UI@Windows@@@?$ComPtr@UIUIElement@Xaml@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIFrameworkElement@Xaml@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Xaml::IUIElement>::As<Windows::UI::Xaml::IFrameworkElement>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Xaml::IFrameworkElement>>)
0x18002f28f  test    eax, eax
0x18002f291  js      short loc_18002F304
0x18002f293  lea     rax, ?_OnLayoutUpdated@CXAMLHostWindow@@AEAAJPEAUIInspectable@@0@Z; CXAMLHostWindow::_OnLayoutUpdated(IInspectable *,IInspectable *)
0x18002f29a  mov     [rbp+57h+var_60], rax
0x18002f29e  mov     [rbp+57h+var_58], 0
0x18002f2a5  mov     eax, [rbp+57h+var_54]
0x18002f2a8  mov     [rbp+57h+var_54], eax
0x18002f2ab  mov     [rbp+57h+var_68], rsi
0x18002f2af  lea     r8, [rbp+57h+var_60]
0x18002f2b3  lea     rdx, [rbp+57h+var_68]
0x18002f2b7  lea     rcx, [rbp+57h+string]
0x18002f2bb  call    ??0_lambda_04913792f92a59aefb070e822afdeddb_@@QEAA@AEBQEAVCSearchScopeSelectorService@@AEBQ81@EAAJPEAUIInspectable@@PEAUIRoutedEventArgs@Xaml@UI@Windows@@@Z@Z; _lambda_04913792f92a59aefb070e822afdeddb_::_lambda_04913792f92a59aefb070e822afdeddb_(CSearchScopeSelectorService * const &,long (CSearchScopeSelectorService::*const &)(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *))
0x18002f2c0  mov     rdx, rax
0x18002f2c3  lea     rcx, [rbp+57h+var_68]
0x18002f2c7  call    ??$Callback@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@V_lambda_8e298b9c695ec0a57076ec54e1d6b1ce_@@@WRL@Microsoft@@YA?AV?$ComPtr@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@@01@$$QEAV_lambda_8e298b9c695ec0a57076ec54e1d6b1ce_@@@Z; Microsoft::WRL::Callback<Windows::Foundation::IEventHandler<IInspectable *>,_lambda_8e298b9c695ec0a57076ec54e1d6b1ce_>(_lambda_8e298b9c695ec0a57076ec54e1d6b1ce_ &&)
0x18002f2cc  nop
0x18002f2cd  mov     rcx, [rbp+57h+var_80]
0x18002f2d1  mov     rax, [rcx]
0x18002f2d4  lea     r8, [rsi+1B8h]
0x18002f2db  mov     rbx, [rbp+57h+var_68]
0x18002f2df  mov     rdx, rbx
0x18002f2e2  mov     rax, [rax+188h]
0x18002f2e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f2ee  nop
0x18002f2ef  test    rbx, rbx
0x18002f2f2  jz      short loc_18002F304
0x18002f2f4  mov     rax, [rbx]
0x18002f2f7  mov     rcx, rbx
0x18002f2fa  mov     rax, [rax+10h]
0x18002f2fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f303  nop
0x18002f304  lea     rcx, [rbp+57h+var_80]
0x18002f308  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002f30d  mov     rcx, rsi; this
0x18002f310  call    ?_InitializeRootLanguageInfo@CXAMLHostWindow@@AEAAXXZ; CXAMLHostWindow::_InitializeRootLanguageInfo(void)
0x18002f315  mov     rcx, [r14]
0x18002f318  mov     rax, [rcx]
0x18002f31b  mov     rdx, [r12]
0x18002f31f  mov     rax, [rax+38h]
0x18002f323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f328  mov     ebx, eax
0x18002f32a  lea     rcx, [rbp+57h+var_78]
0x18002f32e  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002f333  nop
0x18002f334  lea     rcx, [rbp+57h+var_70]
0x18002f338  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002f33d  mov     eax, ebx
0x18002f33f  mov     rcx, [rbp+57h+var_30]
0x18002f343  xor     rcx, rsp; StackCookie
0x18002f346  call    __security_check_cookie
0x18002f34b  lea     r11, [rsp+0B0h+var_20]
0x18002f353  mov     rbx, [r11+38h]
0x18002f357  mov     rsi, [r11+40h]
0x18002f35b  mov     rsp, r11
0x18002f35e  pop     r15
0x18002f360  pop     r14
0x18002f362  pop     r12
0x18002f364  pop     rdi
0x18002f365  pop     rbp
0x18002f366  retn
```
