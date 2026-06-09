# GetExtensionRegistrationWithLaunchContractOptimization(ushort const *,ushort const *,ushort const *,HSTRING__ * *,Windows::Foundation::IExtensionRegistration * *)

- ea: `0x180010ab0`
- end: `0x180011305`
- name: `?GetExtensionRegistrationWithLaunchContractOptimization@@YAJPEBG00PEAPEAUHSTRING__@@PEAPEAUIExtensionRegistration@Foundation@Windows@@@Z`
- size: `2133`
- prototype: `__int64 __usercall@<rax>(PCWSTR psz1@<rcx>, PCWSTR sourceString@<rdx>, LPCWCH lpString1@<r8>, HSTRING *@<r9>, struct Windows::Foundation::IExtensionRegistration **)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180041768`

## callees

- `0x18000b5c0`
- `0x180010a34`
- `0x180010ab0`
- `0x18001130c`
- `0x180011328`
- `0x1800118d0`
- `0x1800445ac`
- `0x18005ae90`
- `0x18005b33c`
- `0x18005b37c`
- `0x18005d2b9`
- `0x18005d2c5`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010ce4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010e10`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800112b8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800112cc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800112e0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800112f4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010ce4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010e10`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800112b8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800112cc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800112e0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800112f4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180010b24`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180011249`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180010b24`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180011249`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010ea5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010ebc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001102b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011054`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800110ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800110d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800111a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010ea5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010ebc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001102b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011054`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800110ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800110d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800111a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001100c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001100c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010d60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010da6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010e29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010e67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010d60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010da6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010e29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010e67`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x180011018`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x180011018`
- `combase!__imp_RoGetExtensionRegistrationForLaunchContracts` at `0x180010e90`
- `combase!__imp_RoGetExtensionRegistrationForLaunchContracts` at `0x180010e90`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180010b5c`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180010b5c`

## string_xrefs

- `0x180010c20`: `onecoreuap\base\appmodel\execmodel\shared\utility\extensionregistrationhelper.cpp`
- `0x180011038`: `onecoreuap\base\appmodel\execmodel\shared\utility\extensionregistrationhelper.cpp`
- `0x180011126`: `onecoreuap\base\appmodel\execmodel\shared\utility\extensionregistrationhelper.cpp`
- `0x18001118b`: `onecoreuap\base\appmodel\execmodel\shared\utility\extensionregistrationhelper.cpp`
- `0x1800111f9`: `onecoreuap\base\appmodel\execmodel\shared\utility\extensionregistrationhelper.cpp`
- `0x180011269`: `onecoreuap\base\appmodel\execmodel\shared\utility\extensionregistrationhelper.cpp`
- `0x18001123d`: `Windows.ComponentUI`

## pseudocode

```c
int __fastcall GetExtensionRegistrationWithLaunchContractOptimization(
        PCWSTR psz1,
        PCWSTR sourceString,
        LPCWCH lpString1,
        HSTRING *a4,
        struct Windows::Foundation::IExtensionRegistration **a5)
{
  HSTRING v5; // rsi
  const WCHAR *v9; // r14
  unsigned __int64 v10; // rdi
  unsigned int v11; // eax
  unsigned __int64 v12; // rbx
  __int64 v13; // rcx
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rcx
  __int64 v18; // r14
  WCHAR *v19; // rax
  const WCHAR *v20; // rsi
  __int64 v21; // rdx
  unsigned __int64 v23; // rbx
  __int64 v24; // rdx
  unsigned __int64 v25; // rdx
  size_t v26; // rbx
  const WCHAR *v27; // rbx
  const WCHAR *v28; // rax
  const WCHAR *v29; // rax
  HRESULT v30; // eax
  unsigned __int64 v31; // rdx
  HRESULT v32; // eax
  unsigned __int64 v33; // rdx
  HRESULT v34; // eax
  HSTRING v35; // rbx
  HRESULT v36; // eax
  int ExtensionRegistrationForLaunchContracts; // eax
  int v38; // ebx
  __int64 *v39; // rdi
  __int64 v40; // rax
  __int64 (__fastcall *v41)(__int64 *, PCWSTR *); // rbx
  int v42; // eax
  int v43; // eax
  __int64 v44; // rcx
  __int64 v45; // rcx
  const WCHAR *StringRawBuffer; // rax
  HSTRING v47; // rax
  HSTRING v48; // rcx
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // rdx
  unsigned int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int *bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  __int64 v54; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v55; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING v56; // [rsp+40h] [rbp-C0h] BYREF
  PCWSTR v57; // [rsp+48h] [rbp-B8h] BYREF
  int v58[2]; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v59; // [rsp+58h] [rbp-A8h] BYREF
  PCWSTR sourceStringa; // [rsp+60h] [rbp-A0h] BYREF
  const WCHAR *v61; // [rsp+68h] [rbp-98h]
  _QWORD v62[2]; // [rsp+70h] [rbp-90h] BYREF
  UINT32 packageRelativeApplicationIdLength; // [rsp+80h] [rbp-80h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+84h] [rbp-7Ch] BYREF
  _QWORD v65[2]; // [rsp+88h] [rbp-78h] BYREF
  HSTRING_HEADER v66; // [rsp+98h] [rbp-68h] BYREF
  HSTRING v67; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING string; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING_HEADER v70; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING v71; // [rsp+F0h] [rbp-10h] BYREF
  HSTRING_HEADER v72; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING v73; // [rsp+110h] [rbp+10h] BYREF
  WCHAR packageRelativeApplicationId[72]; // [rsp+120h] [rbp+20h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+1B0h] [rbp+B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v5 = (HSTRING)a5;
  v57 = psz1;
  v59 = (HSTRING)a5;
  v9 = psz1;
  *a5 = 0;
  if ( a4 )
    *a4 = 0;
  v10 = -1;
  if ( CompareStringOrdinal(lpString1, -1, L"Windows.Launch", -1, 1) != 2
    && CompareStringOrdinal(lpString1, -1, L"Windows.ComponentUI", -1, 1) != 2 )
  {
    return -2147024809;
  }
  packageFamilyNameLength = 65;
  packageRelativeApplicationIdLength = 66;
  v11 = ParseApplicationUserModelId(
          v9,
          &packageFamilyNameLength,
          packageFamilyName,
          &packageRelativeApplicationIdLength,
          packageRelativeApplicationId);
  if ( v11 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x5D,
             (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\extensionregistrationhelper.cpp",
             (const char *)v11,
             bIgnoreCase);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&sourceStringa);
  v12 = -1;
  do
    ++v12;
  while ( packageRelativeApplicationId[v12] );
  v13 = 7;
  if ( sourceStringa == (PCWSTR)v62 )
    v14 = 7;
  else
    v14 = (__int64)(v62[0] - (_QWORD)sourceStringa) >> 1;
  if ( v12 <= v14 )
  {
    v23 = v12;
    memmove_0((void *)sourceStringa, packageRelativeApplicationId, v23 * 2);
    v61 = &sourceStringa[v23];
    sourceStringa[v23] = 0;
  }
  else
  {
    if ( sourceStringa != (PCWSTR)v62 )
      v13 = (__int64)(v62[0] - (_QWORD)sourceStringa) >> 1;
    v15 = 2 * v13 + 1;
    v16 = v12;
    if ( v15 >= v12 )
      v16 = v15;
    if ( v16 > 0x3FFFFFFFFFFFFFF7LL )
    {
      if ( v12 > 0x3FFFFFFFFFFFFFF7LL )
        goto LABEL_17;
      v17 = 0x3FFFFFFFFFFFFFF8LL;
    }
    else
    {
      v17 = v16 + 1;
      if ( v17 > 0x7FFFFFFFFFFFFFFFLL )
      {
LABEL_17:
        v21 = 99;
LABEL_18:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\extensionregistrationhelper.cpp",
          (const char *)0x8007000ELL,
          bIgnoreCase);
        if ( sourceStringa != (PCWSTR)v62 )
          operator delete((void *)sourceStringa, (const struct std::nothrow_t *)&std::nothrow);
        return -2147024882;
      }
    }
    v18 = v17;
    v19 = (WCHAR *)operator new(2 * v17, (const struct std::nothrow_t *)&std::nothrow);
    v20 = v19;
    if ( !v19 )
      goto LABEL_17;
    v26 = v12;
    memcpy_0(v19, packageRelativeApplicationId, v26 * 2);
    v27 = &v20[v26];
    *v27 = 0;
    if ( sourceStringa != (PCWSTR)v62 )
      operator delete((void *)sourceStringa, (const struct std::nothrow_t *)&std::nothrow);
    v28 = v20 - 1;
    sourceStringa = v20;
    v5 = v59;
    v29 = &v28[v18];
    v9 = v57;
    v62[0] = v29;
    v61 = v27;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &sourceStringa,
                           v24,
                           4) )
  {
    v21 = 100;
    goto LABEL_18;
  }
  v25 = -1;
  do
    ++v25;
  while ( packageRelativeApplicationId[v25] );
  if ( v25 > 0xFFFFFFFF || (int)v25 + 1 < (unsigned int)v25 )
    goto LABEL_26;
  v30 = WindowsCreateStringReference(packageRelativeApplicationId, v25, &hstringHeader, &string);
  if ( v30 < 0 )
  {
    RaiseException(v30, 1u, 0, 0);
    __debugbreak();
  }
  v31 = -1;
  v67 = 0;
  do
    ++v31;
  while ( sourceStringa[v31] );
  if ( v31 > 0xFFFFFFFF || (int)v31 + 1 < (unsigned int)v31 )
  {
LABEL_26:
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v32 = WindowsCreateStringReference(sourceStringa, v31, &v66, &v67);
  if ( v32 < 0 )
  {
    RaiseException(v32, 1u, 0, 0);
    __debugbreak();
  }
  v65[0] = string;
  v65[1] = v67;
  *(_QWORD *)v58 = 0;
  v56 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v58);
  v33 = -1;
  v71 = 0;
  do
    ++v33;
  while ( sourceString[v33] );
  if ( v33 > 0xFFFFFFFF || (int)v33 + 1 < (unsigned int)v33 )
    goto LABEL_41;
  v34 = WindowsCreateStringReference(sourceString, v33, &v70, &v71);
  if ( v34 < 0 )
  {
    RaiseException(v34, 1u, 0, 0);
    __debugbreak();
  }
  v73 = 0;
  do
    ++v10;
  while ( lpString1[v10] );
  if ( v10 > 0xFFFFFFFF || (int)v10 + 1 < (unsigned int)v10 )
  {
LABEL_41:
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v35 = v71;
  v36 = WindowsCreateStringReference(lpString1, v10, &v72, &v73);
  if ( v36 < 0 )
  {
    RaiseException(v36, 1u, 0, 0);
    __debugbreak();
  }
  bIgnoreCasea = v58;
  ExtensionRegistrationForLaunchContracts = RoGetExtensionRegistrationForLaunchContracts(v73, v35, 2, v65);
  v38 = ExtensionRegistrationForLaunchContracts;
  if ( ExtensionRegistrationForLaunchContracts < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6B,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\extensionregistrationhelper.cpp",
      (const char *)(unsigned int)ExtensionRegistrationForLaunchContracts,
      (int)v58);
    WindowsDeleteString(v56);
    v56 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v58);
    v67 = 0;
    string = 0;
    if ( sourceStringa != (PCWSTR)v62 )
      operator delete((void *)sourceStringa, (const struct std::nothrow_t *)&std::nothrow);
    return v38;
  }
  WindowsDeleteString(v56);
  v39 = *(__int64 **)v58;
  v56 = 0;
  v59 = 0;
  WindowsDeleteString(0);
  v40 = *v39;
  v59 = 0;
  v57 = 0;
  v55 = 0;
  v41 = *(__int64 (__fastcall **)(__int64 *, PCWSTR *))(v40 + 80);
  v54 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v57);
  v42 = v41(v39, &v57);
  if ( v42 < 0 )
  {
    v49 = 29;
LABEL_70:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v49,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\extensionregistrationhelper.cpp",
      (const char *)(unsigned int)v42,
      (int)v58);
    v50 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v57);
    goto LABEL_60;
  }
  v42 = (**(__int64 (__fastcall ***)(PCWSTR, GUID *, __int64 *))v57)(
          v57,
          &GUID_9308c3c5_c2ac_49d1_a024_660a2bb5d5ac,
          &v55);
  if ( v42 < 0 )
  {
    v49 = 30;
    goto LABEL_70;
  }
  v43 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v55 + 48LL))(v55, &v54);
  if ( v43 < 0 )
  {
    v51 = 31;
    goto LABEL_79;
  }
  v43 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v54 + 72LL))(v54, &v59);
  if ( v43 < 0 )
  {
    v51 = 35;
LABEL_79:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v51,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\extensionregistrationhelper.cpp",
      (const char *)(unsigned int)v43,
      (int)v58);
    Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(&v54);
    Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(&v55);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v57);
