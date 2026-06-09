# ScanForUpdates(void *,std::vector<Microsoft::WRL::Wrappers::HString,std::allocator<Microsoft::WRL::Wrappers::HString>> &,ulong,HSTRING__ *,char const *,ushort const *)

- ea: `0x180076668`
- end: `0x180076e42`
- name: `?ScanForUpdates@@YA?AV?$ComPtr@UIUpdateCollection@@@WRL@Microsoft@@PEAXAEAV?$vector@VHString@Wrappers@WRL@Microsoft@@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@KPEAUHSTRING__@@PEBDPEBG@Z`
- size: `2010`
- prototype: ``
- caller_count: `2`
- callee_count: `23`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180076628`
- `0x1801d2aa8`

## callees

- `0x180009ea0`
- `0x18000ee20`
- `0x1800101f4`
- `0x1800127c8`
- `0x18001cce0`
- `0x18002ec2c`
- `0x1800370f4`
- `0x180051798`
- `0x180063648`
- `0x18006f8b4`
- `0x18007008c`
- `0x180071f20`
- `0x1800731d0`
- `0x180075020`
- `0x180076668`
- `0x1800792f0`
- `0x18007970c`
- `0x180079878`
- `0x180079a68`
- `0x18007a7cc`
- `0x180114ad8`
- `0x180118c30`
- `0x180215010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800769d3`
- `OLEAUT32!__imp_VariantInit` at `0x1800769d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007671c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076cf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076d04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007671c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076cf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076d04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800767af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800767eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076ab0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076c25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076c80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800767af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800767eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076ab0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076c25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076c80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180076765`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180076765`

## string_xrefs

