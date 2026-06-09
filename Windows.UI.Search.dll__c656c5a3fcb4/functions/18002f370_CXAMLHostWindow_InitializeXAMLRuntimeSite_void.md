# CXAMLHostWindow::_InitializeXAMLRuntimeSite(void)

- ea: `0x18002f370`
- end: `0x18002f531`
- name: `?_InitializeXAMLRuntimeSite@CXAMLHostWindow@@AEAAJXZ`
- size: `449`
- prototype: `__int64 __fastcall(CXAMLHostWindow *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002efec`

## callees

- `0x180007b3c`
- `0x1800127ac`
- `0x180012800`
- `0x18002a170`
- `0x18002f370`
- `0x180064f90`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f491`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f491`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002f429`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002f429`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CXAMLHostWindow::_InitializeXAMLRuntimeSite(CXAMLHostWindow *this, __int64 a2, __int64 a3)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, GUID *, __int64 *); // rbx
  __int64 v6; // rcx
  HRESULT ActivationFactory; // ebx
  HSTRING v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-48h] BYREF
  HSTRING string; // [rsp+38h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+58h] [rbp-20h] BYREF

  if ( (Microsoft_Windows_UI_SearchEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_SEARCHUI_PUBLISHER_Context,
      (const EVENT_DESCRIPTOR *)XAML_Load_Start,
      a3,
      1u,
      &v14);
  v12 = 0;
  v4 = *((_QWORD *)this + 26);
  v5 = *(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v4 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v12);
  ActivationFactory = v5(v4, &GUID_1c35e215_859e_41a3_922b_303b8699a29d, &v12);
  if ( ActivationFactory >= 0 )
  {
    v14.Ptr = 0;
    v8 = *Windows::Internal::StringReference::StringReference(&string, L"Windows.UI.Xaml.Hosting.XamlRuntime");
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v14);
    ActivationFactory = RoGetActivationFactory(v8, &GUID_c805b0c0_6210_4e4f_b76a_e894e8b1a4ad, &v14);
    if ( ActivationFactory >= 0 )
    {
      ActivationFactory = (*(__int64 (__fastcall **)(ULONGLONG, _QWORD))(*(_QWORD *)v14.Ptr + 72LL))(v14.Ptr, 0);
      if ( ActivationFactory >= 0 )
      {
        LOBYTE(v9) = 1;
        ActivationFactory = (*(__int64 (__fastcall **)(ULONGLONG, __int64))(*(_QWORD *)v14.Ptr + 56LL))(v14.Ptr, v9);
        if ( ActivationFactory >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 520);
          ActivationFactory = CoCreateInstance(
                                &CLSID_XamlRuntimeSiteAggregator,
                                0,
                                1u,
                                &GUID_00bb2761_6a77_11d0_a535_00c04fd7d062,
                                (LPVOID *)this + 65);
          if ( ActivationFactory >= 0 )
          {
            ActivationFactory = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 65) + 24LL))(
                                  *((_QWORD *)this + 65),
                                  v12);
            if ( ActivationFactory >= 0 )
            {
              v10 = *((_QWORD *)this + 66);
              *((_QWORD *)this + 66) = v12;
              v12 = v10;
            }
          }
        }
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v14);
  }
  if ( (Microsoft_Windows_UI_SearchEnableBits & 1) != 0 )
    McTemplateU0q_EventWriteTransfer(v6, XAML_Load_Stop, (unsigned int)ActivationFactory);
  if ( ActivationFactory >= 0 )
  {
    if ( _InterlockedIncrement(&g_cRegistrationCount) == 1 )
      SearchUI::SearchBoxControlBase::RegisterDependencyProperties();
    *((_BYTE *)this + 449) = 1;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v12);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18002f370  push    rbp
