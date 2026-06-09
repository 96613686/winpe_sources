# TryLaunchStoreApp(HWND__ * const,ulong)

- ea: `0x18001d1bc`
- end: `0x18001ddd1`
- name: `?TryLaunchStoreApp@@YAJQEAUHWND__@@K@Z`
- size: `3093`
- prototype: `__int64 __fastcall(HWND, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001b510`

## callees

- `0x180001800`
- `0x180003c38`
- `0x180006e00`
- `0x1800186ec`
- `0x18001c4c4`
- `0x18001d1bc`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001d328`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001d436`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001d874`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001d328`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001d436`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001d874`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001d276`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001d276`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d249`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d25f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d29f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dc8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dd5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d249`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d25f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d29f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dc8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dd5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d2ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d3fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d57f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d83a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d2ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d3fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d57f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d83a`

## string_xrefs

- `0x18001d2e7`: `Windows.Foundation.Uri`

## pseudocode

```c
__int64 __fastcall TryLaunchStoreApp(HWND a1, unsigned int a2)
{
  const WCHAR *v4; // rdi
  unsigned __int64 v5; // rbx
  UINT32 v6; // edx
  const WCHAR *v7; // rcx
  HRESULT v8; // ebx
  HRESULT v10; // eax
  int v11; // edx
  unsigned int v12; // r8d
  HSTRING v13; // rbx
  __int64 v14; // rcx
  int ActivationFactory; // eax
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  HRESULT v20; // eax
  int v21; // edx
  unsigned int v22; // r8d
  HSTRING v23; // rbx
  __int64 (__fastcall ***v24)(_QWORD, GUID *, _QWORD **); // rcx
  int v25; // eax
  __int64 (__fastcall ***v26)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  int v29; // eax
  _QWORD *v30; // rcx
  __int64 (__fastcall ***v31)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  _QWORD *v34; // rbx
  __int64 v35; // rsi
  HRESULT v36; // eax
  int v37; // edx
  unsigned int v38; // r8d
  int v39; // eax
  __int64 v40; // rcx
  _QWORD *v41; // rcx
  __int64 (__fastcall ***v42)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rsi
  __int64 v46; // rcx
  __int64 v47; // rcx
  _QWORD *v48; // rcx
  __int64 (__fastcall ***v49)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  int v52; // eax
  __int64 v53; // rcx
  __int64 v54; // rcx
  _QWORD *v55; // rcx
  __int64 (__fastcall ***v56)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 v57; // rcx
  __int64 v58; // rcx
  HRESULT v59; // eax
  int v60; // edx
  unsigned int v61; // r8d
  HSTRING v62; // rbx
  __int64 (__fastcall ***v63)(_QWORD, GUID *, _QWORD *); // rcx
  int v64; // eax
  __int64 (__fastcall ***v65)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v66; // rcx
  __int64 v67; // rcx
  _QWORD *v68; // rcx
  __int64 (__fastcall ***v69)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 v70; // rcx
  __int64 v71; // rcx
  int v72; // eax
  __int64 v73; // rcx
  __int64 (__fastcall ***v74)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v75; // rcx
  __int64 v76; // rcx
  _QWORD *v77; // rcx
  __int64 (__fastcall ***v78)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 v79; // rcx
  __int64 v80; // rcx
  int v81; // eax
  __int64 v82; // rcx
  __int64 v83; // rcx
  __int64 (__fastcall ***v84)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v85; // rcx
  __int64 v86; // rcx
  _QWORD *v87; // rcx
  __int64 (__fastcall ***v88)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 v89; // rcx
  __int64 v90; // rcx
  __int64 v91; // rcx
  __int64 v92; // rcx
  __int64 (__fastcall ***v93)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v94; // rcx
  __int64 v95; // rcx
  _QWORD *v96; // rcx
  __int64 (__fastcall ***v97)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 v98; // rcx
  __int64 v99; // rcx
  __int64 v100; // rcx
  __int64 v101; // rcx
  _QWORD *v102; // rcx
  __int64 (__fastcall ***v103)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 v104; // rcx
  __int64 v105; // rcx
  HSTRING string; // [rsp+20h] [rbp-59h] BYREF
  __int64 v107; // [rsp+28h] [rbp-51h] BYREF
  __int64 (__fastcall ***v108)(_QWORD, GUID *, _QWORD **); // [rsp+30h] [rbp-49h] BYREF
  __int64 v109; // [rsp+38h] [rbp-41h] BYREF
  _QWORD *v110; // [rsp+40h] [rbp-39h] BYREF
  __int64 v111; // [rsp+48h] [rbp-31h] BYREF
  __int64 v112; // [rsp+50h] [rbp-29h] BYREF
  __int64 (__fastcall ***v113)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-21h] BYREF
  __int64 v114; // [rsp+60h] [rbp-19h] BYREF
  int v115; // [rsp+68h] [rbp-11h] BYREF
  __int64 v116; // [rsp+70h] [rbp-9h] BYREF
  __int64 v117; // [rsp+78h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp+7h] BYREF
  HSTRING v119; // [rsp+98h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v117 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    &v117,
    L"microsoft-f12://?pid=%lu&hwnd=%llu",
    a2,
    a1);
  string = 0;
  v4 = (const WCHAR *)v117;
  if ( v117 )
  {
    v5 = -1;
    do
      ++v5;
    while ( *(_WORD *)(v117 + 2 * v5) );
    if ( v5 > 0xFFFFFFFF )
    {
      v8 = -2147024362;
      goto LABEL_9;
    }
    WindowsDeleteString(0);
    v6 = v5;
    v7 = v4;
  }
  else
  {
    WindowsDeleteString(0);
    v6 = 0;
    v7 = &String;
  }
  string = 0;
  v8 = WindowsCreateString(v7, v6, &string);
