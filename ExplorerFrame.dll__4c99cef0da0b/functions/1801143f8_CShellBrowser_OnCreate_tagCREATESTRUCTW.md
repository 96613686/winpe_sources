# CShellBrowser::_OnCreate(tagCREATESTRUCTW *)

- ea: `0x1801143f8`
- end: `0x180114983`
- name: `?_OnCreate@CShellBrowser@@AEAAJPEAUtagCREATESTRUCTW@@@Z`
- size: `1419`
- prototype: `__int64 __fastcall(CShellBrowser *__hidden this, struct tagCREATESTRUCTW *)`
- caller_count: `1`
- callee_count: `33`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004ec84`

## callees

- `0x1800218ac`
- `0x1800218d8`
- `0x18002e4e0`
- `0x1800360a0`
- `0x180039270`
- `0x180039680`
- `0x180053a9c`
- `0x180053c10`
- `0x18006a92c`
- `0x1800721b8`
- `0x180072890`
- `0x1800899cc`
- `0x18008f508`
- `0x18009044c`
- `0x1800a36c0`
- `0x1800c5d3c`
- `0x1800d5b9c`
- `0x1800df45c`
- `0x1800df53c`
- `0x1800e9a4c`
- `0x1800fa274`
- `0x180104984`
- `0x1801059e4`
- `0x1801143f8`
- `0x180115a20`
- `0x180125924`
- `0x1801287a0`
- `0x18012d208`
- `0x18013f7d0`
- `0x18017ad60`
- `0x1801b918c`
- `0x1801d51dc`
- `0x180210010`

## import_xrefs

- `SHELL32!SHGetFolderLocation` at `0x180114716`
- `SHELL32!SHGetFolderLocation` at `0x180114716`
- `SHELL32!__imp_ILFree` at `0x180114739`
- `SHELL32!__imp_ILFree` at `0x180114739`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1801147ba`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1801147ba`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180114802`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180114802`
- `USER32!AddClipboardFormatListener` at `0x1801148d1`
- `USER32!AddClipboardFormatListener` at `0x1801148d1`
- `USER32!RegisterWindowMessageW` at `0x18011450d`
- `USER32!RegisterWindowMessageW` at `0x18011450d`
- `PROPSYS!PSPropertyBag_WriteBOOL` at `0x1801145ac`
- `PROPSYS!PSPropertyBag_WriteBOOL` at `0x1801145cc`
- `PROPSYS!PSPropertyBag_WriteBOOL` at `0x1801145ea`
- `PROPSYS!PSPropertyBag_WriteBOOL` at `0x1801145ac`
- `PROPSYS!PSPropertyBag_WriteBOOL` at `0x1801145cc`
- `PROPSYS!PSPropertyBag_WriteBOOL` at `0x1801145ea`
- `UxTheme!__imp_ShouldAppsUseDarkMode` at `0x18011447b`
- `UxTheme!__imp_ShouldAppsUseDarkMode` at `0x18011447b`
- `UxTheme!__imp_IsDarkModeAllowedForApp` at `0x18011448b`
- `UxTheme!__imp_IsDarkModeAllowedForApp` at `0x18011448b`

## string_xrefs

- `0x1801144a2`: `ShellBrowserCreate`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CShellBrowser::_OnCreate(CShellBrowser *this, struct tagCREATESTRUCTW *a2)
{
  __int64 v3; // r14
  __int64 v4; // rcx
  _QWORD *v5; // rbx
  const struct FileExplorerPolicyTelemetryData *FileExplorerPolicyTelemetryData; // rdi
  bool v7; // r13
  bool v8; // r15
  bool v9; // r12
  const char *v10; // rbx
  int *v11; // r8
  int (__fastcall *v12)(char *, GUID *, GUID *, IPropertyBag **); // rbx
  int AgileReference; // edi
  int v14; // r8d
  __int64 v15; // rdx
  __int64 v16; // rcx
  int (__fastcall *v17)(char *, GUID *, GUID *, LPITEMIDLIST *); // rax
  int v18; // ebx
  _QWORD *v19; // rbx
  __int64 v20; // rcx
  int (__fastcall ***v21)(_QWORD, GUID *, __int64 *); // rcx
  int (__fastcall **v22)(_QWORD, GUID *, __int64 *); // rax
  __int64 v23; // rcx
  const char *v24; // rbx
  LPITEMIDLIST pidl; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h] BYREF
  IPropertyBag *propBag; // [rsp+60h] [rbp-A0h] BYREF
  LPSTREAM pStm; // [rsp+68h] [rbp-98h] BYREF
  char *v30[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v31[42]; // [rsp+80h] [rbp-80h] BYREF

  v3 = *((_QWORD *)a2->lpCreateParams + 1);
  v4 = *(_QWORD *)(v3 + 192);
  v5 = (_QWORD *)((char *)this + 640);
  if ( v4 )
  {
    *v5 = v4;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
  }
  TelemetryCorrelationVectorServiceProvider::Increment(v30, *v5);
  FileExplorerPolicyTelemetryData = GetFileExplorerPolicyTelemetryData();
  v7 = SHIsFileExplorerInTabletMode();
  LODWORD(v27) = IsHighContrast();
  v8 = 1;
  v9 = (unsigned __int8)ShouldAppsUseDarkMode() && (unsigned __int8)IsDarkModeAllowedForApp();
  v10 = v30[0];
  wil::ActivityBase<FileExplorerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FileExplorerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v31,
    "ShellBrowserCreate");
  v31[0] = &FileExplorerTelemetry::ShellBrowserCreate::`vftable';
  FileExplorerTelemetry::ShellBrowserCreate::StartActivityWithCorrelationVector(
    (FileExplorerTelemetry::ShellBrowserCreate *)v31,
    v10,
    v9,
    (_DWORD)v27 != 0,
    v7,
    *(_BYTE *)FileExplorerPolicyTelemetryData,
    *((_BYTE *)FileExplorerPolicyTelemetryData + 1),
    *((_BYTE *)FileExplorerPolicyTelemetryData + 2),
    *((_DWORD *)FileExplorerPolicyTelemetryData + 1),
    *((_DWORD *)FileExplorerPolicyTelemetryData + 2));
  if ( !g_idMsgGetAuto )
    g_idMsgGetAuto = RegisterWindowMessageW(L"GetAutomationObject");
  (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 46) + 24LL))(*((_QWORD *)this + 46), (char *)this + 16);
  CShellBrowser::_RegisterAsDropTarget(this);
  ResolveInitialBrowserLocation(*((HWND *)this + 41), (struct IETHREADPARAM *)v3, v11);
  propBag = 0;
  v12 = *(int (__fastcall **)(char *, GUID *, GUID *, IPropertyBag **))(*((_QWORD *)this + 5) + 24LL);
  Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(&propBag);
  if ( v12(
         (char *)this + 40,
         &GUID_a3b24a0a_7b68_448d_9979_c700059c3ad1,
         &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
         &propBag) >= 0 )
  {
    if ( ((*((_DWORD *)this + 164) >> 27) & 1) != 0 || (*((_DWORD *)this + 164) & 0x10000000) != 0 )
    {
      PSPropertyBag_WriteBOOL(propBag, L"InExplorerBrowser", (*((_DWORD *)this + 164) >> 27) & 1);
      PSPropertyBag_WriteBOOL(propBag, L"ExpandInitialNav", (*((_DWORD *)this + 164) >> 28) & 1);
    }
    if ( CanShowTabs() )
      PSPropertyBag_WriteBOOL(propBag, L"RibbonVisible", 1);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59355007>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59355007>::GetImpl'::`2'::impl)
    || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60938018>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60938018>::GetImpl'::`2'::impl) )
  {
    *((_BYTE *)this + 1333) = (*(_DWORD *)(v3 + 8) & 4) != 0;
  }
  AgileReference = CShellBrowser::_InitializeBrowserState(
                     this,
                     *(const struct _ITEMIDLIST_ABSOLUTE **)(v3 + 40),
                     (struct IETHREADPARAM *)v3);
  if ( *(_QWORD *)(v3 + 40) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58778013>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58778013>::GetImpl'::`2'::impl) )
      v14 = 8 * (*(_DWORD *)(v3 + 8) & 4);
    else
      v14 = 0;
    AgileReference = CShellBrowser::_NavigateToPidl(this, *(const struct _ITEMIDLIST_ABSOLUTE **)(v3 + 40), v14, 0);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59355007>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59355007>::GetImpl'::`2'::impl) )
    {
      v17 = *(int (__fastcall **)(char *, GUID *, GUID *, LPITEMIDLIST *))(*((_QWORD *)this + 5) + 24LL);
      pidl = 0;
      if ( v17((char *)this + 40, &IID_INameSpaceTreeControl, &GUID_cd874c13_3505_4784_a05d_66a2692d6a92, &pidl) >= 0 )
        (*(void (__fastcall **)(LPITEMIDLIST, _QWORD))(*(_QWORD *)&pidl->mkid.cb + 24LL))(
          pidl,
          *((unsigned __int8 *)this + 1333));
      ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&pidl);
    }
    if ( AgileReference < 0 )
    {
      if ( (*(_BYTE *)(v3 + 8) & 8) != 0 )
      {
        if ( AgileReference != -2147023673
          || (pidl = 0, SHGetFolderLocation(0, 5, 0, 0, &pidl) >= 0)
          && (v18 = ILIsEqualIncludingHiddenEx(*(_QWORD *)(v3 + 40), pidl, 0xFFFFFFFFLL), ILFree(pidl), v18) )
        {
          AgileReference = CShellBrowser::_NavigateToPidl(
                             this,
                             (const struct _ITEMIDLIST_ABSOLUTE *)&c_idlDesktop,
                             0,
                             0);
        }
      }
    }
    else
    {
      Fire_ExplorerNavigateOnIDList(v16, v15, (char *)this + 16, *(_QWORD *)(v3 + 40));
    }
  }
  v19 = (_QWORD *)(v3 + 32);
  v20 = *(_QWORD *)(v3 + 32);
  if ( v20 )
  {
    if ( AgileReference >= 0 )
    {
      pStm = 0;
      AgileReference = (*(__int64 (__fastcall **)(__int64, LPSTREAM *))(*(_QWORD *)v20 + 32LL))(v20, &pStm);
      if ( AgileReference >= 0 )
      {
        AgileReference = CoMarshalInterface(pStm, &IID_IUnknown, *((LPUNKNOWN *)this + 44), 3u, 0, 0);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58778013>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58778013>::GetImpl'::`2'::impl)
          && AgileReference >= 0 )
        {
          pidl = 0;
          wil::com_ptr_t<IAgileReference,wil::err_exception_policy>::reset(&pidl);
          AgileReference = RoGetAgileReference(0, &IID_IUnknown, *((_QWORD *)this + 44), &pidl);
          if ( AgileReference >= 0 )
          {
            v27 = 0;
            v21 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*v19;
            v22 = *(int (__fastcall ***)(_QWORD, GUID *, __int64 *))*v19;
            v27 = 0;
            if ( (*v22)(v21, &GUID_f9b388a9_dd0f_480e_8c1c_6398324d8c2e, &v27) >= 0 )
              (*(void (__fastcall **)(__int64, LPITEMIDLIST))(*(_QWORD *)v27 + 72LL))(v27, pidl);
            ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&v27);
          }
          wil::com_ptr_t<IObjectArray,wil::err_returncode_policy>::~com_ptr_t<IObjectArray,wil::err_returncode_policy>(&pidl);
        }
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)pStm + 16LL))(pStm);
      }
    }
    (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v19 + 40LL))(*v19, (unsigned int)AgileReference);
    AgileReference = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v19 + 56LL))(*v19);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59324556>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59324556>::GetImpl'::`2'::impl) )
      SafeRelease<IBrowserThreadHandshake>(v3 + 32);
  }
  if ( AgileReference >= 0 )
  {
    CShellBrowser::_SetTitle(this);
    CShellBrowser::_SetIcon(this);
    if ( AddClipboardFormatListener(*((HWND *)this + 41)) )
      AgileReference = 0;
    else
      AgileReference = ResultFromKnownLastError();
  }
  else
  {
    CShellBrowser::_SetMenu(this, 0);
  }
  v23 = *((_QWORD *)this + 150);
  if ( v23 && !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v23 + 104LL))(v23) )
    v8 = 0;
  v24 = v30[0];
  wil::ActivityBase<FileExplorerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
    v31,
    (unsigned int)AgileReference);
  FileExplorerTelemetry::ShellBrowserCreate::Stop(
    (FileExplorerTelemetry::ShellBrowserCreate *)v31,
    *((HWND *)this + 41),
    *(const struct _ITEMIDLIST_ABSOLUTE **)(v3 + 40),
    v24,
    v8);
  *((_DWORD *)this + 332) = AgileReference;
  Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(&propBag);
  FileExplorerTelemetry::ShellBrowserCreate::~ShellBrowserCreate((FileExplorerTelemetry::ShellBrowserCreate *)v31);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(v30);
  return (unsigned int)AgileReference;
}

