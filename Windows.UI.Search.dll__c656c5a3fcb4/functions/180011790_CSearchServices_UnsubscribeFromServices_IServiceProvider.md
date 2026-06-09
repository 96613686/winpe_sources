# CSearchServices::UnsubscribeFromServices(IServiceProvider *)

- ea: `0x180011790`
- end: `0x1800118ac`
- name: `?UnsubscribeFromServices@CSearchServices@@UEAAJPEAUIServiceProvider@@@Z`
- size: `284`
- prototype: `int(CSearchServices *__hidden this, struct IServiceProvider *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180007b3c`
- `0x18000d9bc`
- `0x180010ec4`
- `0x180011790`
- `0x18007b010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x180011808`
- `SHCORE!IUnknown_QueryService` at `0x180011808`
- `SHCORE!IUnknown_SetSite` at `0x1800117c8`
- `SHCORE!IUnknown_SetSite` at `0x1800117c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSearchServices::UnsubscribeFromServices(CSearchServices *this, IUnknown *a2)
{
  _QWORD *v4; // rcx
  IUnknown *v5; // rcx
  int v6; // ecx
  unsigned int v7; // edi
  __int64 v8; // rax
  __int64 v9; // rdx
  void *ppvOut; // [rsp+30h] [rbp+8h] BYREF

  v4 = (_QWORD *)((char *)this + 224);
  if ( *v4 )
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(v4);
  v5 = (IUnknown *)*((_QWORD *)this + 29);
  if ( v5 )
  {
    IUnknown_SetSite(v5, 0);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 232);
  }
  if ( *((_DWORD *)this + 60) )
  {
    ppvOut = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
    if ( IUnknown_QueryService(a2, &guidService, &GUID_103231ae_04cb_4e5e_b63d_e3ce47cd0f0a, &ppvOut) >= 0 )
      (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvOut + 72LL))(ppvOut, *((unsigned int *)this + 60));
    *((_DWORD *)this + 60) = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
  }
  LOBYTE(ppvOut) = 0;
  if ( *((_QWORD *)this + 27) )
  {
    v6 = 1;
    v7 = 0;
    do
    {
      if ( v7 >= *((_DWORD *)this + 51) )
        break;
      v8 = 16LL * v7;
      v9 = *((_QWORD *)this + 27);
      if ( *(_DWORD *)(v8 + v9) == 1 )
        v6 = CSimpleHashTable_enum_SearchView_CSearchServices::ViewInformation___CDefaultHashPolicy_enum_SearchView__CDefaultKeyCompare_enum_SearchView__CDefaultResizePolicy_CDefaultRehashPolicy_::s_EnumAdaptor__lambda_6b72c731f756e0f6b4f84270c586eb34___(
               &ppvOut,
               v8 + v9 + 4,
               v8 + v9 + 8);
      ++v7;
    }
    while ( v6 );
  }
  CSimpleHashTable<enum SearchView,CSearchServices::ViewInformation *,CDefaultHashPolicy<enum SearchView>,CDefaultKeyCompare<enum SearchView>,CDefaultResizePolicy,CDefaultRehashPolicy>::RemoveAll((char *)this + 200);
  return 0;
}

```

## disassembly

```asm
0x180011790  mov     [rsp+arg_8], rbx
0x180011795  mov     [rsp+arg_10], rsi
0x18001179a  push    rdi
0x18001179b  sub     rsp, 20h
0x18001179f  mov     rsi, rdx
0x1800117a2  mov     rbx, rcx
0x1800117a5  add     rcx, 0E0h
0x1800117ac  cmp     qword ptr [rcx], 0
0x1800117b0  jz      short loc_1800117B7
0x1800117b2  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800117b7  lea     rdi, [rbx+0E8h]
0x1800117be  mov     rcx, [rdi]; punk
0x1800117c1  test    rcx, rcx
0x1800117c4  jz      short loc_1800117D6
0x1800117c6  xor     edx, edx; punkSite
0x1800117c8  call    cs:__imp_IUnknown_SetSite
0x1800117ce  mov     rcx, rdi
0x1800117d1  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800117d6  cmp     dword ptr [rbx+0F0h], 0
0x1800117dd  jz      short loc_18001183D
0x1800117df  mov     [rsp+28h+ppvOut], 0
0x1800117e8  lea     rcx, [rsp+28h+ppvOut]
0x1800117ed  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800117f2  lea     r9, [rsp+28h+ppvOut]; ppvOut
0x1800117f7  lea     r8, _GUID_103231ae_04cb_4e5e_b63d_e3ce47cd0f0a; riid
0x1800117fe  lea     rdx, guidService; guidService
0x180011805  mov     rcx, rsi; punk
0x180011808  call    cs:__imp_IUnknown_QueryService
0x18001180e  test    eax, eax
0x180011810  js      short loc_180011829
0x180011812  mov     rcx, [rsp+28h+ppvOut]
0x180011817  mov     rax, [rcx]
0x18001181a  mov     edx, [rbx+0F0h]
0x180011820  mov     rax, [rax+48h]
0x180011824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011829  mov     dword ptr [rbx+0F0h], 0
0x180011833  lea     rcx, [rsp+28h+ppvOut]
0x180011838  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18001183d  mov     byte ptr [rsp+28h+ppvOut], 0
0x180011842  cmp     qword ptr [rbx+0D8h], 0
0x18001184a  jz      short loc_18001188E
0x18001184c  mov     ecx, 1
0x180011851  xor     edi, edi
0x180011853  cmp     edi, [rbx+0CCh]
0x180011859  jnb     short loc_18001188E
0x18001185b  mov     eax, edi
0x18001185d  shl     rax, 4
0x180011861  mov     rdx, [rbx+0D8h]
0x180011868  cmp     dword ptr [rax+rdx], 1
0x18001186c  jnz     short loc_180011888
0x18001186e  lea     r8, [rdx+8]
0x180011872  add     r8, rax
0x180011875  add     rdx, 4
0x180011879  add     rdx, rax
0x18001187c  lea     rcx, [rsp+28h+ppvOut]
0x180011881  call    CSimpleHashTable_enum_SearchView_CSearchServices__ViewInformation___CDefaultHashPolicy_enum_SearchView__CDefaultKeyCompare_enum_SearchView__CDefaultResizePolicy_CDefaultRehashPolicy___s_EnumAdaptor__lambda_6b72c731f756e0f6b4f84270c586eb34___
0x180011886  mov     ecx, eax
0x180011888  inc     edi
0x18001188a  test    ecx, ecx
0x18001188c  jnz     short loc_180011853
0x18001188e  lea     rcx, [rbx+0C8h]
0x180011895  call    ?RemoveAll@?$CSimpleHashTable@W4SearchView@@PEAUViewInformation@CSearchServices@@V?$CDefaultHashPolicy@W4SearchView@@@@V?$CDefaultKeyCompare@W4SearchView@@@@VCDefaultResizePolicy@@VCDefaultRehashPolicy@@@@QEAAXXZ; CSimpleHashTable<SearchView,CSearchServices::ViewInformation *,CDefaultHashPolicy<SearchView>,CDefaultKeyCompare<SearchView>,CDefaultResizePolicy,CDefaultRehashPolicy>::RemoveAll(void)
0x18001189a  xor     eax, eax
0x18001189c  mov     rbx, [rsp+28h+arg_8]
0x1800118a1  mov     rsi, [rsp+28h+arg_10]
0x1800118a6  add     rsp, 20h
0x1800118aa  pop     rdi
0x1800118ab  retn
```
