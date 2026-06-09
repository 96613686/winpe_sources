# GetWindowFromSite(IUnknown *,HWND__ * *)

- ea: `0x1800358b0`
- end: `0x180035979`
- name: `?GetWindowFromSite@@YAJPEAUIUnknown@@PEAPEAUHWND__@@@Z`
- size: `201`
- prototype: `__int64 __fastcall(IUnknown *punk, HWND *phwnd)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180038640`
- `0x1800393ac`
- `0x18006ed90`
- `0x1800767ec`

## callees

- `0x180007b3c`
- `0x1800358b0`
- `0x18007b010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x1800358f0`
- `SHCORE!IUnknown_QueryService` at `0x18003593b`
- `SHCORE!IUnknown_QueryService` at `0x1800358f0`
- `SHCORE!IUnknown_QueryService` at `0x18003593b`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18003594f`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18003594f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetWindowFromSite(IUnknown *punk, HWND *phwnd)
{
  HRESULT Service; // ebx
  IUnknown *punka; // [rsp+38h] [rbp+10h] BYREF
  void *ppvOut; // [rsp+40h] [rbp+18h] BYREF

  *phwnd = 0;
  ppvOut = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
  if ( IUnknown_QueryService(
         punk,
         &GUID_c3852ed5_c926_4cac_98c4_b7afc5d289d6,
         &GUID_00000114_0000_0000_c000_000000000046,
         &ppvOut) < 0 )
  {
    punka = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&punka);
    Service = IUnknown_QueryService(
                punk,
                (const GUID *const)&SID_STopLevelBrowser,
                &GUID_00000000_0000_0000_c000_000000000046,
                (void **)&punka);
    if ( Service >= 0 )
      Service = IUnknown_GetWindow(punka, phwnd);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&punka);
  }
  else
  {
    Service = (*(__int64 (__fastcall **)(void *, HWND *))(*(_QWORD *)ppvOut + 24LL))(ppvOut, phwnd);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
  return (unsigned int)Service;
}

```

## disassembly

```asm
0x1800358b0  mov     [rsp+arg_0], rbx
0x1800358b5  push    rdi
0x1800358b6  sub     rsp, 20h
0x1800358ba  mov     rdi, rdx
0x1800358bd  mov     rbx, rcx
0x1800358c0  mov     qword ptr [rdx], 0
0x1800358c7  mov     [rsp+28h+ppvOut], 0
0x1800358d0  lea     rcx, [rsp+28h+ppvOut]
0x1800358d5  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800358da  lea     r9, [rsp+28h+ppvOut]; ppvOut
0x1800358df  lea     r8, _GUID_00000114_0000_0000_c000_000000000046; riid
0x1800358e6  lea     rdx, _GUID_c3852ed5_c926_4cac_98c4_b7afc5d289d6; guidService
0x1800358ed  mov     rcx, rbx; punk
0x1800358f0  call    cs:__imp_IUnknown_QueryService
0x1800358f6  test    eax, eax
0x1800358f8  js      short loc_180035912
0x1800358fa  mov     rcx, [rsp+28h+ppvOut]
0x1800358ff  mov     rax, [rcx]
0x180035902  mov     rdx, rdi
0x180035905  mov     rax, [rax+18h]
0x180035909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003590e  mov     ebx, eax
0x180035910  jmp     short loc_180035962
0x180035912  mov     [rsp+28h+punk], 0
0x18003591b  lea     rcx, [rsp+28h+punk]
0x180035920  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180035925  lea     r9, [rsp+28h+punk]; ppvOut
0x18003592a  lea     r8, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180035931  lea     rdx, SID_STopLevelBrowser; guidService
0x180035938  mov     rcx, rbx; punk
0x18003593b  call    cs:__imp_IUnknown_QueryService
0x180035941  mov     ebx, eax
0x180035943  test    eax, eax
0x180035945  js      short loc_180035957
0x180035947  mov     rdx, rdi; phwnd
0x18003594a  mov     rcx, [rsp+28h+punk]; punk
0x18003594f  call    cs:__imp_IUnknown_GetWindow
0x180035955  mov     ebx, eax
0x180035957  lea     rcx, [rsp+28h+punk]
0x18003595c  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180035961  nop
0x180035962  lea     rcx, [rsp+28h+ppvOut]
0x180035967  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003596c  mov     eax, ebx
0x18003596e  mov     rbx, [rsp+28h+arg_0]
0x180035973  add     rsp, 20h
0x180035977  pop     rdi
0x180035978  retn
```
