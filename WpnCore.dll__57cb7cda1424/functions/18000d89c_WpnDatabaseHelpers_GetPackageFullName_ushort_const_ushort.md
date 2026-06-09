# WpnDatabaseHelpers::GetPackageFullName(ushort const *,ushort * *)

- ea: `0x18000d89c`
- end: `0x18000de38`
- name: `?GetPackageFullName@WpnDatabaseHelpers@@YAJPEBGPEAPEAG@Z`
- size: `1436`
- prototype: `__int64 __fastcall(WpnDatabaseHelpers *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `12`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180040c98`
- `0x180054160`
- `0x180075c5c`
- `0x18007c880`
- `0x180085560`
- `0x180091ce0`
- `0x18009f8a8`
- `0x1800d579c`
- `0x180100fdc`
- `0x1801011f0`
- `0x180101538`
- `0x1801018b4`

## callees

- `0x180004e38`
- `0x18000d89c`
- `0x18000de40`
- `0x18000e090`
- `0x180011618`
- `0x180024614`
- `0x1800b99f0`
- `0x180118010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000d8d3`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000d8d3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d9ac`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000de1e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000de31`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d9ac`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000de1e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000de31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dab2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dba0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dab2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dba0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d92c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000dc7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d92c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000dc7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d9f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000da52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dc08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ddb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d9f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000da52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dc08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ddb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000da27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000da27`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000d955`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000d955`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall WpnDatabaseHelpers::GetPackageFullName(
        const wchar_t *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  wchar_t *v5; // rax
  int v6; // eax
  unsigned int v7; // ebx
  HRESULT v8; // eax
  HSTRING v9; // rbx
  int ActivationFactory; // eax
  _QWORD *v11; // rdi
  __int64 v12; // r14
  WCHAR *v13; // rsi
  unsigned __int64 v14; // rbx
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING *); // rbx
  int v19; // eax
  PCWSTR StringRawBuffer; // rax
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  _QWORD *v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  _QWORD *v27; // rcx
  __int64 v28; // rcx
  _QWORD *v29; // rcx
  WCHAR *v30; // rcx
  _QWORD *v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  _QWORD *v34; // rcx
  unsigned int v35; // eax
  UINT32 v36; // edx
  HRESULT v37; // eax
  int v38; // eax
  int v39; // eax
  __int64 v40; // rcx
  _QWORD *v41; // rcx
  __int64 v42; // rcx
  _QWORD *v43; // rcx
  __int64 v44; // rcx
  int v45; // [rsp+20h] [rbp-49h]
  _QWORD *v46; // [rsp+30h] [rbp-39h] BYREF
  int v47[2]; // [rsp+38h] [rbp-31h] BYREF
  __int64 v48; // [rsp+40h] [rbp-29h] BYREF
  HSTRING v49; // [rsp+48h] [rbp-21h] BYREF
  int v50; // [rsp+50h] [rbp-19h] BYREF
  LPVOID pv[3]; // [rsp+58h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+7h] BYREF
  HSTRING string; // [rsp+88h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v5 = wcschr(this, 0x21u);
  if ( !v5 )
    return 2147943568LL;
  memset(pv, 0, sizeof(pv));
  v6 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
         pv,
         this,
         v5 - this);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA2,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\databasehelpers.cpp",
      (const char *)(unsigned int)v6,
      v45);
LABEL_67:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pv);
    return v7;
  }
  v46 = 0;
  string = 0;
  v8 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Package", 0x28u, &hstringHeader, &string);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    goto LABEL_70;
  }
  v9 = string;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
  ActivationFactory = RoGetActivationFactory(v9, &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419, &v46);
  v7 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\databasehelpers.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v45);
    v31 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v31 + 16LL))(v31);
    }
    v30 = (WCHAR *)pv[0];
    if ( !pv[0] )
      return v7;
    goto LABEL_35;
  }
  *(_QWORD *)v47 = 0;
  v11 = v46;
  v12 = *v46;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v47);
  string = 0;
  v13 = (WCHAR *)pv[0];
  v14 = -1;
  do
    ++v14;
  while ( *((_WORD *)pv[0] + v14) );
  if ( v14 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    return 2147943568LL;
  }
  v35 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v14);
  v36 = v35 - 1;
  if ( (unsigned int)v14 < v35 )
    v36 = v14;
  v37 = WindowsCreateStringReference(v13, v36, &hstringHeader, &string);
  if ( v37 < 0 )
  {
LABEL_70:
    RaiseException(v37, 1u, 0, 0);
    JUMPOUT(0x18000DE37LL);
  }
  v38 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, HSTRING, __int64))(v12 + 504))(v11, 0, string, 49);
  v7 = v38;
  if ( v38 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\databasehelpers.cpp",
      (const char *)(unsigned int)v38,
      (int)v47);
    v28 = *(_QWORD *)v47;
    if ( *(_QWORD *)v47 )
    {
      *(_QWORD *)v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    }
    v29 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v29 + 16LL))(v29);
    }
    goto LABEL_33;
  }
  v50 = 0;
  v39 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)v47 + 56LL))(*(_QWORD *)v47, &v50);
  v7 = v39;
  if ( v39 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAF,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\databasehelpers.cpp",
      (const char *)(unsigned int)v39,
      (int)v47);
    v42 = *(_QWORD *)v47;
    if ( *(_QWORD *)v47 )
    {
      *(_QWORD *)v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    }
    v43 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v43 + 16LL))(v43);
    }
    goto LABEL_33;
  }
  if ( v50 != 1 )
  {
    v7 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB0,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\databasehelpers.cpp",
      (const char *)0x8000FFFFLL,
      (int)v47);
    v40 = *(_QWORD *)v47;
    if ( *(_QWORD *)v47 )
    {
      *(_QWORD *)v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    }
    v41 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v41 + 16LL))(v41);
    }