```

## disassembly

```asm
0x1801143f8  mov     [rsp-8+arg_10], rbx
0x1801143fd  push    rbp
0x1801143fe  push    rsi
0x1801143ff  push    rdi
0x180114400  push    r12
0x180114402  push    r13
0x180114404  push    r14
0x180114406  push    r15
0x180114408  lea     rbp, [rsp-0E0h]
0x180114410  sub     rsp, 1E0h
0x180114417  mov     rax, cs:__security_cookie
0x18011441e  xor     rax, rsp
0x180114421  mov     [rbp+110h+var_40], rax
0x180114428  mov     rsi, rcx
0x18011442b  mov     rax, [rdx]
0x18011442e  mov     r14, [rax+8]
0x180114432  mov     rcx, [r14+0C0h]
0x180114439  lea     rbx, [rsi+280h]
0x180114440  test    rcx, rcx
0x180114443  jz      short loc_180114454
0x180114445  mov     [rbx], rcx
0x180114448  mov     rax, [rcx]
0x18011444b  mov     rax, [rax+8]
0x18011444f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114454  mov     rdx, [rbx]
0x180114457  lea     rcx, [rsp+210h+var_1A0]
0x18011445c  call    ?Increment@TelemetryCorrelationVectorServiceProvider@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIUnknown@@@Z; TelemetryCorrelationVectorServiceProvider::Increment(IUnknown *)
0x180114461  nop
0x180114462  call    ?GetFileExplorerPolicyTelemetryData@@YAAEBUFileExplorerPolicyTelemetryData@@XZ; GetFileExplorerPolicyTelemetryData(void)
0x180114467  mov     rdi, rax
0x18011446a  call    ?SHIsFileExplorerInTabletMode@@YA_NXZ; SHIsFileExplorerInTabletMode(void)
0x18011446f  mov     r13b, al
0x180114472  call    ?IsHighContrast@@YAHXZ; IsHighContrast(void)
0x180114477  mov     dword ptr [rsp+210h+var_1B8], eax
0x18011447b  call    cs:__imp_ShouldAppsUseDarkMode
0x180114481  mov     r15d, 1
0x180114487  test    al, al
0x180114489  jz      short loc_18011449A
0x18011448b  call    cs:__imp_IsDarkModeAllowedForApp
0x180114491  test    al, al
0x180114493  jz      short loc_18011449A
0x180114495  mov     r12b, r15b
0x180114498  jmp     short loc_18011449D
0x18011449a  xor     r12b, r12b
0x18011449d  mov     rbx, [rsp+210h+var_1A0]
0x1801144a2  lea     rdx, aShellbrowsercr; "ShellBrowserCreate"
0x1801144a9  lea     rcx, [rbp+110h+var_190]
0x1801144ad  call    ??0?$ActivityBase@VFileExplorerLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FileExplorerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FileExplorerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1801144b2  lea     rax, ??_7ShellBrowserCreate@FileExplorerTelemetry@@6B@; const FileExplorerTelemetry::ShellBrowserCreate::`vftable'
0x1801144b9  mov     [rbp+110h+var_190], rax
0x1801144bd  cmp     dword ptr [rsp+210h+var_1B8], 0
0x1801144c2  setnz   r9b; bool
0x1801144c6  mov     eax, [rdi+8]
0x1801144c9  mov     [rsp+210h+var_1C8], eax; unsigned int
0x1801144cd  mov     eax, [rdi+4]
0x1801144d0  mov     [rsp+210h+var_1D0], eax; unsigned int
0x1801144d4  mov     al, [rdi+2]
0x1801144d7  mov     [rsp+210h+var_1D8], al; bool
0x1801144db  mov     al, [rdi+1]
0x1801144de  mov     [rsp+210h+var_1E0], al; bool
0x1801144e2  mov     al, [rdi]
0x1801144e4  mov     byte ptr [rsp+210h+mshlflags], al; bool
0x1801144e8  mov     byte ptr [rsp+210h+ppidl], r13b; bool
0x1801144ed  mov     r8b, r12b; bool
0x1801144f0  mov     rdx, rbx; char *
0x1801144f3  lea     rcx, [rbp+110h+var_190]; this
0x1801144f7  call    ?StartActivityWithCorrelationVector@ShellBrowserCreate@FileExplorerTelemetry@@QEAAXPEBD_N11111II@Z; FileExplorerTelemetry::ShellBrowserCreate::StartActivityWithCorrelationVector(char const *,bool,bool,bool,bool,bool,bool,uint,uint)
0x1801144fc  nop
0x1801144fd  cmp     cs:?g_idMsgGetAuto@@3IA, 0; uint g_idMsgGetAuto
0x180114504  jnz     short loc_180114519
0x180114506  lea     rcx, aGetautomationo; "GetAutomationObject"
0x18011450d  call    cs:__imp_RegisterWindowMessageW
0x180114513  mov     cs:?g_idMsgGetAuto@@3IA, eax; uint g_idMsgGetAuto
0x180114519  mov     rcx, [rsi+170h]
0x180114520  mov     rax, [rcx]
0x180114523  lea     rdx, [rsi+10h]
0x180114527  mov     rax, [rax+18h]
0x18011452b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114530  mov     rcx, rsi; this
0x180114533  call    ?_RegisterAsDropTarget@CShellBrowser@@AEAAXXZ; CShellBrowser::_RegisterAsDropTarget(void)
0x180114538  mov     rdx, r14; struct IETHREADPARAM *
0x18011453b  mov     rcx, [rsi+148h]; HWND
0x180114542  call    ?ResolveInitialBrowserLocation@@YAJPEAUHWND__@@PEAUIETHREADPARAM@@PEAH@Z; ResolveInitialBrowserLocation(HWND__ *,IETHREADPARAM *,int *)
0x180114547  mov     [rsp+210h+propBag], 0
0x180114550  lea     r13, [rsi+28h]
0x180114554  mov     rax, [r13+0]
0x180114558  mov     rbx, [rax+18h]
0x18011455c  lea     rcx, [rsp+210h+propBag]
0x180114561  call    ?InternalRelease@?$ComPtr@UIKnownFolderProperties@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(void)
0x180114566  lea     r9, [rsp+210h+propBag]
0x18011456b  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851
0x180114572  lea     rdx, _GUID_a3b24a0a_7b68_448d_9979_c700059c3ad1
0x180114579  mov     rcx, r13
0x18011457c  mov     rax, rbx
0x18011457f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114584  test    eax, eax
0x180114586  js      short loc_1801145F0
0x180114588  mov     eax, [rsi+290h]
0x18011458e  mov     r8d, eax
0x180114591  shr     r8d, 1Bh
0x180114595  and     r8d, r15d; value
0x180114598  jnz     short loc_1801145A0
0x18011459a  bt      eax, 1Ch
0x18011459e  jnb     short loc_1801145D2
0x1801145a0  lea     rdx, aInexplorerbrow; "InExplorerBrowser"
0x1801145a7  mov     rcx, [rsp+210h+propBag]; propBag
0x1801145ac  call    cs:__imp_PSPropertyBag_WriteBOOL
0x1801145b2  mov     r8d, [rsi+290h]
0x1801145b9  shr     r8d, 1Ch
0x1801145bd  and     r8d, r15d; value
0x1801145c0  lea     rdx, aExpandinitialn; "ExpandInitialNav"
0x1801145c7  mov     rcx, [rsp+210h+propBag]; propBag
0x1801145cc  call    cs:__imp_PSPropertyBag_WriteBOOL
0x1801145d2  call    ?CanShowTabs@@YA_NXZ; CanShowTabs(void)
0x1801145d7  test    al, al
0x1801145d9  jz      short loc_1801145F0
0x1801145db  mov     r8d, r15d; value
0x1801145de  lea     rdx, aRibbonvisible; "RibbonVisible"
0x1801145e5  mov     rcx, [rsp+210h+propBag]; propBag
0x1801145ea  call    cs:__imp_PSPropertyBag_WriteBOOL
0x1801145f0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59355007@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59355007@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59355007> `wil::Feature<__WilFeatureTraits_Feature_59355007>::GetImpl(void)'::`2'::impl
0x1801145f7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59355007@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59355007>::__private_IsEnabled(void)
0x1801145fc  test    al, al
0x1801145fe  jnz     short loc_180114610
0x180114600  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60938018@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60938018@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60938018> `wil::Feature<__WilFeatureTraits_Feature_60938018>::GetImpl(void)'::`2'::impl
0x180114607  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60938018@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60938018>::__private_IsEnabled(void)
0x18011460c  test    al, al
0x18011460e  jz      short loc_180114620
0x180114610  mov     eax, [r14+8]
0x180114614  shr     eax, 2
0x180114617  and     al, r15b
0x18011461a  mov     [rsi+535h], al
0x180114620  mov     r8, r14; struct IETHREADPARAM *
0x180114623  mov     rdx, [r14+28h]; struct _ITEMIDLIST_ABSOLUTE *
0x180114627  mov     rcx, rsi; this
0x18011462a  call    ?_InitializeBrowserState@CShellBrowser@@AEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAUIETHREADPARAM@@@Z; CShellBrowser::_InitializeBrowserState(_ITEMIDLIST_ABSOLUTE const *,IETHREADPARAM *)
0x18011462f  mov     edi, eax
0x180114631  cmp     qword ptr [r14+28h], 0
0x180114636  jz      loc_18011475C
0x18011463c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_58778013@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_58778013@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58778013> `wil::Feature<__WilFeatureTraits_Feature_58778013>::GetImpl(void)'::`2'::impl
0x180114643  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_58778013@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58778013>::__private_IsEnabled(void)
0x180114648  test    al, al
0x18011464a  jnz     short loc_180114651
0x18011464c  xor     r8d, r8d
0x18011464f  jmp     short loc_18011465D
0x180114651  mov     r8d, [r14+8]
0x180114655  and     r8d, 4
0x180114659  shl     r8d, 3; unsigned int
0x18011465d  xor     r9d, r9d; unsigned int
0x180114660  mov     rdx, [r14+28h]; pidl
0x180114664  mov     rcx, rsi; this
0x180114667  call    ?_NavigateToPidl@CShellBrowser@@AEAAJPEBU_ITEMIDLIST_ABSOLUTE@@KK@Z; CShellBrowser::_NavigateToPidl(_ITEMIDLIST_ABSOLUTE const *,ulong,ulong)
0x18011466c  mov     edi, eax
0x18011466e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59355007@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59355007@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59355007> `wil::Feature<__WilFeatureTraits_Feature_59355007>::GetImpl(void)'::`2'::impl
0x180114675  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59355007@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59355007>::__private_IsEnabled(void)
0x18011467a  test    al, al
0x18011467c  jz      short loc_1801146D6
0x18011467e  mov     rdx, [rsi+28h]
0x180114682  mov     rax, [rdx+18h]
0x180114686  mov     [rsp+210h+pidl], 0
0x18011468f  lea     r9, [rsp+210h+pidl]
0x180114694  lea     r8, _GUID_cd874c13_3505_4784_a05d_66a2692d6a92
0x18011469b  lea     rdx, IID_INameSpaceTreeControl
0x1801146a2  mov     rcx, r13
0x1801146a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801146aa  xor     r13d, r13d
0x1801146ad  test    eax, eax
0x1801146af  js      short loc_1801146CA
0x1801146b1  mov     rcx, [rsp+210h+pidl]
0x1801146b6  mov     rax, [rcx]
0x1801146b9  movzx   edx, byte ptr [rsi+535h]
0x1801146c0  mov     rax, [rax+18h]
0x1801146c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801146c9  nop
0x1801146ca  lea     rcx, [rsp+210h+pidl]
0x1801146cf  call    ??1?$CComPtrBase@UISearchIDListFactory@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(void)
0x1801146d4  jmp     short loc_1801146D9
0x1801146d6  xor     r13d, r13d
0x1801146d9  test    edi, edi
0x1801146db  js      short loc_1801146EC
0x1801146dd  mov     r9, [r14+28h]
0x1801146e1  lea     r8, [rsi+10h]
0x1801146e5  call    Fire_ExplorerNavigateOnIDList
0x1801146ea  jmp     short loc_18011475F
0x1801146ec  test    byte ptr [r14+8], 8
0x1801146f1  jz      short loc_18011475F
0x1801146f3  cmp     edi, 800704C7h
0x1801146f9  jnz     short loc_180114743
0x1801146fb  mov     [rsp+210h+pidl], r13
0x180114700  lea     rax, [rsp+210h+pidl]
0x180114705  mov     [rsp+210h+ppidl], rax; ppidl
0x18011470a  xor     r9d, r9d; dwFlags
0x18011470d  xor     r8d, r8d; hToken
0x180114710  lea     edx, [r9+5]; csidl
0x180114714  xor     ecx, ecx; hwnd
0x180114716  call    cs:__imp_SHGetFolderLocation
0x18011471c  test    eax, eax
0x18011471e  js      short loc_18011475F
0x180114720  or      r8d, 0FFFFFFFFh
0x180114724  mov     rdx, [rsp+210h+pidl]
0x180114729  mov     rcx, [r14+28h]
0x18011472d  call    ?ILIsEqualIncludingHiddenEx@@YAHPEBU_ITEMIDLIST_ABSOLUTE@@0W4IIEIHE@@@Z; ILIsEqualIncludingHiddenEx(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *,IIEIHE)
0x180114732  mov     ebx, eax
0x180114734  mov     rcx, [rsp+210h+pidl]; pidl
0x180114739  call    cs:__imp_ILFree
0x18011473f  test    ebx, ebx
0x180114741  jz      short loc_18011475F
0x180114743  xor     r9d, r9d; unsigned int
0x180114746  xor     r8d, r8d; unsigned int
0x180114749  lea     rdx, c_idlDesktop; pidl
0x180114750  mov     rcx, rsi; this
0x180114753  call    ?_NavigateToPidl@CShellBrowser@@AEAAJPEBU_ITEMIDLIST_ABSOLUTE@@KK@Z; CShellBrowser::_NavigateToPidl(_ITEMIDLIST_ABSOLUTE const *,ulong,ulong)
0x180114758  mov     edi, eax
0x18011475a  jmp     short loc_18011475F
0x18011475c  xor     r13d, r13d
0x18011475f  lea     rbx, [r14+20h]
0x180114763  mov     rcx, [rbx]
0x180114766  test    rcx, rcx
0x180114769  jz      loc_1801148AD
0x18011476f  test    edi, edi
0x180114771  js      loc_180114873
0x180114777  mov     [rsp+210h+pStm], r13
0x18011477c  mov     rax, [rcx]
0x18011477f  lea     rdx, [rsp+210h+pStm]
0x180114784  mov     rax, [rax+20h]
0x180114788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011478d  mov     edi, eax
0x18011478f  test    eax, eax
0x180114791  js      loc_180114873
0x180114797  mov     [rsp+210h+mshlflags], r13d; mshlflags
0x18011479c  mov     [rsp+210h+ppidl], r13; pvDestContext
0x1801147a1  mov     r9d, 3; dwDestContext
0x1801147a7  mov     r8, [rsi+160h]; pUnk
0x1801147ae  lea     rdx, IID_IUnknown; riid
0x1801147b5  mov     rcx, [rsp+210h+pStm]; pStm
0x1801147ba  call    cs:__imp_CoMarshalInterface
0x1801147c0  mov     edi, eax
0x1801147c2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_58778013@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_58778013@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58778013> `wil::Feature<__WilFeatureTraits_Feature_58778013>::GetImpl(void)'::`2'::impl
0x1801147c9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_58778013@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58778013>::__private_IsEnabled(void)
0x1801147ce  test    al, al
0x1801147d0  jz      loc_180114862
0x1801147d6  test    edi, edi
0x1801147d8  js      loc_180114862
0x1801147de  mov     [rsp+210h+pidl], r13
0x1801147e3  lea     rcx, [rsp+210h+pidl]
0x1801147e8  call    ?reset@?$com_ptr_t@UIAgileReference@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IAgileReference,wil::err_exception_policy>::reset(void)
0x1801147ed  lea     r9, [rsp+210h+pidl]
0x1801147f2  mov     r8, [rsi+160h]
0x1801147f9  lea     rdx, IID_IUnknown
0x180114800  xor     ecx, ecx
0x180114802  call    cs:__imp_RoGetAgileReference
0x180114808  mov     edi, eax
0x18011480a  test    eax, eax
0x18011480c  js      short loc_180114858
0x18011480e  mov     [rsp+210h+var_1B8], r13
0x180114813  mov     rcx, [rbx]
0x180114816  mov     rax, [rcx]
0x180114819  mov     [rsp+210h+var_1B8], r13
0x18011481e  lea     r8, [rsp+210h+var_1B8]
0x180114823  lea     rdx, _GUID_f9b388a9_dd0f_480e_8c1c_6398324d8c2e
0x18011482a  mov     rax, [rax]
0x18011482d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114832  test    eax, eax
0x180114834  js      short loc_18011484D
0x180114836  mov     rcx, [rsp+210h+var_1B8]
0x18011483b  mov     rax, [rcx]
0x18011483e  mov     rdx, [rsp+210h+pidl]
0x180114843  mov     rax, [rax+48h]
0x180114847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011484c  nop
0x18011484d  lea     rcx, [rsp+210h+var_1B8]
0x180114852  call    ??1?$CComPtrBase@UISearchIDListFactory@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(void)
0x180114857  nop
0x180114858  lea     rcx, [rsp+210h+pidl]
0x18011485d  call    ??1?$com_ptr_t@UIObjectArray@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectArray,wil::err_returncode_policy>::~com_ptr_t<IObjectArray,wil::err_returncode_policy>(void)
0x180114862  mov     rcx, [rsp+210h+pStm]
0x180114867  mov     rax, [rcx]
0x18011486a  mov     rax, [rax+10h]
0x18011486e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114873  mov     rcx, [rbx]
0x180114876  mov     rax, [rcx]
0x180114879  mov     edx, edi
0x18011487b  mov     rax, [rax+28h]
0x18011487f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114884  mov     rcx, [rbx]
0x180114887  mov     rax, [rcx]
0x18011488a  mov     rax, [rax+38h]
0x18011488e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114893  mov     edi, eax
0x180114895  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59324556@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59324556@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59324556> `wil::Feature<__WilFeatureTraits_Feature_59324556>::GetImpl(void)'::`2'::impl
0x18011489c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59324556@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59324556>::__private_IsEnabled(void)
0x1801148a1  test    al, al
0x1801148a3  jz      short loc_1801148AD
0x1801148a5  mov     rcx, rbx
0x1801148a8  call    ??$SafeRelease@UIBrowserThreadHandshake@@@@YAXPEAPEAUIBrowserThreadHandshake@@@Z; SafeRelease<IBrowserThreadHandshake>(IBrowserThreadHandshake * *)
0x1801148ad  mov     rcx, rsi; this
0x1801148b0  test    edi, edi
0x1801148b2  jns     short loc_1801148BD
0x1801148b4  xor     edx, edx; HMENU
0x1801148b6  call    ?_SetMenu@CShellBrowser@@AEAA_NPEAUHMENU__@@@Z; CShellBrowser::_SetMenu(HMENU__ *)
  ... truncated ...
```