LABEL_60:
    WindowsDeleteString(v59);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\extensionregistrationhelper.cpp",
      (const char *)0x80270254LL,
      (int)bIgnoreCasea);
    WindowsDeleteString(v56);
    v56 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v58);
    v67 = 0;
    string = 0;
    if ( sourceStringa != (PCWSTR)v62 )
      operator delete((void *)sourceStringa, (const struct std::nothrow_t *)&std::nothrow);
    return -2144927148;
  }
  v43 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v54 + 56LL))(v54, &v56);
  if ( v43 < 0 )
  {
    v51 = 40;
    goto LABEL_79;
  }
  v44 = v54;
  if ( v54 )
  {
    v54 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
  v45 = v55;
  if ( v55 )
  {
    v55 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v57);
  StringRawBuffer = WindowsGetStringRawBuffer(v59, 0);
  if ( StrCmpIW(v9, StringRawBuffer) )
    goto LABEL_60;
  WindowsDeleteString(v59);
  *(_QWORD *)v5 = *(_QWORD *)v58;
  *(_QWORD *)v58 = 0;
  if ( a4 )
  {
    v47 = v56;
    v48 = 0;
    v56 = 0;
    *a4 = v47;
  }
  else
  {
    v48 = v56;
  }
  WindowsDeleteString(v48);
  v56 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v58);
  v67 = 0;
  string = 0;
  if ( sourceStringa != (PCWSTR)v62 )
    operator delete((void *)sourceStringa, (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x180010ab0  push    rbp
0x180010ab2  push    rsi
0x180010ab3  push    rdi
0x180010ab4  push    r12
0x180010ab6  push    r13
0x180010ab8  push    r14
0x180010aba  push    r15
0x180010abc  lea     rbp, [rsp-160h]
0x180010ac4  sub     rsp, 260h
0x180010acb  mov     rax, cs:__security_cookie
0x180010ad2  xor     rax, rsp
0x180010ad5  mov     [rbp+190h+var_50], rax
0x180010adc  mov     rsi, [rbp+190h+arg_20]
0x180010ae3  xor     eax, eax
0x180010ae5  mov     [rsp+290h+var_248], rcx
0x180010aea  mov     r13, r9
0x180010aed  mov     [rsp+290h+var_238], rsi
0x180010af2  mov     r15, r8
0x180010af5  mov     r12, rdx
0x180010af8  mov     r14, rcx
0x180010afb  mov     [rsi], rax
0x180010afe  test    r9, r9
0x180010b01  jz      short loc_180010B06
0x180010b03  mov     [r9], rax
0x180010b06  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180010b0d  mov     [rsp+290h+bIgnoreCase], 1; bIgnoreCase
0x180010b15  mov     r9d, edi; cchCount2
0x180010b18  lea     r8, String2; "Windows.Launch"
0x180010b1f  mov     edx, edi; cchCount1
0x180010b21  mov     rcx, r15; lpString1
0x180010b24  call    cs:__imp_CompareStringOrdinal
0x180010b2a  cmp     eax, 2
0x180010b2d  jnz     loc_180011232
0x180010b33  lea     rax, [rbp+190h+packageRelativeApplicationId]
0x180010b37  mov     [rbp+190h+packageFamilyNameLength], 41h ; 'A'
0x180010b3e  lea     r9, [rbp+190h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x180010b42  mov     qword ptr [rsp+290h+bIgnoreCase], rax; unsigned int
0x180010b47  lea     r8, [rbp+190h+packageFamilyName]; packageFamilyName
0x180010b4e  mov     [rbp+190h+packageRelativeApplicationIdLength], 42h ; 'B'
0x180010b55  lea     rdx, [rbp+190h+packageFamilyNameLength]; packageFamilyNameLength
0x180010b59  mov     rcx, r14; applicationUserModelId
0x180010b5c  call    cs:__imp_ParseApplicationUserModelId
0x180010b62  test    eax, eax
0x180010b64  jnz     loc_180011262
0x180010b6a  lea     rcx, [rsp+290h+sourceString]
0x180010b6f  mov     [rsp+290h+var_38], rbx
0x180010b77  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180010b7c  lea     rcx, [rbp+190h+packageRelativeApplicationId]
0x180010b80  mov     rbx, rdi
0x180010b83  inc     rbx
0x180010b86  cmp     word ptr [rcx+rbx*2], 0
0x180010b8b  jnz     short loc_180010B83
0x180010b8d  mov     r9, [rsp+290h+sourceString]
0x180010b92  lea     rax, [rsp+290h+var_220]
0x180010b97  mov     ecx, 7
0x180010b9c  cmp     r9, rax
0x180010b9f  jnz     loc_180010CEB
0x180010ba5  mov     eax, ecx
0x180010ba7  cmp     rbx, rax
0x180010baa  jbe     loc_180010C7C
0x180010bb0  lea     rax, [rsp+290h+var_220]
0x180010bb5  cmp     r9, rax
0x180010bb8  jnz     loc_180011096
0x180010bbe  lea     rax, ds:1[rcx*2]
0x180010bc6  mov     rcx, rbx
0x180010bc9  cmp     rax, rbx
0x180010bcc  cmovnb  rcx, rax
0x180010bd0  mov     rax, 3FFFFFFFFFFFFFF7h
0x180010bda  cmp     rcx, rax
0x180010bdd  ja      loc_180011282
0x180010be3  inc     rcx
0x180010be6  mov     rax, 7FFFFFFFFFFFFFFFh
0x180010bf0  cmp     rcx, rax
0x180010bf3  ja      short loc_180010C14
0x180010bf5  lea     r14, [rcx+rcx]
0x180010bf9  mov     rcx, r14; unsigned __int64
0x180010bfc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010c03  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010c08  mov     rsi, rax
0x180010c0b  test    rax, rax
0x180010c0e  jnz     loc_180010CFB
0x180010c14  mov     edx, 63h ; 'c'; void *
0x180010c19  mov     rcx, [rbp+198h]; this
0x180010c20  lea     r8, aOnecoreuapBase_26; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180010c27  mov     r9d, 8007000Eh; char *
0x180010c2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010c32  mov     rcx, [rsp+290h+sourceString]; void *
0x180010c37  lea     rax, [rsp+290h+var_220]
0x180010c3c  cmp     rcx, rax
0x180010c3f  jz      short loc_180010C4D
0x180010c41  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010c48  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010c4d  mov     eax, 8007000Eh
0x180010c52  mov     rbx, [rsp+290h+var_38]
0x180010c5a  mov     rcx, [rbp+190h+var_50]
0x180010c61  xor     rcx, rsp; StackCookie
0x180010c64  call    __security_check_cookie
0x180010c69  add     rsp, 260h
0x180010c70  pop     r15
0x180010c72  pop     r14
0x180010c74  pop     r13
0x180010c76  pop     r12
0x180010c78  pop     rdi
0x180010c79  pop     rsi
0x180010c7a  pop     rbp
0x180010c7b  retn
0x180010c7c  add     rbx, rbx
0x180010c7f  lea     rdx, [rbp+190h+packageRelativeApplicationId]; Src
0x180010c83  mov     r8, rbx; Size
0x180010c86  mov     rcx, r9; void *
0x180010c89  call    memmove_0
0x180010c8e  mov     rcx, [rsp+290h+sourceString]
0x180010c93  add     rcx, rbx
0x180010c96  xor     eax, eax
0x180010c98  mov     [rsp+290h+var_228], rcx
0x180010c9d  mov     [rcx], ax
0x180010ca0  mov     r8d, 4
0x180010ca6  lea     rcx, [rsp+290h+sourceString]
0x180010cab  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180010cb0  test    al, al
0x180010cb2  jz      loc_18001117A
0x180010cb8  lea     rax, [rbp+190h+packageRelativeApplicationId]
0x180010cbc  mov     rdx, rdi
0x180010cbf  nop
0x180010cc0  inc     rdx; length
0x180010cc3  cmp     word ptr [rax+rdx*2], 0
0x180010cc8  jnz     short loc_180010CC0
0x180010cca  mov     ebx, 0FFFFFFFFh
0x180010ccf  cmp     rdx, rbx
0x180010cd2  jbe     short loc_180010D4D
0x180010cd4  xor     r9d, r9d; lpArguments
0x180010cd7  xor     r8d, r8d; nNumberOfArguments
0x180010cda  mov     edx, 1; dwExceptionFlags
0x180010cdf  mov     ecx, 80070216h; dwExceptionCode
0x180010ce4  call    cs:__imp_RaiseException
0x180010cea  int     3; Trap to Debugger
0x180010ceb  mov     rax, [rsp+290h+var_220]
0x180010cf0  sub     rax, r9
0x180010cf3  sar     rax, 1
0x180010cf6  jmp     loc_180010BA7
0x180010cfb  add     rbx, rbx
0x180010cfe  lea     rdx, [rbp+190h+packageRelativeApplicationId]; Src
0x180010d02  mov     r8, rbx; Size
0x180010d05  mov     rcx, rsi; void *
0x180010d08  call    memcpy_0
0x180010d0d  xor     ecx, ecx
0x180010d0f  lea     rax, [rsp+290h+var_220]
0x180010d14  add     rbx, rsi
0x180010d17  mov     [rbx], cx
0x180010d1a  mov     rcx, [rsp+290h+sourceString]; void *
0x180010d1f  cmp     rcx, rax
0x180010d22  jnz     loc_18001129A
0x180010d28  lea     rax, [rsi-2]
0x180010d2c  mov     [rsp+290h+sourceString], rsi
0x180010d31  mov     rsi, [rsp+290h+var_238]
0x180010d36  add     rax, r14
0x180010d39  mov     r14, [rsp+290h+var_248]
0x180010d3e  mov     [rsp+290h+var_220], rax
0x180010d43  mov     [rsp+290h+var_228], rbx
0x180010d48  jmp     loc_180010CA0
0x180010d4d  lea     eax, [rdx+1]
0x180010d50  cmp     eax, edx
0x180010d52  jb      short loc_180010CD4
0x180010d54  lea     r9, [rbp+190h+string]; string
0x180010d58  lea     r8, [rbp+190h+hstringHeader]; hstringHeader
0x180010d5c  lea     rcx, [rbp+190h+packageRelativeApplicationId]; sourceString
0x180010d60  call    cs:__imp_WindowsCreateStringReference
0x180010d66  test    eax, eax
0x180010d68  js      loc_1800112AB
0x180010d6e  mov     rcx, [rsp+290h+sourceString]; sourceString
0x180010d73  mov     rdx, rdi
0x180010d76  mov     [rbp+190h+var_1E0], 0
0x180010d7e  xchg    ax, ax
0x180010d80  inc     rdx; length
0x180010d83  cmp     word ptr [rcx+rdx*2], 0
0x180010d88  jnz     short loc_180010D80
0x180010d8a  cmp     rdx, rbx
0x180010d8d  ja      loc_180010CD4
0x180010d93  lea     eax, [rdx+1]
0x180010d96  cmp     eax, edx
0x180010d98  jb      loc_180010CD4
0x180010d9e  lea     r9, [rbp+190h+var_1E0]; string
0x180010da2  lea     r8, [rbp+190h+var_1F8]; hstringHeader
0x180010da6  call    cs:__imp_WindowsCreateStringReference
0x180010dac  test    eax, eax
0x180010dae  js      loc_1800112BF
0x180010db4  mov     rax, [rbp+190h+string]
0x180010db8  lea     rcx, [rsp+290h+var_240]
0x180010dbd  mov     [rbp+190h+var_208], rax
0x180010dc1  mov     rax, [rbp+190h+var_1E0]
0x180010dc5  mov     [rbp+190h+var_200], rax
0x180010dc9  mov     qword ptr [rsp+290h+var_240], 0
0x180010dd2  mov     [rsp+290h+var_250], 0
0x180010ddb  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180010de0  mov     rdx, rdi
0x180010de3  mov     [rbp+190h+var_1A0], 0
0x180010deb  nop     dword ptr [rax+rax+00h]
0x180010df0  inc     rdx; length
0x180010df3  cmp     word ptr [r12+rdx*2], 0
0x180010df9  jnz     short loc_180010DF0
0x180010dfb  cmp     rdx, rbx
0x180010dfe  jbe     short loc_180010E17
0x180010e00  xor     r9d, r9d; lpArguments
0x180010e03  xor     r8d, r8d; nNumberOfArguments
0x180010e06  mov     edx, 1; dwExceptionFlags
0x180010e0b  mov     ecx, 80070216h; dwExceptionCode
0x180010e10  call    cs:__imp_RaiseException
0x180010e16  int     3; Trap to Debugger
0x180010e17  lea     eax, [rdx+1]
0x180010e1a  cmp     eax, edx
0x180010e1c  jb      short loc_180010E00
0x180010e1e  lea     r9, [rbp+190h+var_1A0]; string
0x180010e22  mov     rcx, r12; sourceString
0x180010e25  lea     r8, [rbp+190h+var_1B8]; hstringHeader
0x180010e29  call    cs:__imp_WindowsCreateStringReference
0x180010e2f  test    eax, eax
0x180010e31  js      loc_1800112D3
0x180010e37  xor     r12d, r12d
0x180010e3a  mov     [rbp+190h+var_180], r12
0x180010e3e  xchg    ax, ax
0x180010e40  inc     rdi
0x180010e43  cmp     [r15+rdi*2], r12w
0x180010e48  jnz     short loc_180010E40
0x180010e4a  cmp     rdi, rbx
0x180010e4d  ja      short loc_180010E00
0x180010e4f  lea     eax, [rdi+1]
0x180010e52  cmp     eax, edi
0x180010e54  jb      short loc_180010E00
0x180010e56  mov     rbx, [rbp+190h+var_1A0]
0x180010e5a  lea     r9, [rbp+190h+var_180]; string
0x180010e5e  lea     r8, [rbp+190h+var_198]; hstringHeader
0x180010e62  mov     edx, edi; length
0x180010e64  mov     rcx, r15; sourceString
0x180010e67  call    cs:__imp_WindowsCreateStringReference
0x180010e6d  test    eax, eax
0x180010e6f  js      loc_1800112E7
0x180010e75  mov     rcx, [rbp+190h+var_180]
0x180010e79  lea     rax, [rsp+290h+var_240]
0x180010e7e  lea     r9, [rbp+190h+var_208]
0x180010e82  mov     qword ptr [rsp+290h+bIgnoreCase], rax; int
0x180010e87  mov     r8d, 2
0x180010e8d  mov     rdx, rbx
0x180010e90  call    cs:__imp_RoGetExtensionRegistrationForLaunchContracts
0x180010e96  mov     ebx, eax
0x180010e98  test    eax, eax
0x180010e9a  js      loc_180011184
0x180010ea0  mov     rcx, [rsp+290h+var_250]; string
0x180010ea5  call    cs:__imp_WindowsDeleteString
0x180010eab  mov     rdi, qword ptr [rsp+290h+var_240]
0x180010eb0  xor     ecx, ecx; string
0x180010eb2  mov     [rsp+290h+var_250], r12
0x180010eb7  mov     [rsp+290h+var_238], r12
0x180010ebc  call    cs:__imp_WindowsDeleteString
0x180010ec2  mov     rax, [rdi]
0x180010ec5  lea     rcx, [rsp+290h+var_248]
0x180010eca  mov     [rsp+290h+var_238], r12
0x180010ecf  mov     [rsp+290h+var_248], r12
0x180010ed4  mov     [rsp+290h+var_258], r12
0x180010ed9  mov     rbx, [rax+50h]
0x180010edd  mov     [rsp+290h+var_260], r12
0x180010ee2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180010ee7  lea     rdx, [rsp+290h+var_248]
0x180010eec  mov     rcx, rdi
0x180010eef  mov     rax, rbx
0x180010ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ef7  test    eax, eax
0x180010ef9  js      loc_18001111A
0x180010eff  mov     rbx, [rsp+290h+var_248]
0x180010f04  mov     rdx, [rsp+290h+var_258]
0x180010f09  mov     rax, [rbx]
0x180010f0c  mov     rdi, [rax]
0x180010f0f  test    rdx, rdx
0x180010f12  jz      short loc_180010F28
0x180010f14  mov     [rsp+290h+var_258], r12
0x180010f19  mov     rcx, [rdx]
0x180010f1c  mov     rax, [rcx+10h]
0x180010f20  mov     rcx, rdx
0x180010f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f28  lea     r8, [rsp+290h+var_258]
0x180010f2d  mov     rcx, rbx
0x180010f30  lea     rdx, _GUID_9308c3c5_c2ac_49d1_a024_660a2bb5d5ac
0x180010f37  mov     rax, rdi
0x180010f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f3f  test    eax, eax
0x180010f41  js      loc_1800111E3
0x180010f47  mov     rbx, [rsp+290h+var_258]
0x180010f4c  mov     rdx, [rsp+290h+var_260]
0x180010f51  mov     rax, [rbx]
0x180010f54  mov     rdi, [rax+30h]
0x180010f58  test    rdx, rdx
0x180010f5b  jz      short loc_180010F71
0x180010f5d  mov     [rsp+290h+var_260], r12
0x180010f62  mov     rcx, [rdx]
0x180010f65  mov     rax, [rcx+10h]
0x180010f69  mov     rcx, rdx
0x180010f6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f71  lea     rdx, [rsp+290h+var_260]
0x180010f76  mov     rcx, rbx
0x180010f79  mov     rax, rdi
0x180010f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
