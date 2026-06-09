# KeyMachine::GetConsoleUserIdsLinkedToPuid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Microsoft::WRL::ComPtr<ILicenseIdentityContext> const &)

- ea: `0x180087268`
- end: `0x180087a3f`
- name: `?GetConsoleUserIdsLinkedToPuid@KeyMachine@@KA?AV?$vector@IV?$allocator@I@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@AEBV?$ComPtr@UILicenseIdentityContext@@@WRL@Microsoft@@@Z`
- size: `2007`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18002a484`

## callees

- `0x180004738`
- `0x180013b50`
- `0x180026914`
- `0x18003dab0`
- `0x18003dbc0`
- `0x1800588b4`
- `0x1800593bc`
- `0x180059460`
- `0x18006dbe4`
- `0x180074bc8`
- `0x180074ec8`
- `0x180075e60`
- `0x180084d70`
- `0x180087268`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180087746`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180087746`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180087737`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180087737`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180087705`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008778a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800877ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180087705`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008778a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800877ce`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18008730d`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18008737a`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800873eb`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180087478`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800874f8`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180087579`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800875f2`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18008730d`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18008737a`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800873eb`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180087478`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800874f8`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180087579`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800875f2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800875bc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800875bc`

## string_xrefs

- `0x180087766`: `KeyMachine::GetConsoleUserIdsLinkedToPuid`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
_QWORD *__fastcall KeyMachine::GetConsoleUserIdsLinkedToPuid(_QWORD *a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *v4; // r14
  HRESULT v5; // eax
  int v6; // eax
  HRESULT v7; // eax
  int v8; // eax
  HRESULT v9; // eax
  int v10; // eax
  HRESULT v11; // eax
  IUnknown *v12; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  int v14; // eax
  HRESULT v15; // eax
  IUnknown *v16; // rbx
  HRESULT (__stdcall *v17)(IUnknown *, const IID *const, void **); // rdi
  int v18; // eax
  HRESULT v19; // eax
  HRESULT v20; // eax
  HRESULT v21; // eax
  int v22; // eax
  unsigned int i; // r15d
  IUnknown *v24; // rdi
  HRESULT (__stdcall *v25)(IUnknown *, const IID *const, void **); // rbx
  int v26; // eax
  const unsigned __int16 *v27; // r9
  const unsigned __int16 *v28; // r8
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, HSTRING *); // rbx
  int v31; // eax
  const wchar_t *StringRawBuffer; // rax
  unsigned int v33; // eax
  IUnknown *v34; // rcx
  __int64 v35; // rcx
  wil *v36; // rcx
  __int64 v37; // r8
  __int64 v38; // rdx
  __int64 v39; // rcx
  int v41; // ecx
  _QWORD *v42; // rbx
  _QWORD *v43; // rax
  wil *v44; // rcx
  int v45; // ecx
  int v46; // r8d
  int v47; // r9d
  int dwAuthnLevel; // [rsp+20h] [rbp-118h]
  int dwAuthnLevela; // [rsp+20h] [rbp-118h]
  int dwAuthnLevelb; // [rsp+20h] [rbp-118h]
  int dwAuthnLevelc; // [rsp+20h] [rbp-118h]
  int dwAuthnLeveld; // [rsp+20h] [rbp-118h]
  int dwAuthnLevele; // [rsp+20h] [rbp-118h]
  int dwAuthnLevelf; // [rsp+20h] [rbp-118h]
  int dwAuthnLevelg; // [rsp+20h] [rbp-118h]
  unsigned int v56; // [rsp+40h] [rbp-F8h] BYREF
  HSTRING string; // [rsp+48h] [rbp-F0h] BYREF
  __int64 v58; // [rsp+50h] [rbp-E8h] BYREF
  IUnknown *v59; // [rsp+58h] [rbp-E0h] BYREF
  unsigned int v60; // [rsp+60h] [rbp-D8h] BYREF
  int v61; // [rsp+64h] [rbp-D4h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-D0h] BYREF
  IUnknown *v63; // [rsp+70h] [rbp-C8h] BYREF
  IUnknown *v64; // [rsp+78h] [rbp-C0h] BYREF
  __int64 v65; // [rsp+80h] [rbp-B8h] BYREF
  IUnknown *v66; // [rsp+88h] [rbp-B0h] BYREF
  IUnknown *pProxy; // [rsp+90h] [rbp-A8h] BYREF
  __int128 v68; // [rsp+98h] [rbp-A0h] BYREF
  __int64 v69; // [rsp+A8h] [rbp-90h]
  _QWORD *v70; // [rsp+B0h] [rbp-88h] BYREF
  unsigned __int64 v71; // [rsp+B8h] [rbp-80h] BYREF
  _QWORD *v72; // [rsp+C8h] [rbp-70h]
  _BYTE v73[16]; // [rsp+D0h] [rbp-68h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+E0h] [rbp-58h] BYREF
  __int64 v75; // [rsp+F8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  try
  {
    v4 = a1;
    v72 = a1;
    v70 = a2;
    v68 = 0;
    v69 = 0;
    ImpersonationScope<LicenseIdentityContextTraits>::ImpersonationScope<LicenseIdentityContextTraits>(v73, *a3);
    GetActivationFactory<Windows::System::IUserStatics>(&pProxy);
    v5 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x40u);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5A8,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
        (const char *)(unsigned int)v5,
        dwAuthnLevel);
    v65 = 0;
    v6 = ((__int64 (__fastcall *)(IUnknown *, __int64 *))pProxy->lpVtbl[2].AddRef)(pProxy, &v65);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5AB,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
        (const char *)(unsigned int)v6,
        dwAuthnLevel);
    v7 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x40u);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5AC,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
        (const char *)(unsigned int)v7,
        dwAuthnLevela);
    WaitForOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>(&v65);
    v59 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, IUnknown **))(*(_QWORD *)v65 + 64LL))(v65, &v59);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5B1,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
        (const char *)(unsigned int)v8,
        dwAuthnLevela);
    v9 = CoSetProxyBlanket(v59, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x40u);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5B2,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
        (const char *)(unsigned int)v9,
        dwAuthnLevelb);
    v66 = 0;
    v75 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.System.Internal.UserManager",
      0x24u,
      0x23u);
    v10 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>>(
            v75,
            &v66);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5B5,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
        (const char *)(unsigned int)v10,
        dwAuthnLevelb);
    v11 = CoSetProxyBlanket(v66, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x40u);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5B6,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
        (const char *)(unsigned int)v11,
        dwAuthnLevelc);
    v64 = 0;
    v12 = v66;
    QueryInterface = v66->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v64);
    v14 = ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))QueryInterface)(
            v12,
            &GUID_00000000_0000_0000_c000_000000000046,
            &v64);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5B9,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
        (const char *)(unsigned int)v14,
        dwAuthnLevelc);
    v15 = CoSetProxyBlanket(v64, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x40u);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5BA,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
        (const char *)(unsigned int)v15,
        dwAuthnLeveld);
    v63 = 0;
    v16 = v64;
    v17 = v64->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v63);
    v18 = ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))v17)(
            v16,
            &GUID_100eb64b_b24c_4c38_8964_720d926d05a4,
            &v63);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5BD,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
        (const char *)(unsigned int)v18,
        dwAuthnLeveld);
    v19 = CoSetProxyBlanket(v63, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x40u);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5BE,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
        (const char *)(unsigned int)v19,
        dwAuthnLevele);
    ppv = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
    v20 = CoCreateInstance(
            &GUID_0134a8b2_3407_4b45_ad25_e9f7c92a80bc,
            0,
            0x17u,
            &GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5,
            &ppv);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5C1,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
        (const char *)(unsigned int)v20,
        dwAuthnLevelf);
    v21 = CoSetProxyBlanket((IUnknown *)ppv, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x40u);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5C2,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
        (const char *)(unsigned int)v21,
        dwAuthnLevelg);
    v60 = 0;
    v22 = ((__int64 (__fastcall *)(IUnknown *, unsigned int *))v59->lpVtbl[2].AddRef)(v59, &v60);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5C6,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
        (const char *)(unsigned int)v22,
        dwAuthnLevelg);
    for ( i = 0; i < v60; ++i )
    {
      v58 = 0;
      v24 = v59;
      v25 = v59->lpVtbl[2].QueryInterface;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v58);
      v26 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, __int64 *))v25)(v24, i, &v58);
      if ( v26 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5CA,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
          (const char *)(unsigned int)v26,
          dwAuthnLevelg);
      v71 = 0;
      if ( ((int (__fastcall *)(IUnknown *, __int64, unsigned __int64 *))v63->lpVtbl[5].Release)(v63, v58, &v71) >= 0 )
      {
        v61 = 0;
        v28 = a2[3] <= 7u ? (const unsigned __int16 *)a2 : (const unsigned __int16 *)*a2;
        if ( (int)KeyMachine::DoesUserHaveLinkedWebAccountHelper((struct IXblAuthManager *)ppv, v71, v28, v27, &v61) >= 0
          && v61 )
        {
          string = 0;
          v29 = v58;
          v30 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v58 + 48LL);
          WindowsDeleteString(0);
          string = 0;
          v31 = v30(v29, &string);
          if ( v31 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x5D4,
              (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
              (const char *)(unsigned int)v31,
              dwAuthnLevelg);
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          v33 = wcstoul(StringRawBuffer, 0, 10);
          v56 = v33;
          if ( v33 == -1 )
          {
            LogMessage(
              1u,
              "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
              0x5D9u,
              "KeyMachine::GetConsoleUserIdsLinkedToPuid",
              (wchar_t *)L"invalid user ID, i=%d");
            WindowsDeleteString(string);
            string = 0;
          }
          else
          {
            if ( *((_QWORD *)&v68 + 1) == v69 )
            {
              std::vector<unsigned int>::_Emplace_reallocate<unsigned int const &>(&v68, *((_QWORD *)&v68 + 1), &v56);
            }
            else
            {
              **((_DWORD **)&v68 + 1) = v33;
              *((_QWORD *)&v68 + 1) += 4LL;
            }
            WindowsDeleteString(string);
          }
        }
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v58);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v63);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v64);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v66);
    v34 = v59;
    if ( v59 )
    {
      v59 = 0;
      ((void (__fastcall *)(IUnknown *))v34->lpVtbl->Release)(v34);
    }
    v35 = v65;
    if ( v65 )
    {
      v65 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&pProxy);
    ImpersonationScope<LicenseIdentityContextTraits>::~ImpersonationScope<LicenseIdentityContextTraits>(v73);
  }
  catch ( ... )
  {
    v41 = wil::ResultFromCaughtException(v36);
    v42 = v70;
    v43 = v70;
    if ( v70[3] > 7u )
      v43 = (_QWORD *)*v70;
    LogMessage(
      1u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
      0x5E8u,
      "KeyMachine::GetConsoleUserIdsLinkedToPuid",
      (wchar_t *)L"GetConsoleUserIdsLinkedToPuid failed for puid %s 0x%08x",
      v43,
      v41);
    if ( (unsigned int)dword_1800F11D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800F11D0, 0x400000000000LL) )
    {
      v56 = wil::ResultFromCaughtException(v44);
      if ( v42[3] > 7u )
        v42 = (_QWORD *)*v42;
      v70 = v42;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v45,
        (unsigned int)byte_1800D6BCD,
        v46,
        v47,
        (__int64)&v70,
        (__int64)&v56);
    }
    v4 = v72;
  }
  v37 = v69;
  v69 = 0;
  v38 = *((_QWORD *)&v68 + 1);
  v39 = v68;
  v68 = 0u;
  *v4 = v39;
  v4[1] = v38;
  v4[2] = v37;
  std::vector<unsigned int>::_Tidy(&v68);
  return v4;
}