LABEL_9:
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
      (const char *)(unsigned int)v8,
      (int)string);
LABEL_11:
    WindowsDeleteString(string);
    string = 0;
    if ( _InterlockedDecrement((volatile signed __int32 *)v4 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v4 - 3) + 8LL))(*((_QWORD *)v4 - 3));
    return (unsigned int)v8;
  }
  v107 = 0;
  v119 = 0;
  v10 = WindowsCreateStringReference(L"Windows.Foundation.Uri", 0x16u, &hstringHeader, &v119);
  if ( v10 < 0 )
    goto LABEL_186;
  v13 = v119;
  v14 = v107;
  if ( v107 )
  {
    v107 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  ActivationFactory = RoGetActivationFactory(v13, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v107);
  v8 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E,
      (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)string);
    v16 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    goto LABEL_11;
  }
  v109 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v107 + 48LL))(v107, string, &v109);
  v8 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
      (const char *)(unsigned int)v17,
      (int)string);
    v18 = v109;
    if ( v109 )
    {
      v109 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    goto LABEL_11;
  }
  v108 = 0;
  v119 = 0;
  v20 = WindowsCreateStringReference(L"Windows.System.Launcher", 0x17u, &hstringHeader, &v119);
  if ( v20 < 0 )
    goto LABEL_187;
  v23 = v119;
  v24 = v108;
  if ( v108 )
  {
    v108 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v24)[2])(v24);
  }
  v25 = RoGetActivationFactory(v23, &GUID_00000035_0000_0000_c000_000000000046, &v108);
  v8 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45,
      (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
      (const char *)(unsigned int)v25,
      (int)string);
    v26 = v108;
    if ( v108 )
    {
      v108 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v26)[2])(v26);
    }
    v27 = v109;
    if ( v109 )
    {
      v109 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    v28 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    }
    goto LABEL_11;
  }
  v110 = 0;
  v29 = (**v108)(v108, &GUID_59ba2fbb_24cb_4c02_a4c4_8294569d54f1, &v110);
  v8 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
      (const char *)(unsigned int)v29,
      (int)string);
    v30 = v110;
    if ( v110 )
    {
      v110 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v30 + 16LL))(v30);
    }
    v31 = v108;
    if ( v108 )
    {
      v108 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v31)[2])(v31);
    }
    v32 = v109;
    if ( v109 )
    {
      v109 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
    v33 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    }
    goto LABEL_11;
  }
  v111 = 0;
  v34 = v110;
  v35 = *v110;
  v119 = 0;
  v36 = WindowsCreateStringReference(L"microsoft-f12", 0xDu, &hstringHeader, &v119);
  if ( v36 < 0 )
  {
LABEL_188:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v36, v37, v38);
    JUMPOUT(0x18001DDD0LL);
  }
  v39 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64 *))(v35 + 104))(v34, v119, &v111);
  v8 = v39;
  if ( v39 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
      (const char *)(unsigned int)v39,
      (int)string);
    v40 = v111;
    if ( v111 )
    {
      v111 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    }
    v41 = v110;
    if ( v110 )
    {
      v110 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v41 + 16LL))(v41);
    }
    v42 = v108;
    if ( v108 )
    {
      v108 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v42)[2])(v42);
    }
    v43 = v109;
    if ( v109 )
    {
      v109 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    }
    v44 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    }
    goto LABEL_11;
  }
  v112 = 0;
  v45 = v111;
  v8 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *> *>(v111);
  if ( v8 >= 0 )
    v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 64LL))(v45, &v112);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4E,
      (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
      (const char *)(unsigned int)v8,
      (int)string);
    v46 = v112;
    if ( v112 )
    {
      v112 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    }
    v47 = v111;
    if ( v111 )
    {
      v111 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    }
    v48 = v110;
    if ( v110 )
    {
      v110 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
    }
    v49 = v108;
    if ( v108 )
    {
      v108 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v49)[2])(v49);
    }
    v50 = v109;
    if ( v109 )
    {
      v109 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    }
    v51 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    }
    goto LABEL_11;
  }
  v115 = 0;
  v52 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v112 + 56LL))(v112, &v115);
  v8 = v52;
  if ( v52 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
      (const char *)(unsigned int)v52,
      (int)string);
    v53 = v112;
    if ( v112 )
    {
      v112 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    }
    v54 = v111;
    if ( v111 )
    {
      v111 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    }
    v55 = v110;
    if ( v110 )
    {
      v110 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v55 + 16LL))(v55);
    }
    v56 = v108;
    if ( v108 )
    {
      v108 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v56)[2])(v56);
    }
    v57 = v109;
    if ( v109 )
    {
      v109 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    }
    v58 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    }
    goto LABEL_11;
  }
  if ( !v115 )
  {
    v100 = v112;
    if ( v112 )
    {
      v112 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v100 + 16LL))(v100);
    }
    v101 = v111;
    if ( v111 )
    {
      v111 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v101 + 16LL))(v101);
    }
    v102 = v110;
    if ( v110 )
    {
      v110 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v102 + 16LL))(v102);
    }
    v103 = v108;
    if ( v108 )
    {
      v108 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v103)[2])(v103);
    }
    v104 = v109;
    if ( v109 )
    {
      v109 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
    }
    v105 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 16LL))(v105);
    }
    WindowsDeleteString(string);
    string = 0;
    if ( _InterlockedDecrement((volatile signed __int32 *)v4 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v4 - 3) + 8LL))(*((_QWORD *)v4 - 3));
    return 2150040148LL;
  }
  v113 = 0;
  v119 = 0;
  v59 = WindowsCreateStringReference(L"Windows.System.Launcher", 0x17u, &hstringHeader, &v119);
  if ( v59 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v59, v60, v61);
