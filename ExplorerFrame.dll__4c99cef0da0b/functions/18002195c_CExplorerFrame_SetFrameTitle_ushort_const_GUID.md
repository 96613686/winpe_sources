# CExplorerFrame::SetFrameTitle(ushort const *,_GUID)

- ea: `0x18002195c`
- end: `0x180021d0d`
- name: `?SetFrameTitle@CExplorerFrame@@QEAAXPEBGU_GUID@@@Z`
- size: `945`
- prototype: `void __fastcall(CExplorerFrame *__hidden this, LPARAM lParam, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180021930`

## callees

- `0x1800218ac`
- `0x1800218fc`
- `0x18002195c`
- `0x180023024`
- `0x18002310c`
- `0x18002314c`
- `0x1800235e8`
- `0x180026424`
- `0x18002e4e0`
- `0x18002f35c`
- `0x180037240`
- `0x180038c6c`
- `0x180039680`
- `0x180073438`
- `0x1800b593c`
- `0x1800b6d4c`
- `0x1800ce224`
- `0x180210010`

## import_xrefs

- `SHELL32!SHGetIDListFromObject` at `0x180021b42`
- `SHELL32!SHGetIDListFromObject` at `0x180021b42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021cec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021cec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800219fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180021a08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180021a31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800219fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180021a08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180021a31`
- `USER32!SendMessageW` at `0x180021ca9`
- `USER32!SendMessageW` at `0x180021cdd`
- `USER32!SendMessageW` at `0x180021ca9`
- `USER32!SendMessageW` at `0x180021cdd`
- `USER32!GetWindowThreadProcessId` at `0x1800219f6`
- `USER32!GetWindowThreadProcessId` at `0x1800219f6`
- `USER32!GetShellWindow` at `0x1800219e8`
- `USER32!GetShellWindow` at `0x1800219e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CExplorerFrame::SetFrameTitle(HWND *this, IUnknown *lParam, struct _GUID *a3)
{
  int v6; // eax
  void *v7; // r14
  HWND ShellWindow; // rax
  DWORD v9; // eax
  int v10; // eax
  DWORD CurrentProcessId; // eax
  int v12; // eax
  __int64 *v13; // rax
  __int64 v14; // rcx
  HWND v15; // rdi
  int (__fastcall *v16)(HWND, GUID *, __int64); // rbx
  __int64 v17; // rax
  HRESULT v18; // eax
  __int64 v19; // rax
  int BrowserTabFromId; // eax
  unsigned __int64 v21; // rax
  int v22; // eax
  wil::details::in1diag3 *v23; // rcx
  __int64 v24; // rdx
  int v25; // [rsp+20h] [rbp-99h]
  DWORD dwProcessId; // [rsp+30h] [rbp-89h] BYREF
  __int64 v27; // [rsp+34h] [rbp-85h] BYREF
  int v28; // [rsp+3Ch] [rbp-7Dh] BYREF
  IUnknown *punk[2]; // [rsp+40h] [rbp-79h] BYREF
  __int64 v30; // [rsp+50h] [rbp-69h]
  __int64 v31; // [rsp+60h] [rbp-59h] BYREF
  _QWORD v32[3]; // [rsp+68h] [rbp-51h] BYREF
  LPITEMIDLIST ppidl[2]; // [rsp+80h] [rbp-39h] BYREF
  __int128 v34; // [rsp+90h] [rbp-29h]
  char v35; // [rsp+A0h] [rbp-19h]
  struct _GUID v36; // [rsp+A8h] [rbp-11h] BYREF
  __int128 v37; // [rsp+B8h] [rbp-1h]
  __int128 v38; // [rsp+C8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v6 = dword_180292BD0;
  if ( !dword_180292BD0 )
  {
    dwProcessId = 0;
    if ( (int)SHRegGetDWORD(
                HKEY_LOCAL_MACHINE,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer",
                L"ShowPidInTitle",
                &dwProcessId) < 0 )
    {
      v6 = dword_180292BD0;
    }
    else
    {
      v6 = 2 - (dwProcessId != 0);
      dword_180292BD0 = v6;
    }
  }
  v7 = 0;
  memset(v32, 0, sizeof(v32));
  if ( v6 == 1 )
  {
    dwProcessId = 0;
    ShellWindow = GetShellWindow();
    GetWindowThreadProcessId(ShellWindow, &dwProcessId);
    if ( dwProcessId == GetCurrentProcessId() )
    {
      CurrentProcessId = GetCurrentProcessId();
      v12 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
              v32,
              L"%s - (shell process: %d)",
              lParam,
              CurrentProcessId);
      v7 = (void *)v32[0];
      if ( v12 >= 0 )
        lParam = (IUnknown *)v32[0];
    }
    else
    {
      v9 = GetCurrentProcessId();
      v10 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
              v32,
              L"%s - (separate process: %d)",
              lParam,
              v9);
      v7 = (void *)v32[0];
      if ( v10 >= 0 )
        lParam = (IUnknown *)v32[0];
    }
  }
  if ( !CanShowTabs() )
  {
    SendMessageW(this[1], 0xCu, 0, (LPARAM)lParam);
    goto LABEL_36;
  }
  v37 = 0;
  v38 = 0;
  v36 = *a3;
  v13 = (__int64 *)wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                     punk,
                     lParam);
  v14 = *v13;
  *v13 = 0;
  *(_QWORD *)&v37 = v14;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(punk);
  *((_QWORD *)&v37 + 1) = 0;
  v28 = 0;
  v27 = 0;
  if ( (*(int (__fastcall **)(HWND, __int64 *, char *, int *))(*((_QWORD *)this[85] + 2) + 32LL))(
         this[85] + 4,
         &v27,
         (char *)&v27 + 4,
         &v28) >= 0 )
  {
    *(_QWORD *)((char *)&v38 + 4) = v27;
    HIDWORD(v38) = v28;
  }
  v15 = this[85];
  if ( v15 )
  {
    punk[0] = 0;
    v31 = 0;
    v16 = *(int (__fastcall **)(HWND, GUID *, __int64))(*((_QWORD *)v15 + 2) + 56LL);
    v17 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ISyncRootManager>>(punk);
    if ( v16(v15 + 4, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, v17) >= 0 )
    {
      ppidl[0] = (LPITEMIDLIST)&v31;
      ppidl[1] = 0;
      LOBYTE(v34) = 1;
      v18 = SHGetIDListFromObject(punk[0], &ppidl[1]);
      if ( v18 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x577,
          (unsigned int)"shell\\explorerframe\\explorerframep.cpp",
          (const char *)(unsigned int)v18,
          v25);
      wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(ppidl);
      v19 = v31;
      v31 = 0;
      *((_QWORD *)&v37 + 1) = v19;
    }
    wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      &v31,
      0);
    Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(punk);
  }
  *(_OWORD *)ppidl = 0;
  v34 = 0;
  v35 = 0;
  *(struct _GUID *)punk = *a3;
  BrowserTabFromId = CExplorerFrame::GetBrowserTabFromId(
                       (CExplorerFrame *)this,
                       (struct _GUID *)punk,
                       (struct FEBrowserTab *)ppidl);
  if ( BrowserTabFromId >= 0 )
    CExplorerFrame::FireTabChangedEvent(this, 3, &v36, ppidl);
  else
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x57D,
      (unsigned int)"shell\\explorerframe\\explorerframep.cpp",
      (const char *)(unsigned int)BrowserTabFromId,
      v25);
  punk[0] = 0;
  punk[1] = 0;
  v30 = 0;
  v21 = 0xCCCCCCCCCCCCCCCDuLL * (((char *)this[83] - (char *)this[82]) >> 3);
  if ( v21 <= 2 )
  {
    if ( v21 == 2 )
    {
      v22 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
              punk,
              g_hinst,
              35105,
              lParam);
      v23 = retaddr;
      if ( v22 < 0 )
      {
        v24 = 1421;
        goto LABEL_31;
      }
    }
    else
    {
      v22 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
              punk,
              g_hinst,
              35104,
              lParam);
      v23 = retaddr;
      if ( v22 < 0 )
      {
        v24 = 1426;
        goto LABEL_31;
      }
    }
  }
  else
  {
    v25 = v21 - 1;
    v22 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
            punk,
            g_hinst,
            35106,
            lParam);
    v23 = retaddr;
    if ( v22 < 0 )
    {
      v24 = 1415;
LABEL_31:
      wil::details::in1diag3::_Log_Hr(
        v23,
        (void *)v24,
        (unsigned int)"shell\\explorerframe\\explorerframep.cpp",
        (const char *)(unsigned int)v22,
        v25);
    }
  }
  if ( punk[0] )
    lParam = punk[0];
  SendMessageW(this[1], 0xCu, 0, (LPARAM)lParam);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(punk);
  ShellItemData::~ShellItemData((ShellItemData *)ppidl);
  TabDataFree(&v36);
LABEL_36:
  if ( v7 )
    CoTaskMemFree(v7);
}

```

