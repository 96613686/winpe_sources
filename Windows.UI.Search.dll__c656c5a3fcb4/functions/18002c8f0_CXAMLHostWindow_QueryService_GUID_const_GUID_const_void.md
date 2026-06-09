# CXAMLHostWindow::QueryService(_GUID const &,_GUID const &,void * *)

- ea: `0x18002c8f0`
- end: `0x18002cce9`
- name: `?QueryService@CXAMLHostWindow@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `1017`
- prototype: `int(CXAMLHostWindow *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003d70`
- `0x180007b3c`
- `0x18002aaa0`
- `0x18002adf4`
- `0x18002b770`
- `0x18002c8f0`
- `0x18002d150`
- `0x18002e014`
- `0x180030710`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18002cb8f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18002cb8f`
- `SHCORE!IUnknown_QueryService` at `0x18002ccb5`
- `SHCORE!IUnknown_QueryService` at `0x18002ccb5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CXAMLHostWindow::QueryService(
        CXAMLHostWindow *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v8; // rax
  _QWORD *v9; // rbx
  HRESULT ResourceMap; // edi
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  struct IResourceMap **v17; // rdx
  __int64 v18; // rax
  const struct _GUID *v19; // rcx
  __int64 v20; // rax
  CWaitCursorManager *v21; // rax
  CWaitCursorManager *v22; // rax
  CWaitCursorManager *v23; // rbx
  __int64 v24; // rax
  CXAMLHostWindow *v25; // rcx
  __int64 v26; // rax
  unsigned __int64 i; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rcx
  void *v33; // [rsp+68h] [rbp+20h] BYREF

  *a4 = 0;
  v8 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_c3852ed5_c926_4cac_98c4_b7afc5d289d6.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_c3852ed5_c926_4cac_98c4_b7afc5d289d6.Data1 )
    v8 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_c3852ed5_c926_4cac_98c4_b7afc5d289d6.Data4;
  if ( !v8 )
  {
    v9 = (_QWORD *)((char *)this + 376);
    if ( *((_QWORD *)this + 47) )
      return (unsigned int)(**(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*v9)(*v9, a3, a4);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 376);
    ResourceMap = Microsoft::WRL::Details::MakeAndInitialize<CXAMLOleWindow,IOleWindow,HWND__ * &>(
                    v9,
                    (char *)this + 72);
    if ( ResourceMap >= 0 )
      return (unsigned int)(**(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*v9)(*v9, a3, a4);
    return (unsigned int)ResourceMap;
  }
  v11 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_662a21f0_4ad5_4fcf_b790_7b83d7d9ee2f.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_662a21f0_4ad5_4fcf_b790_7b83d7d9ee2f.Data1 )
    v11 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_662a21f0_4ad5_4fcf_b790_7b83d7d9ee2f.Data4;
  if ( !v11 )
    return (unsigned int)(**((__int64 (__fastcall ***)(char *, const struct _GUID *, void **))this - 15))(
                           (char *)this - 120,
                           a3,
                           a4);
  v12 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IProfferService.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IProfferService.Data1 )
    v12 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IProfferService.Data4;
  if ( !v12 )
    return (unsigned int)(**((__int64 (__fastcall ***)(char *, const struct _GUID *, void **))this - 15))(
                           (char *)this - 120,
                           a3,
                           a4);
  v13 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&SID_ViewVisibleService.Revision;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&SID_ViewVisibleService.Revision )
    v13 = *(_QWORD *)a2->Data4 - *(_QWORD *)SID_ViewVisibleService.SubAuthority;
  if ( !v13 )
    return (unsigned int)(**((__int64 (__fastcall ***)(char *, const struct _GUID *, void **))this - 15))(
                           (char *)this - 120,
                           a3,
                           a4);
  v14 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_db993c09_9f95_4973_8782_25491e171afe.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_db993c09_9f95_4973_8782_25491e171afe.Data1 )
    v14 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_db993c09_9f95_4973_8782_25491e171afe.Data4;
  if ( !v14 )
    return (unsigned int)(***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 11))(
                           *((_QWORD *)this + 11),
                           a3,
                           a4);
  v15 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&SID_RootElement.Revision;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&SID_RootElement.Revision )
    v15 = *(_QWORD *)a2->Data4 - *(_QWORD *)SID_RootElement.SubAuthority;
  if ( !v15 )
    return (unsigned int)(***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 16))(
                           *((_QWORD *)this + 16),
                           a3,
                           a4);
  v16 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&SID_ResourceMap.Revision;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&SID_ResourceMap.Revision )
    v16 = *(_QWORD *)a2->Data4 - *(_QWORD *)SID_ResourceMap.SubAuthority;
  if ( !v16 )
  {
    v33 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v33);
    ResourceMap = SearchUI::ThreadResourceHelpers::GetResourceMap(&v33, v17);
    if ( ResourceMap >= 0 )
      ResourceMap = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))v33)(v33, a3, a4);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v33);
    return (unsigned int)ResourceMap;
  }
  v18 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IShellTaskScheduler.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IShellTaskScheduler.Data1 )
    v18 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IShellTaskScheduler.Data4;
  if ( !v18 )
  {
    if ( *((_QWORD *)this + 35) )
      return (unsigned int)(***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 35))(
                             *((_QWORD *)this + 35),
                             a3,
                             a4);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 280);
    ResourceMap = CreateDefaultTaskScheduler(v19, (void **)this + 35);
    if ( ResourceMap >= 0 )
      return (unsigned int)(***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 35))(
                             *((_QWORD *)this + 35),
                             a3,
                             a4);
    return (unsigned int)ResourceMap;
  }
  v20 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IWaitCursorManager.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IWaitCursorManager.Data1 )
    v20 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IWaitCursorManager.Data4;
  if ( v20 )
  {
    v24 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&SID_ResourceManager.Revision;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&SID_ResourceManager.Revision )
      v24 = *(_QWORD *)a2->Data4 - *(_QWORD *)SID_ResourceManager.SubAuthority;
    if ( !v24 )
    {
      v25 = (CXAMLHostWindow *)((char *)this - 120);
      if ( *((_QWORD *)v25 + 33) )
        return (unsigned int)(***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 18))(
                               *((_QWORD *)this + 18),
                               a3,
                               a4);
      ResourceMap = CXAMLHostWindow::_AcquireResourceManager(v25);
      if ( ResourceMap >= 0 )
        return (unsigned int)(***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 18))(
                               *((_QWORD *)this + 18),
                               a3,
                               a4);
      return (unsigned int)ResourceMap;
    }
    v26 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&SID_ViewPositionController.Revision;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&SID_ViewPositionController.Revision )
      v26 = *(_QWORD *)a2->Data4 - *(_QWORD *)SID_ViewPositionController.SubAuthority;
    if ( !v26 )
      return (unsigned int)(***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 12))(
                             *((_QWORD *)this + 12),
                             a3,
                             a4);
    for ( i = 0; i < *((_QWORD *)this - 7); ++i )
    {
      v28 = 32 * i;
      v29 = *((_QWORD *)this - 8);
      v30 = *(_QWORD *)(32 * i + v29 + 8) - *(_QWORD *)&a2->Data1;
      if ( !v30 )
        v30 = *(_QWORD *)(v28 + v29 + 16) - *(_QWORD *)a2->Data4;
      if ( !v30 )
      {
        ResourceMap = (*(__int64 (__fastcall **)(_QWORD, const struct _GUID *, const struct _GUID *))(**(_QWORD **)(v28 + v29) + 24LL))(
                        *(_QWORD *)(v28 + v29),
                        a2,
                        a3);
        if ( ResourceMap >= 0 )
          return (unsigned int)ResourceMap;
        break;
      }
    }
    return (unsigned int)IUnknown_QueryService(*((IUnknown **)this - 1), a2, a3, a4);
  }
  if ( *((_QWORD *)this + 36) )
    return (unsigned int)(***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 36))(
                           *((_QWORD *)this + 36),
                           a3,
                           a4);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 288);
  *((_QWORD *)this + 36) = 0;
  v21 = (CWaitCursorManager *)operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v21 )
    return (unsigned int)-2147024882;
  v22 = CWaitCursorManager::CWaitCursorManager(v21);
  if ( (v23 = v22) == 0 )
    return (unsigned int)-2147024882;
  ResourceMap = QISearch(
                  v22,
                  &`CWaitCursorManager::QueryInterface'::`2'::qit,
                  &GUID_fc992f1f_debb_4596_b355_50c7a6dd1222,
                  (void **)this + 36);
  CWaitCursorManager::Release(v23);
  if ( ResourceMap >= 0 )
    return (unsigned int)(***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 36))(
                           *((_QWORD *)this + 36),
                           a3,
                           a4);
  return (unsigned int)ResourceMap;
}

