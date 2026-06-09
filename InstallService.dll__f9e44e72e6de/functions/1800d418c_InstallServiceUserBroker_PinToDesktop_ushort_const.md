# InstallServiceUserBroker::PinToDesktop(ushort const *)

- ea: `0x1800d418c`
- end: `0x1800d458e`
- name: `?PinToDesktop@InstallServiceUserBroker@@AEAAJPEBG@Z`
- size: `1026`
- prototype: `int(InstallServiceUserBroker *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d45a0`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x180010b74`
- `0x180014f18`
- `0x18001c414`
- `0x180032c50`
- `0x1800374d0`
- `0x180046ad4`
- `0x1800d4024`
- `0x1800d418c`
- `0x180215010`

## import_xrefs

- `api-ms-win-shell-namespace-l1-1-0!SHGetIDListFromObject` at `0x1800d42a2`
- `api-ms-win-shell-namespace-l1-1-0!SHGetIDListFromObject` at `0x1800d42a2`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800d43ea`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800d43ea`
- `api-ms-win-core-path-l1-1-0!PathCchAddExtension` at `0x1800d4412`
- `api-ms-win-core-path-l1-1-0!PathCchAddExtension` at `0x1800d4412`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d44ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d4557`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d44ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d4557`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d4345`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d4345`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x1800d41d3`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x1800d41d3`
- `ext-ms-win-shell-shell32-l1-2-0!SHCreateItemInKnownFolder` at `0x1800d424e`
- `ext-ms-win-shell-shell32-l1-2-0!SHCreateItemInKnownFolder` at `0x1800d424e`
- `ext-ms-win-shell-shell32-l1-2-1!PathYetAnotherMakeUniqueName` at `0x1800d443b`
- `ext-ms-win-shell-shell32-l1-2-1!PathYetAnotherMakeUniqueName` at `0x1800d443b`

## string_xrefs

- `0x1800d4203`: `onecoreuap\enduser\winstore\installservice\lib\shellhelpers.cpp`
- `0x1800d4262`: `onecoreuap\enduser\winstore\installservice\lib\shellhelpers.cpp`
- `0x1800d4302`: `onecoreuap\enduser\winstore\installservice\lib\shellhelpers.cpp`
- `0x1800d4356`: `onecoreuap\enduser\winstore\installservice\lib\shellhelpers.cpp`
- `0x1800d4489`: `onecoreuap\enduser\winstore\installservice\lib\shellhelpers.cpp`
- `0x1800d4516`: `onecoreuap\enduser\winstore\installservice\lib\shellhelpers.cpp`
- `0x1800d4509`: `InstallServiceUserBroker::PinToDesktop`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall InstallServiceUserBroker::PinToDesktop(InstallServiceUserBroker *this, const unsigned __int16 *a2)
{
  __int64 SelfToken; // rax
  HRESULT v4; // ebx
  HRESULT v6; // eax
  HRESULT v7; // ebx
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  void *v10; // rdi
  __int64 (__fastcall *v11)(void *, _QWORD, PCWSTR *); // rbx
  int v12; // eax
  HRESULT v13; // eax
  __int64 v14; // rdx
  LPVOID v15; // rbx
  __int64 (__fastcall *v16)(LPVOID, GUID *, __int64 *); // rdi
  HRESULT v17; // eax
  __int64 v18; // rdx
  bool v19; // zf
  __int64 (__fastcall *v20)(__int64, WCHAR *, _QWORD); // rax
  void *v21; // rcx
  void *v22; // rcx
  int pszPath; // [rsp+20h] [rbp-4C8h]
  int pszPatha; // [rsp+20h] [rbp-4C8h]
  int pszPathb; // [rsp+20h] [rbp-4C8h]
  LPVOID pv; // [rsp+50h] [rbp-498h] BYREF
  LPVOID v27; // [rsp+58h] [rbp-490h] BYREF
  PCWSTR pszMore; // [rsp+60h] [rbp-488h] BYREF
  __int64 v29; // [rsp+68h] [rbp-480h] BYREF
  void *ppv; // [rsp+70h] [rbp-478h] BYREF
  LPVOID *p_pv; // [rsp+78h] [rbp-470h] BYREF
  LPITEMIDLIST ppidl; // [rsp+80h] [rbp-468h] BYREF
  char v33; // [rsp+88h] [rbp-460h]
  WCHAR v34[264]; // [rsp+90h] [rbp-458h] BYREF
  WCHAR pszUniqueName[264]; // [rsp+2A0h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4E8h] [rbp+0h]

  SelfToken = TokenHelpers::GetSelfToken(&p_pv);
  v4 = SHGetFolderPathW(0, 0, *(HANDLE *)(SelfToken + 8), 1u, v34);
  p_pv = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&p_pv);
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\shellhelpers.cpp",
      (const char *)(unsigned int)v4,
      pszPath);
    return (unsigned int)v4;
  }
  ppv = 0;
  pv = 0;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&ppv);
  v6 = SHCreateItemInKnownFolder(&FOLDERID_AppsFolder, 0x4000u, a2, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = (unsigned int)v6;
    v9 = 81;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\shellhelpers.cpp",
      (const char *)v8,
      pszPatha);
LABEL_29:
    v21 = pv;
    v19 = pv == 0;
    pv = 0;
    if ( !v19 )
      CoTaskMemFree(v21);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&ppv);
    return (unsigned int)v7;
  }
  p_pv = &pv;
  ppidl = 0;
  v33 = 1;
  v7 = SHGetIDListFromObject((IUnknown *)ppv, &ppidl);
  wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( v7 < 0 )
  {
    v8 = (unsigned int)v7;
    v9 = 82;
    goto LABEL_5;
  }
  pszMore = 0;
  v10 = ppv;
  v11 = *(__int64 (__fastcall **)(void *, _QWORD, PCWSTR *))(*(_QWORD *)ppv + 40LL);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &pszMore,
    0);
  v12 = v11(v10, 0, &pszMore);
  v7 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\shellhelpers.cpp",
      (const char *)(unsigned int)v12,
      pszPatha);
LABEL_28:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszMore);
    goto LABEL_29;
  }
  v27 = 0;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v27);
  v13 = CoCreateInstance(
          &GUID_00021401_0000_0000_c000_000000000046,
          0,
          1u,
          &GUID_000214f9_0000_0000_c000_000000000046,
          &v27);
  v7 = v13;
  if ( v13 < 0 )
  {
    v14 = 88;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\shellhelpers.cpp",
      (const char *)(unsigned int)v13,
      pszPathb);
LABEL_27:
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v27);
    goto LABEL_28;
  }
  v13 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)v27 + 40LL))(v27, pv);
  v7 = v13;
  if ( v13 < 0 )
  {
    v14 = 89;
    goto LABEL_12;
  }
  v29 = 0;
  v15 = v27;
  v16 = **(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v27;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v29);
  v17 = v16(v15, &GUID_0000010b_0000_0000_c000_000000000046, &v29);
  v7 = v17;
  if ( v17 < 0 )
  {
    v18 = 92;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\shellhelpers.cpp",
      (const char *)(unsigned int)v17,
      pszPathb);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v29);
    goto LABEL_27;
  }
  v17 = PathCchAppend(v34, 0x104u, pszMore);
  v7 = v17;
  if ( v17 < 0 )
  {
    v18 = 96;
    goto LABEL_26;
  }
  v17 = PathCchAddExtension(v34, 0x104u, L"lnk");
  v7 = v17;
  if ( v17 < 0 )
  {
    v18 = 97;
    goto LABEL_26;
  }
  v19 = !PathYetAnotherMakeUniqueName(pszUniqueName, v34, 0, 0);
  v20 = *(__int64 (__fastcall **)(__int64, WCHAR *, _QWORD))(*(_QWORD *)v29 + 48LL);
  if ( v19 )
  {
    v17 = v20(v29, v34, 0);
    v7 = v17;
    if ( v17 < 0 )
    {
      v18 = 106;
      goto LABEL_26;
    }
  }
  else
  {
    v17 = v20(v29, pszUniqueName, 0);
    v7 = v17;
    if ( v17 < 0 )
    {
      v18 = 102;
      goto LABEL_26;
    }
  }
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\shellhelpers.cpp",
    0x6Du,
    "InstallServiceUserBroker::PinToDesktop",
    -1,
    L"Successfully Pinned %s to Desktop.",
    0,
    0,
    a2);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v29);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v27);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszMore);
  v22 = pv;
  pv = 0;
  if ( v22 )
    CoTaskMemFree(v22);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&ppv);
  return 0;
}

```