0x18002f372  push    rbx
0x18002f373  push    rsi
0x18002f374  push    rdi
0x18002f375  mov     rbp, rsp
0x18002f378  sub     rsp, 78h
0x18002f37c  mov     rax, cs:__security_cookie
0x18002f383  xor     rax, rsp
0x18002f386  mov     [rbp+var_10], rax
0x18002f38a  mov     rsi, rcx
0x18002f38d  test    byte ptr cs:Microsoft_Windows_UI_SearchEnableBits, 1
0x18002f394  jz      short loc_18002F3B8
0x18002f396  lea     rax, [rbp+var_20]
0x18002f39a  mov     [rsp+78h+ppv], rax
0x18002f39f  mov     r9d, 1
0x18002f3a5  lea     rdx, XAML_Load_Start
0x18002f3ac  lea     rcx, MICROSOFT_SEARCHUI_PUBLISHER_Context
0x18002f3b3  call    McGenEventWrite_EventWriteTransfer
0x18002f3b8  mov     [rbp+var_48], 0
0x18002f3c0  mov     rdi, [rsi+0D0h]
0x18002f3c7  mov     rax, [rdi]
0x18002f3ca  mov     rbx, [rax+38h]
0x18002f3ce  lea     rcx, [rbp+var_48]
0x18002f3d2  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002f3d7  lea     r8, [rbp+var_48]
0x18002f3db  lea     rdx, _GUID_1c35e215_859e_41a3_922b_303b8699a29d
0x18002f3e2  mov     rcx, rdi
0x18002f3e5  mov     rax, rbx
0x18002f3e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f3ed  mov     ebx, eax
0x18002f3ef  test    eax, eax
0x18002f3f1  js      loc_18002F4D5
0x18002f3f7  mov     qword ptr [rbp+var_20], 0
0x18002f3ff  lea     rdx, ?RuntimeClass_Windows_UI_Xaml_Hosting_XamlRuntime@@3QBGB; "Windows.UI.Xaml.Hosting.XamlRuntime"
0x18002f406  lea     rcx, [rbp+string]; string
0x18002f40a  call    ??$?0$0CE@@StringReference@Internal@Windows@@QEAA@AEAY0CE@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[36])
0x18002f40f  mov     rbx, [rax]
0x18002f412  lea     rcx, [rbp+var_20]
0x18002f416  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002f41b  lea     r8, [rbp+var_20]
0x18002f41f  lea     rdx, _GUID_c805b0c0_6210_4e4f_b76a_e894e8b1a4ad
0x18002f426  mov     rcx, rbx
0x18002f429  call    cs:__imp_RoGetActivationFactory
0x18002f42f  mov     ebx, eax
0x18002f431  test    eax, eax
0x18002f433  js      loc_18002F4CC
0x18002f439  mov     rcx, qword ptr [rbp+var_20]
0x18002f43d  mov     rax, [rcx]
0x18002f440  xor     edx, edx
0x18002f442  mov     rax, [rax+48h]
0x18002f446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f44b  mov     ebx, eax
0x18002f44d  test    eax, eax
0x18002f44f  js      short loc_18002F4CC
0x18002f451  mov     rcx, qword ptr [rbp+var_20]
0x18002f455  mov     rax, [rcx]
0x18002f458  mov     dl, 1
0x18002f45a  mov     rax, [rax+38h]
0x18002f45e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f463  mov     ebx, eax
0x18002f465  test    eax, eax
0x18002f467  js      short loc_18002F4CC
0x18002f469  lea     rdi, [rsi+208h]
0x18002f470  mov     rcx, rdi
0x18002f473  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002f478  mov     [rsp+78h+ppv], rdi; ppv
0x18002f47d  lea     r9, _GUID_00bb2761_6a77_11d0_a535_00c04fd7d062; riid
0x18002f484  xor     edx, edx; pUnkOuter
0x18002f486  lea     r8d, [rdx+1]; dwClsContext
0x18002f48a  lea     rcx, CLSID_XamlRuntimeSiteAggregator; rclsid
0x18002f491  call    cs:__imp_CoCreateInstance
0x18002f497  mov     ebx, eax
0x18002f499  test    eax, eax
0x18002f49b  js      short loc_18002F4CC
0x18002f49d  mov     rcx, [rdi]
0x18002f4a0  mov     rax, [rcx]
0x18002f4a3  mov     rdx, [rbp+var_48]
0x18002f4a7  mov     rax, [rax+18h]
0x18002f4ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f4b0  mov     ebx, eax
0x18002f4b2  test    eax, eax
0x18002f4b4  js      short loc_18002F4CC
0x18002f4b6  mov     rcx, [rsi+210h]
0x18002f4bd  mov     rax, [rbp+var_48]
0x18002f4c1  mov     [rsi+210h], rax
0x18002f4c8  mov     [rbp+var_48], rcx
0x18002f4cc  lea     rcx, [rbp+var_20]
0x18002f4d0  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002f4d5  test    byte ptr cs:Microsoft_Windows_UI_SearchEnableBits, 1
0x18002f4dc  jz      short loc_18002F4ED
0x18002f4de  mov     r8d, ebx
0x18002f4e1  lea     rdx, XAML_Load_Stop
0x18002f4e8  call    McTemplateU0q_EventWriteTransfer
0x18002f4ed  test    ebx, ebx
0x18002f4ef  js      short loc_18002F511
0x18002f4f1  mov     eax, 1
0x18002f4f6  lock xadd cs:?g_cRegistrationCount@@3JA, eax; long g_cRegistrationCount
0x18002f4fe  inc     eax
0x18002f500  cmp     eax, 1
0x18002f503  jnz     short loc_18002F50A
0x18002f505  call    ?RegisterDependencyProperties@SearchBoxControlBase@SearchUI@@SAXXZ; SearchUI::SearchBoxControlBase::RegisterDependencyProperties(void)
0x18002f50a  mov     byte ptr [rsi+1C1h], 1
0x18002f511  lea     rcx, [rbp+var_48]
0x18002f515  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002f51a  mov     eax, ebx
0x18002f51c  mov     rcx, [rbp+var_10]
0x18002f520  xor     rcx, rsp; StackCookie
0x18002f523  call    __security_check_cookie
0x18002f528  add     rsp, 78h
0x18002f52c  pop     rdi
0x18002f52d  pop     rsi
0x18002f52e  pop     rbx
0x18002f52f  pop     rbp
0x18002f530  retn
```
