# ActivateAppForSearchContract

- ea: `0x18003d19c`
- end: `0x18003d32c`
- name: `ActivateAppForSearchContract`
- size: `400`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003c9d0`

## callees

- `0x180007b3c`
- `0x18000f2a8`
- `0x180015878`
- `0x180032ab4`
- `0x18003a684`
- `0x18003a8f8`
- `0x18003d19c`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003d25d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003d25d`
- `ext-ms-win-com-ole32-l1-1-1!CoAllowSetForegroundWindow` at `0x18003d273`
- `ext-ms-win-com-ole32-l1-1-1!CoAllowSetForegroundWindow` at `0x18003d273`

## pseudocode

```c
__int64 __fastcall ActivateAppForSearchContract(
        __int64 a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct Windows::ApplicationModel::Search::ISearchPaneQueryLinguisticDetails *a4)
{
  _lambda_db6ef18a8a1076c7d75719f12dfb2009_ *v4; // rax
  __int64 v5; // rdx
  int v6; // ecx
  int Instance; // ebx
  IUnknown *v8; // r15
  __int64 v9; // rsi
  struct IUnknownVtbl *lpVtbl; // rax
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // r14
  __int64 v12; // rbx
  __int64 v13; // rdi
  __int64 v14; // rax
  IUnknown *pUnk; // [rsp+40h] [rbp-71h] BYREF
  __int64 v17; // [rsp+48h] [rbp-69h] BYREF
  __int64 v18; // [rsp+50h] [rbp-61h] BYREF
  int v19; // [rsp+58h] [rbp-59h] BYREF
  struct Windows::ApplicationModel::Search::ISearchPaneQueryLinguisticDetails *v20; // [rsp+60h] [rbp-51h] BYREF
  unsigned __int16 *v21; // [rsp+68h] [rbp-49h] BYREF
  unsigned __int16 *v22; // [rsp+70h] [rbp-41h] BYREF
  __int64 v23; // [rsp+78h] [rbp-39h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-31h] BYREF
  __int64 v25; // [rsp+98h] [rbp-19h]
  _BYTE v26[32]; // [rsp+A0h] [rbp-11h] BYREF

  v23 = a1;
  v22 = a2;
  v21 = a3;
  v20 = a4;
  v18 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v18);
  v4 = _lambda_db6ef18a8a1076c7d75719f12dfb2009_::_lambda_db6ef18a8a1076c7d75719f12dfb2009_(
         (_lambda_db6ef18a8a1076c7d75719f12dfb2009_ *)&hstringHeader,
         (const unsigned __int16 **)&v22,
         (const unsigned __int16 **)&v21,
         &v20);
  Instance = Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<CSearchActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,_lambda_db6ef18a8a1076c7d75719f12dfb2009_>(
               v6,
               v5,
               &v18,
               (__int64)v4);
  if ( Instance >= 0 )
  {
    v17 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v17);
    Instance = Microsoft::WRL::Details::MakeAndInitialize<CImmersiveWindowFactory,Windows::UI::Core::ICoreWindowFactory,>(&v17);
    if ( Instance >= 0 )
    {
      pUnk = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&pUnk);
      Instance = CoCreateInstance(
                   &CLSID_ApplicationActivationManager,
                   0,
                   1u,
                   &GUID_54e4c428_d1d4_47d4_ade6_46c829114a7d,
                   (LPVOID *)&pUnk);
      if ( Instance >= 0 )
      {
        CoAllowSetForegroundWindow(pUnk, 0);
        v8 = pUnk;
        v9 = v18;
        v19 = 0;
        lpVtbl = pUnk->lpVtbl;
        v25 = 0;
        QueryInterface = lpVtbl[1].QueryInterface;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Search", 0xFu, 0xEu);
        v12 = v25;
        v13 = v17;
        v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v26, &v23);
        Instance = ((__int64 (__fastcall *)(IUnknown *, _QWORD, __int64, __int64, __int64, _DWORD, int *))QueryInterface)(
                     v8,
                     *(_QWORD *)(v14 + 24),
                     v13,
                     v12,
                     v9,
                     0,
                     &v19);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&pUnk);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v17);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v18);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18003d19c  push    rbp
0x18003d19e  push    rbx
0x18003d19f  push    rsi
0x18003d1a0  push    rdi
0x18003d1a1  push    r14
0x18003d1a3  push    r15
0x18003d1a5  lea     rbp, [rsp-27h]
0x18003d1aa  sub     rsp, 0D8h
0x18003d1b1  mov     rax, cs:__security_cookie
0x18003d1b8  xor     rax, rsp
0x18003d1bb  mov     [rbp+4Fh+var_40], rax
0x18003d1bf  mov     [rbp+4Fh+var_88], rcx
0x18003d1c3  lea     rcx, [rbp+4Fh+var_B0]
0x18003d1c7  mov     [rbp+4Fh+var_90], rdx
0x18003d1cb  mov     [rbp+4Fh+var_98], r8
0x18003d1cf  mov     [rbp+4Fh+var_A0], r9
0x18003d1d3  mov     [rbp+4Fh+var_B0], 0
0x18003d1db  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003d1e0  lea     r9, [rbp+4Fh+var_A0]; struct Windows::ApplicationModel::Search::ISearchPaneQueryLinguisticDetails **
0x18003d1e4  lea     r8, [rbp+4Fh+var_98]; unsigned __int16 **
0x18003d1e8  lea     rdx, [rbp+4Fh+var_90]; unsigned __int16 **
0x18003d1ec  lea     rcx, [rbp+4Fh+hstringHeader]; this
0x18003d1f0  call    ??0_lambda_db6ef18a8a1076c7d75719f12dfb2009_@@QEAA@AEAPEBG0AEAPEAUISearchPaneQueryLinguisticDetails@Search@ApplicationModel@Windows@@@Z; _lambda_db6ef18a8a1076c7d75719f12dfb2009_::_lambda_db6ef18a8a1076c7d75719f12dfb2009_(ushort const * &,ushort const * &,Windows::ApplicationModel::Search::ISearchPaneQueryLinguisticDetails * &)
0x18003d1f5  mov     r9, rax
0x18003d1f8  lea     r8, [rbp+4Fh+var_B0]
0x18003d1fc  call    ??$_MakeAndInitializeOnSTAThread@VCSearchActivatedEventArgs@@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@V_lambda_db6ef18a8a1076c7d75719f12dfb2009_@@@ComTaskPool@Internal@Windows@@CAJW4TaskOptions@12@KPEAPEAUIActivatedEventArgs@Activation@ApplicationModel@2@AEBV_lambda_db6ef18a8a1076c7d75719f12dfb2009_@@@Z; Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<CSearchActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,_lambda_db6ef18a8a1076c7d75719f12dfb2009_>(Windows::Internal::TaskOptions,ulong,Windows::ApplicationModel::Activation::IActivatedEventArgs * *,_lambda_db6ef18a8a1076c7d75719f12dfb2009_ const &)
0x18003d201  mov     ebx, eax
0x18003d203  test    eax, eax
0x18003d205  js      loc_18003D305
0x18003d20b  lea     rcx, [rbp+4Fh+var_B8]
0x18003d20f  mov     [rbp+4Fh+var_B8], 0
0x18003d217  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003d21c  lea     rcx, [rbp+4Fh+var_B8]
0x18003d220  call    ??$MakeAndInitialize@VCImmersiveWindowFactory@@UICoreWindowFactory@Core@UI@Windows@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUICoreWindowFactory@Core@UI@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CImmersiveWindowFactory,Windows::UI::Core::ICoreWindowFactory,>(Windows::UI::Core::ICoreWindowFactory * *)
0x18003d225  mov     ebx, eax
0x18003d227  test    eax, eax
0x18003d229  js      loc_18003D2FC
0x18003d22f  lea     rcx, [rbp+4Fh+pUnk]
0x18003d233  mov     [rbp+4Fh+pUnk], 0
0x18003d23b  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003d240  xor     edx, edx; pUnkOuter
0x18003d242  lea     rax, [rbp+4Fh+pUnk]
0x18003d246  lea     r9, _GUID_54e4c428_d1d4_47d4_ade6_46c829114a7d; riid
0x18003d24d  mov     [rsp+100h+ppv], rax; ppv
0x18003d252  lea     rcx, CLSID_ApplicationActivationManager; rclsid
0x18003d259  lea     r8d, [rdx+1]; dwClsContext
0x18003d25d  call    cs:__imp_CoCreateInstance
0x18003d263  mov     ebx, eax
0x18003d265  test    eax, eax
0x18003d267  js      loc_18003D2F3
0x18003d26d  mov     rcx, [rbp+4Fh+pUnk]; pUnk
0x18003d271  xor     edx, edx; lpvReserved
0x18003d273  call    cs:__imp_CoAllowSetForegroundWindow
0x18003d279  mov     r15, [rbp+4Fh+pUnk]
0x18003d27d  lea     rdx, sourceString; "Windows.Search"
0x18003d284  mov     rsi, [rbp+4Fh+var_B0]
0x18003d288  lea     rcx, [rbp+4Fh+hstringHeader]; hstringHeader
0x18003d28c  mov     [rbp+4Fh+var_A8], 0
0x18003d293  mov     r9d, 0Eh; unsigned int
0x18003d299  mov     rax, [r15]
0x18003d29c  mov     [rbp+4Fh+var_68], 0
0x18003d2a4  lea     r8d, [r9+1]; unsigned int
0x18003d2a8  mov     r14, [rax+18h]
0x18003d2ac  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003d2b1  mov     rbx, [rbp+4Fh+var_68]
0x18003d2b5  lea     rdx, [rbp+4Fh+var_88]
0x18003d2b9  mov     rdi, [rbp+4Fh+var_B8]
0x18003d2bd  lea     rcx, [rbp+4Fh+var_60]
0x18003d2c1  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003d2c6  lea     rcx, [rbp+4Fh+var_A8]
0x18003d2ca  mov     r9, rbx
0x18003d2cd  mov     [rsp+100h+var_D0], rcx
0x18003d2d2  mov     r8, rdi
0x18003d2d5  mov     [rsp+100h+var_D8], 0
0x18003d2dd  mov     rcx, r15
0x18003d2e0  mov     rdx, [rax+18h]
0x18003d2e4  mov     rax, r14
0x18003d2e7  mov     [rsp+100h+ppv], rsi
0x18003d2ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d2f1  mov     ebx, eax
0x18003d2f3  lea     rcx, [rbp+4Fh+pUnk]
0x18003d2f7  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003d2fc  lea     rcx, [rbp+4Fh+var_B8]
0x18003d300  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003d305  lea     rcx, [rbp+4Fh+var_B0]
0x18003d309  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003d30e  mov     eax, ebx
0x18003d310  mov     rcx, [rbp+4Fh+var_40]
0x18003d314  xor     rcx, rsp; StackCookie
0x18003d317  call    __security_check_cookie
0x18003d31c  add     rsp, 0D8h
0x18003d323  pop     r15
0x18003d325  pop     r14
0x18003d327  pop     rdi
0x18003d328  pop     rsi
0x18003d329  pop     rbx
0x18003d32a  pop     rbp
0x18003d32b  retn
```
