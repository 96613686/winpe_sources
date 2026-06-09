# StateRepoHelper::GetSearchExtensionAndProtocols(wchar_t const *,wchar_t const *,bool *,ulong *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> *)

- ea: `0x1800a4694`
- end: `0x1800a4dd8`
- name: `?GetSearchExtensionAndProtocols@StateRepoHelper@@YAJPEB_W0PEA_NPEAKPEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@Z`
- size: `1860`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180180460`

## callees

- `0x18000f880`
- `0x18002dc6c`
- `0x1800a4694`
- `0x1800a4de0`
- `0x1801040b8`
- `0x180104178`
- `0x1801244c0`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a46fd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a4766`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a482b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a4b91`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a4ba5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a4bbd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a4bd1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a4c4e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a4c62`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a46fd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a4766`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a482b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a4b91`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a4ba5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a4bbd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a4bd1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a4c4e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a4c62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a46e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a4750`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a4815`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a499c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a4a3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a4abd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a46e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a4750`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a4815`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a499c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a4a3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a4abd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a484d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a484d`

## string_xrefs

- `0x1800a471e`: `onecoreuap\base\appmodel\search\common\staterepositoryhelper\staterepositoryhelper.cpp`
- `0x1800a4787`: `onecoreuap\base\appmodel\search\common\staterepositoryhelper\staterepositoryhelper.cpp`
- `0x1800a47e3`: `onecoreuap\base\appmodel\search\common\staterepositoryhelper\staterepositoryhelper.cpp`
- `0x1800a4860`: `onecoreuap\base\appmodel\search\common\staterepositoryhelper\staterepositoryhelper.cpp`
- `0x1800a48c3`: `onecoreuap\base\appmodel\search\common\staterepositoryhelper\staterepositoryhelper.cpp`
- `0x1800a4be7`: `onecoreuap\base\appmodel\search\common\staterepositoryhelper\staterepositoryhelper.cpp`
- `0x1800a4c70`: `onecoreuap\base\appmodel\search\common\staterepositoryhelper\staterepositoryhelper.cpp`
- `0x1800a46e1`: `Windows.Internal.StateRepository.ApplicationExtension`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall StateRepoHelper::GetSearchExtensionAndProtocols(__int64 a1, __int64 a2, _BYTE *a3, _DWORD *a4)
{
  HRESULT v6; // eax
  int v7; // eax
  HSTRING v8; // rbx
  HRESULT v9; // eax
  int v10; // eax
  __int64 v11; // rdi
  __int64 v12; // rax
  int v13; // eax
  HRESULT v14; // eax
  int ActivationFactory; // eax
  __int64 v16; // rdi
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rdx
  int v20; // r14d
  unsigned int i; // r15d
  __int64 v22; // rdi
  __int64 v23; // rdi
  unsigned __int64 v24; // rdx
  HRESULT v25; // eax
  __int64 v26; // rdi
  unsigned __int64 v27; // rdx
  HRESULT v28; // eax
  __int64 v29; // rdi
  unsigned __int64 v30; // rdx
  HRESULT v31; // eax
  int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  unsigned __int64 v37; // r9
  __int64 v38; // rdx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  _QWORD *v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  _QWORD *v50; // rcx
  int v51; // [rsp+20h] [rbp-71h]
  char v52; // [rsp+30h] [rbp-61h] BYREF
  _BYTE v53[7]; // [rsp+31h] [rbp-60h] BYREF
  __int64 v54; // [rsp+38h] [rbp-59h] BYREF
  __int64 v55; // [rsp+40h] [rbp-51h] BYREF
  __int64 v56; // [rsp+48h] [rbp-49h] BYREF
  __int64 v57; // [rsp+50h] [rbp-41h] BYREF
  __int64 v58; // [rsp+58h] [rbp-39h] BYREF
  __int64 v59; // [rsp+60h] [rbp-31h] BYREF
  _QWORD *v60; // [rsp+68h] [rbp-29h] BYREF
  unsigned int v61; // [rsp+70h] [rbp-21h] BYREF
  int v62; // [rsp+74h] [rbp-1Dh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-19h] BYREF
  HSTRING string; // [rsp+90h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+57h]

  v59 = a1;
  v54 = a2;
  *a3 = 0;
  v60 = 0;
  string = 0;
  v6 = WindowsCreateStringReference(
         L"Windows.Internal.StateRepository.ApplicationExtension",
         0x35u,
         &hstringHeader,
         &string);
  if ( v6 < 0 )
  {
    RaiseException(v6, 1u, 0, 0);
    __debugbreak();
  }
  v7 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>>(
         string,
         &v60);
  LODWORD(v8) = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x105,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\staterepositoryhelper\\staterepositoryhelper.cpp",
      (const char *)(unsigned int)v7,
      v51);
LABEL_74:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v60);
    return (unsigned int)v8;
  }
  v56 = 0;
  string = 0;
  v9 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.User", 0x25u, &hstringHeader, &string);
  if ( v9 < 0 )
  {
    RaiseException(v9, 1u, 0, 0);
    __debugbreak();
  }
  v10 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUserStatics>>(
          string,
          &v56);
  LODWORD(v8) = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x109,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\staterepositoryhelper\\staterepositoryhelper.cpp",
      (const char *)(unsigned int)v10,
      v51);
LABEL_73:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
    goto LABEL_74;
  }
  v55 = 0;
  v11 = v56;
  v8 = *(HSTRING *)(*(_QWORD *)v56 + 80LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
  v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v59);
  v13 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64 *))v8)(v11, *(_QWORD *)(v12 + 24), &v55);
  LODWORD(v8) = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10C,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\staterepositoryhelper\\staterepositoryhelper.cpp",
      (const char *)(unsigned int)v13,
      v51);
LABEL_72:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
    goto LABEL_73;
  }
  v58 = 0;
  string = 0;
  v14 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Application", 0x2Cu, &hstringHeader, &string);
  if ( v14 < 0 )
  {
    RaiseException(v14, 1u, 0, 0);
    __debugbreak();
  }
  v8 = string;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
  ActivationFactory = RoGetActivationFactory(v8, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, &v58);
  LODWORD(v8) = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x110,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\staterepositoryhelper\\staterepositoryhelper.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v51);
LABEL_71:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
    goto LABEL_72;
  }
  v57 = 0;
  v16 = v58;
  v8 = *(HSTRING *)(*(_QWORD *)v58 + 312LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
  v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v54);
  v18 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64 *))v8)(v16, v55, *(_QWORD *)(v17 + 24), &v57);
  LODWORD(v8) = v18;
  if ( v18 < 0 )
  {
    v19 = 276;
    goto LABEL_17;
  }
  v61 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v57 + 56LL))(v57, &v61);
  LODWORD(v8) = v18;
  if ( v18 < 0 )
  {
    v19 = 279;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\staterepositoryhelper\\staterepositoryhelper.cpp",
      (const char *)(unsigned int)v18,
      v51);
LABEL_70:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
    goto LABEL_71;
  }
  v20 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= v61 )
    {
      if ( !v20 )
      {
LABEL_93:
        if ( a4 )
          *a4 = v20;
        v46 = v57;
        if ( v57 )
        {
          v57 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
        }
        v47 = v58;
        if ( v58 )
        {
          v58 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
        }
        v48 = v55;
        if ( v55 )
        {
          v55 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
        }
        v49 = v56;
        if ( v56 )
        {
          v56 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
        }
        v50 = v60;
        if ( v60 )
        {
          v60 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v50 + 16LL))(v50);
        }
        return 0;
      }
LABEL_92:
      *a3 = 1;
      goto LABEL_93;
    }
    v54 = 0;
    v22 = v57;
    v8 = *(HSTRING *)(*(_QWORD *)v57 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v54);
    LODWORD(v8) = ((__int64 (__fastcall *)(__int64, _QWORD, __int64 *))v8)(v22, i, &v54);
    v23 = 0;
    if ( (int)v8 < 0 )
      goto LABEL_78;
    v59 = 0;
    v8 = (HSTRING)v60;
    v23 = *v60;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
    string = 0;
    v24 = -1;
    do
      ++v24;
    while ( aWindowsSearchp_0[v24] );
    if ( v24 > 0xFFFFFFFF || (int)v24 + 1 < (unsigned int)v24 )
      break;
    v25 = WindowsCreateStringReference(L"windows.searchProtocolHandler", v24, &hstringHeader, &string);
    if ( v25 < 0 )
    {
      RaiseException(v25, 1u, 0, 0);
      __debugbreak();
    }
    LODWORD(v8) = (*(__int64 (__fastcall **)(HSTRING, __int64, HSTRING, __int64 *))(v23 + 136))(v8, v54, string, &v59);
    if ( (int)v8 < 0 )
    {
      v38 = 290;
      goto LABEL_68;
    }
    v62 = 0;
    LODWORD(v8) = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v59 + 56LL))(v59, &v62);
    if ( (int)v8 < 0 )
    {
      v38 = 293;
LABEL_68:
      v37 = (unsigned int)v8;
      goto LABEL_69;
    }
    if ( v62 )
      v20 |= 1u;
    v52 = 0;
    v8 = (HSTRING)v60;
    v26 = *v60;
    string = 0;
    v27 = -1;
    do
      ++v27;
    while ( aWindowsSearchf[v27] );
    if ( v27 > 0xFFFFFFFF || (int)v27 + 1 < (unsigned int)v27 )
    {
      RaiseException(0x80070216, 1u, 0, 0);
      __debugbreak();
    }
    v28 = WindowsCreateStringReference(L"windows.searchFilterHandler", v27, &hstringHeader, &string);
    if ( v28 < 0 )
    {
      RaiseException(v28, 1u, 0, 0);
      __debugbreak();
    }
    LODWORD(v8) = (*(__int64 (__fastcall **)(HSTRING, __int64, HSTRING, char *))(v26 + 64))(v8, v54, string, &v52);
    if ( (int)v8 < 0 )
    {
      v38 = 314;
      goto LABEL_68;
    }
    if ( v52 )
      v20 |= 2u;
    v53[0] = 0;
    v8 = (HSTRING)v60;
    v29 = *v60;
    string = 0;
    v30 = -1;
    do
      ++v30;
    while ( aWindowsSearchp[v30] );
    if ( v30 > 0xFFFFFFFF || (int)v30 + 1 < (unsigned int)v30 )
    {
      RaiseException(0x80070216, 1u, 0, 0);
      __debugbreak();
    }
    v31 = WindowsCreateStringReference(L"windows.searchPropertyHandler", v30, &hstringHeader, &string);
    if ( v31 < 0 )
    {
      RaiseException(v31, 1u, 0, 0);
      __debugbreak();
    }
    v32 = (*(__int64 (__fastcall **)(HSTRING, __int64, HSTRING, _BYTE *))(v29 + 64))(v8, v54, string, v53);
    LODWORD(v8) = v32;
    if ( v32 < 0 )
    {
      v37 = (unsigned int)v32;
      v38 = 324;
LABEL_69:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v38,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\staterepositoryhelper\\staterepositoryhelper.cpp",
        (const char *)v37,
        v51);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v54);
      goto LABEL_70;
    }
    if ( v53[0] )
      v20 |= 4u;
    if ( v20 && (v20 & 7) == 7 )
    {
      v35 = v59;
      if ( v59 )
      {
        v59 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      }
      v36 = v54;
      if ( v54 )
      {
        v54 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      }
      goto LABEL_92;
    }
    v33 = v59;
    if ( v59 )
    {
      v59 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    }
    v34 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    }
  }
  RaiseException(0x80070216, 1u, 0, 0);
LABEL_78:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x11D,
    (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\staterepositoryhelper\\staterepositoryhelper.cpp",
    (const char *)(unsigned int)v8,
    v51);
  v40 = v54;
  if ( v54 )
  {
    v54 = v23;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  }
  v41 = v57;
  if ( v57 )
  {
    v57 = v23;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  }
  v42 = v58;
  if ( v58 )
  {
    v58 = v23;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  }
  v43 = v55;
  if ( v55 )
  {
    v55 = v23;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  v44 = v56;
  if ( v56 )
  {
    v56 = v23;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
  v45 = v60;
  if ( v60 )
  {
    v60 = (_QWORD *)v23;
    (*(void (__fastcall **)(_QWORD *))(*v45 + 16LL))(v45);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800a4694  push    rbp
0x1800a4696  push    rbx
0x1800a4697  push    rsi
0x1800a4698  push    rdi
0x1800a4699  push    r12
0x1800a469b  push    r13
0x1800a469d  push    r14
0x1800a469f  push    r15
0x1800a46a1  lea     rbp, [rsp-17h]
0x1800a46a6  sub     rsp, 0A8h
0x1800a46ad  mov     rax, cs:__security_cookie
0x1800a46b4  xor     rax, rsp
0x1800a46b7  mov     [rbp+4Fh+var_48], rax
0x1800a46bb  mov     r12, r9
0x1800a46be  mov     r13, r8
0x1800a46c1  mov     [rbp+4Fh+var_80], rcx
0x1800a46c5  mov     [rbp+4Fh+var_A8], rdx
0x1800a46c9  xor     esi, esi
0x1800a46cb  mov     [r8], sil
0x1800a46ce  mov     [rbp+4Fh+var_78], rsi
0x1800a46d2  mov     [rbp+4Fh+string], rsi
0x1800a46d6  lea     r9, [rbp+4Fh+string]; string
0x1800a46da  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x1800a46de  lea     edx, [rsi+35h]; length
0x1800a46e1  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_ApplicationExtension@@3QB_WB; "Windows.Internal.StateRepository.Applic"...
0x1800a46e8  call    cs:__imp_WindowsCreateStringReference
0x1800a46ee  test    eax, eax
0x1800a46f0  jns     short loc_1800A4704
0x1800a46f2  xor     r9d, r9d; lpArguments
0x1800a46f5  xor     r8d, r8d; nNumberOfArguments
0x1800a46f8  lea     edx, [rsi+1]; dwExceptionFlags
0x1800a46fb  mov     ecx, eax; dwExceptionCode
0x1800a46fd  call    cs:__imp_RaiseException
0x1800a4703  int     3; Trap to Debugger
0x1800a4704  lea     rdx, [rbp+4Fh+var_78]
0x1800a4708  mov     rcx, [rbp+4Fh+string]
0x1800a470c  call    ??$GetActivationFactory@V?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>>)
0x1800a4711  mov     ebx, eax
0x1800a4713  test    eax, eax
0x1800a4715  jns     short loc_1800A4734
0x1800a4717  mov     rcx, [rbp+57h]; this
0x1800a471b  mov     r9d, eax; char *
0x1800a471e  lea     r8, aOnecoreuapBase_234; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800a4725  mov     edx, 105h; void *
0x1800a472a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a472f  jmp     loc_1800A4C34
0x1800a4734  mov     [rbp+4Fh+var_98], rsi
0x1800a4738  mov     [rbp+4Fh+string], rsi
0x1800a473c  lea     r9, [rbp+4Fh+string]; string
0x1800a4740  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x1800a4744  mov     edx, 25h ; '%'; length
0x1800a4749  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_User@@3QB_WB; "Windows.Internal.StateRepository.User"
0x1800a4750  call    cs:__imp_WindowsCreateStringReference
0x1800a4756  test    eax, eax
0x1800a4758  jns     short loc_1800A476D
0x1800a475a  xor     r9d, r9d; lpArguments
0x1800a475d  xor     r8d, r8d; nNumberOfArguments
0x1800a4760  lea     edx, [r9+1]; dwExceptionFlags
0x1800a4764  mov     ecx, eax; dwExceptionCode
0x1800a4766  call    cs:__imp_RaiseException
0x1800a476c  int     3; Trap to Debugger
0x1800a476d  lea     rdx, [rbp+4Fh+var_98]
0x1800a4771  mov     rcx, [rbp+4Fh+string]
0x1800a4775  call    ??$GetActivationFactory@V?$ComPtr@UIUserStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUserStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUserStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUserStatics>>)
0x1800a477a  mov     ebx, eax
0x1800a477c  test    eax, eax
0x1800a477e  jns     short loc_1800A479D
0x1800a4780  mov     rcx, [rbp+57h]; this
0x1800a4784  mov     r9d, eax; char *
0x1800a4787  lea     r8, aOnecoreuapBase_234; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800a478e  mov     edx, 109h; void *
0x1800a4793  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4798  jmp     loc_1800A4C2A
0x1800a479d  mov     [rbp+4Fh+var_A0], rsi
0x1800a47a1  mov     rdi, [rbp+4Fh+var_98]
0x1800a47a5  mov     rax, [rdi]
0x1800a47a8  mov     rbx, [rax+50h]
0x1800a47ac  lea     rcx, [rbp+4Fh+var_A0]
0x1800a47b0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a47b5  lea     rdx, [rbp+4Fh+var_80]
0x1800a47b9  lea     rcx, [rbp+4Fh+hstringHeader]
0x1800a47bd  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x1800a47c2  nop
0x1800a47c3  lea     r8, [rbp+4Fh+var_A0]
0x1800a47c7  mov     rdx, [rax+18h]
0x1800a47cb  mov     rcx, rdi
0x1800a47ce  mov     rax, rbx
0x1800a47d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a47d6  mov     ebx, eax
0x1800a47d8  test    eax, eax
0x1800a47da  jns     short loc_1800A47F9
0x1800a47dc  mov     rcx, [rbp+57h]; this
0x1800a47e0  mov     r9d, eax; char *
0x1800a47e3  lea     r8, aOnecoreuapBase_234; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800a47ea  mov     edx, 10Ch; void *
0x1800a47ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a47f4  jmp     loc_1800A4C20
0x1800a47f9  mov     [rbp+4Fh+var_88], rsi
0x1800a47fd  mov     [rbp+4Fh+string], rsi
0x1800a4801  lea     r9, [rbp+4Fh+string]; string
0x1800a4805  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x1800a4809  mov     edx, 2Ch ; ','; length
0x1800a480e  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QB_WB; "Windows.Internal.StateRepository.Applic"...
0x1800a4815  call    cs:__imp_WindowsCreateStringReference
0x1800a481b  test    eax, eax
0x1800a481d  jns     short loc_1800A4832
0x1800a481f  xor     r9d, r9d; lpArguments
0x1800a4822  xor     r8d, r8d; nNumberOfArguments
0x1800a4825  lea     edx, [r9+1]; dwExceptionFlags
0x1800a4829  mov     ecx, eax; dwExceptionCode
0x1800a482b  call    cs:__imp_RaiseException
0x1800a4831  int     3; Trap to Debugger
0x1800a4832  mov     rbx, [rbp+4Fh+string]
0x1800a4836  lea     rcx, [rbp+4Fh+var_88]
0x1800a483a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a483f  lea     r8, [rbp+4Fh+var_88]
0x1800a4843  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x1800a484a  mov     rcx, rbx
0x1800a484d  call    cs:__imp_RoGetActivationFactory
0x1800a4853  mov     ebx, eax
0x1800a4855  test    eax, eax
0x1800a4857  jns     short loc_1800A4876
0x1800a4859  mov     rcx, [rbp+57h]; this
0x1800a485d  mov     r9d, eax; char *
0x1800a4860  lea     r8, aOnecoreuapBase_234; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800a4867  mov     edx, 110h; void *
0x1800a486c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4871  jmp     loc_1800A4C16
0x1800a4876  mov     [rbp+4Fh+var_90], rsi
0x1800a487a  mov     rdi, [rbp+4Fh+var_88]
0x1800a487e  mov     rax, [rdi]
0x1800a4881  mov     rbx, [rax+138h]
0x1800a4888  lea     rcx, [rbp+4Fh+var_90]
0x1800a488c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a4891  lea     rdx, [rbp+4Fh+var_A8]
0x1800a4895  lea     rcx, [rbp+4Fh+hstringHeader]
0x1800a4899  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x1800a489e  nop
0x1800a489f  lea     r9, [rbp+4Fh+var_90]
0x1800a48a3  mov     r8, [rax+18h]
0x1800a48a7  mov     rdx, [rbp+4Fh+var_A0]
0x1800a48ab  mov     rcx, rdi
0x1800a48ae  mov     rax, rbx
0x1800a48b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a48b6  mov     ebx, eax
0x1800a48b8  xor     edi, edi
0x1800a48ba  test    eax, eax
0x1800a48bc  jns     short loc_1800A48DB
0x1800a48be  mov     edx, 114h; void *
0x1800a48c3  lea     r8, aOnecoreuapBase_234; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800a48ca  mov     r9d, eax; char *
0x1800a48cd  mov     rcx, [rbp+57h]; this
0x1800a48d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a48d6  jmp     loc_1800A4C0C
0x1800a48db  mov     [rbp+4Fh+var_70], edi
0x1800a48de  mov     rcx, [rbp+4Fh+var_90]
0x1800a48e2  mov     rax, [rcx]
0x1800a48e5  lea     rdx, [rbp+4Fh+var_70]
0x1800a48e9  mov     rax, [rax+38h]
0x1800a48ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a48f2  mov     ebx, eax
0x1800a48f4  test    eax, eax
0x1800a48f6  jns     short loc_1800A48FF
0x1800a48f8  mov     edx, 117h
0x1800a48fd  jmp     short loc_1800A48C3
0x1800a48ff  mov     r14d, edi
0x1800a4902  mov     r15d, edi
0x1800a4905  mov     esi, 1
0x1800a490a  mov     eax, r14d
0x1800a490d  cmp     r15d, [rbp+4Fh+var_70]
0x1800a4911  jnb     loc_1800A4D23
0x1800a4917  mov     [rbp+4Fh+var_A8], rdi
0x1800a491b  mov     rdi, [rbp+4Fh+var_90]
0x1800a491f  mov     rax, [rdi]
0x1800a4922  mov     rbx, [rax+30h]
0x1800a4926  lea     rcx, [rbp+4Fh+var_A8]
0x1800a492a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a492f  lea     r8, [rbp+4Fh+var_A8]
0x1800a4933  mov     edx, r15d
0x1800a4936  mov     rcx, rdi
0x1800a4939  mov     rax, rbx
0x1800a493c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4941  mov     ebx, eax
0x1800a4943  xor     edi, edi
0x1800a4945  test    eax, eax
0x1800a4947  js      loc_1800A4C69
0x1800a494d  mov     [rbp+4Fh+var_80], rdi
0x1800a4951  mov     rbx, [rbp+4Fh+var_78]
0x1800a4955  mov     rdi, [rbx]
0x1800a4958  lea     rcx, [rbp+4Fh+var_80]
0x1800a495c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a4961  xor     eax, eax
0x1800a4963  mov     [rbp+4Fh+string], rax
0x1800a4967  mov     rcx, cs:sourceString; sourceString
0x1800a496e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800a4972  inc     rdx; length
0x1800a4975  cmp     [rcx+rdx*2], ax
0x1800a4979  jnz     short loc_1800A4972
0x1800a497b  mov     eax, 0FFFFFFFFh
0x1800a4980  cmp     rdx, rax
0x1800a4983  ja      loc_1800A4C55
0x1800a4989  lea     eax, [rdx+1]
0x1800a498c  cmp     eax, edx
0x1800a498e  jb      loc_1800A4C55
0x1800a4994  lea     r9, [rbp+4Fh+string]; string
0x1800a4998  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x1800a499c  call    cs:__imp_WindowsCreateStringReference
0x1800a49a2  test    eax, eax
0x1800a49a4  js      loc_1800A4C44
0x1800a49aa  lea     r9, [rbp+4Fh+var_80]
0x1800a49ae  mov     r8, [rbp+4Fh+string]
0x1800a49b2  mov     rdx, [rbp+4Fh+var_A8]
0x1800a49b6  mov     rcx, rbx
0x1800a49b9  mov     rax, [rdi+88h]
0x1800a49c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a49c5  mov     ebx, eax
0x1800a49c7  xor     eax, eax
0x1800a49c9  test    ebx, ebx
0x1800a49cb  js      loc_1800A4BDF
0x1800a49d1  mov     [rbp+4Fh+var_6C], eax
0x1800a49d4  mov     rcx, [rbp+4Fh+var_80]
0x1800a49d8  mov     rax, [rcx]
0x1800a49db  lea     rdx, [rbp+4Fh+var_6C]
0x1800a49df  mov     rax, [rax+38h]
0x1800a49e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a49e8  mov     ebx, eax
0x1800a49ea  xor     eax, eax
0x1800a49ec  test    ebx, ebx
0x1800a49ee  js      loc_1800A4BD8
0x1800a49f4  cmp     [rbp+4Fh+var_6C], eax
0x1800a49f7  jbe     short loc_1800A49FC
0x1800a49f9  or      r14d, esi
0x1800a49fc  mov     [rbp+4Fh+var_B0], al
0x1800a49ff  mov     rbx, [rbp+4Fh+var_78]
0x1800a4a03  mov     rdi, [rbx]
0x1800a4a06  mov     [rbp+4Fh+string], rax
0x1800a4a0a  mov     rcx, cs:off_180245E98; sourceString
0x1800a4a11  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800a4a15  inc     rdx; length
0x1800a4a18  cmp     [rcx+rdx*2], ax
0x1800a4a1c  jnz     short loc_1800A4A15
0x1800a4a1e  mov     eax, 0FFFFFFFFh
0x1800a4a23  cmp     rdx, rax
0x1800a4a26  ja      loc_1800A4BC4
0x1800a4a2c  lea     eax, [rdx+1]
0x1800a4a2f  cmp     eax, edx
0x1800a4a31  jb      loc_1800A4BC4
0x1800a4a37  lea     r9, [rbp+4Fh+string]; string
0x1800a4a3b  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x1800a4a3f  call    cs:__imp_WindowsCreateStringReference
0x1800a4a45  test    eax, eax
0x1800a4a47  js      loc_1800A4BB3
0x1800a4a4d  lea     r9, [rbp+4Fh+var_B0]
0x1800a4a51  mov     r8, [rbp+4Fh+string]
0x1800a4a55  mov     rdx, [rbp+4Fh+var_A8]
0x1800a4a59  mov     rcx, rbx
0x1800a4a5c  mov     rax, [rdi+40h]
0x1800a4a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4a65  mov     ebx, eax
0x1800a4a67  xor     eax, eax
0x1800a4a69  test    ebx, ebx
0x1800a4a6b  js      loc_1800A4BAC
0x1800a4a71  cmp     [rbp+4Fh+var_B0], al
0x1800a4a74  jz      short loc_1800A4A7A
0x1800a4a76  or      r14d, 2
0x1800a4a7a  mov     [rbp+4Fh+var_AF], al
0x1800a4a7d  mov     rbx, [rbp+4Fh+var_78]
0x1800a4a81  mov     rdi, [rbx]
0x1800a4a84  mov     [rbp+4Fh+string], rax
0x1800a4a88  mov     rcx, cs:off_180245EA8; sourceString
0x1800a4a8f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800a4a93  inc     rdx; length
0x1800a4a96  cmp     [rcx+rdx*2], ax
0x1800a4a9a  jnz     short loc_1800A4A93
0x1800a4a9c  mov     eax, 0FFFFFFFFh
0x1800a4aa1  cmp     rdx, rax
0x1800a4aa4  ja      loc_1800A4B98
0x1800a4aaa  lea     eax, [rdx+1]
0x1800a4aad  cmp     eax, edx
0x1800a4aaf  jb      loc_1800A4B98
0x1800a4ab5  lea     r9, [rbp+4Fh+string]; string
0x1800a4ab9  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x1800a4abd  call    cs:__imp_WindowsCreateStringReference
0x1800a4ac3  test    eax, eax
0x1800a4ac5  js      loc_1800A4B87
0x1800a4acb  lea     r9, [rbp+4Fh+var_AF]
0x1800a4acf  mov     r8, [rbp+4Fh+string]
0x1800a4ad3  mov     rdx, [rbp+4Fh+var_A8]
0x1800a4ad7  mov     rcx, rbx
0x1800a4ada  mov     rax, [rdi+40h]
0x1800a4ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4ae3  mov     ebx, eax
0x1800a4ae5  xor     edi, edi
0x1800a4ae7  test    eax, eax
0x1800a4ae9  js      loc_1800A4B7D
0x1800a4aef  cmp     [rbp+4Fh+var_AF], dil
0x1800a4af3  jz      short loc_1800A4AF9
0x1800a4af5  or      r14d, 4
0x1800a4af9  test    r14d, r14d
0x1800a4afc  jz      short loc_1800A4B08
  ... truncated ...
```