LABEL_186:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v10, v11, v12);
LABEL_187:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v20, v21, v22);
    goto LABEL_188;
  }
  v62 = v119;
  v63 = v113;
  if ( v113 )
  {
    v113 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v63)[2])(v63);
  }
  v64 = RoGetActivationFactory(v62, &GUID_00000035_0000_0000_c000_000000000046, &v113);
  v8 = v64;
  if ( v64 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x68,
      (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
      (const char *)(unsigned int)v64,
      (int)string);
    v65 = v113;
    if ( v113 )
    {
      v113 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v65)[2])(v65);
    }
    v66 = v112;
    if ( v112 )
    {
      v112 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
    }
    v67 = v111;
    if ( v111 )
    {
      v111 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
    }
    v68 = v110;
    if ( v110 )
    {
      v110 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v68 + 16LL))(v68);
    }
    v69 = v108;
    if ( v108 )
    {
      v108 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v69)[2])(v69);
    }
    v70 = v109;
    if ( v109 )
    {
      v109 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
    }
    v71 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
    }
    goto LABEL_11;
  }
  v114 = 0;
  v72 = (**v113)(v113, &GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451, &v114);
  v8 = v72;
  if ( v72 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6B,
      (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
      (const char *)(unsigned int)v72,
      (int)string);
    v73 = v114;
    if ( v114 )
    {
      v114 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
    }
    v74 = v113;
    if ( v113 )
    {
      v113 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v74)[2])(v74);
    }
    v75 = v112;
    if ( v112 )
    {
      v112 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
    }
    v76 = v111;
    if ( v111 )
    {
      v111 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
    }
    v77 = v110;
    if ( v110 )
    {
      v110 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v77 + 16LL))(v77);
    }
    v78 = v108;
    if ( v108 )
    {
      v108 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v78)[2])(v78);
    }
    v79 = v109;
    if ( v109 )
    {
      v109 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
    }
    v80 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
    }
    goto LABEL_11;
  }
  v116 = 0;
  v81 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v114 + 64LL))(v114, v109, &v116);
  v8 = v81;
  if ( v81 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
      (const char *)(unsigned int)v81,
      (int)string);
    v82 = v116;
    if ( v116 )
    {
      v116 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
    }
    v83 = v114;
    if ( v114 )
    {
      v114 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
    }
    v84 = v113;
    if ( v113 )
    {
      v113 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v84)[2])(v84);
    }
    v85 = v112;
    if ( v112 )
    {
      v112 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
    }
    v86 = v111;
    if ( v111 )
    {
      v111 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
    }
    v87 = v110;
    if ( v110 )
    {
      v110 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v87 + 16LL))(v87);
    }
    v88 = v108;
    if ( v108 )
    {
      v108 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v88)[2])(v88);
    }
    v89 = v109;
    if ( v109 )
    {
      v109 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
    }
    v90 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
    }
    goto LABEL_11;
  }
  v91 = v116;
  if ( v116 )
  {
    v116 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
  }
  v92 = v114;
  if ( v114 )
  {
    v114 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
  }
  v93 = v113;
  if ( v113 )
  {
    v113 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v93)[2])(v93);
  }
  v94 = v112;
  if ( v112 )
  {
    v112 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
  }
  v95 = v111;
  if ( v111 )
  {
    v111 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
  }
  v96 = v110;
  if ( v110 )
  {
    v110 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v96 + 16LL))(v96);
  }
  v97 = v108;
  if ( v108 )
  {
    v108 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v97)[2])(v97);
  }
  v98 = v109;
  if ( v109 )
  {
    v109 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
  }
  v99 = v107;
  if ( v107 )
  {
    v107 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 16LL))(v99);
  }
  WindowsDeleteString(string);
  string = 0;
  if ( _InterlockedDecrement((volatile signed __int32 *)v4 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v4 - 3) + 8LL))(*((_QWORD *)v4 - 3));
  return 0;
}

