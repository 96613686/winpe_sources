# RetailDemoUserAgent::PinAppsToTaskbar(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &)

- ea: `0x18003f228`
- end: `0x18003f5c8`
- name: `?PinAppsToTaskbar@RetailDemoUserAgent@@AEAAXAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `928`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180036f74`

## callees

- `0x180003390`
- `0x180008bbc`
- `0x18001092c`
- `0x18001094c`
- `0x18001c904`
- `0x18002df4c`
- `0x18003f228`
- `0x180050010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x18003f2c2`
- `SHCORE!IUnknown_QueryService` at `0x18003f2c2`
- `SHLWAPI!StrStrIW` at `0x18003f307`
- `SHLWAPI!StrStrIW` at `0x18003f334`
- `SHLWAPI!StrStrIW` at `0x18003f351`
- `SHLWAPI!StrStrIW` at `0x18003f307`
- `SHLWAPI!StrStrIW` at `0x18003f334`
- `SHLWAPI!StrStrIW` at `0x18003f351`
- `SHELL32!SHGetKnownFolderIDList` at `0x18003f3a0`
- `SHELL32!SHGetKnownFolderIDList` at `0x18003f3a0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003f281`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003f281`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f45f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f47d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f4ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f4c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f516`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f45f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f47d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f4ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f4c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f516`
- `api-ms-win-shell-namespace-l1-1-0!SHBindToObject` at `0x18003f3e1`
- `api-ms-win-shell-namespace-l1-1-0!SHBindToObject` at `0x18003f3e1`
- `api-ms-win-shell-namespace-l1-1-0!ILCombine` at `0x18003f491`
- `api-ms-win-shell-namespace-l1-1-0!ILCombine` at `0x18003f491`
- `ext-ms-win-shell-shell32-l1-2-1!ILCreateFromPathW` at `0x18003f367`
- `ext-ms-win-shell-shell32-l1-2-1!ILCreateFromPathW` at `0x18003f367`

## string_xrefs

- `0x18003f562`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003f577`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003f58c`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003f5a1`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003f5b6`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall RetailDemoUserAgent::PinAppsToTaskbar(__int64 a1, __int64 *a2, __int64 a3)
{
  HRESULT v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  IUnknown **v8; // rax
  HRESULT v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdi
  __int64 v15; // r14
  const WCHAR *v16; // rax
  const WCHAR *v17; // rax
  const WCHAR *v18; // rax
  const WCHAR *v19; // rax
  LPITEMIDLIST v20; // rbx
  LPITEMIDLIST v21; // rsi
  HRESULT v22; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  HRESULT v25; // eax
  __int64 v26; // rax
  __int64 (__fastcall *v27)(__int64, _QWORD, _QWORD, __int64); // r10
  __int64 v28; // r11
  int v29; // ebx
  __int64 v30; // rdx
  __int64 v31; // r8
  void *v32; // rcx
  ITEMIDLIST *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // r8
  void *v36; // rcx
  ITEMIDLIST *v37; // rcx
  int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // r8
  int ppv; // [rsp+20h] [rbp-49h]
  int ppva; // [rsp+20h] [rbp-49h]
  LPCITEMIDLIST pidl; // [rsp+40h] [rbp-29h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-21h] BYREF
  void *v46; // [rsp+50h] [rbp-19h] BYREF
  void *ppvOut; // [rsp+58h] [rbp-11h] BYREF
  LPVOID v48; // [rsp+60h] [rbp-9h] BYREF
  LPITEMIDLIST v49; // [rsp+68h] [rbp-1h] BYREF
  void *p_pidl; // [rsp+70h] [rbp+7h] BYREF
  LPITEMIDLIST ppidl; // [rsp+78h] [rbp+Fh] BYREF
  char v52; // [rsp+80h] [rbp+17h]
  KNOWNFOLDERID rfid; // [rsp+88h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v48 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48, a2, a3);
  v5 = CoCreateInstance(&CLSID_TaskbandPin, 0, 1u, &GUID_0dd79ae2_d156_45d4_9eeb_3b549769e940, &v48);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6FC,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)(unsigned int)v5,
      ppv);
  ppvOut = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvOut, v6, v7);
  v8 = (IUnknown **)CWRLObjectWithGITSite::SiteUnk(a1, &v49);
  v9 = IUnknown_QueryService(
         *v8,
         (const GUID *const)&SID_PinManager,
         &GUID_d75f625f_6df9_4874_970d_17cbf846f00d,
         &ppvOut);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6FF,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)(unsigned int)v9,
      ppv);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49, v10, v11);
  v14 = *a2;
  v15 = a2[1];
  while ( v14 != v15 )
  {
    rfid = FOLDERID_AppsFolder;
    v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14);
    if ( StrStrIW(v16, L"File Explorer.lnk") )
      rfid = FOLDERID_Programs;
    v49 = 0;
    v17 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14);
    if ( StrStrIW(v17, L".lnk") )
    {
      v18 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14);
      if ( !StrStrIW(v18, L"File Explorer.lnk") )
      {
        v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14);
        v20 = ILCreateFromPathW(v19);
        v49 = v20;
        v21 = v20;
LABEL_22:
        if ( (*(unsigned int (__fastcall **)(LPVOID, LPITEMIDLIST))(*(_QWORD *)v48 + 72LL))(v48, v20) )
        {
          v38 = (*(__int64 (__fastcall **)(void *, LPITEMIDLIST, __int64))(*(_QWORD *)ppvOut + 32LL))(ppvOut, v20, 16);
          if ( v38 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x724,
              (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
              (const char *)(unsigned int)v38,
              ppv);
        }
        if ( v21 )
          CoTaskMemFree(v21);
        goto LABEL_26;
      }
    }
    pidl = 0;
    p_pidl = &pidl;
    ppidl = 0;
    v52 = 1;
    v22 = SHGetKnownFolderIDList(&rfid, 0x4000u, 0, &ppidl);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x713,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
        (const char *)(unsigned int)v22,
        ppv);
    wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pidl);
    v46 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46, v23, v24);
    v25 = SHBindToObject(0, pidl, 0, &GUID_000214e6_0000_0000_c000_000000000046, &v46);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x716,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
        (const char *)(unsigned int)v25,
        ppva);
    pv = 0;
    p_pidl = &pv;
    ppidl = 0;
    v52 = 1;
    v26 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14);
    ppv = 0;
    v29 = v27(v28, 0, 0, v26);
    wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pidl);
    if ( v29 >= 0 )
    {
      v20 = ILCombine(pidl, (LPCITEMIDLIST)pv);
      v49 = v20;
      v36 = pv;
      pv = 0;
      if ( v36 )
        CoTaskMemFree(v36);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46, v34, v35);
      v37 = (ITEMIDLIST *)pidl;
      pidl = 0;
      if ( v37 )
        CoTaskMemFree(v37);
      v21 = v20;
      goto LABEL_22;
    }
    v32 = pv;
    pv = 0;
    if ( v32 )
      CoTaskMemFree(v32);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46, v30, v31);
    v33 = (ITEMIDLIST *)pidl;
    pidl = 0;
    if ( v33 )
      CoTaskMemFree(v33);
LABEL_26:
    v14 += 32;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvOut, v12, v13);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48, v39, v40);
}

```