- `0x1800766f7`: `Update;`
- `0x180076a7c`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x180076ce4`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x180076d34`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x180076d49`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x180076d5d`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x180076d71`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x180076d86`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x180076d9a`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x180076dae`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x180076dc3`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x180076dd7`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x180076e1b`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x180076e2f`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x180076a6f`: `ScanForUpdates`
- `0x180076cd7`: `ScanForUpdates`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
_QWORD *__fastcall ScanForUpdates(
        _QWORD *a1,
        void *a2,
        __int64 a3,
        unsigned int a4,
        HSTRING a5,
        unsigned __int16 *a6,
        __int64 a7)
{
  unsigned int v7; // r15d
  _QWORD *v10; // r12
  __int64 v11; // rax
  HRESULT v12; // eax
  HSTRING v13; // rbx
  unsigned int StringRawBuffer; // eax
  const char *v15; // r9
  const unsigned __int16 *v16; // r13
  const unsigned __int16 *v17; // rdi
  int UpdateSearcher; // eax
  __int64 v19; // rdx
  int v20; // eax
  int v21; // eax
  struct IUpdateSearcher *v22; // rsi
  HRESULT (__stdcall *QueryInterface)(IUpdateSearcher *, const IID *const, void **); // rdi
  int v24; // eax
  int v25; // eax
  int v26; // eax
  struct IUpdateSearcher *v27; // rdi
  HRESULT (__stdcall *Search)(IUpdateSearcher *, BSTR, ISearchResult **); // rsi
  PCWSTR v29; // rdx
  _QWORD *bstr; // rax
  int v31; // edi
  LONG lVal; // esi
  int v33; // eax
  int v34; // eax
  unsigned int v35; // eax
  int v36; // eax
  PCWSTR v37; // rax
  unsigned int v38; // edi
  unsigned int v39; // eax
  HSTRING v40; // rcx
  ScanException *v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  unsigned int v45; // eax
  unsigned __int16 *v46; // [rsp+20h] [rbp-228h]
  int v47; // [rsp+20h] [rbp-228h]
  char *v48; // [rsp+30h] [rbp-218h]
  int v49; // [rsp+38h] [rbp-210h]
  LONG v50; // [rsp+40h] [rbp-208h]
  struct IUpdateSearcher *v51; // [rsp+48h] [rbp-200h] BYREF
  HSTRING newString; // [rsp+50h] [rbp-1F8h] BYREF
  unsigned __int16 *v53; // [rsp+58h] [rbp-1F0h] BYREF
  struct IUpdateInternalConfiguration *v54; // [rsp+60h] [rbp-1E8h] BYREF
  unsigned int v55; // [rsp+68h] [rbp-1E0h]
  __int64 v56; // [rsp+70h] [rbp-1D8h] BYREF
  __int64 v57; // [rsp+78h] [rbp-1D0h] BYREF
  unsigned __int16 *v58; // [rsp+80h] [rbp-1C8h]
  void *v59; // [rsp+88h] [rbp-1C0h] BYREF
  int v60; // [rsp+90h] [rbp-1B8h]
  HSTRING string2; // [rsp+98h] [rbp-1B0h]
  const size_t *v62; // [rsp+A0h] [rbp-1A8h]
  int v63[2]; // [rsp+A8h] [rbp-1A0h]
  VARIANTARG pvarg; // [rsp+B0h] [rbp-198h] BYREF
  _QWORD v65[2]; // [rsp+C8h] [rbp-180h] BYREF
  HSTRING string; // [rsp+D8h] [rbp-170h] BYREF
  _QWORD *v67; // [rsp+E0h] [rbp-168h]
  _BYTE v68[216]; // [rsp+E8h] [rbp-160h] BYREF
  VARIANTARG Buffer; // [rsp+1C0h] [rbp-88h] BYREF
  int v70; // [rsp+1D8h] [rbp-70h]
  char v71; // [rsp+1DCh] [rbp-6Ch]
  int v72; // [rsp+1E0h] [rbp-68h]
  bool v73; // [rsp+1E4h] [rbp-64h]
  int v74; // [rsp+1E8h] [rbp-60h]
  bool v75; // [rsp+1ECh] [rbp-5Ch]
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  v7 = a4;
  v59 = a2;
  v10 = a1;
  v67 = a1;
  v55 = a4;
  string2 = a5;
  v58 = a6;
  *(_QWORD *)v63 = a7;
  *a1 = 0;
  v60 = 1;
  v65[0] = L"Update;";
  v65[1] = L"Acquisition;";
  WindowsDeleteString(0);
  newString = 0;
  v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&Buffer, (char *)v65 + ((v7 & 4) != 0 ? 8 : 0));
  v12 = WindowsConcatString(*(HSTRING *)(v11 + 24), string2, &newString);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5E0,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
      (const char *)(unsigned int)v12,
      v47);
  BuildUpdateQuery(&string, a3, (v7 & 4) != 0 ? 2 : 0);
  v13 = string;
  if ( string )
  {
    StringRawBuffer = (unsigned int)WindowsGetStringRawBuffer(newString, 0);
    WindowsUpdate::Telemetry::BeginScanForUpdates((WindowsUpdate::Telemetry *)v7, StringRawBuffer, a6, v15);
    LODWORD(v53) = 0;
    v65[0] = 0;
    v16 = (const unsigned __int16 *)&dword_18023C12C;
    v62 = &dword_18023C12C;
    v51 = 0;
    v17 = WindowsGetStringRawBuffer(newString, 0);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v51);
    UpdateSearcher = GetUpdateSearcher(
                       0,
                       (enum tagSearchScope)(a2 != 0 ? searchScopeCurrentUserOnly : searchScopeMachineAndAllUsers),
                       &v51,
                       v17);
    if ( UpdateSearcher < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5F3,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
        (const char *)(unsigned int)UpdateSearcher,
        v47);
    LOWORD(v19) = -((v7 & 2) != 0);
    v20 = ((__int64 (__fastcall *)(struct IUpdateSearcher *, __int64))v51->lpVtbl->put_Online)(v51, v19);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5F4,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
        (const char *)(unsigned int)v20,
        v47);
    *(_DWORD *)&Buffer.vt = 262152;
    LOBYTE(Buffer.decVal.Hi32) = (v7 & 0x900) != 0;
    Buffer.lVal = 262145;
    LODWORD(v56) = v7 & 0x10;
    BYTE4(Buffer.decVal.Lo64) = (_DWORD)v56 != 0;
    *((_DWORD *)&Buffer.decVal + 4) = 262149;
    v70 = 262147;
    if ( (v7 & 4) != 0 )
    {
      *((_BYTE *)&Buffer.decVal + 20) = 0;
      v71 = 0;
    }
    else
    {
      *((_BYTE *)&Buffer.decVal + 20) = 1;
      v71 = 1;
    }
    v72 = 262156;
    v73 = (v7 & 0x200) != 0;
    v74 = 262146;
    v75 = (v7 & 0x14) == 0;
    v21 = SetInternalConfigurationFlags(v51, &Buffer, 6, v58);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x601,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
        (const char *)(unsigned int)v21,
        v47);
    if ( a2 )
    {
      v54 = 0;
      v22 = v51;
      QueryInterface = v51->lpVtbl->QueryInterface;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v54);
      v24 = ((__int64 (__fastcall *)(struct IUpdateSearcher *, GUID *, struct IUpdateInternalConfiguration **))QueryInterface)(
              v22,
              &GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b,
              &v54);
      if ( v24 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x606,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
          (const char *)(unsigned int)v24,
          v47);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureTokensAreDuplicable>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnsureTokensAreDuplicable>::GetImpl'::`2'::impl) )
      {
        v25 = _SetWuUserTokenProperty(v54, 0x40006u, v59);
        if ( v25 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x609,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
            (const char *)(unsigned int)v25,
            v47);
      }
      else
      {
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        pvarg.vt = 19;
        pvarg.lVal = (int)v59;
        Buffer = pvarg;
        v26 = (*(__int64 (__fastcall **)(struct IUpdateInternalConfiguration *, __int64, VARIANTARG *))(*(_QWORD *)v54 + 32LL))(
                v54,
                262150,
                &Buffer);
        if ( v26 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x611,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
            (const char *)(unsigned int)v26,
            v47);
      }
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v54);
    }
    else
    {
      LogSimpleMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
        0x616u,
        "ScanForUpdates",
        -1,
        L"User wasnt logged in. Scanning as LocalSystem",
        0,
        0);
    }
    v57 = 0;
    v27 = v51;
    Search = v51->lpVtbl->Search;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v57);
    v29 = WindowsGetStringRawBuffer(v13, 0);
    bstr = (_QWORD *)wil::make_bstr(&v59, v29);
    v31 = ((__int64 (__fastcall *)(struct IUpdateSearcher *, _QWORD, __int64 *))Search)(v27, *bstr, &v57);
    LODWORD(v54) = v31;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v59);
    lVal = 0;
    if ( (v31 == -2145107923 || v31 == 2392065) && !(_DWORD)v56 )
    {
      v56 = 0;
      v33 = Microsoft::WRL::ComPtr<IUpdateSearcher>::As<IUpdateInternalConfiguration>(&v51, &v56);
      try
      {
        if ( v33 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x61F,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
            (const char *)(unsigned int)v33,
            v47);
        memset(&pvarg, 0, sizeof(pvarg));
        v34 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v56 + 24LL))(v56, 262158, &pvarg);
        if ( v34 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x621,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
            (const char *)(unsigned int)v34,
            v47);
        lVal = pvarg.lVal;
        v50 = pvarg.lVal;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v56);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtExceptionMsg(
          retaddr,
          (void *)0x623,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
          "Error getting recommended retry interval",
          (const char *)v46);
        v13 = string;
        v16 = (const unsigned __int16 *)v62;
        lVal = v50;
        v10 = v67;
        v7 = v55;
        v31 = (int)v54;
      }
    }
    if ( v31 < 0 )
    {
      v42 = ScanException::ScanException((ScanException *)v68, lVal, v31);
      wil::details::ReportFailure_CustomException<ScanException>(retaddr, v43, v44, v42);
    }
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v10);
    v35 = PackagesFromSearchResult(v57, v10);
    if ( (int)(v35 + 0x80000000) >= 0 && v35 != -2145124316 )
    {
      v45 = wil::verify_hresult<long>(v35);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x62D,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
        (const char *)v45,
        v47);
    }
    if ( *v10 )
    {
      v36 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **))(*(_QWORD *)*v10 + 80LL))(*v10, &v53);
      if ( v36 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x632,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
          (const char *)(unsigned int)v36,
          v47);
      v37 = WindowsGetStringRawBuffer(string2, 0);
      if ( (unsigned __int8)_RetrieveAndSetAutoUpdateWorkScheduledWithUOTime(v37, v65) )
      {
        v16 = (const unsigned __int16 *)time_point_iso8601::time_point_iso8601(&Buffer.vt);
        v62 = (const size_t *)v16;
      }
    }
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v57);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v51);
    v38 = (unsigned int)v53;
    v39 = (unsigned int)WindowsGetStringRawBuffer(newString, 0);
    LODWORD(v48) = 0;
    WindowsUpdate::Telemetry::EndScanForUpdates(
      (WindowsUpdate::Telemetry *)v7,
      v39,
      (const unsigned __int16 *)v38,
      v63[0],
      v16,
      v58,
      v48,
      v49);
    v40 = v13;
  }
  else
  {
    LogSimpleMessage(
      2u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
      0x5E4u,
      "ScanForUpdates",
      -1,
      L"Empty CategoryId list. Did not scan. Returning empty packages",
      0,
      0);
    v40 = 0;
  }
  WindowsDeleteString(v40);
  WindowsDeleteString(newString);
  return v10;
}