## disassembly

```asm
0x18002195c  mov     [rsp-8+arg_18], rbx
0x180021961  push    rbp
0x180021962  push    rsi
0x180021963  push    rdi
0x180021964  push    r12
0x180021966  push    r13
0x180021968  push    r14
0x18002196a  push    r15
0x18002196c  lea     rbp, [rsp-27h]
0x180021971  sub     rsp, 0E0h
0x180021978  mov     r12, r8
0x18002197b  mov     rsi, rdx
0x18002197e  mov     r15, rcx
0x180021981  mov     eax, cs:dword_180292BD0
0x180021987  xor     r13d, r13d
0x18002198a  test    eax, eax
0x18002198c  jnz     short loc_1800219CF
0x18002198e  mov     [rsp+110h+dwProcessId], r13d
0x180021993  lea     r9, [rsp+110h+dwProcessId]; unsigned int *
0x180021998  lea     r8, aShowpidintitle; "ShowPidInTitle"
0x18002199f  lea     rdx, aSoftwareMicros_31; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800219a6  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800219ad  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800219b2  test    eax, eax
0x1800219b4  js      short loc_1800219C9
0x1800219b6  mov     eax, [rsp+110h+dwProcessId]
0x1800219ba  neg     eax
0x1800219bc  sbb     eax, eax
0x1800219be  add     eax, 2
0x1800219c1  mov     cs:dword_180292BD0, eax
0x1800219c7  jmp     short loc_1800219CF
0x1800219c9  mov     eax, cs:dword_180292BD0
0x1800219cf  mov     r14, r13
0x1800219d2  mov     [rbp+57h+var_A8], r13
0x1800219d6  mov     [rbp+57h+var_A0], r13
0x1800219da  mov     [rbp+57h+var_98], r13
0x1800219de  cmp     eax, 1
0x1800219e1  jnz     short loc_180021A57
0x1800219e3  mov     [rsp+110h+dwProcessId], r13d
0x1800219e8  call    cs:__imp_GetShellWindow
0x1800219ee  mov     rcx, rax; hWnd
0x1800219f1  lea     rdx, [rsp+110h+dwProcessId]; lpdwProcessId
0x1800219f6  call    cs:__imp_GetWindowThreadProcessId
0x1800219fc  call    cs:__imp_GetCurrentProcessId
0x180021a02  cmp     [rsp+110h+dwProcessId], eax
0x180021a06  jz      short loc_180021A31
0x180021a08  call    cs:__imp_GetCurrentProcessId
0x180021a0e  mov     r9d, eax
0x180021a11  mov     r8, rsi
0x180021a14  lea     rdx, aSSeparateProce; "%s - (separate process: %d)"
0x180021a1b  lea     rcx, [rbp+57h+var_A8]
0x180021a1f  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180021a24  mov     r14, [rbp+57h+var_A8]
0x180021a28  test    eax, eax
0x180021a2a  js      short loc_180021A57
0x180021a2c  mov     rsi, r14
0x180021a2f  jmp     short loc_180021A57
0x180021a31  call    cs:__imp_GetCurrentProcessId
0x180021a37  mov     r9d, eax
0x180021a3a  mov     r8, rsi
0x180021a3d  lea     rdx, aSShellProcessD; "%s - (shell process: %d)"
0x180021a44  lea     rcx, [rbp+57h+var_A8]
0x180021a48  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180021a4d  mov     r14, [rbp+57h+var_A8]
0x180021a51  test    eax, eax
0x180021a53  cmovns  rsi, r14
0x180021a57  call    ?CanShowTabs@@YA_NXZ; CanShowTabs(void)
0x180021a5c  test    al, al
0x180021a5e  jz      loc_180021CCF
0x180021a64  xorps   xmm0, xmm0
0x180021a67  movups  [rbp+57h+var_58], xmm0
0x180021a6b  movups  [rbp+57h+var_48], xmm0
0x180021a6f  movaps  xmm0, xmmword ptr [r12]
0x180021a74  movdqu  [rbp+57h+var_68], xmm0
0x180021a79  mov     rdx, rsi
0x180021a7c  lea     rcx, [rbp+57h+punk]
0x180021a80  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180021a85  mov     rcx, [rax]
0x180021a88  mov     [rax], r13
0x180021a8b  mov     qword ptr [rbp+57h+var_58], rcx
0x180021a8f  lea     rcx, [rbp+57h+punk]; void *
0x180021a93  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180021a98  mov     qword ptr [rbp+57h+var_58+8], r13
0x180021a9c  mov     dword ptr [rsp+110h+var_DC+4], r13d
0x180021aa1  mov     [rbp+57h+var_D4], r13d
0x180021aa5  mov     dword ptr [rsp+110h+var_DC], r13d
0x180021aaa  mov     rcx, [r15+2A8h]
0x180021ab1  add     rcx, 10h
0x180021ab5  mov     rax, [rcx]
0x180021ab8  lea     r9, [rbp+57h+var_D4]
0x180021abc  lea     r8, [rsp+110h+var_DC+4]
0x180021ac1  lea     rdx, [rsp+110h+var_DC]
0x180021ac6  mov     rax, [rax+20h]
0x180021aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021acf  test    eax, eax
0x180021ad1  js      short loc_180021AE7
0x180021ad3  mov     eax, dword ptr [rsp+110h+var_DC]
0x180021ad7  mov     dword ptr [rbp+57h+var_48+4], eax
0x180021ada  mov     eax, dword ptr [rsp+110h+var_DC+4]
0x180021ade  mov     dword ptr [rbp+57h+var_48+8], eax
0x180021ae1  mov     eax, [rbp+57h+var_D4]
0x180021ae4  mov     dword ptr [rbp+57h+var_48+0Ch], eax
0x180021ae7  mov     rdi, [r15+2A8h]
0x180021aee  test    rdi, rdi
0x180021af1  jz      loc_180021B8E
0x180021af7  mov     [rbp+57h+punk], r13
0x180021afb  mov     [rbp+57h+var_B0], r13
0x180021aff  mov     rax, [rdi+10h]
0x180021b03  mov     rbx, [rax+38h]
0x180021b07  lea     rcx, [rbp+57h+punk]
0x180021b0b  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ISyncRootManager>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ISyncRootManager>>)
0x180021b10  mov     r8, rax
0x180021b13  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x180021b1a  lea     rcx, [rdi+10h]
0x180021b1e  mov     rax, rbx
0x180021b21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b26  test    eax, eax
0x180021b28  js      short loc_180021B79
0x180021b2a  lea     rax, [rbp+57h+var_B0]
0x180021b2e  mov     [rbp+57h+ppidl], rax
0x180021b32  mov     [rbp+57h+ppidl+8], r13
0x180021b36  mov     byte ptr [rbp+57h+var_80], 1
0x180021b3a  lea     rdx, [rbp+57h+ppidl+8]; ppidl
0x180021b3e  mov     rcx, [rbp+57h+punk]; punk
0x180021b42  call    cs:__imp_SHGetIDListFromObject
0x180021b48  mov     rcx, [rbp+5Fh]; this
0x180021b4c  test    eax, eax
0x180021b4e  jns     short loc_180021B64
0x180021b50  mov     r9d, eax; char *
0x180021b53  lea     r8, aShellExplorerf_10; "shell\\explorerframe\\explorerframep.cp"...
0x180021b5a  mov     edx, 577h; void *
0x180021b5f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180021b64  lea     rcx, [rbp+57h+ppidl]
0x180021b68  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180021b6d  mov     rax, [rbp+57h+var_B0]
0x180021b71  mov     [rbp+57h+var_B0], r13
0x180021b75  mov     qword ptr [rbp+57h+var_58+8], rax
0x180021b79  xor     edx, edx
0x180021b7b  lea     rcx, [rbp+57h+var_B0]
0x180021b7f  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x180021b84  nop
0x180021b85  lea     rcx, [rbp+57h+punk]
0x180021b89  call    ?InternalRelease@?$ComPtr@UIKnownFolderProperties@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(void)
0x180021b8e  xorps   xmm0, xmm0
0x180021b91  movdqu  xmmword ptr [rbp+57h+ppidl], xmm0
0x180021b96  movups  [rbp+57h+var_80], xmm0
0x180021b9a  mov     [rbp+57h+var_70], r13b
0x180021b9e  movaps  xmm0, xmmword ptr [r12]
0x180021ba3  movdqa  xmmword ptr [rbp+57h+punk], xmm0
0x180021ba8  lea     r8, [rbp+57h+ppidl]; struct FEBrowserTab *
0x180021bac  lea     rdx, [rbp+57h+punk]; struct _GUID
0x180021bb0  mov     rcx, r15; this
0x180021bb3  call    ?GetBrowserTabFromId@CExplorerFrame@@AEBAJU_GUID@@AEAUFEBrowserTab@@@Z; CExplorerFrame::GetBrowserTabFromId(_GUID,FEBrowserTab &)
0x180021bb8  mov     rcx, [rbp+5Fh]; this
0x180021bbc  test    eax, eax
0x180021bbe  jns     short loc_180021BD6
0x180021bc0  mov     r9d, eax; char *
0x180021bc3  lea     r8, aShellExplorerf_10; "shell\\explorerframe\\explorerframep.cp"...
0x180021bca  mov     edx, 57Dh; void *
0x180021bcf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180021bd4  jmp     short loc_180021BEB
0x180021bd6  lea     r9, [rbp+57h+ppidl]
0x180021bda  lea     r8, [rbp+57h+var_68]
0x180021bde  mov     edx, 3
0x180021be3  mov     rcx, r15
0x180021be6  call    ?FireTabChangedEvent@CExplorerFrame@@AEAAXW4EXPLORER_TAB_ACTION@@AEBUFileExplorerTabData@@AEBUFEBrowserTab@@@Z; CExplorerFrame::FireTabChangedEvent(EXPLORER_TAB_ACTION,FileExplorerTabData const &,FEBrowserTab const &)
0x180021beb  mov     [rbp+57h+punk], r13
0x180021bef  mov     [rbp+57h+punk+8], r13
0x180021bf3  mov     [rbp+57h+var_C0], r13
0x180021bf7  mov     rax, [r15+298h]
0x180021bfe  sub     rax, [r15+290h]
0x180021c05  sar     rax, 3
0x180021c09  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x180021c13  imul    rax, rcx
0x180021c17  mov     r9, rsi
0x180021c1a  mov     rdx, cs:g_hinst
0x180021c21  lea     rcx, [rbp+57h+punk]
0x180021c25  cmp     rax, 2
0x180021c29  jbe     short loc_180021C4D
0x180021c2b  dec     rax
0x180021c2e  mov     qword ptr [rsp+110h+var_F0], rax
0x180021c33  mov     r8d, 8922h
0x180021c39  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x180021c3e  mov     rcx, [rbp+5Fh]
0x180021c42  test    eax, eax
0x180021c44  jns     short loc_180021C90
0x180021c46  mov     edx, 587h
0x180021c4b  jmp     short loc_180021C81
0x180021c4d  jnz     short loc_180021C69
0x180021c4f  mov     r8d, 8921h
0x180021c55  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x180021c5a  mov     rcx, [rbp+5Fh]
0x180021c5e  test    eax, eax
0x180021c60  jns     short loc_180021C90
0x180021c62  mov     edx, 58Dh
0x180021c67  jmp     short loc_180021C81
0x180021c69  mov     r8d, 8920h
0x180021c6f  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x180021c74  mov     rcx, [rbp+5Fh]; this
0x180021c78  test    eax, eax
0x180021c7a  jns     short loc_180021C90
0x180021c7c  mov     edx, 592h; void *
0x180021c81  mov     r9d, eax; char *
0x180021c84  lea     r8, aShellExplorerf_10; "shell\\explorerframe\\explorerframep.cp"...
0x180021c8b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180021c90  mov     rax, [rbp+57h+punk]
0x180021c94  test    rax, rax
0x180021c97  cmovnz  rsi, rax
0x180021c9b  mov     r9, rsi; lParam
0x180021c9e  xor     r8d, r8d; wParam
0x180021ca1  lea     edx, [r8+0Ch]; Msg
0x180021ca5  mov     rcx, [r15+8]; hWnd
0x180021ca9  call    cs:__imp_SendMessageW
0x180021caf  lea     rcx, [rbp+57h+punk]
0x180021cb3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180021cb8  nop
0x180021cb9  lea     rcx, [rbp+57h+ppidl]; this
0x180021cbd  call    ??1ShellItemData@@QEAA@XZ; ShellItemData::~ShellItemData(void)
0x180021cc2  nop
0x180021cc3  lea     rcx, [rbp+57h+var_68]
0x180021cc7  call    TabDataFree
0x180021ccc  nop
0x180021ccd  jmp     short loc_180021CE4
0x180021ccf  mov     r9, rsi; lParam
0x180021cd2  xor     r8d, r8d; wParam
0x180021cd5  lea     edx, [r8+0Ch]; Msg
0x180021cd9  mov     rcx, [r15+8]; hWnd
0x180021cdd  call    cs:__imp_SendMessageW
0x180021ce3  nop
0x180021ce4  test    r14, r14
0x180021ce7  jz      short loc_180021CF2
0x180021ce9  mov     rcx, r14; pv
0x180021cec  call    cs:__imp_CoTaskMemFree
0x180021cf2  mov     rbx, [rsp+110h+arg_18]
0x180021cfa  add     rsp, 0E0h
0x180021d01  pop     r15
0x180021d03  pop     r14
0x180021d05  pop     r13
0x180021d07  pop     r12
0x180021d09  pop     rdi
0x180021d0a  pop     rsi
0x180021d0b  pop     rbp
0x180021d0c  retn
```