```

## disassembly

```asm
0x18001d1bc  mov     [rsp-8+arg_10], rbx
0x18001d1c1  push    rbp
0x18001d1c2  push    rsi
0x18001d1c3  push    rdi
0x18001d1c4  push    r14
0x18001d1c6  push    r15
0x18001d1c8  lea     rbp, [rsp-37h]
0x18001d1cd  sub     rsp, 0B0h
0x18001d1d4  mov     rax, cs:__security_cookie
0x18001d1db  xor     rax, rsp
0x18001d1de  mov     [rbp+57h+var_30], rax
0x18001d1e2  mov     edi, edx
0x18001d1e4  mov     rbx, rcx
0x18001d1e7  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001d1ee  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001d1f5  mov     rax, [rax+18h]
0x18001d1f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1fe  add     rax, 18h
0x18001d202  mov     [rbp+57h+var_58], rax
0x18001d206  mov     r9, rbx
0x18001d209  mov     r8d, edi
0x18001d20c  lea     rdx, aMicrosoftF12Pi; "microsoft-f12://?pid=%lu&hwnd=%llu"
0x18001d213  lea     rcx, [rbp+57h+var_58]
0x18001d217  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18001d21c  xor     r14d, r14d
0x18001d21f  mov     [rbp+57h+string], r14
0x18001d223  mov     rdi, [rbp+57h+var_58]
0x18001d227  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001d22b  test    rdi, rdi
0x18001d22e  jz      short loc_18001D25D
0x18001d230  mov     rbx, r15
0x18001d233  inc     rbx
0x18001d236  cmp     [rdi+rbx*2], r14w
0x18001d23b  jnz     short loc_18001D233
0x18001d23d  mov     eax, 0FFFFFFFFh
0x18001d242  cmp     rbx, rax
0x18001d245  ja      short loc_18001D256
0x18001d247  xor     ecx, ecx; string
0x18001d249  call    cs:__imp_WindowsDeleteString
0x18001d24f  mov     edx, ebx
0x18001d251  mov     rcx, rdi
0x18001d254  jmp     short loc_18001D26E
0x18001d256  mov     ebx, 80070216h
0x18001d25b  jmp     short loc_18001D27E
0x18001d25d  xor     ecx, ecx; string
0x18001d25f  call    cs:__imp_WindowsDeleteString
0x18001d265  xor     edx, edx; length
0x18001d267  lea     rcx, String; sourceString
0x18001d26e  mov     [rbp+57h+string], r14
0x18001d272  lea     r8, [rbp+57h+string]; string
0x18001d276  call    cs:__imp_WindowsCreateString
0x18001d27c  mov     ebx, eax
0x18001d27e  test    ebx, ebx
0x18001d280  jns     short loc_18001D2D2
0x18001d282  mov     rcx, [rbp+5Fh]; this
0x18001d286  mov     r9d, ebx; char *
0x18001d289  lea     r8, aInetcoreDevtoo; "inetcore\\devtoolbar\\v3\\f12app\\appfr"...
0x18001d290  mov     edx, 3Bh ; ';'; void *
0x18001d295  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d29a  nop
0x18001d29b  mov     rcx, [rbp+57h+string]; string
0x18001d29f  call    cs:__imp_WindowsDeleteString
0x18001d2a5  mov     [rbp+57h+string], r14
0x18001d2a9  lea     rdx, [rdi-18h]
0x18001d2ad  mov     eax, r15d
0x18001d2b0  lock xadd [rdx+10h], eax
0x18001d2b5  add     eax, r15d
0x18001d2b8  test    eax, eax
0x18001d2ba  jg      short loc_18001D2CB
0x18001d2bc  mov     rcx, [rdx]
0x18001d2bf  mov     rax, [rcx]
0x18001d2c2  mov     rax, [rax+8]
0x18001d2c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2cb  mov     eax, ebx
0x18001d2cd  jmp     loc_18001DD8E
0x18001d2d2  mov     [rbp+57h+var_A8], r14
0x18001d2d6  mov     [rbp+57h+var_38], r14
0x18001d2da  lea     r9, [rbp+57h+var_38]; string
0x18001d2de  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18001d2e2  mov     edx, 16h; length
0x18001d2e7  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x18001d2ee  call    cs:__imp_WindowsCreateStringReference
0x18001d2f4  test    eax, eax
0x18001d2f6  js      loc_18001DDB9
0x18001d2fc  mov     rbx, [rbp+57h+var_38]
0x18001d300  mov     rcx, [rbp+57h+var_A8]
0x18001d304  test    rcx, rcx
0x18001d307  jz      short loc_18001D31A
0x18001d309  mov     [rbp+57h+var_A8], r14
0x18001d30d  mov     rax, [rcx]
0x18001d310  mov     rax, [rax+10h]
0x18001d314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d319  nop
0x18001d31a  lea     r8, [rbp+57h+var_A8]
0x18001d31e  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x18001d325  mov     rcx, rbx
0x18001d328  call    cs:__imp_RoGetActivationFactory
0x18001d32e  mov     ebx, eax
0x18001d330  test    eax, eax
0x18001d332  jns     short loc_18001D36C
0x18001d334  mov     rcx, [rbp+5Fh]; this
0x18001d338  mov     r9d, eax; char *
0x18001d33b  lea     r8, aInetcoreDevtoo; "inetcore\\devtoolbar\\v3\\f12app\\appfr"...
0x18001d342  mov     edx, 3Eh ; '>'; void *
0x18001d347  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d34c  nop
0x18001d34d  mov     rcx, [rbp+57h+var_A8]
0x18001d351  test    rcx, rcx
0x18001d354  jz      short loc_18001D367
0x18001d356  mov     [rbp+57h+var_A8], r14
0x18001d35a  mov     rax, [rcx]
0x18001d35d  mov     rax, [rax+10h]
0x18001d361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d366  nop
0x18001d367  jmp     loc_18001D29B
0x18001d36c  mov     [rbp+57h+var_98], r14
0x18001d370  mov     rcx, [rbp+57h+var_A8]
0x18001d374  mov     rax, [rcx]
0x18001d377  lea     r8, [rbp+57h+var_98]
0x18001d37b  mov     rdx, [rbp+57h+string]
0x18001d37f  mov     rax, [rax+30h]
0x18001d383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d388  mov     ebx, eax
0x18001d38a  test    eax, eax
0x18001d38c  jns     short loc_18001D3E0
0x18001d38e  mov     rcx, [rbp+5Fh]; this
0x18001d392  mov     r9d, eax; char *
0x18001d395  lea     r8, aInetcoreDevtoo; "inetcore\\devtoolbar\\v3\\f12app\\appfr"...
0x18001d39c  mov     edx, 41h ; 'A'; void *
0x18001d3a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d3a6  nop
0x18001d3a7  mov     rcx, [rbp+57h+var_98]
0x18001d3ab  test    rcx, rcx
0x18001d3ae  jz      short loc_18001D3C1
0x18001d3b0  mov     [rbp+57h+var_98], r14
0x18001d3b4  mov     rax, [rcx]
0x18001d3b7  mov     rax, [rax+10h]
0x18001d3bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3c0  nop
0x18001d3c1  mov     rcx, [rbp+57h+var_A8]
0x18001d3c5  test    rcx, rcx
0x18001d3c8  jz      short loc_18001D3DB
0x18001d3ca  mov     [rbp+57h+var_A8], r14
0x18001d3ce  mov     rax, [rcx]
0x18001d3d1  mov     rax, [rax+10h]
0x18001d3d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3da  nop
0x18001d3db  jmp     loc_18001D29B
0x18001d3e0  mov     [rbp+57h+var_A0], r14
0x18001d3e4  mov     [rbp+57h+var_38], r14
0x18001d3e8  lea     r9, [rbp+57h+var_38]; string
0x18001d3ec  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18001d3f0  mov     edx, 17h; length
0x18001d3f5  lea     rcx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x18001d3fc  call    cs:__imp_WindowsCreateStringReference
0x18001d402  test    eax, eax
0x18001d404  js      loc_18001DDC1
0x18001d40a  mov     rbx, [rbp+57h+var_38]
0x18001d40e  mov     rcx, [rbp+57h+var_A0]
0x18001d412  test    rcx, rcx
0x18001d415  jz      short loc_18001D428
0x18001d417  mov     [rbp+57h+var_A0], r14
0x18001d41b  mov     rax, [rcx]
0x18001d41e  mov     rax, [rax+10h]
0x18001d422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d427  nop
0x18001d428  lea     r8, [rbp+57h+var_A0]
0x18001d42c  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x18001d433  mov     rcx, rbx
0x18001d436  call    cs:__imp_RoGetActivationFactory
0x18001d43c  mov     ebx, eax
0x18001d43e  test    eax, eax
0x18001d440  jns     short loc_18001D4AE
0x18001d442  mov     rcx, [rbp+5Fh]; this
0x18001d446  mov     r9d, eax; char *
0x18001d449  lea     r8, aInetcoreDevtoo; "inetcore\\devtoolbar\\v3\\f12app\\appfr"...
0x18001d450  mov     edx, 45h ; 'E'; void *
0x18001d455  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d45a  nop
0x18001d45b  mov     rcx, [rbp+57h+var_A0]
0x18001d45f  test    rcx, rcx
0x18001d462  jz      short loc_18001D475
0x18001d464  mov     [rbp+57h+var_A0], r14
0x18001d468  mov     rax, [rcx]
0x18001d46b  mov     rax, [rax+10h]
0x18001d46f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d474  nop
0x18001d475  mov     rcx, [rbp+57h+var_98]
0x18001d479  test    rcx, rcx
0x18001d47c  jz      short loc_18001D48F
0x18001d47e  mov     [rbp+57h+var_98], r14
0x18001d482  mov     rax, [rcx]
0x18001d485  mov     rax, [rax+10h]
0x18001d489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d48e  nop
0x18001d48f  mov     rcx, [rbp+57h+var_A8]
0x18001d493  test    rcx, rcx
0x18001d496  jz      short loc_18001D4A9
0x18001d498  mov     [rbp+57h+var_A8], r14
0x18001d49c  mov     rax, [rcx]
0x18001d49f  mov     rax, [rax+10h]
0x18001d4a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4a8  nop
0x18001d4a9  jmp     loc_18001D29B
0x18001d4ae  mov     [rbp+57h+var_90], r14
0x18001d4b2  mov     rcx, [rbp+57h+var_A0]
0x18001d4b6  mov     rax, [rcx]
0x18001d4b9  lea     r8, [rbp+57h+var_90]
0x18001d4bd  lea     rdx, _GUID_59ba2fbb_24cb_4c02_a4c4_8294569d54f1
0x18001d4c4  mov     rax, [rax]
0x18001d4c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4cc  mov     ebx, eax
0x18001d4ce  test    eax, eax
0x18001d4d0  jns     loc_18001D55C
0x18001d4d6  mov     rcx, [rbp+5Fh]; this
0x18001d4da  mov     r9d, eax; char *
0x18001d4dd  lea     r8, aInetcoreDevtoo; "inetcore\\devtoolbar\\v3\\f12app\\appfr"...
0x18001d4e4  mov     edx, 48h ; 'H'; void *
0x18001d4e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d4ee  nop
0x18001d4ef  mov     rcx, [rbp+57h+var_90]
0x18001d4f3  test    rcx, rcx
0x18001d4f6  jz      short loc_18001D509
0x18001d4f8  mov     [rbp+57h+var_90], r14
0x18001d4fc  mov     rax, [rcx]
0x18001d4ff  mov     rax, [rax+10h]
0x18001d503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d508  nop
0x18001d509  mov     rcx, [rbp+57h+var_A0]
0x18001d50d  test    rcx, rcx
0x18001d510  jz      short loc_18001D523
0x18001d512  mov     [rbp+57h+var_A0], r14
0x18001d516  mov     rax, [rcx]
0x18001d519  mov     rax, [rax+10h]
0x18001d51d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d522  nop
0x18001d523  mov     rcx, [rbp+57h+var_98]
0x18001d527  test    rcx, rcx
0x18001d52a  jz      short loc_18001D53D
0x18001d52c  mov     [rbp+57h+var_98], r14
0x18001d530  mov     rax, [rcx]
0x18001d533  mov     rax, [rax+10h]
0x18001d537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d53c  nop
0x18001d53d  mov     rcx, [rbp+57h+var_A8]
0x18001d541  test    rcx, rcx
0x18001d544  jz      short loc_18001D557
0x18001d546  mov     [rbp+57h+var_A8], r14
0x18001d54a  mov     rax, [rcx]
0x18001d54d  mov     rax, [rax+10h]
0x18001d551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d556  nop
0x18001d557  jmp     loc_18001D29B
0x18001d55c  mov     [rbp+57h+var_88], r14
0x18001d560  mov     rbx, [rbp+57h+var_90]
0x18001d564  mov     rsi, [rbx]
0x18001d567  mov     [rbp+57h+var_38], r14
0x18001d56b  lea     r9, [rbp+57h+var_38]; string
0x18001d56f  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18001d573  mov     edx, 0Dh; length
0x18001d578  lea     rcx, aMicrosoftF12; "microsoft-f12"
0x18001d57f  call    cs:__imp_WindowsCreateStringReference
0x18001d585  test    eax, eax
0x18001d587  js      loc_18001DDC9
0x18001d58d  lea     r8, [rbp+57h+var_88]
0x18001d591  mov     rdx, [rbp+57h+var_38]
0x18001d595  mov     rcx, rbx
0x18001d598  mov     rax, [rsi+68h]
0x18001d59c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5a1  mov     ebx, eax
0x18001d5a3  test    eax, eax
0x18001d5a5  jns     loc_18001D64B
0x18001d5ab  mov     rcx, [rbp+5Fh]; this
0x18001d5af  mov     r9d, eax; char *
0x18001d5b2  lea     r8, aInetcoreDevtoo; "inetcore\\devtoolbar\\v3\\f12app\\appfr"...
0x18001d5b9  mov     edx, 4Bh ; 'K'; void *
0x18001d5be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d5c3  nop
0x18001d5c4  mov     rcx, [rbp+57h+var_88]
0x18001d5c8  test    rcx, rcx
0x18001d5cb  jz      short loc_18001D5DE
0x18001d5cd  mov     [rbp+57h+var_88], r14
0x18001d5d1  mov     rax, [rcx]
0x18001d5d4  mov     rax, [rax+10h]
0x18001d5d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5dd  nop
0x18001d5de  mov     rcx, [rbp+57h+var_90]
0x18001d5e2  test    rcx, rcx
0x18001d5e5  jz      short loc_18001D5F8
0x18001d5e7  mov     [rbp+57h+var_90], r14
0x18001d5eb  mov     rax, [rcx]
0x18001d5ee  mov     rax, [rax+10h]
0x18001d5f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5f7  nop
0x18001d5f8  mov     rcx, [rbp+57h+var_A0]
0x18001d5fc  test    rcx, rcx
0x18001d5ff  jz      short loc_18001D612
0x18001d601  mov     [rbp+57h+var_A0], r14
0x18001d605  mov     rax, [rcx]
0x18001d608  mov     rax, [rax+10h]
  ... truncated ...
```
