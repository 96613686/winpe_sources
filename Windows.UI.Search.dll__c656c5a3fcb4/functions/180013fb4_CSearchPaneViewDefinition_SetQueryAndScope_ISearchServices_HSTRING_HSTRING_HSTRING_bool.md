# CSearchPaneViewDefinition::_SetQueryAndScope(ISearchServices *,HSTRING__ *,HSTRING__ *,HSTRING__ *,bool)

- ea: `0x180013fb4`
- end: `0x1800140ec`
- name: `?_SetQueryAndScope@CSearchPaneViewDefinition@@AEAAXPEAUISearchServices@@PEAUHSTRING__@@11_N@Z`
- size: `312`
- prototype: `void(CSearchPaneViewDefinition *__hidden this, struct ISearchServices *, HSTRING, HSTRING, HSTRING, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800142a0`

## callees

- `0x180007b3c`
- `0x1800114f4`
- `0x180013fb4`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014024`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014024`
- `SHCORE!IUnknown_QueryService` at `0x180014078`
- `SHCORE!IUnknown_QueryService` at `0x180014078`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CSearchPaneViewDefinition::_SetQueryAndScope(
        CSearchPaneViewDefinition *this,
        struct ISearchServices *a2,
        HSTRING a3,
        HSTRING a4,
        HSTRING a5,
        bool a6)
{
  int (__fastcall *v10)(struct ISearchServices *, _QWORD, GUID *, GUID *, __int64 *); // rbx
  __int64 v11; // rdi
  void (__fastcall *v12)(__int64, PCWSTR, _QWORD); // rbx
  PCWSTR StringRawBuffer; // rax
  IUnknown **v14; // rax
  unsigned int v15; // ebx
  void *ppvOut; // [rsp+60h] [rbp+30h] BYREF
  __int64 v17; // [rsp+78h] [rbp+48h] BYREF

  if ( a4 )
  {
    v17 = 0;
    v10 = *(int (__fastcall **)(struct ISearchServices *, _QWORD, GUID *, GUID *, __int64 *))(*(_QWORD *)a2 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v17);
    if ( v10(a2, 0, &GUID_52f077cc_10e3_40ea_ad6d_9313803f91f3, &GUID_52f077cc_10e3_40ea_ad6d_9313803f91f3, &v17) >= 0 )
    {
      v11 = v17;
      v12 = *(void (__fastcall **)(__int64, PCWSTR, _QWORD))(*(_QWORD *)v17 + 40LL);
      StringRawBuffer = WindowsGetStringRawBuffer(a4, 0);
      v12(v11, StringRawBuffer, 0);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v17);
  }
  ppvOut = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
  v14 = (IUnknown **)CWRLObjectWithGITSite::SiteUnk((char *)this + 8, &v17);
  v15 = (unsigned int)IUnknown_QueryService(
                        *v14,
                        (const GUID *const)&SID_SearchBox,
                        &GUID_aa90700f_2340_46a7_ab00_867fd691ecee,
                        &ppvOut) >> 31;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v17);
  if ( (unsigned __int8)v15 != 1 )
  {
    (*(void (__fastcall **)(void *, HSTRING))(*(_QWORD *)ppvOut + 56LL))(ppvOut, a3);
    (*(void (__fastcall **)(void *, HSTRING))(*(_QWORD *)ppvOut + 72LL))(ppvOut, a5);
    if ( a6 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 144LL))(ppvOut);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
}

```

## disassembly

```asm
0x180013fb4  mov     [rsp-28h+arg_8], rbx
0x180013fb9  push    rbp
0x180013fba  push    rsi
0x180013fbb  push    rdi
0x180013fbc  push    r14
0x180013fbe  push    r15
0x180013fc0  mov     rbp, rsp
0x180013fc3  sub     rsp, 30h
0x180013fc7  mov     rsi, r9
0x180013fca  mov     r15, r8
0x180013fcd  mov     rdi, rdx
0x180013fd0  mov     r14, rcx
0x180013fd3  test    r9, r9
0x180013fd6  jz      short loc_180014045
0x180013fd8  mov     [rbp+arg_18], 0
0x180013fe0  mov     rax, [rdx]
0x180013fe3  mov     rbx, [rax+30h]
0x180013fe7  lea     rcx, [rbp+arg_18]
0x180013feb  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180013ff0  lea     rax, [rbp+arg_18]
0x180013ff4  mov     [rsp+30h+var_10], rax
0x180013ff9  lea     r8, _GUID_52f077cc_10e3_40ea_ad6d_9313803f91f3
0x180014000  mov     r9, r8
0x180014003  xor     edx, edx
0x180014005  mov     rcx, rdi
0x180014008  mov     rax, rbx
0x18001400b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014010  test    eax, eax
0x180014012  js      short loc_18001403C
0x180014014  mov     rdi, [rbp+arg_18]
0x180014018  mov     rax, [rdi]
0x18001401b  mov     rbx, [rax+28h]
0x18001401f  xor     edx, edx; length
0x180014021  mov     rcx, rsi; string
0x180014024  call    cs:__imp_WindowsGetStringRawBuffer
0x18001402a  xor     r8d, r8d
0x18001402d  mov     rdx, rax
0x180014030  mov     rcx, rdi
0x180014033  mov     rax, rbx
0x180014036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001403b  nop
0x18001403c  lea     rcx, [rbp+arg_18]
0x180014040  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180014045  mov     [rbp+ppvOut], 0
0x18001404d  lea     rcx, [rbp+ppvOut]
0x180014051  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180014056  lea     rcx, [r14+8]
0x18001405a  lea     rdx, [rbp+arg_18]
0x18001405e  call    ?SiteUnk@CWRLObjectWithGITSite@@IEAA?AV?$ComPtr@UIUnknown@@@WRL@Microsoft@@XZ; CWRLObjectWithGITSite::SiteUnk(void)
0x180014063  lea     r9, [rbp+ppvOut]; ppvOut
0x180014067  lea     r8, _GUID_aa90700f_2340_46a7_ab00_867fd691ecee; riid
0x18001406e  lea     rdx, SID_SearchBox; guidService
0x180014075  mov     rcx, [rax]; punk
0x180014078  call    cs:__imp_IUnknown_QueryService
0x18001407e  mov     ebx, eax
0x180014080  shr     ebx, 1Fh
0x180014083  lea     rcx, [rbp+arg_18]
0x180014087  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18001408c  xor     bl, 1
0x18001408f  jz      short loc_1800140D2
0x180014091  mov     rcx, [rbp+ppvOut]
0x180014095  mov     rax, [rcx]
0x180014098  mov     rdx, r15
0x18001409b  mov     rax, [rax+38h]
0x18001409f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140a4  mov     rcx, [rbp+ppvOut]
0x1800140a8  mov     rax, [rcx]
0x1800140ab  mov     rdx, [rbp+arg_20]
0x1800140af  mov     rax, [rax+48h]
0x1800140b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140b8  cmp     [rbp+arg_28], 0
0x1800140bc  jz      short loc_1800140D2
0x1800140be  mov     rcx, [rbp+ppvOut]
0x1800140c2  mov     rax, [rcx]
0x1800140c5  mov     rax, [rax+90h]
0x1800140cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140d1  nop
0x1800140d2  lea     rcx, [rbp+ppvOut]
0x1800140d6  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800140db  mov     rbx, [rsp+30h+arg_8]
0x1800140e0  add     rsp, 30h
0x1800140e4  pop     r15
0x1800140e6  pop     r14
0x1800140e8  pop     rdi
0x1800140e9  pop     rsi
0x1800140ea  pop     rbp
0x1800140eb  retn
```