## disassembly

```asm
0x1800d418c  push    rbx
0x1800d418e  push    rsi
0x1800d418f  push    rdi
0x1800d4190  push    r14
0x1800d4192  sub     rsp, 4C8h
0x1800d4199  mov     rax, cs:__security_cookie
0x1800d41a0  xor     rax, rsp
0x1800d41a3  mov     [rsp+4E8h+var_38], rax
0x1800d41ab  mov     rsi, rdx
0x1800d41ae  lea     rcx, [rsp+4E8h+var_470]
0x1800d41b3  call    ?GetSelfToken@TokenHelpers@@YA?AV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@XZ; TokenHelpers::GetSelfToken(void)
0x1800d41b8  lea     rcx, [rsp+4E8h+var_458]
0x1800d41c0  mov     [rsp+4E8h+pszPath], rcx; int
0x1800d41c5  mov     r9d, 1; dwFlags
0x1800d41cb  mov     r8, [rax+8]; hToken
0x1800d41cf  xor     edx, edx; csidl
0x1800d41d1  xor     ecx, ecx; hwnd
0x1800d41d3  call    cs:__imp_SHGetFolderPathW
0x1800d41d9  mov     ebx, eax
0x1800d41db  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x1800d41e2  mov     [rsp+4E8h+var_470], rax
0x1800d41e7  lea     rcx, [rsp+4E8h+var_470]
0x1800d41ec  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x1800d41f1  xor     r14d, r14d
0x1800d41f4  test    ebx, ebx
0x1800d41f6  jns     short loc_1800D421A
0x1800d41f8  mov     rcx, [rsp+4E8h]; this
0x1800d4200  mov     r9d, ebx; char *
0x1800d4203  lea     r8, aOnecoreuapEndu_51; "onecoreuap\\enduser\\winstore\\installs"...
0x1800d420a  lea     edx, [r14+4Ch]; void *
0x1800d420e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4213  mov     eax, ebx
0x1800d4215  jmp     loc_1800D4570
0x1800d421a  mov     [rsp+4E8h+ppv], r14
0x1800d421f  mov     [rsp+4E8h+pv], r14
0x1800d4224  lea     rcx, [rsp+4E8h+ppv]
0x1800d4229  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800d422e  lea     rax, [rsp+4E8h+ppv]
0x1800d4233  mov     [rsp+4E8h+pszPath], rax; int
0x1800d4238  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800d423f  mov     r8, rsi; pszItem
0x1800d4242  mov     edx, 4000h; dwKFFlags
0x1800d4247  lea     rcx, FOLDERID_AppsFolder; kfid
0x1800d424e  call    cs:__imp_SHCreateItemInKnownFolder
0x1800d4254  mov     ebx, eax
0x1800d4256  test    eax, eax
0x1800d4258  jns     short loc_1800D427B
0x1800d425a  mov     r9d, eax; char *
0x1800d425d  mov     edx, 51h ; 'Q'; void *
0x1800d4262  lea     r8, aOnecoreuapEndu_51; "onecoreuap\\enduser\\winstore\\installs"...
0x1800d4269  mov     rcx, [rsp+4E8h]; this
0x1800d4271  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4276  jmp     loc_1800D44BF
0x1800d427b  lea     rax, [rsp+4E8h+pv]
0x1800d4280  mov     [rsp+4E8h+var_470], rax
0x1800d4285  mov     [rsp+4E8h+ppidl], r14
0x1800d428d  mov     [rsp+4E8h+var_460], 1
0x1800d4295  lea     rdx, [rsp+4E8h+ppidl]; ppidl
0x1800d429d  mov     rcx, [rsp+4E8h+ppv]; punk
0x1800d42a2  call    cs:__imp_SHGetIDListFromObject
0x1800d42a8  mov     ebx, eax
0x1800d42aa  lea     rcx, [rsp+4E8h+var_470]
0x1800d42af  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800d42b4  test    ebx, ebx
0x1800d42b6  jns     short loc_1800D42C2
0x1800d42b8  mov     r9d, ebx
0x1800d42bb  mov     edx, 52h ; 'R'
0x1800d42c0  jmp     short loc_1800D4262
0x1800d42c2  mov     [rsp+4E8h+pszMore], r14
0x1800d42c7  mov     rdi, [rsp+4E8h+ppv]
0x1800d42cc  mov     rax, [rdi]
0x1800d42cf  mov     rbx, [rax+28h]
0x1800d42d3  xor     edx, edx
0x1800d42d5  lea     rcx, [rsp+4E8h+pszMore]
0x1800d42da  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800d42df  lea     r8, [rsp+4E8h+pszMore]
0x1800d42e4  xor     edx, edx
0x1800d42e6  mov     rcx, rdi
0x1800d42e9  mov     rax, rbx
0x1800d42ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d42f1  mov     ebx, eax
0x1800d42f3  test    eax, eax
0x1800d42f5  jns     short loc_1800D4318
0x1800d42f7  mov     rcx, [rsp+4E8h]; this
0x1800d42ff  mov     r9d, eax; char *
0x1800d4302  lea     r8, aOnecoreuapEndu_51; "onecoreuap\\enduser\\winstore\\installs"...
0x1800d4309  mov     edx, 55h ; 'U'; void *
0x1800d430e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4313  jmp     loc_1800D44B4
0x1800d4318  mov     [rsp+4E8h+var_490], r14
0x1800d431d  lea     rcx, [rsp+4E8h+var_490]
0x1800d4322  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800d4327  lea     rax, [rsp+4E8h+var_490]
0x1800d432c  mov     [rsp+4E8h+pszPath], rax; int
0x1800d4331  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046; riid
0x1800d4338  xor     edx, edx; pUnkOuter
0x1800d433a  lea     r8d, [rdx+1]; dwClsContext
0x1800d433e  lea     rcx, _GUID_00021401_0000_0000_c000_000000000046; rclsid
0x1800d4345  call    cs:__imp_CoCreateInstance
0x1800d434b  mov     ebx, eax
0x1800d434d  test    eax, eax
0x1800d434f  jns     short loc_1800D4372
0x1800d4351  mov     edx, 58h ; 'X'; void *
0x1800d4356  lea     r8, aOnecoreuapEndu_51; "onecoreuap\\enduser\\winstore\\installs"...
0x1800d435d  mov     r9d, eax; char *
0x1800d4360  mov     rcx, [rsp+4E8h]; this
0x1800d4368  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d436d  jmp     loc_1800D44A9
0x1800d4372  mov     rcx, [rsp+4E8h+var_490]
0x1800d4377  mov     rax, [rcx]
0x1800d437a  mov     rdx, [rsp+4E8h+pv]
0x1800d437f  mov     rax, [rax+28h]
0x1800d4383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4388  mov     ebx, eax
0x1800d438a  test    eax, eax
0x1800d438c  jns     short loc_1800D4395
0x1800d438e  mov     edx, 59h ; 'Y'
0x1800d4393  jmp     short loc_1800D4356
0x1800d4395  mov     [rsp+4E8h+var_480], r14
0x1800d439a  mov     rbx, [rsp+4E8h+var_490]
0x1800d439f  mov     rax, [rbx]
0x1800d43a2  mov     rdi, [rax]
0x1800d43a5  lea     rcx, [rsp+4E8h+var_480]
0x1800d43aa  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800d43af  lea     r8, [rsp+4E8h+var_480]
0x1800d43b4  lea     rdx, _GUID_0000010b_0000_0000_c000_000000000046
0x1800d43bb  mov     rcx, rbx
0x1800d43be  mov     rax, rdi
0x1800d43c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d43c6  mov     ebx, eax
0x1800d43c8  test    eax, eax
0x1800d43ca  jns     short loc_1800D43D6
0x1800d43cc  mov     edx, 5Ch ; '\'
0x1800d43d1  jmp     loc_1800D4486
0x1800d43d6  mov     r8, [rsp+4E8h+pszMore]; pszMore
0x1800d43db  mov     edi, 104h
0x1800d43e0  mov     edx, edi; cchPath
0x1800d43e2  lea     rcx, [rsp+4E8h+var_458]; pszPath
0x1800d43ea  call    cs:__imp_PathCchAppend
0x1800d43f0  mov     ebx, eax
0x1800d43f2  test    eax, eax
0x1800d43f4  jns     short loc_1800D4400
0x1800d43f6  mov     edx, 60h ; '`'
0x1800d43fb  jmp     loc_1800D4486
0x1800d4400  lea     r8, pszExt; "lnk"
0x1800d4407  mov     rdx, rdi; cchPath
0x1800d440a  lea     rcx, [rsp+4E8h+var_458]; pszPath
0x1800d4412  call    cs:__imp_PathCchAddExtension
0x1800d4418  mov     ebx, eax
0x1800d441a  test    eax, eax
0x1800d441c  jns     short loc_1800D4425
0x1800d441e  mov     edx, 61h ; 'a'
0x1800d4423  jmp     short loc_1800D4486
0x1800d4425  xor     r9d, r9d; pszFileSpec
0x1800d4428  xor     r8d, r8d; pszShort
0x1800d442b  lea     rdx, [rsp+4E8h+var_458]; pszPath
0x1800d4433  lea     rcx, [rsp+4E8h+pszUniqueName]; pszUniqueName
0x1800d443b  call    cs:__imp_PathYetAnotherMakeUniqueName
0x1800d4441  mov     rcx, [rsp+4E8h+var_480]
0x1800d4446  xor     r8d, r8d
0x1800d4449  test    eax, eax
0x1800d444b  mov     rax, [rcx]
0x1800d444e  mov     rax, [rax+30h]
0x1800d4452  jz      short loc_1800D446E
0x1800d4454  lea     rdx, [rsp+4E8h+pszUniqueName]
0x1800d445c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4461  mov     ebx, eax
0x1800d4463  test    eax, eax
0x1800d4465  jns     short loc_1800D44E6
0x1800d4467  mov     edx, 66h ; 'f'
0x1800d446c  jmp     short loc_1800D4486
0x1800d446e  lea     rdx, [rsp+4E8h+var_458]
0x1800d4476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d447b  mov     ebx, eax
0x1800d447d  test    eax, eax
0x1800d447f  jns     short loc_1800D44E6
0x1800d4481  mov     edx, 6Ah ; 'j'; void *
0x1800d4486  mov     r9d, eax; char *
0x1800d4489  lea     r8, aOnecoreuapEndu_51; "onecoreuap\\enduser\\winstore\\installs"...
0x1800d4490  mov     rcx, [rsp+4E8h]; this
0x1800d4498  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d449d  nop
0x1800d449e  lea     rcx, [rsp+4E8h+var_480]
0x1800d44a3  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800d44a8  nop
0x1800d44a9  lea     rcx, [rsp+4E8h+var_490]
0x1800d44ae  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800d44b3  nop
0x1800d44b4  lea     rcx, [rsp+4E8h+pszMore]
0x1800d44b9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800d44be  nop
0x1800d44bf  mov     rcx, [rsp+4E8h+pv]; pv
0x1800d44c4  test    rcx, rcx
0x1800d44c7  mov     [rsp+4E8h+pv], r14
0x1800d44cc  jz      short loc_1800D44D5
0x1800d44ce  call    cs:__imp_CoTaskMemFree
0x1800d44d4  nop
0x1800d44d5  lea     rcx, [rsp+4E8h+ppv]
0x1800d44da  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800d44df  mov     eax, ebx
0x1800d44e1  jmp     loc_1800D4570
0x1800d44e6  mov     [rsp+4E8h+var_4A8], rsi
0x1800d44eb  mov     [rsp+4E8h+var_4B0], r14; unsigned __int16 *
0x1800d44f0  mov     [rsp+4E8h+var_4B8], r14; char *
0x1800d44f5  lea     rax, aSuccessfullyPi_1; "Successfully Pinned %s to Desktop."
0x1800d44fc  mov     [rsp+4E8h+var_4C0], rax; unsigned __int16 *
0x1800d4501  mov     dword ptr [rsp+4E8h+pszPath], 0FFFFFFFFh; int
0x1800d4509  lea     r9, aInstallservice_15; "InstallServiceUserBroker::PinToDesktop"
0x1800d4510  mov     r8d, 6Dh ; 'm'; unsigned int
0x1800d4516  lea     rdx, aOnecoreuapEndu_51; "onecoreuap\\enduser\\winstore\\installs"...
0x1800d451d  lea     ecx, [r8-6Ah]; unsigned int
0x1800d4521  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800d4526  nop
0x1800d4527  lea     rcx, [rsp+4E8h+var_480]
0x1800d452c  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800d4531  nop
0x1800d4532  lea     rcx, [rsp+4E8h+var_490]
0x1800d4537  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800d453c  nop
0x1800d453d  lea     rcx, [rsp+4E8h+pszMore]
0x1800d4542  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800d4547  nop
0x1800d4548  mov     rcx, [rsp+4E8h+pv]; pv
0x1800d454d  mov     [rsp+4E8h+pv], r14
0x1800d4552  test    rcx, rcx
0x1800d4555  jz      short loc_1800D455E
0x1800d4557  call    cs:__imp_CoTaskMemFree
0x1800d455d  nop
0x1800d455e  lea     rcx, [rsp+4E8h+ppv]
0x1800d4563  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800d4568  xor     eax, eax
0x1800d456a  jmp     short loc_1800D4570
0x1800d456c  mov     eax, dword ptr [rsp+4E8h+pv]
0x1800d4570  mov     rcx, [rsp+4E8h+var_38]
0x1800d4578  xor     rcx, rsp; StackCookie
0x1800d457b  call    __security_check_cookie
0x1800d4580  add     rsp, 4C8h
0x1800d4587  pop     r14
0x1800d4589  pop     rdi
0x1800d458a  pop     rsi
0x1800d458b  pop     rbx
0x1800d458c  retn
```