```

## disassembly

```asm
0x18002c8f0  mov     [rsp+arg_0], rbx
0x18002c8f5  mov     [rsp+arg_8], rbp
0x18002c8fa  push    rsi
0x18002c8fb  push    rdi
0x18002c8fc  push    r14
0x18002c8fe  sub     rsp, 30h
0x18002c902  mov     r14, r9
0x18002c905  mov     rbp, r8
0x18002c908  mov     rbx, rdx
0x18002c90b  mov     rsi, rcx
0x18002c90e  mov     qword ptr [r9], 0
0x18002c915  mov     rax, [rdx]
0x18002c918  sub     rax, qword ptr cs:_GUID_c3852ed5_c926_4cac_98c4_b7afc5d289d6.Data1
0x18002c91f  jnz     short loc_18002C92C
0x18002c921  mov     rax, [rdx+8]
0x18002c925  sub     rax, qword ptr cs:_GUID_c3852ed5_c926_4cac_98c4_b7afc5d289d6.Data4
0x18002c92c  test    rax, rax
0x18002c92f  jnz     short loc_18002C976
0x18002c931  lea     rbx, [rcx+178h]
0x18002c938  cmp     [rbx], rax
0x18002c93b  jnz     short loc_18002C95B
0x18002c93d  mov     rcx, rbx
0x18002c940  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002c945  lea     rdx, [rsi+48h]
0x18002c949  mov     rcx, rbx
0x18002c94c  call    ??$MakeAndInitialize@VCXAMLOleWindow@@UIOleWindow@@AEAPEAUHWND__@@@Details@WRL@Microsoft@@YAJPEAPEAUIOleWindow@@AEAPEAUHWND__@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CXAMLOleWindow,IOleWindow,HWND__ * &>(IOleWindow * *,HWND__ * &)
0x18002c951  mov     edi, eax
0x18002c953  test    eax, eax
0x18002c955  js      loc_18002CCD4
0x18002c95b  mov     rcx, [rbx]
0x18002c95e  mov     rax, [rcx]
0x18002c961  mov     r8, r14
0x18002c964  mov     rdx, rbp
0x18002c967  mov     rax, [rax]
0x18002c96a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c96f  mov     edi, eax
0x18002c971  jmp     loc_18002CCD4
0x18002c976  mov     rax, [rdx]
0x18002c979  sub     rax, qword ptr cs:_GUID_662a21f0_4ad5_4fcf_b790_7b83d7d9ee2f.Data1
0x18002c980  jnz     short loc_18002C98D
0x18002c982  mov     rax, [rdx+8]
0x18002c986  sub     rax, qword ptr cs:_GUID_662a21f0_4ad5_4fcf_b790_7b83d7d9ee2f.Data4
0x18002c98d  test    rax, rax
0x18002c990  jz      loc_18002CCBD
0x18002c996  mov     rax, [rdx]
0x18002c999  sub     rax, qword ptr cs:IID_IProfferService.Data1
0x18002c9a0  jnz     short loc_18002C9AD
0x18002c9a2  mov     rax, [rdx+8]
0x18002c9a6  sub     rax, qword ptr cs:IID_IProfferService.Data4
0x18002c9ad  test    rax, rax
0x18002c9b0  jz      loc_18002CCBD
0x18002c9b6  mov     rax, [rdx]
0x18002c9b9  sub     rax, qword ptr cs:SID_ViewVisibleService.Revision
0x18002c9c0  jnz     short loc_18002C9CD
0x18002c9c2  mov     rax, [rdx+8]
0x18002c9c6  sub     rax, qword ptr cs:SID_ViewVisibleService.SubAuthority
0x18002c9cd  test    rax, rax
0x18002c9d0  jz      loc_18002CCBD
0x18002c9d6  mov     rax, [rdx]
0x18002c9d9  sub     rax, qword ptr cs:_GUID_db993c09_9f95_4973_8782_25491e171afe.Data1
0x18002c9e0  jnz     short loc_18002C9ED
0x18002c9e2  mov     rax, [rdx+8]
0x18002c9e6  sub     rax, qword ptr cs:_GUID_db993c09_9f95_4973_8782_25491e171afe.Data4
0x18002c9ed  test    rax, rax
0x18002c9f0  jnz     short loc_18002CA0E
0x18002c9f2  mov     rcx, [rcx+58h]
0x18002c9f6  mov     rax, [rcx]
0x18002c9f9  mov     r8, r14
0x18002c9fc  mov     rdx, rbp
0x18002c9ff  mov     rax, [rax]
0x18002ca02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca07  mov     edi, eax
0x18002ca09  jmp     loc_18002CCD4
0x18002ca0e  mov     rax, [rdx]
0x18002ca11  sub     rax, qword ptr cs:SID_RootElement.Revision
0x18002ca18  jnz     short loc_18002CA25
0x18002ca1a  mov     rax, [rdx+8]
0x18002ca1e  sub     rax, qword ptr cs:SID_RootElement.SubAuthority
0x18002ca25  test    rax, rax
0x18002ca28  jnz     short loc_18002CA49
0x18002ca2a  mov     rcx, [rcx+80h]
0x18002ca31  mov     rax, [rcx]
0x18002ca34  mov     r8, r14
0x18002ca37  mov     rdx, rbp
0x18002ca3a  mov     rax, [rax]
0x18002ca3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca42  mov     edi, eax
0x18002ca44  jmp     loc_18002CCD4
0x18002ca49  mov     rax, [rdx]
0x18002ca4c  sub     rax, qword ptr cs:SID_ResourceMap.Revision
0x18002ca53  jnz     short loc_18002CA60
0x18002ca55  mov     rax, [rdx+8]
0x18002ca59  sub     rax, qword ptr cs:SID_ResourceMap.SubAuthority
0x18002ca60  test    rax, rax
0x18002ca63  jnz     short loc_18002CAAB
0x18002ca65  mov     [rsp+48h+arg_18], rax
0x18002ca6a  lea     rcx, [rsp+48h+arg_18]
0x18002ca6f  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002ca74  lea     rcx, [rsp+48h+arg_18]; this
0x18002ca79  call    ?GetResourceMap@ThreadResourceHelpers@SearchUI@@YAJPEAPEAUIResourceMap@@@Z; SearchUI::ThreadResourceHelpers::GetResourceMap(IResourceMap * *)
0x18002ca7e  mov     edi, eax
0x18002ca80  test    eax, eax
0x18002ca82  js      short loc_18002CA9C
0x18002ca84  mov     rcx, [rsp+48h+arg_18]
0x18002ca89  mov     rax, [rcx]
0x18002ca8c  mov     r8, r14
0x18002ca8f  mov     rdx, rbp
0x18002ca92  mov     rax, [rax]
0x18002ca95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca9a  mov     edi, eax
0x18002ca9c  lea     rcx, [rsp+48h+arg_18]
0x18002caa1  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002caa6  jmp     loc_18002CCD4
0x18002caab  mov     rax, [rdx]
0x18002caae  sub     rax, qword ptr cs:IID_IShellTaskScheduler.Data1
0x18002cab5  jnz     short loc_18002CAC2
0x18002cab7  mov     rax, [rdx+8]
0x18002cabb  sub     rax, qword ptr cs:IID_IShellTaskScheduler.Data4
0x18002cac2  test    rax, rax
0x18002cac5  jnz     short loc_18002CB11
0x18002cac7  cmp     [rcx+118h], rax
0x18002cace  jnz     short loc_18002CAF2
0x18002cad0  add     rcx, 118h
0x18002cad7  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002cadc  lea     rdx, [rsi+118h]; void **
0x18002cae3  call    ?CreateDefaultTaskScheduler@@YAJAEBU_GUID@@PEAPEAX@Z; CreateDefaultTaskScheduler(_GUID const &,void * *)
0x18002cae8  mov     edi, eax
0x18002caea  test    eax, eax
0x18002caec  js      loc_18002CCD4
0x18002caf2  mov     rcx, [rsi+118h]
0x18002caf9  mov     rax, [rcx]
0x18002cafc  mov     r8, r14
0x18002caff  mov     rdx, rbp
0x18002cb02  mov     rax, [rax]
0x18002cb05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb0a  mov     edi, eax
0x18002cb0c  jmp     loc_18002CCD4
0x18002cb11  mov     rax, [rdx]
0x18002cb14  sub     rax, qword ptr cs:IID_IWaitCursorManager.Data1
0x18002cb1b  jnz     short loc_18002CB28
0x18002cb1d  mov     rax, [rdx+8]
0x18002cb21  sub     rax, qword ptr cs:IID_IWaitCursorManager.Data4
0x18002cb28  test    rax, rax
0x18002cb2b  jnz     loc_18002CBD0
0x18002cb31  cmp     [rcx+120h], rax
0x18002cb38  jnz     short loc_18002CBA7
0x18002cb3a  add     rcx, 120h
0x18002cb41  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002cb46  mov     qword ptr [rsi+120h], 0
0x18002cb51  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002cb58  mov     ecx, 20h ; ' '; unsigned __int64
0x18002cb5d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002cb62  test    rax, rax
0x18002cb65  jz      short loc_18002CBC6
0x18002cb67  mov     rcx, rax; this
0x18002cb6a  call    ??0CWaitCursorManager@@AEAA@XZ; CWaitCursorManager::CWaitCursorManager(void)
0x18002cb6f  mov     rbx, rax
0x18002cb72  test    rax, rax
0x18002cb75  jz      short loc_18002CBC6
0x18002cb77  lea     r9, [rsi+120h]; ppv
0x18002cb7e  lea     r8, _GUID_fc992f1f_debb_4596_b355_50c7a6dd1222; riid
0x18002cb85  lea     rdx, ?qit@?1??QueryInterface@CWaitCursorManager@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; pqit
0x18002cb8c  mov     rcx, rax; that
0x18002cb8f  call    cs:__imp_QISearch
0x18002cb95  mov     edi, eax
0x18002cb97  mov     rcx, rbx; this
0x18002cb9a  call    ?Release@CWaitCursorManager@@UEAAKXZ; CWaitCursorManager::Release(void)
0x18002cb9f  test    edi, edi
0x18002cba1  js      loc_18002CCD4
0x18002cba7  mov     rcx, [rsi+120h]
0x18002cbae  mov     rax, [rcx]
0x18002cbb1  mov     r8, r14
0x18002cbb4  mov     rdx, rbp
0x18002cbb7  mov     rax, [rax]
0x18002cbba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cbbf  mov     edi, eax
0x18002cbc1  jmp     loc_18002CCD4
0x18002cbc6  mov     edi, 8007000Eh
0x18002cbcb  jmp     loc_18002CCD4
0x18002cbd0  mov     rax, [rdx]
0x18002cbd3  sub     rax, qword ptr cs:SID_ResourceManager.Revision
0x18002cbda  jnz     short loc_18002CBE7
0x18002cbdc  mov     rax, [rdx+8]
0x18002cbe0  sub     rax, qword ptr cs:SID_ResourceManager.SubAuthority
0x18002cbe7  test    rax, rax
0x18002cbea  jnz     short loc_18002CC27
0x18002cbec  add     rcx, 0FFFFFFFFFFFFFF88h; this
0x18002cbf0  cmp     [rcx+108h], rax
0x18002cbf7  jnz     short loc_18002CC08
0x18002cbf9  call    ?_AcquireResourceManager@CXAMLHostWindow@@AEAAJXZ; CXAMLHostWindow::_AcquireResourceManager(void)
0x18002cbfe  mov     edi, eax
0x18002cc00  test    eax, eax
0x18002cc02  js      loc_18002CCD4
0x18002cc08  mov     rcx, [rsi+90h]
0x18002cc0f  mov     rax, [rcx]
0x18002cc12  mov     r8, r14
0x18002cc15  mov     rdx, rbp
0x18002cc18  mov     rax, [rax]
0x18002cc1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc20  mov     edi, eax
0x18002cc22  jmp     loc_18002CCD4
0x18002cc27  mov     rax, [rdx]
0x18002cc2a  sub     rax, qword ptr cs:SID_ViewPositionController.Revision
0x18002cc31  jnz     short loc_18002CC3E
0x18002cc33  mov     rax, [rdx+8]
0x18002cc37  sub     rax, qword ptr cs:SID_ViewPositionController.SubAuthority
0x18002cc3e  test    rax, rax
0x18002cc41  jnz     short loc_18002CC5C
0x18002cc43  mov     rcx, [rcx+60h]
0x18002cc47  mov     rax, [rcx]
0x18002cc4a  mov     r8, r14
0x18002cc4d  mov     rdx, rbp
0x18002cc50  mov     rax, [rax]
0x18002cc53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc58  mov     edi, eax
0x18002cc5a  jmp     short loc_18002CCD4
0x18002cc5c  xor     eax, eax
0x18002cc5e  cmp     rax, [rsi-38h]
0x18002cc62  jnb     short loc_18002CCA8
0x18002cc64  mov     rdx, rax
0x18002cc67  shl     rdx, 5
0x18002cc6b  mov     r8, [rsi-40h]
0x18002cc6f  mov     rcx, [rdx+r8+8]
0x18002cc74  sub     rcx, [rbx]
0x18002cc77  jnz     short loc_18002CC82
0x18002cc79  mov     rcx, [rdx+r8+10h]
0x18002cc7e  sub     rcx, [rbx+8]
0x18002cc82  test    rcx, rcx
0x18002cc85  jz      short loc_18002CC8C
0x18002cc87  inc     rax
0x18002cc8a  jmp     short loc_18002CC5E
0x18002cc8c  mov     rcx, [rdx+r8]
0x18002cc90  mov     rax, [rcx]
0x18002cc93  mov     r8, rbp
0x18002cc96  mov     rdx, rbx
0x18002cc99  mov     rax, [rax+18h]
0x18002cc9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cca2  mov     edi, eax
0x18002cca4  test    eax, eax
0x18002cca6  jns     short loc_18002CCD4
0x18002cca8  mov     r9, r14; ppvOut
0x18002ccab  mov     r8, rbp; riid
0x18002ccae  mov     rdx, rbx; guidService
0x18002ccb1  mov     rcx, [rsi-8]; punk
0x18002ccb5  call    cs:__imp_IUnknown_QueryService
0x18002ccbb  jmp     short loc_18002CCD2
0x18002ccbd  add     rcx, 0FFFFFFFFFFFFFF88h
0x18002ccc1  mov     rax, [rcx]
0x18002ccc4  mov     r8, r14
0x18002ccc7  mov     rdx, rbp
0x18002ccca  mov     rax, [rax]
0x18002cccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ccd2  mov     edi, eax
0x18002ccd4  mov     eax, edi
0x18002ccd6  mov     rbx, [rsp+48h+arg_0]
0x18002ccdb  mov     rbp, [rsp+48h+arg_8]
0x18002cce0  add     rsp, 30h
0x18002cce4  pop     r14
0x18002cce6  pop     rdi
0x18002cce7  pop     rsi
0x18002cce8  retn
```
