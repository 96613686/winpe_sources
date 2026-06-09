# CSearchServices::SubscribeToServices(IServiceProvider *)

- ea: `0x1800115e0`
- end: `0x18001171b`
- name: `?SubscribeToServices@CSearchServices@@UEAAJPEAUIServiceProvider@@@Z`
- size: `315`
- prototype: `int(CSearchServices *__hidden this, struct IServiceProvider *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180007b3c`
- `0x1800115e0`
- `0x1800169a4`
- `0x180016dac`
- `0x18007b010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x18001161f`
- `SHCORE!IUnknown_QueryService` at `0x18001161f`
- `SHCORE!IUnknown_SetSite` at `0x180011686`
- `SHCORE!IUnknown_SetSite` at `0x180011686`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSearchServices::SubscribeToServices(IUnknown *this, IUnknown *a2)
{
  int v4; // edi
  IUnknown **v5; // rbx
  IUnknown *v7; // [rsp+20h] [rbp-10h] BYREF
  __int64 (__fastcall ***v8)(_QWORD, GUID *, IUnknown *); // [rsp+60h] [rbp+30h] BYREF
  void *ppvOut; // [rsp+68h] [rbp+38h] BYREF

  v4 = 0;
  ppvOut = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
  if ( IUnknown_QueryService(a2, &guidService, &GUID_103231ae_04cb_4e5e_b63d_e3ce47cd0f0a, &ppvOut) >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(void *, _QWORD, IUnknown *))(*(_QWORD *)ppvOut + 64LL))(
           ppvOut,
           (unsigned __int64)&this[18] & ((unsigned __int128)-(__int128)(unsigned __int64)&this[-6] >> 64),
           this + 30);
    if ( v4 >= 0 )
    {
      v5 = (IUnknown **)&this[29];
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&this[29]);
      v4 = Microsoft::WRL::Details::MakeAndInitialize<CURLExecutionContextImpl,IGetSearchLaunchModeForWindow,>(&this[29]);
      if ( v4 >= 0 )
      {
        v4 = IUnknown_SetSite(*v5, this - 6);
        if ( v4 >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&this[28]);
          v7 = *v5;
          this[28].lpVtbl = 0;
          v8 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v8);
          v4 = Microsoft::WRL::Details::MakeAndInitialize<CURLExecutionContextService,IURLExecutionContextInternal,IGetSearchLaunchModeForWindow * &>(
                 &v8,
                 (__int64 *)&v7);
          if ( v4 >= 0 )
            v4 = (**v8)(v8, &GUID_f01d35df_ec24_4e75_8085_cf9ebe01274c, this + 28);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v8);
        }
      }
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800115e0  mov     [rsp-18h+arg_0], rbx
0x1800115e5  mov     [rsp-18h+arg_8], rsi
0x1800115ea  push    rbp
0x1800115eb  push    rdi
0x1800115ec  push    r14
0x1800115ee  mov     rbp, rsp
0x1800115f1  sub     rsp, 30h
0x1800115f5  mov     rbx, rdx
0x1800115f8  mov     rsi, rcx
0x1800115fb  xor     edi, edi
0x1800115fd  mov     [rbp+ppvOut], rdi
0x180011601  lea     rcx, [rbp+ppvOut]
0x180011605  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18001160a  lea     r9, [rbp+ppvOut]; ppvOut
0x18001160e  lea     r8, _GUID_103231ae_04cb_4e5e_b63d_e3ce47cd0f0a; riid
0x180011615  lea     rdx, guidService; guidService
0x18001161c  mov     rcx, rbx; punk
0x18001161f  call    cs:__imp_IUnknown_QueryService
0x180011625  test    eax, eax
0x180011627  js      loc_1800116FD
0x18001162d  mov     rcx, [rbp+ppvOut]
0x180011631  mov     r10, [rcx]
0x180011634  lea     r8, [rsi+0F0h]
0x18001163b  lea     rax, [rsi-30h]
0x18001163f  lea     r9, [rsi+90h]
0x180011646  neg     rax
0x180011649  sbb     rdx, rdx
0x18001164c  and     rdx, r9
0x18001164f  mov     rax, [r10+40h]
0x180011653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011658  mov     edi, eax
0x18001165a  test    eax, eax
0x18001165c  js      loc_1800116FD
0x180011662  lea     rbx, [rsi+0E8h]
0x180011669  mov     rcx, rbx
0x18001166c  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180011671  mov     rcx, rbx
0x180011674  call    ??$MakeAndInitialize@VCURLExecutionContextImpl@@UIGetSearchLaunchModeForWindow@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIGetSearchLaunchModeForWindow@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CURLExecutionContextImpl,IGetSearchLaunchModeForWindow,>(IGetSearchLaunchModeForWindow * *)
0x180011679  mov     edi, eax
0x18001167b  test    eax, eax
0x18001167d  js      short loc_1800116FD
0x18001167f  lea     rdx, [rsi-30h]; punkSite
0x180011683  mov     rcx, [rbx]; punk
0x180011686  call    cs:__imp_IUnknown_SetSite
0x18001168c  mov     edi, eax
0x18001168e  test    eax, eax
0x180011690  js      short loc_1800116FD
0x180011692  lea     rcx, [rsi+0E0h]
0x180011699  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18001169e  mov     rax, [rbx]
0x1800116a1  mov     [rbp+var_10], rax
0x1800116a5  mov     qword ptr [rsi+0E0h], 0
0x1800116b0  mov     [rbp+arg_10], 0
0x1800116b8  lea     rcx, [rbp+arg_10]
0x1800116bc  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800116c1  lea     rdx, [rbp+var_10]
0x1800116c5  lea     rcx, [rbp+arg_10]
0x1800116c9  call    ??$MakeAndInitialize@VCURLExecutionContextService@@UIURLExecutionContextInternal@@AEAPEAUIGetSearchLaunchModeForWindow@@@Details@WRL@Microsoft@@YAJPEAPEAUIURLExecutionContextInternal@@AEAPEAUIGetSearchLaunchModeForWindow@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CURLExecutionContextService,IURLExecutionContextInternal,IGetSearchLaunchModeForWindow * &>(IURLExecutionContextInternal * *,IGetSearchLaunchModeForWindow * &)
0x1800116ce  mov     edi, eax
0x1800116d0  test    eax, eax
0x1800116d2  js      short loc_1800116F3
0x1800116d4  mov     rcx, [rbp+arg_10]
0x1800116d8  mov     rax, [rcx]
0x1800116db  lea     r8, [rsi+0E0h]
0x1800116e2  lea     rdx, _GUID_f01d35df_ec24_4e75_8085_cf9ebe01274c
0x1800116e9  mov     rax, [rax]
0x1800116ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116f1  mov     edi, eax
0x1800116f3  lea     rcx, [rbp+arg_10]
0x1800116f7  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800116fc  nop
0x1800116fd  lea     rcx, [rbp+ppvOut]
0x180011701  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180011706  mov     eax, edi
0x180011708  mov     rbx, [rsp+30h+arg_0]
0x18001170d  mov     rsi, [rsp+30h+arg_8]
0x180011712  add     rsp, 30h
0x180011716  pop     r14
0x180011718  pop     rdi
0x180011719  pop     rbp
0x18001171a  retn
```