```

## disassembly

```asm
0x180087268  mov     r11, rsp
0x18008726b  mov     [r11+18h], rbx
0x18008726f  mov     [r11+20h], rsi
0x180087273  push    rdi
0x180087274  push    r12
0x180087276  push    r13
0x180087278  push    r14
0x18008727a  push    r15
0x18008727c  sub     rsp, 110h
0x180087283  mov     rax, cs:__security_cookie
0x18008728a  xor     rax, rsp
0x18008728d  mov     [rsp+138h+var_38], rax
0x180087295  mov     r12, rdx
0x180087298  mov     r14, rcx
0x18008729b  mov     [rsp+138h+var_70], rcx
0x1800872a3  mov     [rsp+138h+var_88], rdx
0x1800872ab  xor     esi, esi
0x1800872ad  xorps   xmm0, xmm0
0x1800872b0  movdqu  [rsp+138h+var_A0], xmm0
0x1800872b9  mov     [r11-90h], rsi
0x1800872c0  mov     rdx, [r8]
0x1800872c3  lea     rcx, [r11-68h]
0x1800872c7  call    ??0?$ImpersonationScope@ULicenseIdentityContextTraits@@@@QEAA@PEAUILicenseIdentityContext@@@Z; ImpersonationScope<LicenseIdentityContextTraits>::ImpersonationScope<LicenseIdentityContextTraits>(ILicenseIdentityContext *)
0x1800872cc  nop
0x1800872cd  lea     rcx, [rsp+138h+pProxy]
0x1800872d5  call    ??$GetActivationFactory@UIUserStatics@System@Windows@@@@YA?AV?$ComPtr@UIUserStatics@System@Windows@@@WRL@Microsoft@@PEBG@Z; GetActivationFactory<Windows::System::IUserStatics>(ushort const *)
0x1800872da  nop
0x1800872db  lea     r15d, [rsi+40h]
0x1800872df  mov     [rsp+138h+dwCapabilities], r15d; dwCapabilities
0x1800872e4  mov     [rsp+138h+pAuthInfo], rsi; pAuthInfo
0x1800872e9  lea     ebx, [rsi+3]
0x1800872ec  mov     [rsp+138h+dwImpLevel], ebx; dwImpLevel
0x1800872f0  mov     [rsp+138h+dwAuthnLevel], esi; int
0x1800872f4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800872f8  mov     r9, rdi; pServerPrincName
0x1800872fb  or      r13d, 0FFFFFFFFh
0x1800872ff  mov     r8d, r13d; dwAuthzSvc
0x180087302  mov     edx, r13d; dwAuthnSvc
0x180087305  mov     rcx, [rsp+138h+pProxy]; pProxy
0x18008730d  call    cs:__imp_CoSetProxyBlanket
0x180087313  mov     rcx, [rsp+138h]; this
0x18008731b  test    eax, eax
0x18008731d  js      loc_1800878F4
0x180087323  mov     [rsp+138h+var_B8], rsi
0x18008732b  mov     rcx, [rsp+138h+pProxy]
0x180087333  mov     rax, [rcx]
0x180087336  lea     rdx, [rsp+138h+var_B8]
0x18008733e  mov     rax, [rax+38h]
0x180087342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087347  mov     rcx, [rsp+138h]; this
0x18008734f  test    eax, eax
0x180087351  js      loc_180087909
0x180087357  mov     [rsp+138h+dwCapabilities], r15d; dwCapabilities
0x18008735c  mov     [rsp+138h+pAuthInfo], rsi; pAuthInfo
0x180087361  mov     [rsp+138h+dwImpLevel], ebx; dwImpLevel
0x180087365  mov     [rsp+138h+dwAuthnLevel], esi; int
0x180087369  mov     r9, rdi; pServerPrincName
0x18008736c  mov     r8d, r13d; dwAuthzSvc
0x18008736f  mov     edx, r13d; dwAuthnSvc
0x180087372  mov     rcx, [rsp+138h+pProxy]; pProxy
0x18008737a  call    cs:__imp_CoSetProxyBlanket
0x180087380  mov     rcx, [rsp+138h]; this
0x180087388  test    eax, eax
0x18008738a  js      loc_18008791D
0x180087390  lea     rcx, [rsp+138h+var_B8]
0x180087398  call    ??$WaitForOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@@YAXAEBV?$ComPtr@U?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@WRL@Microsoft@@@Z; WaitForOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>(Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>> const &)
0x18008739d  mov     [rsp+138h+var_E0], rsi
0x1800873a2  mov     rcx, [rsp+138h+var_B8]
0x1800873aa  mov     rax, [rcx]
0x1800873ad  lea     rdx, [rsp+138h+var_E0]
0x1800873b2  mov     rax, [rax+40h]
0x1800873b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800873bb  mov     rcx, [rsp+138h]; this
0x1800873c3  test    eax, eax
0x1800873c5  js      loc_180087932
0x1800873cb  mov     [rsp+138h+dwCapabilities], r15d; dwCapabilities
0x1800873d0  mov     [rsp+138h+pAuthInfo], rsi; pAuthInfo
0x1800873d5  mov     [rsp+138h+dwImpLevel], ebx; dwImpLevel
0x1800873d9  mov     [rsp+138h+dwAuthnLevel], esi; int
0x1800873dd  mov     r9, rdi; pServerPrincName
0x1800873e0  mov     r8d, r13d; dwAuthzSvc
0x1800873e3  mov     edx, r13d; dwAuthnSvc
0x1800873e6  mov     rcx, [rsp+138h+var_E0]; pProxy
0x1800873eb  call    cs:__imp_CoSetProxyBlanket
0x1800873f1  mov     rcx, [rsp+138h]; this
0x1800873f9  test    eax, eax
0x1800873fb  js      loc_180087946
0x180087401  mov     [rsp+138h+var_B0], rsi
0x180087409  mov     [rsp+138h+var_40], rsi
0x180087411  mov     r9d, 23h ; '#'; unsigned int
0x180087417  lea     r8d, [r9+1]; unsigned int
0x18008741b  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x180087422  lea     rcx, [rsp+138h+hstringHeader]; hstringHeader
0x18008742a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18008742f  nop
0x180087430  lea     rdx, [rsp+138h+var_B0]
0x180087438  mov     rcx, [rsp+138h+var_40]
0x180087440  call    ??$GetActivationFactory@V?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>>)
0x180087445  mov     rcx, [rsp+138h]; this
0x18008744d  test    eax, eax
0x18008744f  js      loc_18008795B
0x180087455  mov     [rsp+138h+dwCapabilities], r15d; dwCapabilities
0x18008745a  mov     [rsp+138h+pAuthInfo], rsi; pAuthInfo
0x18008745f  mov     [rsp+138h+dwImpLevel], ebx; dwImpLevel
0x180087463  mov     [rsp+138h+dwAuthnLevel], esi; int
0x180087467  mov     r9, rdi; pServerPrincName
0x18008746a  mov     r8d, r13d; dwAuthzSvc
0x18008746d  mov     edx, r13d; dwAuthnSvc
0x180087470  mov     rcx, [rsp+138h+var_B0]; pProxy
0x180087478  call    cs:__imp_CoSetProxyBlanket
0x18008747e  mov     rcx, [rsp+138h]; this
0x180087486  test    eax, eax
0x180087488  js      loc_180087970
0x18008748e  mov     [rsp+138h+var_C0], rsi
0x180087493  mov     rbx, [rsp+138h+var_B0]
0x18008749b  mov     rax, [rbx]
0x18008749e  mov     rdi, [rax]
0x1800874a1  lea     rcx, [rsp+138h+var_C0]
0x1800874a6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800874ab  lea     r8, [rsp+138h+var_C0]
0x1800874b0  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800874b7  mov     rcx, rbx
0x1800874ba  mov     rax, rdi
0x1800874bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800874c2  nop
0x1800874c3  mov     rcx, [rsp+138h]; this
0x1800874cb  test    eax, eax
0x1800874cd  js      loc_180087985
0x1800874d3  mov     [rsp+138h+dwCapabilities], r15d; dwCapabilities
0x1800874d8  mov     [rsp+138h+pAuthInfo], rsi; pAuthInfo
0x1800874dd  mov     [rsp+138h+dwImpLevel], 3; dwImpLevel
0x1800874e5  mov     [rsp+138h+dwAuthnLevel], esi; int
0x1800874e9  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1800874ed  mov     r8d, r13d; dwAuthzSvc
0x1800874f0  mov     edx, r13d; dwAuthnSvc
0x1800874f3  mov     rcx, [rsp+138h+var_C0]; pProxy
0x1800874f8  call    cs:__imp_CoSetProxyBlanket
0x1800874fe  mov     rcx, [rsp+138h]; this
0x180087506  test    eax, eax
0x180087508  js      loc_180087999
0x18008750e  mov     [rsp+138h+var_C8], rsi
0x180087513  mov     rbx, [rsp+138h+var_C0]
0x180087518  mov     rax, [rbx]
0x18008751b  mov     rdi, [rax]
0x18008751e  lea     rcx, [rsp+138h+var_C8]
0x180087523  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180087528  lea     r8, [rsp+138h+var_C8]
0x18008752d  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x180087534  mov     rcx, rbx
0x180087537  mov     rax, rdi
0x18008753a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008753f  nop
0x180087540  mov     rcx, [rsp+138h]; this
0x180087548  test    eax, eax
0x18008754a  js      loc_1800879AE
0x180087550  mov     [rsp+138h+dwCapabilities], r15d; dwCapabilities
0x180087555  mov     [rsp+138h+pAuthInfo], rsi; pAuthInfo
0x18008755a  mov     ebx, 3
0x18008755f  mov     [rsp+138h+dwImpLevel], ebx; dwImpLevel
0x180087563  mov     [rsp+138h+dwAuthnLevel], esi; int
0x180087567  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18008756b  mov     r9, rdi; pServerPrincName
0x18008756e  mov     r8d, r13d; dwAuthzSvc
0x180087571  mov     edx, r13d; dwAuthnSvc
0x180087574  mov     rcx, [rsp+138h+var_C8]; pProxy
0x180087579  call    cs:__imp_CoSetProxyBlanket
0x18008757f  mov     rcx, [rsp+138h]; this
0x180087587  test    eax, eax
0x180087589  js      loc_1800879C2
0x18008758f  mov     [rsp+138h+ppv], rsi
0x180087594  lea     rcx, [rsp+138h+ppv]
0x180087599  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008759e  lea     rax, [rsp+138h+ppv]
0x1800875a3  mov     qword ptr [rsp+138h+dwAuthnLevel], rax; int
0x1800875a8  lea     r9, _GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5; riid
0x1800875af  xor     edx, edx; pUnkOuter
0x1800875b1  lea     r8d, [rdx+17h]; dwClsContext
0x1800875b5  lea     rcx, _GUID_0134a8b2_3407_4b45_ad25_e9f7c92a80bc; rclsid
0x1800875bc  call    cs:__imp_CoCreateInstance
0x1800875c2  mov     rcx, [rsp+138h]; this
0x1800875ca  test    eax, eax
0x1800875cc  js      loc_1800879D7
0x1800875d2  mov     [rsp+138h+dwCapabilities], r15d; dwCapabilities
0x1800875d7  mov     [rsp+138h+pAuthInfo], rsi; pAuthInfo
0x1800875dc  mov     [rsp+138h+dwImpLevel], ebx; dwImpLevel
0x1800875e0  mov     [rsp+138h+dwAuthnLevel], esi; int
0x1800875e4  mov     r9, rdi; pServerPrincName
0x1800875e7  mov     r8d, r13d; dwAuthzSvc
0x1800875ea  mov     edx, r13d; dwAuthnSvc
0x1800875ed  mov     rcx, [rsp+138h+ppv]; pProxy
0x1800875f2  call    cs:__imp_CoSetProxyBlanket
0x1800875f8  mov     rcx, [rsp+138h]; this
0x180087600  test    eax, eax
0x180087602  js      loc_1800879EB
0x180087608  mov     [rsp+138h+var_D8], esi
0x18008760c  mov     rcx, [rsp+138h+var_E0]
0x180087611  mov     rax, [rcx]
0x180087614  lea     rdx, [rsp+138h+var_D8]
0x180087619  mov     rax, [rax+38h]
0x18008761d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087622  mov     rcx, [rsp+138h]; this
0x18008762a  test    eax, eax
0x18008762c  js      loc_1800879FF
0x180087632  mov     r15d, esi
0x180087635  cmp     r15d, [rsp+138h+var_D8]
0x18008763a  jnb     loc_1800877E7
0x180087640  mov     [rsp+138h+var_E8], rsi
0x180087645  mov     rdi, [rsp+138h+var_E0]
0x18008764a  mov     rax, [rdi]
0x18008764d  mov     rbx, [rax+30h]
0x180087651  lea     rcx, [rsp+138h+var_E8]
0x180087656  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008765b  lea     r8, [rsp+138h+var_E8]
0x180087660  mov     edx, r15d
0x180087663  mov     rcx, rdi
0x180087666  mov     rax, rbx
0x180087669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008766e  mov     rcx, [rsp+138h]; this
0x180087676  test    eax, eax
0x180087678  js      loc_180087A14
0x18008767e  mov     [rsp+138h+var_80], rsi
0x180087686  mov     rcx, [rsp+138h+var_C8]
0x18008768b  mov     rax, [rcx]
0x18008768e  lea     r8, [rsp+138h+var_80]
0x180087696  mov     rdx, [rsp+138h+var_E8]
0x18008769b  mov     rax, [rax+88h]
0x1800876a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800876a7  test    eax, eax
0x1800876a9  js      loc_1800877D5
0x1800876af  mov     [rsp+138h+var_D4], esi
0x1800876b3  cmp     qword ptr [r12+18h], 7
0x1800876b9  jbe     short loc_1800876C1
0x1800876bb  mov     r8, [r12]
0x1800876bf  jmp     short loc_1800876C4
0x1800876c1  mov     r8, r12; unsigned __int16 *
0x1800876c4  lea     rax, [rsp+138h+var_D4]
0x1800876c9  mov     qword ptr [rsp+138h+dwAuthnLevel], rax; int
0x1800876ce  mov     rdx, [rsp+138h+var_80]; unsigned __int64
0x1800876d6  mov     rcx, [rsp+138h+ppv]; struct IXblAuthManager *
0x1800876db  call    ?DoesUserHaveLinkedWebAccountHelper@KeyMachine@@KAJPEAUIXblAuthManager@@_KPEBG2PEAH@Z; KeyMachine::DoesUserHaveLinkedWebAccountHelper(IXblAuthManager *,unsigned __int64,ushort const *,ushort const *,int *)
0x1800876e0  test    eax, eax
0x1800876e2  js      loc_1800877D5
0x1800876e8  cmp     [rsp+138h+var_D4], esi
0x1800876ec  jz      loc_1800877D5
0x1800876f2  mov     [rsp+138h+string], rsi
0x1800876f7  mov     rdi, [rsp+138h+var_E8]
0x1800876fc  mov     rax, [rdi]
0x1800876ff  mov     rbx, [rax+30h]
0x180087703  xor     ecx, ecx; string
0x180087705  call    cs:__imp_WindowsDeleteString
0x18008770b  mov     [rsp+138h+string], rsi
0x180087710  lea     rdx, [rsp+138h+string]
0x180087715  mov     rcx, rdi
0x180087718  mov     rax, rbx
0x18008771b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087720  mov     rcx, [rsp+138h]; this
0x180087728  test    eax, eax
0x18008772a  js      loc_180087A29
0x180087730  xor     edx, edx; length
0x180087732  mov     rcx, [rsp+138h+string]; string
0x180087737  call    cs:__imp_WindowsGetStringRawBuffer
0x18008773d  xor     edx, edx; EndPtr
0x18008773f  lea     r8d, [rdx+0Ah]; Radix
0x180087743  mov     rcx, rax; String
0x180087746  call    cs:__imp_wcstoul
0x18008774c  mov     [rsp+138h+var_F8], eax
0x180087750  cmp     eax, r13d
0x180087753  jnz     short loc_180087797
0x180087755  mov     [rsp+138h+dwImpLevel], r15d
0x18008775a  lea     rax, aInvalidUserIdI; "invalid user ID, i=%d"
0x180087761  mov     qword ptr [rsp+138h+dwAuthnLevel], rax; Format
0x180087766  lea     r9, aKeymachineGetc; "KeyMachine::GetConsoleUserIdsLinkedToPu"...
0x18008776d  mov     r8d, 5D9h; unsigned int
0x180087773  lea     rdx, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\licensem"...
0x18008777a  mov     ecx, 1; unsigned int
0x18008777f  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180087784  nop
0x180087785  mov     rcx, [rsp+138h+string]; string
0x18008778a  call    cs:__imp_WindowsDeleteString
0x180087790  mov     [rsp+138h+string], rsi
0x180087795  jmp     short loc_1800877D5
0x180087797  mov     rdx, qword ptr [rsp+138h+var_A0+8]
0x18008779f  cmp     rdx, [rsp+138h+var_90]
0x1800877a7  jz      short loc_1800877B6
0x1800877a9  mov     [rdx], eax
0x1800877ab  add     qword ptr [rsp+138h+var_A0+8], 4
0x1800877b4  jmp     short loc_1800877C9
0x1800877b6  lea     r8, [rsp+138h+var_F8]
0x1800877bb  lea     rcx, [rsp+138h+var_A0]
0x1800877c3  call    ??$_Emplace_reallocate@AEBI@?$vector@IV?$allocator@I@std@@@std@@AEAAPEAIQEAIAEBI@Z; std::vector<uint>::_Emplace_reallocate<uint const &>(uint * const,uint const &)
0x1800877c8  nop
0x1800877c9  mov     rcx, [rsp+138h+string]; string
0x1800877ce  call    cs:__imp_WindowsDeleteString
0x1800877d4  nop
0x1800877d5  lea     rcx, [rsp+138h+var_E8]
0x1800877da  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800877df  inc     r15d
0x1800877e2  jmp     loc_180087635
0x1800877e7  lea     rcx, [rsp+138h+ppv]
0x1800877ec  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
  ... truncated ...
```