```

## disassembly

```asm
0x180076668  push    rbx
0x18007666a  push    rsi
0x18007666b  push    rdi
0x18007666c  push    r12
0x18007666e  push    r13
0x180076670  push    r14
0x180076672  push    r15
0x180076674  sub     rsp, 210h
0x18007667b  mov     rax, cs:__security_cookie
0x180076682  xor     rax, rsp
0x180076685  mov     [rsp+248h+var_48], rax
0x18007668d  mov     r15d, r9d
0x180076690  mov     rdi, r8
0x180076693  mov     rsi, rdx
0x180076696  mov     [rsp+248h+var_1C0], rdx
0x18007669e  mov     r12, rcx
0x1800766a1  mov     [rsp+248h+var_168], rcx
0x1800766a9  mov     [rsp+248h+var_1E0], r9d
0x1800766ae  mov     rax, [rsp+248h+arg_20]
0x1800766b6  mov     [rsp+248h+string2], rax
0x1800766be  mov     r13, [rsp+248h+arg_28]
0x1800766c6  mov     [rsp+248h+var_1C8], r13
0x1800766ce  mov     rax, [rsp+248h+arg_30]
0x1800766d6  mov     qword ptr [rsp+248h+var_1A0], rax
0x1800766de  mov     eax, 1
0x1800766e3  mov     [rsp+248h+var_1B8], eax
0x1800766ea  xor     r14d, r14d
0x1800766ed  mov     [rcx], r14
0x1800766f0  mov     [rsp+248h+var_1B8], eax
0x1800766f7  lea     rax, pwzValue; "Update;"
0x1800766fe  mov     [rsp+248h+var_180], rax
0x180076706  lea     rax, aAcquisition_0; "Acquisition;"
0x18007670d  mov     [rsp+248h+var_178], rax
0x180076715  mov     [rsp+248h+newString], r14
0x18007671a  xor     ecx, ecx; string
0x18007671c  call    cs:__imp_WindowsDeleteString
0x180076722  mov     [rsp+248h+newString], r14
0x180076727  mov     ebx, r15d
0x18007672a  and     ebx, 4
0x18007672d  mov     [rsp+248h+var_208], ebx
0x180076731  mov     eax, ebx
0x180076733  neg     eax
0x180076735  sbb     rcx, rcx
0x180076738  and     ecx, 8
0x18007673b  lea     rdx, [rsp+248h+var_180]
0x180076743  add     rdx, rcx
0x180076746  lea     rcx, [rsp+248h+Buffer]
0x18007674e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180076753  nop
0x180076754  lea     r8, [rsp+248h+newString]; newString
0x180076759  mov     rdx, [rsp+248h+string2]; string2
0x180076761  mov     rcx, [rax+18h]; string1
0x180076765  call    cs:__imp_WindowsConcatString
0x18007676b  mov     rcx, [rsp+248h]; this
0x180076773  test    eax, eax
0x180076775  js      loc_180076D31
0x18007677b  mov     eax, ebx
0x18007677d  neg     eax
0x18007677f  sbb     r8d, r8d
0x180076782  and     r8d, 2
0x180076786  mov     rdx, rdi
0x180076789  lea     rcx, [rsp+248h+string]
0x180076791  call    ?BuildUpdateQuery@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$vector@VHString@Wrappers@WRL@Microsoft@@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@W4WU_INSTALLED_FLAG@@@Z; BuildUpdateQuery(std::vector<Microsoft::WRL::Wrappers::HString> const &,WU_INSTALLED_FLAG)
0x180076796  nop
0x180076797  mov     rbx, [rsp+248h+string]
0x18007679f  test    rbx, rbx
0x1800767a2  jz      loc_180076CB9
0x1800767a8  xor     edx, edx; length
0x1800767aa  mov     rcx, [rsp+248h+newString]; string
0x1800767af  call    cs:__imp_WindowsGetStringRawBuffer
0x1800767b5  mov     r8, r13; unsigned __int16 *
0x1800767b8  mov     rdx, rax; unsigned int
0x1800767bb  mov     ecx, r15d; this
0x1800767be  call    ?BeginScanForUpdates@Telemetry@WindowsUpdate@@YAXKPEBGPEBD@Z; WindowsUpdate::Telemetry::BeginScanForUpdates(ulong,ushort const *,char const *)
0x1800767c3  mov     dword ptr [rsp+248h+var_1F0], r14d
0x1800767c8  mov     [rsp+248h+var_180], r14
0x1800767d0  lea     r13, dword_18023C12C
0x1800767d7  mov     [rsp+248h+var_1A8], r13
0x1800767df  mov     [rsp+248h+var_200], r14
0x1800767e4  xor     edx, edx; length
0x1800767e6  mov     rcx, [rsp+248h+newString]; string
0x1800767eb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800767f1  mov     rdi, rax
0x1800767f4  lea     rcx, [rsp+248h+var_200]
0x1800767f9  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800767fe  mov     rax, rsi
0x180076801  neg     rax
0x180076804  sbb     edx, edx
0x180076806  and     edx, 0FFFFFFFEh
0x180076809  add     edx, 4; enum tagSearchScope
0x18007680c  mov     r9, rdi; unsigned __int16 *
0x18007680f  lea     r8, [rsp+248h+var_200]; struct IUpdateSearcher **
0x180076814  xor     ecx, ecx; struct IUpdateSession *
0x180076816  call    ?GetUpdateSearcher@@YAJPEAUIUpdateSession@@W4tagSearchScope@@PEAPEAUIUpdateSearcher@@PEBG@Z; GetUpdateSearcher(IUpdateSession *,tagSearchScope,IUpdateSearcher * *,ushort const *)
0x18007681b  mov     rcx, [rsp+248h]; this
0x180076823  test    eax, eax
0x180076825  js      loc_180076D46
0x18007682b  mov     rcx, [rsp+248h+var_200]
0x180076830  mov     r8, [rcx]
0x180076833  mov     eax, r15d
0x180076836  and     al, 2
0x180076838  neg     al
0x18007683a  sbb     dx, dx
0x18007683d  mov     rax, [r8+0A8h]
0x180076844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076849  mov     rcx, [rsp+248h]; this
0x180076851  test    eax, eax
0x180076853  js      loc_180076D5A
0x180076859  mov     dword ptr [rsp+248h+Buffer], 40008h
0x180076864  test    r15d, 900h
0x18007686b  setnz   byte ptr [rsp+248h+Buffer+4]
0x180076873  mov     dword ptr [rsp+248h+Buffer+8], 40001h
0x18007687e  mov     eax, r15d
0x180076881  and     eax, 10h
0x180076884  mov     dword ptr [rsp+248h+var_1D8], eax
0x180076888  setnz   byte ptr [rsp+248h+Buffer+0Ch]
0x180076890  mov     dword ptr [rsp+248h+var_78], 40005h
0x18007689b  mov     [rsp+248h+var_70], 40003h
0x1800768a6  cmp     [rsp+248h+var_208], r14d
0x1800768ab  jnz     short loc_1800768BF
0x1800768ad  mov     byte ptr [rsp+248h+var_78+4], 1
0x1800768b5  mov     [rsp+248h+var_6C], 1
0x1800768bd  jmp     short loc_1800768CF
0x1800768bf  mov     byte ptr [rsp+248h+var_78+4], r14b
0x1800768c7  mov     [rsp+248h+var_6C], r14b
0x1800768cf  mov     [rsp+248h+var_68], 4000Ch
0x1800768da  mov     eax, r15d
0x1800768dd  shr     eax, 9
0x1800768e0  and     al, 1
0x1800768e2  mov     [rsp+248h+var_64], al
0x1800768e9  mov     [rsp+248h+var_60], 40002h
0x1800768f4  test    r15b, 14h
0x1800768f8  setz    [rsp+248h+var_5C]
0x180076900  mov     r9, [rsp+248h+var_1C8]
0x180076908  mov     r8d, 6
0x18007690e  lea     rdx, [rsp+248h+Buffer]
0x180076916  mov     rcx, [rsp+248h+var_200]
0x18007691b  call    _SetInternalConfigurationFlags
0x180076920  mov     rcx, [rsp+248h]; this
0x180076928  test    eax, eax
0x18007692a  js      loc_180076D6E
0x180076930  test    rsi, rsi
0x180076933  jz      loc_180076A51
0x180076939  mov     [rsp+248h+var_1E8], r14
0x18007693e  mov     rsi, [rsp+248h+var_200]
0x180076943  mov     rax, [rsi]
0x180076946  mov     rdi, [rax]
0x180076949  lea     rcx, [rsp+248h+var_1E8]
0x18007694e  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180076953  lea     r8, [rsp+248h+var_1E8]
0x180076958  lea     rdx, _GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b
0x18007695f  mov     rcx, rsi
0x180076962  mov     rax, rdi
0x180076965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007696a  mov     rcx, [rsp+248h]; this
0x180076972  test    eax, eax
0x180076974  js      loc_180076D83
0x18007697a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnsureTokensAreDuplicable@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnsureTokensAreDuplicable@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureTokensAreDuplicable> `wil::Feature<__WilFeatureTraits_Feature_EnsureTokensAreDuplicable>::GetImpl(void)'::`2'::impl
0x180076981  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnsureTokensAreDuplicable@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureTokensAreDuplicable>::__private_IsEnabled(void)
0x180076986  test    al, al
0x180076988  jz      short loc_1800769B6
0x18007698a  mov     r8, [rsp+248h+var_1C0]; void *
0x180076992  mov     edx, 40006h; unsigned int
0x180076997  mov     rcx, [rsp+248h+var_1E8]; struct IUpdateInternalConfiguration *
0x18007699c  call    ?_SetWuUserTokenProperty@@YAJPEAUIUpdateInternalConfiguration@@KPEAX@Z; _SetWuUserTokenProperty(IUpdateInternalConfiguration *,ulong,void *)
0x1800769a1  mov     rcx, [rsp+248h]; this
0x1800769a9  test    eax, eax
0x1800769ab  js      loc_180076D97
0x1800769b1  jmp     loc_180076A45
0x1800769b6  xorps   xmm0, xmm0
0x1800769b9  xor     eax, eax
0x1800769bb  movups  xmmword ptr [rsp+248h+pvarg], xmm0
0x1800769c3  mov     qword ptr [rsp+248h+pvarg+10h], rax
0x1800769cb  lea     rcx, [rsp+248h+pvarg]; pvarg
0x1800769d3  call    cs:__imp_VariantInit
0x1800769d9  mov     eax, 13h
0x1800769de  mov     word ptr [rsp+248h+pvarg], ax
0x1800769e6  mov     rax, [rsp+248h+var_1C0]
0x1800769ee  mov     dword ptr [rsp+248h+pvarg+8], eax
0x1800769f5  mov     rcx, [rsp+248h+var_1E8]
0x1800769fa  movups  xmm0, xmmword ptr [rsp+248h+pvarg]
0x180076a02  movaps  xmmword ptr [rsp+248h+Buffer], xmm0
0x180076a0a  movsd   xmm1, qword ptr [rsp+248h+pvarg+10h]
0x180076a13  movsd   [rsp+248h+var_78], xmm1
0x180076a1c  mov     rax, [rcx]
0x180076a1f  lea     r8, [rsp+248h+Buffer]
0x180076a27  mov     edx, 40006h
0x180076a2c  mov     rax, [rax+20h]
0x180076a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076a35  mov     rcx, [rsp+248h]; this
0x180076a3d  test    eax, eax
0x180076a3f  js      loc_180076DAB
0x180076a45  lea     rcx, [rsp+248h+var_1E8]
0x180076a4a  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180076a4f  jmp     short loc_180076A8D
0x180076a51  mov     [rsp+248h+var_210], r14; unsigned __int16 *
0x180076a56  mov     [rsp+248h+var_218], r14; char *
0x180076a5b  lea     rax, aUserWasntLogge; "User wasnt logged in. Scanning as Local"...
0x180076a62  mov     [rsp+248h+var_220], rax; unsigned __int16 *
0x180076a67  mov     dword ptr [rsp+248h+var_228], 0FFFFFFFFh; int
0x180076a6f  lea     r9, aScanforupdates_2; "ScanForUpdates"
0x180076a76  mov     r8d, 616h; unsigned int
0x180076a7c  lea     rdx, aOnecoreuapEndu_18; "onecoreuap\\enduser\\winstore\\installs"...
0x180076a83  mov     ecx, 3; unsigned int
0x180076a88  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x180076a8d  mov     [rsp+248h+var_1D0], r14
0x180076a92  mov     rdi, [rsp+248h+var_200]
0x180076a97  mov     rax, [rdi]
0x180076a9a  mov     rsi, [rax+98h]
0x180076aa1  lea     rcx, [rsp+248h+var_1D0]
0x180076aa6  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180076aab  xor     edx, edx; length
0x180076aad  mov     rcx, rbx; string
0x180076ab0  call    cs:__imp_WindowsGetStringRawBuffer
0x180076ab6  mov     rdx, rax
0x180076ab9  lea     rcx, [rsp+248h+var_1C0]
0x180076ac1  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180076ac6  nop
0x180076ac7  lea     r8, [rsp+248h+var_1D0]
0x180076acc  mov     rdx, [rax]
0x180076acf  mov     rcx, rdi
0x180076ad2  mov     rax, rsi
0x180076ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076ada  mov     edi, eax
0x180076adc  mov     dword ptr [rsp+248h+var_1E8], eax
0x180076ae0  lea     rcx, [rsp+248h+var_1C0]
0x180076ae8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180076aed  mov     esi, r14d
0x180076af0  mov     [rsp+248h+var_208], r14d
0x180076af5  cmp     edi, 8024402Dh
0x180076afb  jz      short loc_180076B09
0x180076afd  cmp     edi, 248001h
0x180076b03  jnz     loc_180076BBB
0x180076b09  cmp     dword ptr [rsp+248h+var_1D8], r14d
0x180076b0e  jnz     loc_180076BBB
0x180076b14  mov     [rsp+248h+var_1D8], r14
0x180076b19  lea     rdx, [rsp+248h+var_1D8]
0x180076b1e  lea     rcx, [rsp+248h+var_200]
0x180076b23  call    ??$As@UIUpdateInternalConfiguration@@@?$ComPtr@UIUpdateSearcher@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUpdateInternalConfiguration@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IUpdateSearcher>::As<IUpdateInternalConfiguration>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IUpdateInternalConfiguration>>)
0x180076b28  mov     rcx, [rsp+248h]; this
0x180076b30  test    eax, eax
0x180076b32  js      loc_180076DC0
0x180076b38  xorps   xmm0, xmm0
0x180076b3b  xor     eax, eax
0x180076b3d  movups  xmmword ptr [rsp+248h+pvarg], xmm0
0x180076b45  mov     qword ptr [rsp+248h+pvarg+10h], rax
0x180076b4d  mov     rcx, [rsp+248h+var_1D8]
0x180076b52  mov     rax, [rcx]
0x180076b55  lea     r8, [rsp+248h+pvarg]
0x180076b5d  mov     edx, 4000Eh
0x180076b62  mov     rax, [rax+18h]
0x180076b66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076b6b  mov     rcx, [rsp+248h]; this
0x180076b73  test    eax, eax
0x180076b75  js      loc_180076DD4
0x180076b7b  mov     esi, dword ptr [rsp+248h+pvarg+8]
0x180076b82  mov     [rsp+248h+var_208], esi
0x180076b86  lea     rcx, [rsp+248h+var_1D8]
0x180076b8b  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180076b90  nop
0x180076b91  jmp     short loc_180076BBB
0x180076b93  xor     r14d, r14d
0x180076b96  mov     rbx, [rsp+248h+string]
0x180076b9e  mov     r13, [rsp+248h+var_1A8]
0x180076ba6  mov     esi, [rsp+248h+var_208]
0x180076baa  mov     r12, [rsp+248h+var_168]
0x180076bb2  mov     r15d, [rsp+248h+var_1E0]
0x180076bb7  mov     edi, dword ptr [rsp+248h+var_1E8]
0x180076bbb  test    edi, edi
0x180076bbd  js      loc_180076DE9
0x180076bc3  mov     rcx, r12
0x180076bc6  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180076bcb  mov     rdx, r12
0x180076bce  mov     rcx, [rsp+248h+var_1D0]
0x180076bd3  call    _PackagesFromSearchResult
0x180076bd8  mov     ecx, eax
0x180076bda  mov     edx, 80000000h
0x180076bdf  add     eax, edx
0x180076be1  test    edx, eax
0x180076be3  jnz     short loc_180076BF1
0x180076be5  cmp     ecx, 80240024h
0x180076beb  jnz     loc_180076E0B
0x180076bf1  mov     rcx, [r12]
0x180076bf5  test    rcx, rcx
0x180076bf8  jz      short loc_180076C5F
0x180076bfa  mov     rax, [rcx]
0x180076bfd  lea     rdx, [rsp+248h+var_1F0]
0x180076c02  mov     rax, [rax+50h]
0x180076c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076c0b  mov     rcx, [rsp+248h]; this
0x180076c13  test    eax, eax
0x180076c15  js      loc_180076E2C
0x180076c1b  xor     edx, edx; length
0x180076c1d  mov     rcx, [rsp+248h+string2]; string
0x180076c25  call    cs:__imp_WindowsGetStringRawBuffer
0x180076c2b  mov     rcx, rax
0x180076c2e  lea     rdx, [rsp+248h+var_180]
0x180076c36  call    ?_RetrieveAndSetAutoUpdateWorkScheduledWithUOTime@@YA_NPEBGAEAV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; _RetrieveAndSetAutoUpdateWorkScheduledWithUOTime(ushort const *,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> &)
0x180076c3b  test    al, al
0x180076c3d  jz      short loc_180076C5F
  ... truncated ...
```