## disassembly

```asm
0x18003f228  mov     [rsp-8+arg_10], rbx
0x18003f22d  push    rbp
0x18003f22e  push    rsi
0x18003f22f  push    rdi
0x18003f230  push    r14
0x18003f232  push    r15
0x18003f234  lea     rbp, [rsp-37h]
0x18003f239  sub     rsp, 0A0h
0x18003f240  mov     rax, cs:__security_cookie
0x18003f247  xor     rax, rsp
0x18003f24a  mov     [rbp+57h+var_28], rax
0x18003f24e  mov     rbx, rdx
0x18003f251  mov     rdi, rcx
0x18003f254  xor     r15d, r15d
0x18003f257  mov     [rbp+57h+var_60], r15
0x18003f25b  lea     rcx, [rbp+57h+var_60]
0x18003f25f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003f264  lea     rax, [rbp+57h+var_60]
0x18003f268  mov     [rsp+0C0h+ppv], rax; int
0x18003f26d  lea     r9, _GUID_0dd79ae2_d156_45d4_9eeb_3b549769e940; riid
0x18003f274  xor     edx, edx; pUnkOuter
0x18003f276  lea     r8d, [r15+1]; dwClsContext
0x18003f27a  lea     rcx, CLSID_TaskbandPin; rclsid
0x18003f281  call    cs:__imp_CoCreateInstance
0x18003f287  mov     rcx, [rbp+5Fh]; this
0x18003f28b  test    eax, eax
0x18003f28d  js      loc_18003F589
0x18003f293  mov     [rbp+57h+ppvOut], r15
0x18003f297  lea     rcx, [rbp+57h+ppvOut]
0x18003f29b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003f2a0  lea     rdx, [rbp+57h+var_58]
0x18003f2a4  mov     rcx, rdi
0x18003f2a7  call    ?SiteUnk@CWRLObjectWithGITSite@@IEAA?AV?$ComPtr@UIUnknown@@@WRL@Microsoft@@XZ; CWRLObjectWithGITSite::SiteUnk(void)
0x18003f2ac  nop
0x18003f2ad  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x18003f2b1  lea     r8, _GUID_d75f625f_6df9_4874_970d_17cbf846f00d; riid
0x18003f2b8  lea     rdx, SID_PinManager; guidService
0x18003f2bf  mov     rcx, [rax]; punk
0x18003f2c2  call    cs:__imp_IUnknown_QueryService
0x18003f2c8  mov     rcx, [rbp+5Fh]; this
0x18003f2cc  test    eax, eax
0x18003f2ce  js      loc_18003F59E
0x18003f2d4  lea     rcx, [rbp+57h+var_58]
0x18003f2d8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003f2dd  mov     rdi, [rbx]
0x18003f2e0  mov     r14, [rbx+8]
0x18003f2e4  jmp     loc_18003F520
0x18003f2e9  movups  xmm0, xmmword ptr cs:FOLDERID_AppsFolder.Data1
0x18003f2f0  movdqu  xmmword ptr [rbp+57h+rfid.Data1], xmm0
0x18003f2f5  mov     rcx, rdi
0x18003f2f8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003f2fd  lea     rdx, aFileExplorerLn; "File Explorer.lnk"
0x18003f304  mov     rcx, rax; pszFirst
0x18003f307  call    cs:__imp_StrStrIW
0x18003f30d  test    rax, rax
0x18003f310  jz      short loc_18003F31E
0x18003f312  movups  xmm0, xmmword ptr cs:FOLDERID_Programs.Data1
0x18003f319  movdqu  xmmword ptr [rbp+57h+rfid.Data1], xmm0
0x18003f31e  mov     [rbp+57h+var_58], r15
0x18003f322  mov     rcx, rdi
0x18003f325  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003f32a  lea     rdx, aLnk_0; ".lnk"
0x18003f331  mov     rcx, rax; pszFirst
0x18003f334  call    cs:__imp_StrStrIW
0x18003f33a  test    rax, rax
0x18003f33d  jz      short loc_18003F37C
0x18003f33f  mov     rcx, rdi
0x18003f342  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003f347  lea     rdx, aFileExplorerLn; "File Explorer.lnk"
0x18003f34e  mov     rcx, rax; pszFirst
0x18003f351  call    cs:__imp_StrStrIW
0x18003f357  test    rax, rax
0x18003f35a  jnz     short loc_18003F37C
0x18003f35c  mov     rcx, rdi
0x18003f35f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003f364  mov     rcx, rax; pszPath
0x18003f367  call    cs:__imp_ILCreateFromPathW
0x18003f36d  mov     rbx, rax
0x18003f370  mov     [rbp+57h+var_58], rax
0x18003f374  mov     rsi, rax
0x18003f377  jmp     loc_18003F4D2
0x18003f37c  mov     [rbp+57h+pidl], r15
0x18003f380  lea     rax, [rbp+57h+pidl]
0x18003f384  mov     [rbp+57h+var_50], rax
0x18003f388  mov     [rbp+57h+ppidl], r15
0x18003f38c  mov     [rbp+57h+var_40], 1
0x18003f390  lea     r9, [rbp+57h+ppidl]; ppidl
0x18003f394  xor     r8d, r8d; hToken
0x18003f397  mov     edx, 4000h; dwFlags
0x18003f39c  lea     rcx, [rbp+57h+rfid]; rfid
0x18003f3a0  call    cs:__imp_SHGetKnownFolderIDList
0x18003f3a6  mov     rcx, [rbp+5Fh]; this
0x18003f3aa  test    eax, eax
0x18003f3ac  js      loc_18003F574
0x18003f3b2  lea     rcx, [rbp+57h+var_50]
0x18003f3b6  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003f3bb  mov     [rbp+57h+var_70], r15
0x18003f3bf  lea     rcx, [rbp+57h+var_70]
0x18003f3c3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003f3c8  lea     rax, [rbp+57h+var_70]
0x18003f3cc  mov     [rsp+0C0h+ppv], rax; int
0x18003f3d1  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18003f3d8  xor     r8d, r8d; pbc
0x18003f3db  mov     rdx, [rbp+57h+pidl]; pidl
0x18003f3df  xor     ecx, ecx; psf
0x18003f3e1  call    cs:__imp_SHBindToObject
0x18003f3e7  mov     rcx, [rbp+5Fh]; this
0x18003f3eb  test    eax, eax
0x18003f3ed  js      loc_18003F55F
0x18003f3f3  mov     [rbp+57h+pv], r15
0x18003f3f7  mov     r11, [rbp+57h+var_70]
0x18003f3fb  mov     rax, [r11]
0x18003f3fe  mov     r10, [rax+18h]
0x18003f402  lea     rax, [rbp+57h+pv]
0x18003f406  mov     [rbp+57h+var_50], rax
0x18003f40a  mov     [rbp+57h+ppidl], r15
0x18003f40e  mov     [rbp+57h+var_40], 1
0x18003f412  mov     rcx, rdi
0x18003f415  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003f41a  mov     [rsp+0C0h+var_90], r15
0x18003f41f  lea     rcx, [rbp+57h+ppidl]
0x18003f423  mov     [rsp+0C0h+var_98], rcx
0x18003f428  mov     [rsp+0C0h+ppv], r15; int
0x18003f42d  mov     r9, rax
0x18003f430  xor     r8d, r8d
0x18003f433  xor     edx, edx
0x18003f435  mov     rcx, r11
0x18003f438  mov     rax, r10
0x18003f43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f440  mov     ebx, eax
0x18003f442  lea     rcx, [rbp+57h+var_50]
0x18003f446  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003f44b  shr     ebx, 1Fh
0x18003f44e  test    bl, bl
0x18003f450  jz      short loc_18003F489
0x18003f452  mov     rcx, [rbp+57h+pv]; pv
0x18003f456  mov     [rbp+57h+pv], r15
0x18003f45a  test    rcx, rcx
0x18003f45d  jz      short loc_18003F466
0x18003f45f  call    cs:__imp_CoTaskMemFree
0x18003f465  nop
0x18003f466  lea     rcx, [rbp+57h+var_70]
0x18003f46a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003f46f  nop
0x18003f470  mov     rcx, [rbp+57h+pidl]; pv
0x18003f474  mov     [rbp+57h+pidl], r15
0x18003f478  test    rcx, rcx
0x18003f47b  jz      short loc_18003F484
0x18003f47d  call    cs:__imp_CoTaskMemFree
0x18003f483  nop
0x18003f484  jmp     loc_18003F51C
0x18003f489  mov     rdx, [rbp+57h+pv]; pidl2
0x18003f48d  mov     rcx, [rbp+57h+pidl]; pidl1
0x18003f491  call    cs:__imp_ILCombine
0x18003f497  mov     rbx, rax
0x18003f49a  mov     [rbp+57h+var_58], rax
0x18003f49e  mov     rcx, [rbp+57h+pv]; pv
0x18003f4a2  mov     [rbp+57h+pv], r15
0x18003f4a6  test    rcx, rcx
0x18003f4a9  jz      short loc_18003F4B2
0x18003f4ab  call    cs:__imp_CoTaskMemFree
0x18003f4b1  nop
0x18003f4b2  lea     rcx, [rbp+57h+var_70]
0x18003f4b6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003f4bb  nop
0x18003f4bc  mov     rcx, [rbp+57h+pidl]; pv
0x18003f4c0  mov     [rbp+57h+pidl], r15
0x18003f4c4  test    rcx, rcx
0x18003f4c7  jz      short loc_18003F4CF
0x18003f4c9  call    cs:__imp_CoTaskMemFree
0x18003f4cf  mov     rsi, rbx
0x18003f4d2  mov     rcx, [rbp+57h+var_60]
0x18003f4d6  mov     rax, [rcx]
0x18003f4d9  mov     rdx, rbx
0x18003f4dc  mov     rax, [rax+48h]
0x18003f4e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f4e5  test    eax, eax
0x18003f4e7  jz      short loc_18003F50E
0x18003f4e9  mov     rcx, [rbp+57h+ppvOut]
0x18003f4ed  mov     rax, [rcx]
0x18003f4f0  mov     r8d, 10h
0x18003f4f6  mov     rdx, rbx
0x18003f4f9  mov     rax, [rax+20h]
0x18003f4fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f502  mov     rcx, [rbp+5Fh]; this
0x18003f506  test    eax, eax
0x18003f508  js      loc_18003F5B3
0x18003f50e  test    rsi, rsi
0x18003f511  jz      short loc_18003F51C
0x18003f513  mov     rcx, rsi; pv
0x18003f516  call    cs:__imp_CoTaskMemFree
0x18003f51c  add     rdi, 20h ; ' '
0x18003f520  cmp     rdi, r14
0x18003f523  jnz     loc_18003F2E9
0x18003f529  lea     rcx, [rbp+57h+ppvOut]
0x18003f52d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003f532  nop
0x18003f533  lea     rcx, [rbp+57h+var_60]
0x18003f537  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003f53c  mov     rcx, [rbp+57h+var_28]
0x18003f540  xor     rcx, rsp; StackCookie
0x18003f543  call    __security_check_cookie
0x18003f548  mov     rbx, [rsp+0C0h+arg_10]
0x18003f550  add     rsp, 0A0h
0x18003f557  pop     r15
0x18003f559  pop     r14
0x18003f55b  pop     rdi
0x18003f55c  pop     rsi
0x18003f55d  pop     rbp
0x18003f55e  retn
0x18003f55f  mov     r9d, eax; char *
0x18003f562  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003f569  mov     edx, 716h; void *
0x18003f56e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003f574  mov     r9d, eax; char *
0x18003f577  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003f57e  mov     edx, 713h; void *
0x18003f583  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003f589  mov     r9d, eax; char *
0x18003f58c  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003f593  mov     edx, 6FCh; void *
0x18003f598  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003f59e  mov     r9d, eax; char *
0x18003f5a1  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003f5a8  mov     edx, 6FFh; void *
0x18003f5ad  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003f5b3  mov     r9d, eax; char *
0x18003f5b6  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003f5bd  mov     edx, 724h; void *
0x18003f5c2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