LABEL_33:
    if ( !v13 )
      return v7;
    v30 = v13;
LABEL_35:
    CoTaskMemFree(v30);
    return v7;
  }
  v48 = 0;
  v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**(_QWORD **)v47 + 48LL))(*(_QWORD *)v47, 0, &v48);
  v7 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\databasehelpers.cpp",
      (const char *)(unsigned int)v16,
      (int)v47);
    v25 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    v26 = *(_QWORD *)v47;
    if ( *(_QWORD *)v47 )
    {
      *(_QWORD *)v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    v27 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v27 + 16LL))(v27);
    }
    goto LABEL_33;
  }
  v49 = 0;
  v17 = v48;
  v18 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v48 + 112LL);
  WindowsDeleteString(0);
  v49 = 0;
  v19 = v18(v17, &v49);
  v7 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB6,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\databasehelpers.cpp",
      (const char *)(unsigned int)v19,
      (int)v47);
    WindowsDeleteString(v49);
    v49 = 0;
    v32 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
    v33 = *(_QWORD *)v47;
    if ( *(_QWORD *)v47 )
    {
      *(_QWORD *)v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    }
    v34 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v34 + 16LL))(v34);
    }
    goto LABEL_33;
  }
  memset(&hstringHeader, 0, sizeof(hstringHeader));
  StringRawBuffer = WindowsGetStringRawBuffer(v49, 0);
  v21 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
          &hstringHeader,
          StringRawBuffer,
          -1);
  v7 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB9,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\databasehelpers.cpp",
      (const char *)(unsigned int)v21,
      (int)v47);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
    WindowsDeleteString(v49);
    v49 = 0;
    v44 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v47);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
    goto LABEL_67;
  }
  *(_QWORD *)a2 = hstringHeader.Reserved.Reserved1;
  WindowsDeleteString(v49);
  v49 = 0;
  v22 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  v23 = *(_QWORD *)v47;
  if ( *(_QWORD *)v47 )
  {
    *(_QWORD *)v47 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  v24 = v46;
  if ( v46 )
  {
    v46 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v24 + 16LL))(v24);
  }
  if ( v13 )
    CoTaskMemFree(v13);
  return 0;
}

```

## disassembly

```asm
0x18000d89c  mov     [rsp-8+arg_10], rbx
0x18000d8a1  mov     [rsp-8+arg_18], rsi
0x18000d8a6  push    rbp
0x18000d8a7  push    rdi
0x18000d8a8  push    r12
0x18000d8aa  push    r14
0x18000d8ac  push    r15
0x18000d8ae  lea     rbp, [rsp-37h]
0x18000d8b3  sub     rsp, 0A0h
0x18000d8ba  mov     rax, cs:__security_cookie
0x18000d8c1  xor     rax, rsp
0x18000d8c4  mov     [rbp+57h+var_30], rax
0x18000d8c8  mov     r15, rdx
0x18000d8cb  mov     rbx, rcx
0x18000d8ce  mov     edx, 21h ; '!'; Ch
0x18000d8d3  call    cs:__imp_wcschr
0x18000d8d9  xor     r12d, r12d
0x18000d8dc  test    rax, rax
0x18000d8df  jz      loc_18000D9B3
0x18000d8e5  mov     [rbp+57h+pv], r12
0x18000d8e9  mov     [rbp+57h+var_60], r12
0x18000d8ed  mov     [rbp+57h+var_58], r12
0x18000d8f1  sub     rax, rbx
0x18000d8f4  sar     rax, 1
0x18000d8f7  mov     r8, rax
0x18000d8fa  mov     rdx, rbx
0x18000d8fd  lea     rcx, [rbp+57h+pv]
0x18000d901  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18000d906  mov     ebx, eax
0x18000d908  test    eax, eax
0x18000d90a  js      loc_18000DDF8
0x18000d910  mov     [rbp+57h+var_90], r12
0x18000d914  mov     [rbp+57h+string], r12
0x18000d918  lea     r9, [rbp+57h+string]; string
0x18000d91c  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18000d920  lea     edx, [r12+28h]; length
0x18000d925  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18000d92c  call    cs:__imp_WindowsCreateStringReference
0x18000d932  test    eax, eax
0x18000d934  js      loc_18000DE12
0x18000d93a  mov     rbx, [rbp+57h+string]
0x18000d93e  lea     rcx, [rbp+57h+var_90]
0x18000d942  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000d947  lea     r8, [rbp+57h+var_90]
0x18000d94b  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x18000d952  mov     rcx, rbx
0x18000d955  call    cs:__imp_RoGetActivationFactory
0x18000d95b  mov     ebx, eax
0x18000d95d  test    eax, eax
0x18000d95f  js      loc_18000DBAD
0x18000d965  mov     qword ptr [rbp+57h+var_88], r12
0x18000d969  mov     rdi, [rbp+57h+var_90]
0x18000d96d  mov     r14, [rdi]
0x18000d970  lea     rcx, [rbp+57h+var_88]
0x18000d974  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000d979  mov     [rbp+57h+string], r12
0x18000d97d  mov     rsi, [rbp+57h+pv]
0x18000d981  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000d985  inc     rbx
0x18000d988  cmp     [rsi+rbx*2], r12w
0x18000d98d  jnz     short loc_18000D985
0x18000d98f  mov     eax, 0FFFFFFFFh
0x18000d994  cmp     rbx, rax
0x18000d997  jbe     loc_18000DC65
0x18000d99d  xor     r9d, r9d; lpArguments
0x18000d9a0  xor     r8d, r8d; nNumberOfArguments
0x18000d9a3  lea     edx, [r9+1]; dwExceptionFlags
0x18000d9a7  mov     ecx, 80070216h; dwExceptionCode
0x18000d9ac  call    cs:__imp_RaiseException
0x18000d9b2  nop
0x18000d9b3  mov     eax, 80070490h
0x18000d9b8  jmp     loc_18000DABA
0x18000d9bd  mov     [rbp+57h+var_80], r12
0x18000d9c1  mov     rcx, qword ptr [rbp+57h+var_88]
0x18000d9c5  mov     rax, [rcx]
0x18000d9c8  lea     r8, [rbp+57h+var_80]
0x18000d9cc  xor     edx, edx
0x18000d9ce  mov     rax, [rax+30h]
0x18000d9d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9d7  mov     ebx, eax
0x18000d9d9  test    eax, eax
0x18000d9db  js      loc_18000DAE2
0x18000d9e1  mov     [rbp+57h+var_78], r12
0x18000d9e5  mov     rdi, [rbp+57h+var_80]
0x18000d9e9  mov     rax, [rdi]
0x18000d9ec  mov     rbx, [rax+70h]
0x18000d9f0  xor     ecx, ecx; string
0x18000d9f2  call    cs:__imp_WindowsDeleteString
0x18000d9f8  mov     [rbp+57h+var_78], r12
0x18000d9fc  lea     rdx, [rbp+57h+var_78]
0x18000da00  mov     rcx, rdi
0x18000da03  mov     rax, rbx
0x18000da06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da0b  mov     ebx, eax
0x18000da0d  test    eax, eax
0x18000da0f  js      loc_18000DBEB
0x18000da15  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r12
0x18000da19  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r12
0x18000da1d  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], r12
0x18000da21  xor     edx, edx; length
0x18000da23  mov     rcx, [rbp+57h+var_78]; string
0x18000da27  call    cs:__imp_WindowsGetStringRawBuffer
0x18000da2d  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000da31  mov     rdx, rax
0x18000da34  lea     rcx, [rbp+57h+hstringHeader]
0x18000da38  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18000da3d  mov     ebx, eax
0x18000da3f  test    eax, eax
0x18000da41  js      loc_18000DD8C
0x18000da47  mov     rax, qword ptr [rbp+57h+hstringHeader.Reserved]
0x18000da4b  mov     [r15], rax
0x18000da4e  mov     rcx, [rbp+57h+var_78]; string
0x18000da52  call    cs:__imp_WindowsDeleteString
0x18000da58  mov     [rbp+57h+var_78], r12
0x18000da5c  mov     rcx, [rbp+57h+var_80]
0x18000da60  test    rcx, rcx
0x18000da63  jz      short loc_18000DA76
0x18000da65  mov     [rbp+57h+var_80], r12
0x18000da69  mov     rax, [rcx]
0x18000da6c  mov     rax, [rax+10h]
0x18000da70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da75  nop
0x18000da76  mov     rcx, qword ptr [rbp+57h+var_88]
0x18000da7a  test    rcx, rcx
0x18000da7d  jz      short loc_18000DA90
0x18000da7f  mov     qword ptr [rbp+57h+var_88], r12
0x18000da83  mov     rax, [rcx]
0x18000da86  mov     rax, [rax+10h]
0x18000da8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da8f  nop
0x18000da90  mov     rcx, [rbp+57h+var_90]
0x18000da94  test    rcx, rcx
0x18000da97  jz      short loc_18000DAAA
0x18000da99  mov     [rbp+57h+var_90], r12
0x18000da9d  mov     rax, [rcx]
0x18000daa0  mov     rax, [rax+10h]
0x18000daa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daa9  nop
0x18000daaa  test    rsi, rsi
0x18000daad  jz      short loc_18000DAB8
0x18000daaf  mov     rcx, rsi; pv
0x18000dab2  call    cs:__imp_CoTaskMemFree
0x18000dab8  xor     eax, eax
0x18000daba  mov     rcx, [rbp+57h+var_30]
0x18000dabe  xor     rcx, rsp; StackCookie
0x18000dac1  call    __security_check_cookie
0x18000dac6  lea     r11, [rsp+0C0h+var_20]
0x18000dace  mov     rbx, [r11+40h]
0x18000dad2  mov     rsi, [r11+48h]
0x18000dad6  mov     rsp, r11
0x18000dad9  pop     r15
0x18000dadb  pop     r14
0x18000dadd  pop     r12
0x18000dadf  pop     rdi
0x18000dae0  pop     rbp
0x18000dae1  retn
0x18000dae2  mov     rcx, [rbp+5Fh]; this
0x18000dae6  mov     r9d, ebx; char *
0x18000dae9  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000daf0  mov     edx, 0B3h; void *
0x18000daf5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dafa  nop
0x18000dafb  mov     rcx, [rbp+57h+var_80]
0x18000daff  test    rcx, rcx
0x18000db02  jz      short loc_18000DB15
0x18000db04  mov     [rbp+57h+var_80], r12
0x18000db08  mov     rax, [rcx]
0x18000db0b  mov     rax, [rax+10h]
0x18000db0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db14  nop
0x18000db15  mov     rcx, qword ptr [rbp+57h+var_88]
0x18000db19  test    rcx, rcx
0x18000db1c  jz      short loc_18000DB2F
0x18000db1e  mov     qword ptr [rbp+57h+var_88], r12
0x18000db22  mov     rax, [rcx]
0x18000db25  mov     rax, [rax+10h]
0x18000db29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db2e  nop
0x18000db2f  mov     rcx, [rbp+57h+var_90]
0x18000db33  test    rcx, rcx
0x18000db36  jz      short loc_18000DB49
0x18000db38  mov     [rbp+57h+var_90], r12
0x18000db3c  mov     rax, [rcx]
0x18000db3f  mov     rax, [rax+10h]
0x18000db43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db48  nop
0x18000db49  jmp     short loc_18000DB98
0x18000db4b  mov     rcx, [rbp+5Fh]; this
0x18000db4f  mov     r9d, ebx; char *
0x18000db52  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000db59  mov     edx, 0ACh; void *
0x18000db5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000db63  nop
0x18000db64  mov     rcx, qword ptr [rbp+57h+var_88]
0x18000db68  test    rcx, rcx
0x18000db6b  jz      short loc_18000DB7E
0x18000db6d  mov     qword ptr [rbp+57h+var_88], r12
0x18000db71  mov     rax, [rcx]
0x18000db74  mov     rax, [rax+10h]
0x18000db78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db7d  nop
0x18000db7e  mov     rcx, [rbp+57h+var_90]
0x18000db82  test    rcx, rcx
0x18000db85  jz      short loc_18000DB98
0x18000db87  mov     [rbp+57h+var_90], r12
0x18000db8b  mov     rax, [rcx]
0x18000db8e  mov     rax, [rax+10h]
0x18000db92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db97  nop
0x18000db98  test    rsi, rsi
0x18000db9b  jz      short loc_18000DBA6
0x18000db9d  mov     rcx, rsi; pv
0x18000dba0  call    cs:__imp_CoTaskMemFree
0x18000dba6  mov     eax, ebx
0x18000dba8  jmp     loc_18000DABA
0x18000dbad  mov     rcx, [rbp+5Fh]; this
0x18000dbb1  mov     r9d, ebx; char *
0x18000dbb4  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000dbbb  mov     edx, 0A5h; void *
0x18000dbc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dbc5  nop
0x18000dbc6  mov     rcx, [rbp+57h+var_90]
0x18000dbca  test    rcx, rcx
0x18000dbcd  jz      short loc_18000DBE0
0x18000dbcf  mov     [rbp+57h+var_90], r12
0x18000dbd3  mov     rax, [rcx]
0x18000dbd6  mov     rax, [rax+10h]
0x18000dbda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbdf  nop
0x18000dbe0  mov     rcx, [rbp+57h+pv]
0x18000dbe4  test    rcx, rcx
0x18000dbe7  jnz     short loc_18000DBA0
0x18000dbe9  jmp     short loc_18000DBA6
0x18000dbeb  mov     rcx, [rbp+5Fh]; this
0x18000dbef  mov     r9d, ebx; char *
0x18000dbf2  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000dbf9  mov     edx, 0B6h; void *
0x18000dbfe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dc03  nop
0x18000dc04  mov     rcx, [rbp+57h+var_78]; string
0x18000dc08  call    cs:__imp_WindowsDeleteString
0x18000dc0e  mov     [rbp+57h+var_78], r12
0x18000dc12  mov     rcx, [rbp+57h+var_80]
0x18000dc16  test    rcx, rcx
0x18000dc19  jz      short loc_18000DC2C
0x18000dc1b  mov     [rbp+57h+var_80], r12
0x18000dc1f  mov     rax, [rcx]
0x18000dc22  mov     rax, [rax+10h]
0x18000dc26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc2b  nop
0x18000dc2c  mov     rcx, qword ptr [rbp+57h+var_88]
0x18000dc30  test    rcx, rcx
0x18000dc33  jz      short loc_18000DC46
0x18000dc35  mov     qword ptr [rbp+57h+var_88], r12
0x18000dc39  mov     rax, [rcx]
0x18000dc3c  mov     rax, [rax+10h]
0x18000dc40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc45  nop
0x18000dc46  mov     rcx, [rbp+57h+var_90]
0x18000dc4a  test    rcx, rcx
0x18000dc4d  jz      short loc_18000DC60
0x18000dc4f  mov     [rbp+57h+var_90], r12
0x18000dc53  mov     rax, [rcx]
0x18000dc56  mov     rax, [rax+10h]
0x18000dc5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc5f  nop
0x18000dc60  jmp     loc_18000DB98
0x18000dc65  mov     ecx, ebx; unsigned int
0x18000dc67  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18000dc6c  lea     edx, [rax-1]
0x18000dc6f  cmp     ebx, eax
0x18000dc71  cmovb   edx, ebx; length
0x18000dc74  lea     r9, [rbp+57h+string]; string
0x18000dc78  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18000dc7c  mov     rcx, rsi; sourceString
0x18000dc7f  call    cs:__imp_WindowsCreateStringReference
0x18000dc85  test    eax, eax
0x18000dc87  js      loc_18000DE25
0x18000dc8d  lea     rax, [rbp+57h+var_88]
0x18000dc91  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18000dc96  mov     r9d, 31h ; '1'
0x18000dc9c  mov     r8, [rbp+57h+string]
0x18000dca0  xor     edx, edx
0x18000dca2  mov     rcx, rdi
0x18000dca5  mov     rax, [r14+1F8h]
0x18000dcac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcb1  mov     ebx, eax
0x18000dcb3  test    eax, eax
0x18000dcb5  js      loc_18000DB4B
0x18000dcbb  mov     [rbp+57h+var_70], r12d
0x18000dcbf  mov     rcx, qword ptr [rbp+57h+var_88]
0x18000dcc3  mov     rax, [rcx]
0x18000dcc6  lea     rdx, [rbp+57h+var_70]
0x18000dcca  mov     rax, [rax+38h]
0x18000dcce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcd3  mov     ebx, eax
0x18000dcd5  test    eax, eax
0x18000dcd7  js      short loc_18000DD3A
0x18000dcd9  cmp     [rbp+57h+var_70], 1
0x18000dcdd  jz      loc_18000D9BD
  ... truncated ...
```
